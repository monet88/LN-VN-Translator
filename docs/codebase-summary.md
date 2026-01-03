# Codebase Summary

> **Generated:** 2026-01-03 | **Source:** repomix-output.xml (1.1M tokens, 24 files)

---

## 1. Repository Overview

**Project:** LN VN-Translator
**Type:** Prompt Engineering System (XML-based)
**Platform:** Google Gemini (1M+ context window)
**Domain:** Light Novel Japanese→Vietnamese Translation

**Key Metrics:**
- Total files: 24
- Total tokens: 1,113,035
- Total size: 2.6MB
- Largest file: `Library_KANJI_KNOWLEDGE_BASE.md` (2.4MB, 88.3% of total)

---

## 2. Directory Structure

```
F:\CodeBase\LN-VN-Translator/
├── .gitignore                                      # Git exclusions
├── LICENSE                                         # GNU AGPLv3
├── README.md                                       # User guide (Vietnamese)
├── VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml   # Core logic (48KB)
│
├── docs/                                           # Documentation
│   ├── project-overview-pdr.md                     # Product requirements
│   ├── codebase-summary.md                         # This file
│   ├── code-standards.md                           # Code conventions
│   └── system-architecture.md                      # Technical design
│
├── Examples/                                       # Sample translations
│   ├── sample_chapter_JP.txt                       # Japanese source
│   └── sample_chapter_VN.txt                       # Vietnamese output
│
├── Reference/                                      # Knowledge Base (2.7MB)
│   ├── Library Modules (External RAG)
│   │   ├── Library_KANJI_KNOWLEDGE_BASE.md         # 2.4MB, 12,559 Kanji
│   │   ├── Library_COMMON_KANJI_SINO_VN.md         # 23KB, common Kanji
│   │   ├── Library_GOLDEN_SAMPLES.md               # 28KB, 19 S-Tier samples
│   │   ├── Library_LOCALIZATION_PRIMER_VN.md       # 43KB, localization guide
│   │   └── Library_REAL_WORLD_CRITIQUE_ICL.md      # 31KB, critique examples
│   │
│   └── Ref Modules (Integrated/Lookup)
│       ├── Ref_VIETNAMESE_PRONOUN_SYSTEM.md        # 34KB, pronoun system
│       ├── Ref_HYBRID_HONORIFIC_SYSTEM.md          # 9KB, honorific rules
│       ├── Ref_BOLDNESS_MODULE_v1.0.md             # 31KB, boldness techniques
│       ├── Ref_SENSORY_LEXICON.md                  # 12KB, vivid verbs
│       ├── Ref_FORMATTING_STANDARDS.md             # 4KB, output formatting
│       ├── Ref_VISUAL_PROXEMICS_QUICK_REFERENCE.md # 10KB, proxemics guide
│       ├── Ref_LONG_VOWEL_ROMANIZATION.md          # 14KB, name romanization
│       ├── Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md   # 25KB, anti-translationese
│       ├── Ref_RUBY_TEXT_PARSING_ICL.md            # 10KB, furigana handling
│       ├── Ref_SAFETY_COMPLIANCE_MATRIX.md         # 5KB, content safety
│       ├── Ref_THINKING_LOG_ICL.md                 # 10KB, thought process
│       └── Ref_VIETNAMESE_EXPRESSION_MAPPING.md    # 15KB, expression mapping
│
└── plans/                                          # Agent workflow
    └── reports/                                    # Scout reports
        └── scout-external-260103-1646-reference-directory.md
```

---

## 3. Core Components

### 3.1 VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml

**Size:** 48KB (14,225 tokens)
**Lines:** 1,075
**Purpose:** Self-contained translation logic for Gemini System Instruction

