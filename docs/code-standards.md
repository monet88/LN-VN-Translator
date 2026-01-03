# Code Standards & Structure

## 1. Tổng quan Kiến trúc

### 1.1 Hybrid Brain-Book Model

**Nguyên tắc thiết kế:** Tách biệt Logic (Brain) và Data (Book) để tối ưu token usage và maintainability.

**Brain (RAM) - Core Logic:**
- File: `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml` (48KB, 1,075 lines)
- Chứa: RTAS engine, Boldness Module, Conflict Resolution, Ruby Parsing
- Load vào System Instruction của Gemini
- **Mục tiêu:** ≤ 50KB (buffer 4%)

**Book (HDD) - Reference Data:**
- Thư mục: `Reference/` (2.7MB, 17 modules)
- Chứa: Kanji database, Golden Samples, Sensory Lexicon
- Tra cứu on-demand qua Knowledge Base
- **Mục tiêu:** ≤ 50MB (buffer 94%)

---

## 2. Module Naming Conventions

### 2.1 Library Modules (External RAG)

**Pattern:** `Library_[NAME].md`

**Đặc điểm:**
- **Heavy data:** File size lớn (>100KB)
- **Low frequency access:** Tra cứu khi cần, không load full vào context
- **Examples:**
  - `Library_KANJI_KNOWLEDGE_BASE.md` (2.4MB) — 12,559 Kanji entries
  - `Library_GOLDEN_SAMPLES.md` (28KB) — 19 mẫu dịch S-Tier
  - `Library_LOCALIZATION_PRIMER_VN.md` (43KB) — Hướng dẫn bản địa hóa

**Use case:** Gemini sẽ RAG search khi gặp Kanji không rõ hoặc cần reference samples.

---

### 2.2 Ref Modules (Integrated/Lookup)

**Pattern:** `Ref_[NAME].md`

**Đặc điểm:**
- **Lightweight:** File size nhỏ (<50KB)
- **High frequency:** Logic đã integrate vào XML, file .md dùng làm lookup bổ sung
- **Examples:**
  - `Ref_VIETNAMESE_PRONOUN_SYSTEM.md` (34KB) — Hệ thống đại từ đầy đủ
  - `Ref_BOLDNESS_MODULE_v1.0.md` (31KB) — Chi tiết Boldness techniques
  - `Ref_SENSORY_LEXICON.md` (12KB) — Từ điển cảm giác

**Use case:** XML đã có core logic, file .md dùng khi cần expand hoặc troubleshoot.

---

### 2.3 Decision Tree: Library vs Ref

```
┌─ File size > 100KB? ──► YES ──► Library_
│
├─ Logic đã tích hợp vào XML? ──► YES ──► Ref_
│
├─ Cần tra cứu thường xuyên? ──► NO ──► Library_
│
└─ Default ──────────────────────────► Ref_
```

---

## 3. XML Structure Standards

### 3.1 Top-Level Organization

```xml
<?xml version="1.0" encoding="UTF-8"?>
<VN_TRANSLATOR_LOGIC_CORE version="1.2">

  <!-- SECTION 1: Character Archetypes -->
  <LOC>
    <ARCHETYPES>...</ARCHETYPES>
  </LOC>

  <!-- SECTION 2: RTAS Engine -->
  <RTAS min="1.0" max="5.0">
    <RULE>...</RULE>
    <THRESHOLD>...</THRESHOLD>
    <PAIR_MAP>...</PAIR_MAP>
  </RTAS>

  <!-- SECTION 3: Calculation Tables -->
  <RTAS_CALCULATION version="2.0" baseline="3.0">
    <SCORING_TABLES>...</SCORING_TABLES>
    <CONFLICT_RESOLUTION>...</CONFLICT_RESOLUTION>
  </RTAS_CALCULATION>

  <!-- SECTION 4: Boldness Module -->
  <BOLDNESS_ACTIVATION>...</BOLDNESS_ACTIVATION>

  <!-- SECTION 5: Ruby Text Parsing -->
  <RUBY_TEXT_PARSING version="2.0">...</RUBY_TEXT_PARSING>

  <!-- SECTION 6: Romanization -->
  <ROMANIZATION version="2.0">...</ROMANIZATION>

  <!-- SECTION 7: Safety & Compliance -->
  <SAFETY_MATRIX>...</SAFETY_MATRIX>

</VN_TRANSLATOR_LOGIC_CORE>
```