**Structure:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<VN_TRANSLATOR_LOGIC_CORE version="1.2">

  <!-- Line 5-24: Character Archetypes -->
  <LOC>
    <ARCHETYPES>
      <A id="OJOU"/> <A id="GYARU"/> <A id="DELINQ"/>
      <A id="KANSAI"/> <A id="SAMURAI"/> <A id="CHUUNI"/>
      <A id="KUUDERE"/> <A id="ONEE"/> <A id="BOKUKKO"/>
      <A id="LOLIBABA"/>
      <SUB_ARC id="TSUNDERE"/> <SUB_ARC id="YANDERE"/>
    </ARCHETYPES>
  </LOC>

  <!-- Line 26-42: RTAS Core Rules -->
  <RTAS min="1.0" max="5.0">
    <RULE>FAMILY_OVERRIDE</RULE>
    <THRESHOLD val="4.0"/>
    <PAIR_MAP><!-- 5 pronoun pairs --></PAIR_MAP>
  </RTAS>

  <!-- Line 44-136: RTAS Calculation Engine v2.0 -->
  <RTAS_CALCULATION version="2.0" baseline="3.0">
    <SCORING_TABLES>
      <PRONOUN_JP>     <!-- 俺/僕/お前/君... --></PRONOUN_JP>
      <HONORIFIC_JP>   <!-- -san/-kun/-chan... --></HONORIFIC_JP>
      <SENTENCE_ENDING><!-- よ/ね/な/です... --></SENTENCE_ENDING>
      <CONTEXT_KEYWORDS><!-- 好き/殺す/告白... --></CONTEXT_KEYWORDS>
    </SCORING_TABLES>

    <CONFLICT_RESOLUTION priority="OVERRIDE">
      <RULE name="YANDERE_PARADOX"/>
      <RULE name="TSUNDERE_FLIP"/>
      <RULE name="KEIGO_WALL"/>
      <RULE name="VISUAL_OVERRIDE"/>
    </CONFLICT_RESOLUTION>
  </RTAS_CALCULATION>

  <!-- Line 138-180: Boldness Module v1.0 -->
  <BOLDNESS_ACTIVATION threshold="4.8">
    <TECHNIQUE name="SENTENCE_SHATTERING"/>
    <TECHNIQUE name="VIVID_VERB_REPLACEMENT"/>
    <TECHNIQUE name="SLANG_INJECTION" levels="1-5"/>
  </BOLDNESS_ACTIVATION>

  <!-- Line 182-250: Ruby Text Parsing v2.0 -->
  <RUBY_TEXT_PARSING version="2.0">
    <STRATEGY name="SEMANTIC_OVERRIDE"/>
    <STRATEGY name="SOUND_CLASH_DETECTION"/>
    <STRATEGY name="CHUUNIBYOU_NAMES"/>
  </RUBY_TEXT_PARSING>

  <!-- Line 252-320: Romanization v2.0 -->
  <ROMANIZATION version="2.0">
    <LONG_VOWEL_RULES>
      <RULE pattern="おう" output="ō"/>
      <RULE pattern="えい" output="ē"/>
      <!-- Full table: 15 rules -->
    </LONG_VOWEL_RULES>
  </ROMANIZATION>

  <!-- Line 322-380: Safety Compliance -->
  <SAFETY_MATRIX>
    <LEVEL id="1" desc="General audience"/>
    <LEVEL id="3" desc="Mild suggestive"/>
    <LEVEL id="5" desc="Explicit (flag required)"/>
  </SAFETY_MATRIX>

  <!-- Line 382-450: Anti-Translationese -->
  <ANTI_TRANSLATIONESE>
    <BANNED_PATTERN>Một cách [adv]</BANNED_PATTERN>
    <BANNED_PATTERN>Có vẻ như...</BANNED_PATTERN>
    <!-- 20+ patterns -->
  </ANTI_TRANSLATIONESE>

  <!-- Line 452-520: Hybrid Honorifics -->
  <HONORIFIC_SYSTEM type="HYBRID">
    <DIALOGUE mode="KEEP_JP"/>
    <NARRATION mode="USE_VN"/>
    <FAMILY mode="ALWAYS_VN"/>
  </HONORIFIC_SYSTEM>

  <!-- Line 522-600: Output Protocol -->
  <DUAL_OUTPUT>
    <CHATBOX><!-- Metadata: RTAS, techniques --></CHATBOX>
    <CANVAS><!-- Clean translation --></CANVAS>
  </DUAL_OUTPUT>

  <!-- Line 602-1075: Extended logic & edge cases -->
  <!-- Proxemics, Visual cues, Multi-speaker dialogue... -->

</VN_TRANSLATOR_LOGIC_CORE>
```

**Key Features:**
- **10 character archetypes** (OJOU, GYARU, DELINQ...)
- **RTAS 2.0:** 4 scoring tables + 4 conflict resolution rules
- **Boldness Module:** 3 techniques with 5 intensity levels
- **Ruby Parsing:** 3 strategies for furigana handling
- **Romanization:** 15 long vowel rules
- **Safety Matrix:** 5-level content rating
- **20+ anti-translationese patterns**

---

## 4. Module Organization

### 4.1 Library Modules (External RAG)

**Chức năng:** Heavy data files, accessed via RAG (Retrieval-Augmented Generation)

| File | Size | Tokens | Purpose |
|------|------|--------|---------|
| `Library_KANJI_KNOWLEDGE_BASE.md` | 2.4MB | 983,174 | 12,559 Kanji + Hán-Việt mapping |
| `Library_GOLDEN_SAMPLES.md` | 28KB | ~7,000 | 19 S-Tier translation examples |
| `Library_LOCALIZATION_PRIMER_VN.md` | 43KB | 13,871 | Localization theory & best practices |
| `Library_REAL_WORLD_CRITIQUE_ICL.md` | 31KB | ~8,000 | Real-world critique examples (In-Context Learning) |
| `Library_COMMON_KANJI_SINO_VN.md` | 23KB | ~6,000 | 200 common Kanji with Sino-Vietnamese readings |

**Usage Pattern:**
```
User input: "魔法少女"
→ Gemini RAG search: Library_KANJI_KNOWLEDGE_BASE.md
→ Find: 魔 (ma), 法 (pháp), 少 (thiếu), 女 (nữ)
→ Output: "Cô gái phép thuật" (not "Ma pháp thiếu nữ")
```

---

### 4.2 Ref Modules (Integrated/Lookup)

**Chức năng:** Lightweight references, logic already in XML

| File | Size | Integration Status | Purpose |
|------|------|-------------------|---------|
| `Ref_VIETNAMESE_PRONOUN_SYSTEM.md` | 34KB | 80% integrated | Full pronoun table (100+ pairs) |
| `Ref_BOLDNESS_MODULE_v1.0.md` | 31KB | 100% integrated | Boldness technique details |
| `Ref_SENSORY_LEXICON.md` | 12KB | 90% integrated | 200+ vivid verb alternatives |
| `Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md` | 25KB | 100% integrated | Anti-translationese patterns |
| `Ref_HYBRID_HONORIFIC_SYSTEM.md` | 9KB | 100% integrated | Honorific handling rules |
| `Ref_RUBY_TEXT_PARSING_ICL.md` | 10KB | 100% integrated | Furigana parsing examples |
| `Ref_LONG_VOWEL_ROMANIZATION.md` | 14KB | 100% integrated | Romanization rules |
| `Ref_VISUAL_PROXEMICS_QUICK_REFERENCE.md` | 10KB | 80% integrated | Proxemics (distance/touch) |
| `Ref_SAFETY_COMPLIANCE_MATRIX.md` | 5KB | 100% integrated | Content safety levels |
| `Ref_FORMATTING_STANDARDS.md` | 4KB | 100% integrated | Output formatting |
| `Ref_VIETNAMESE_EXPRESSION_MAPPING.md` | 15KB | 70% integrated | JP→VN expression mapping |
| `Ref_THINKING_LOG_ICL.md` | 10KB | Optional | Thought process examples |

**Integration Legend:**
- **100%:** Full logic in XML, file là reference only
- **80-90%:** Core logic in XML, file có edge cases
- **70%:** Partial integration, cần expand
- **Optional:** Không bắt buộc cho core workflow

---

## 5. Data Flow & Processing Pipeline

### 5.1 Translation Pipeline

```
┌─────────────────────────────────────────────────────────────┐
│ USER INPUT (Japanese Text)                                  │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 1: Character Archetype Detection                       │
│ - Scan for archetype markers (boku, ore, keigo...)          │
│ - Assign personality profile (OJOU, GYARU, DELINQ...)       │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 2: RTAS Calculation v2.0                               │
│ - Baseline: 3.0                                             │
│ - Add: Pronoun (+0.3~+0.7), Honorific (-0.8~+0.5)          │
│ - Add: Sentence Ending (+0.2~+0.4)                          │
│ - Add: Context Keywords (-2.0~+1.5)                         │
│ - Add: Proxemics (-0.5~+1.2)                                │
│ - Apply: Conflict Resolution (Yandere Paradox, etc.)        │
│ → Output: RTAS Score (1.0-5.0)                              │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 3: Pronoun Pair Selection                              │
│ - RTAS 2.0-3.5 → Tớ-Cậu                                     │
│ - RTAS 3.5-4.2 → Tớ-Anh                                     │
│ - RTAS 4.2-5.0 → Em-Anh                                     │
│ - Family context → Override to Anh/Chị/Em/Ba/Mẹ             │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 4: Boldness Module Activation                          │
│ - IF RTAS ≥ 4.8 OR RTAS ≤ 1.2:                              │
│   - Sentence Shattering (break long sentences)              │
│   - Vivid Verb Replacement (RAG: Sensory Lexicon)           │
│   - Slang Injection (Level 1-5)                             │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 5: Ruby Text Parsing                                   │
│ - Detect furigana: 魔法<マホウ> or 魔法<まほう>             │
│ - Strategy 1: Semantic Override (use Kanji meaning)         │
│ - Strategy 2: Sound Clash Detection (choose appropriate)    │
│ - Strategy 3: Chuunibyou Names (聖剣<エクスカリバー>)       │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 6: Romanization (for names)                            │
│ - Apply Long Vowel Rules (おう→ō, えい→ē)                  │
│ - Preserve phonetic accuracy                                │
│ → 「紅葉」→ "Kōyō" (not "Kouyou")                           │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 7: Anti-Translationese Filtering                       │
│ - Scan for 20+ banned patterns                              │
│ - Replace: "Một cách nhanh chóng" → "Vội vã"                │
│ - Replace: "Có vẻ như anh buồn" → "Anh buồn"                │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 8: Safety Compliance Check                             │
│ - Rate content: Level 1-5                                   │
│ - IF Level ≥ 4: Add warning flag                            │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ STEP 9: Dual-Output Generation                              │
│ - Chatbox: [RTAS: X.Y | Cặp: A-B | Kỹ thuật: ...]          │
│ - Canvas: Clean Vietnamese translation                      │
└────────────────┬────────────────────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────────────────────┐
│ FINAL OUTPUT (Vietnamese Translation)                       │
└─────────────────────────────────────────────────────────────┘
```

### 5.2 RAG Integration Points

**Knowledge Base files được tra cứu tại các bước:**

1. **STEP 1 (Archetype Detection):**
   - `Ref_VIETNAMESE_PRONOUN_SYSTEM.md` → Pronoun archetypes

2. **STEP 2 (RTAS Calculation):**
   - `Ref_HYBRID_HONORIFIC_SYSTEM.md` → Honorific modifiers
   - `Ref_VISUAL_PROXEMICS_QUICK_REFERENCE.md` → Proxemics scores

3. **STEP 4 (Boldness Module):**
   - `Ref_SENSORY_LEXICON.md` → Vivid verb alternatives
   - `Ref_BOLDNESS_MODULE_v1.0.md` → Slang lists

4. **STEP 5 (Ruby Parsing):**
   - `Library_KANJI_KNOWLEDGE_BASE.md` → Kanji semantic meaning
   - `Ref_RUBY_TEXT_PARSING_ICL.md` → Edge case examples

5. **STEP 6 (Romanization):**
   - `Ref_LONG_VOWEL_ROMANIZATION.md` → Romanization rules

6. **STEP 7 (Anti-Translationese):**
   - `Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md` → Banned patterns

7. **Throughout (Quality Check):**
   - `Library_GOLDEN_SAMPLES.md` → Reference examples

---

## 6. File Purpose & Responsibility

### 6.1 Core Files

| File | Responsibility | Modify Frequency |
|------|---------------|-----------------|
| `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml` | Translation logic engine | High (per feature) |
| `README.md` | User documentation | Medium (per release) |
| `LICENSE` | Legal compliance (AGPLv3) | Never |
| `.gitignore` | Git exclusions | Low |

### 6.2 Documentation Files

| File | Responsibility | Target Audience |
|------|---------------|----------------|
| `docs/project-overview-pdr.md` | Product requirements | PM, Contributors |
| `docs/codebase-summary.md` | Architecture overview | Developers, AI agents |
| `docs/code-standards.md` | Coding conventions | Contributors |
| `docs/system-architecture.md` | Technical design | Architects, Advanced users |

### 6.3 Reference Files (Priority Order)

**Essential (MUST load to Knowledge Base):**
1. `Library_KANJI_KNOWLEDGE_BASE.md` — Core Kanji database
2. `Library_GOLDEN_SAMPLES.md` — Quality reference
3. `Ref_SENSORY_LEXICON.md` — Vivid verb pool

**Recommended:**
4. `Ref_VIETNAMESE_PRONOUN_SYSTEM.md` — Pronoun edge cases
5. `Ref_BOLDNESS_MODULE_v1.0.md` — Boldness details
6. `Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md` — Anti-translationese full list

**Optional:**
7. `Library_LOCALIZATION_PRIMER_VN.md` — Theoretical background
8. `Library_REAL_WORLD_CRITIQUE_ICL.md` — Critique examples
9. `Ref_THINKING_LOG_ICL.md` — Thought process guide

---

## 7. Token Budget Analysis

### 7.1 Current Usage

| Component | Tokens | % of Total | Status |
|-----------|--------|-----------|--------|
| XML Core | 14,225 | 1.3% | ✅ Optimized |
| Kanji DB | 983,174 | 88.3% | ⚠️ Large but essential |
| Golden Samples | ~7,000 | 0.6% | ✅ Good |
| Sensory Lexicon | ~3,000 | 0.3% | ✅ Good |
| Other Ref files | ~105,636 | 9.5% | ⚠️ Review for minification |
| **TOTAL** | **1,113,035** | **100%** | ⚠️ Near 1M limit |

### 7.2 Optimization Targets

**Goal:** Keep total ≤ 1.5M tokens for comfortable 1M context window usage.

**Actions:**
1. ✅ XML Core: Already minified (14K tokens)
2. ⚠️ Kanji DB: Cannot reduce (essential data)
3. 🔄 Ref files: Identify redundant content
   - Remove verbose examples (keep in docs/ instead)
   - Merge overlapping files
   - Abbreviate attribute names

**Potential savings:**
- Ref files minification: 105,636 → ~70,000 tokens (33% reduction)
- **New total:** ~978,000 tokens (35% buffer remaining)

---

## 8. Integration Points

### 8.1 Gemini Platform

**Setup Method 1: Gemini Gems (Recommended)**
```
1. Create Gem in AI Studio
2. Paste VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml into "Instructions"
3. Upload Reference/ files to "Knowledge"
4. Enable Canvas mode in "Default Tools"
```

**Setup Method 2: API Integration**
```javascript
import { GoogleGenerativeAI } from "@google/generative-ai";