### 3.2 Naming Conventions

**Tags:**
- UPPERCASE cho top-level sections: `<RTAS>`, `<BOLDNESS>`
- PascalCase cho nested elements: `<PairMap>`, `<ConflictResolution>`

**Attributes:**
- lowercase với underscore: `version="1.2"`, `rtas="4.0-5.0"`
- Boolean: `true/false` (không dùng 1/0)

**Comments:**
```xml
<!-- SECTION: High-level description -->
<!-- RULE: Specific constraint -->
<!-- EXAMPLE: Inline example -->
```

### 3.3 Versioning

**Format:** `version="[MAJOR].[MINOR]"`
- **MAJOR:** Breaking changes (RTAS 1.0 → 2.0)
- **MINOR:** Backward-compatible additions (Boldness 1.0 → 1.1)

**Example:**
```xml
<RTAS_CALCULATION version="2.0" baseline="3.0">
  <!-- v2.0: Added Conflict Resolution layer -->
  <!-- v1.0: Basic scoring table -->
</RTAS_CALCULATION>
```

---

## 4. Code Quality Standards

### 4.1 XML Minification

**Goal:** Giảm token usage mà không mất readability.

**Rules:**
- ✅ Giữ indentation cho structure (2 spaces)
- ✅ Giữ comments cho critical logic
- ❌ Remove empty lines (chỉ giữ 1 dòng giữa sections)
- ❌ Remove verbose examples (move to Ref_ files)

**Example:**
```xml
<!-- BEFORE (Verbose) -->
<ITEM val="好き" mod="+1.0" note="Love/Affection keyword">
  <!-- This adds 1.0 to RTAS when detected -->
  <!-- Example: 好きだ → RTAS +1.0 -->
</ITEM>

<!-- AFTER (Minified) -->
<ITEM val="好き" mod="+1.0" note="Love/Affection"/>
```

### 4.2 Logic Clarity

**Principle:** Self-documenting code > External docs

**Rules:**
1. **Inline notes:** Mỗi scoring rule phải có `note` attribute
2. **Examples:** Complex logic cần ≥1 example trong comment
3. **Override flags:** Gắn `priority="CRITICAL"` cho override rules

**Example:**
```xml
<RULE name="YANDERE_PARADOX" priority="CRITICAL">
  <!-- OVERRIDE: 殺す + 好き → RTAS = 5.0 (Twisted Love) -->
  <TRIGGER>
    <KEYWORDS negative="true">殺す,死ね</KEYWORDS>
    <KEYWORDS affection="true">好き,愛してる</KEYWORDS>
  </TRIGGER>
  <ACTION>
    SET RTAS = 5.0
    SET tone = "Possessive/Unstable"
  </ACTION>
</RULE>
```

### 4.3 Data Validation

**XML Schema (Informal):**
- `RTAS`: `min="1.0" max="5.0"` (enforce bounds)
- `PAIR`: `rtas="[float]-[float]"` (range format)
- `ITEM`: `mod="[+/-][float]"` (signed float)

**Validation checklist:**
- [ ] All RTAS ranges non-overlapping
- [ ] All mod values sum to reasonable range (-3.0 to +3.0)
- [ ] All references to external files exist

---

## 5. Markdown Standards (Reference Modules)

### 5.1 File Structure

```markdown
# [Module Name] v[Version]

## 1. Overview
Brief description (2-3 sentences)

## 2. Core Concepts
Key terminology and definitions

## 3. Usage Examples
Practical examples with input/output

## 4. Edge Cases
Known limitations and workarounds

## 5. Integration Notes
How this module interacts with XML core

---

**Version:** [X.Y]
**Last Updated:** [YYYY-MM-DD]
**Integration Status:** [Integrated/Standalone/Deprecated]
```

### 5.2 Code Blocks

**Format:**
```markdown
**Input (Nhật):**
\```
「好きだ。ずっと前から、お前のことが好きだった」
\```

**Output (Việt):**
\```
Tớ thích cậu.
Từ lâu rồi... tớ đã thích cậu.
\```

**Metadata:**
- RTAS: 4.9
- Cặp đại từ: Tớ-Cậu
- Kỹ thuật: Sentence Shattering
```

### 5.3 Versioning