const genAI = new GoogleGenerativeAI(API_KEY);
const model = genAI.getGenerativeModel({
  model: "gemini-1.5-pro",
  systemInstruction: fs.readFileSync("VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml"),
  // Upload Reference/ files to Files API
});
```

### 8.2 External Dependencies

**NONE** — Fully self-contained prompt system.

**Optional enhancements:**
- MeCab/Sudachi (JP tokenizer) for advanced RTAS scoring
- Gemini Vision (future) for manga translation with visual context

---

## 9. Version History

### v1.2 (Current - 2026-01-03)
- ✅ Modularized Reference/ into Library_ and Ref_ prefixes
- ✅ Integrated full Ruby Text Parsing v2.0
- ✅ Integrated full Romanization v2.0
- ✅ Updated `REF_PROTOCOL` documentation

### v1.0 (2024-12-31)
- ✅ Initial release as LN VN-Translator
- ✅ AGPLv3 license
- ✅ RTAS v2.0, Boldness Module v1.0
- ✅ 12,559 Kanji database
- ✅ Dual-Output Protocol

---

## 10. Maintenance Notes

### 10.1 File Dependencies

**If modifying XML:**
- Update version number in `<VN_TRANSLATOR_LOGIC_CORE version="X.Y">`
- Run all 19 Golden Samples for regression testing
- Update relevant Ref_ files if behavior changes

**If modifying Library_KANJI_KNOWLEDGE_BASE.md:**
- Maintain format: `Kanji: [X] | Hán-Việt: [Y] | Meaning: [Z]`
- Preserve alphabetical sorting (by Kanji unicode)
- Update `README.md` with new entry count

**If adding new Ref_ module:**
- Follow naming: `Ref_[NAME].md` or `Library_[NAME].md`
- Add to integration table in this document
- Update `README.md` setup instructions

### 10.2 Common Modification Scenarios

**Scenario 1: Add new character archetype (e.g., KNIGHT)**
1. Add to XML: `<A id="KNIGHT" voice="..." pair="..." .../>`
2. Update `Ref_VIETNAMESE_PRONOUN_SYSTEM.md` with pronoun pair
3. Add Golden Sample showcasing archetype
4. Test with 5+ dialogue examples

**Scenario 2: Expand RTAS scoring table**
1. Add to XML: `<ITEM val="..." mod="..." note="..."/>`
2. Update `docs/system-architecture.md` with new rule
3. Run regression tests (all Golden Samples)
4. Document in changelog

**Scenario 3: Improve anti-translationese rules**
1. Add pattern to XML: `<BANNED_PATTERN>...</BANNED_PATTERN>`
2. Update `Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md` with examples
3. Test with existing translations (should improve, not break)

---

**Document Version:** 1.0
**Last Updated:** 2026-01-03
**Token Count:** ~4,500 tokens
**Maintainer:** Thang (thangdam7790@gmail.com)