**Filename:** `Ref_[NAME]_v[X.Y].md` (khi có breaking changes)
**Header:** `# [Module Name] v[X.Y]`

**Example:**
- `Ref_BOLDNESS_MODULE_v1.0.md` (current)
- `Ref_BOLDNESS_MODULE_v2.0.md` (nếu refactor logic)

---

## 6. Git Commit Standards

### 6.1 Conventional Commits

**Format:** `<type>(<scope>): <subject>`

**Types:**
- `feat`: New feature (RTAS v2.0, Boldness Module)
- `fix`: Bug fix (RTAS calculation error)
- `docs`: Documentation only (README update)
- `refactor`: Code restructure (XML minification)
- `test`: Add tests (Golden Samples)
- `chore`: Maintenance (update dependencies)

**Examples:**
```bash
feat(rtas): Add Yandere Paradox conflict resolution
fix(ruby): Correct semantic override for 魔法
docs(readme): Add installation guide for Gemini Gems
refactor(xml): Minify Boldness Module to reduce tokens
```

### 6.2 Breaking Changes

**Format:** `feat!(<scope>): <subject>` (dấu `!` indicates breaking)

**Example:**
```bash
feat!(rtas): Refactor scoring table to v2.0

BREAKING CHANGE: RTAS baseline changed from 2.5 to 3.0.
Update all custom prompts to recalibrate thresholds.
```

---

## 7. Testing Standards

### 7.1 Golden Samples

**Location:** `Library_GOLDEN_SAMPLES.md`

**Format:**
```markdown
### Sample #[ID]: [Scene Type] (RTAS: [X.Y])

**Source (Nhật):**
\```
[Original Japanese text]
\```

**Expected Output (Việt):**
\```
[Expected translation]
\```

**Metadata:**
- RTAS: [X.Y]
- Archetype: [GYARU/OJOU/etc.]
- Techniques: [Sentence Shattering, Vivid Verb, etc.]
- Notes: [Special considerations]
```

### 7.2 Regression Testing

**Process:**
1. Run all 19 Golden Samples through current XML
2. Compare output với expected output
3. Flag deviations > 20% edit distance
4. Document breaking changes in changelog

**Acceptance:**
- ≥ 17/19 samples pass (89% pass rate)
- 0 critical failures (RTAS miscalculation)

---

## 8. Performance Optimization

### 8.1 Token Budget

**Current Usage:**
- XML Core: 14,225 tokens (48KB)
- Knowledge Base: 983,174 tokens (2.4MB Kanji DB)
- Total: ~1M tokens

**Targets:**
- XML Core: ≤ 15,000 tokens (50KB budget)
- Knowledge Base: ≤ 1.5M tokens (RAG efficiency)

### 8.2 Minification Techniques

1. **Remove redundant examples:** Move to Ref_ files
2. **Abbreviate attribute names:** `modification` → `mod`
3. **Inline short comments:** Multi-line → single line
4. **Remove whitespace:** Keep only structural indentation

**Before/After:**
```xml
<!-- BEFORE: 180 tokens -->
<ITEM val="好き" modification="+1.0" description="Love/Affection keyword">
  <!-- This modifier adds 1.0 to the RTAS score -->
  <!-- Example usage: 好きだ → +1.0 -->
  <!-- See Ref_CONTEXT_KEYWORDS.md for full list -->
</ITEM>

<!-- AFTER: 45 tokens -->
<ITEM val="好き" mod="+1.0" note="Love/Affection"/>
```

**Reduction:** 75% token savings

---

## 9. Documentation Standards

### 9.1 Inline XML Documentation

**Requirement:** Every section phải có 1 comment mô tả purpose.

**Template:**
```xml
<!-- SECTION: [Name]
     PURPOSE: [What it does]
     USAGE: [When to use]
     DEPENDENCIES: [What it requires]
-->
```

**Example:**
```xml
<!-- SECTION: RTAS Calculation v2.0
     PURPOSE: Calculate Relationship Tension & Affection Score (1.0-5.0)
     USAGE: Every dialogue line with pronouns/honorifics
     DEPENDENCIES: SCORING_TABLES, CONFLICT_RESOLUTION
-->
<RTAS_CALCULATION version="2.0" baseline="3.0">
  ...
</RTAS_CALCULATION>
```

### 9.2 External Documentation

**Required files:**
- `README.md`: User guide (Vietnamese)
- `docs/project-overview-pdr.md`: Product requirements
- `docs/codebase-summary.md`: Architecture overview
- `docs/code-standards.md`: This document
- `docs/system-architecture.md`: Technical design

**Optional files:**
- `CHANGELOG.md`: Version history
- `CONTRIBUTING.md`: Contribution guidelines
- `TROUBLESHOOTING.md`: Common issues

---

## 10. Code Review Checklist

### 10.1 XML Changes

- [ ] Version number updated if breaking change
- [ ] All tags properly closed
- [ ] Attributes use correct format (`key="value"`)
- [ ] Comments explain "why" not "what"
- [ ] No hardcoded Vietnamese text (use dynamic generation)
- [ ] Token count ≤ budget (50KB)

### 10.2 Reference Module Changes

- [ ] Filename follows `Library_` or `Ref_` convention
- [ ] Version header matches filename
- [ ] Examples include input/output/metadata
- [ ] Integration notes updated if XML changes
- [ ] File size ≤ 100KB for Ref_ modules

### 10.3 Golden Samples

- [ ] Each sample has unique ID
- [ ] RTAS score explicitly stated
- [ ] Expected output matches current XML behavior
- [ ] Edge cases documented in notes
- [ ] No PII (Personally Identifiable Information)

---

## 11. Maintenance Guidelines

### 11.1 Adding New Features

**Process:**
1. **Design:** Document in `docs/` first (PDR format)
2. **Prototype:** Test in separate XML file
3. **Integrate:** Merge into main XML with versioning
4. **Test:** Run all Golden Samples
5. **Document:** Update README + relevant Ref_ files

**Example:** Adding new archetype (KNIGHT)
1. Create `docs/feature-knight-archetype.md`
2. Test in `test-knight.xml`
3. Add to `<ARCHETYPES>` with `version="1.3"`
4. Run 19 Golden Samples (ensure no regression)
5. Update `Ref_CHARACTER_ARCHETYPES.md`

### 11.2 Deprecation Policy

**When to deprecate:**
- Feature unused for 6+ months
- Replaced by better alternative
- Causes maintenance burden

**Process:**
1. Mark as `deprecated="true"` in XML
2. Add deprecation notice in comments
3. Remove after 2 minor versions

**Example:**
```xml
<OLD_RTAS_ENGINE deprecated="true">
  <!-- DEPRECATED since v10.0, use RTAS_CALCULATION v2.0 instead -->
  <!-- Will be removed in v12.0 -->
</OLD_RTAS_ENGINE>
```

### 11.3 Hotfix Protocol

**Critical bugs (production impact):**
1. Create hotfix branch: `hotfix/[issue-id]-[short-desc]`
2. Fix in XML + add regression test
3. Bump patch version: `1.2.3` → `1.2.4`
4. Merge to main immediately
5. Backport to stable if needed

---

## 12. Anti-Patterns (DON'T DO THIS)

### 12.1 XML Anti-Patterns

❌ **Hardcoded Vietnamese text:**
```xml
<OUTPUT>Tớ thích cậu</OUTPUT> <!-- BAD: Static text -->
```

✅ **Dynamic generation:**
```xml
<RULE>Generate pronoun pair based on RTAS</RULE>
```

❌ **Nested comments:**
```xml
<!-- Outer comment
     <!-- Inner comment --> BAD
-->
```

✅ **Flat comments:**
```xml
<!-- Outer comment -->
<!-- Inner comment (separate) -->
```

### 12.2 Naming Anti-Patterns

❌ `module_final_v2_REAL.md`
✅ `Ref_BOLDNESS_MODULE_v2.0.md`

❌ `temp_test_kanji.md`
✅ `Library_KANJI_KNOWLEDGE_BASE.md`

### 12.3 Performance Anti-Patterns

❌ **Loading entire Library_ files into XML:**
```xml
<!-- DON'T INCLUDE 2.4MB Kanji DB in XML -->
```

✅ **Reference external file:**
```xml
<!-- Kanji DB available in Knowledge Base: Library_KANJI_KNOWLEDGE_BASE.md -->
```

---

**Document Version:** 1.0
**Last Updated:** 2026-01-03
**Maintainer:** Thang (thangdam7790@gmail.com)
