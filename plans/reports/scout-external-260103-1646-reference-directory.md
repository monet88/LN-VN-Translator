# Reference Directory Scout Report

**Agent:** scout-external | **ID:** a8543ce  
**Date:** 2026-01-03 16:46  
**Scope:** F:/CodeBase/LN-VN-Translator/Reference/

---

## Executive Summary

Reference/ contains **17 markdown files** organized into 2 categories:
- **Library Modules (5 files):** External RAG resources, large datasets
- **Reference Modules (12 files):** Integrated logic, lookup tables, quick references

Total size: ~2.4MB (dominated by Kanji database)

---

## File Inventory

### Category 1: Library Modules (External RAG)

**Purpose:** Heavy reference data loaded on-demand via Knowledge Base

| File | Size | Purpose |
|------|------|---------|
| `Library_KANJI_KNOWLEDGE_BASE.md` | ~2.4MB | 12,559 Kanji entries: Onyomi, Kunyomi, English, Hán-Việt, JLPT, frequency |
| `Library_COMMON_KANJI_SINO_VN.md` | Medium | Common Kanji → Thuần Việt/Hán-Việt natural mapping (high priority) |
| `Library_GOLDEN_SAMPLES.md` | Large | 19 S-Tier translation examples (JP→EN→VN) with reasoning traces |
| `Library_REAL_WORLD_CRITIQUE_ICL.md` | Medium | Real critique extracts (80+ reviews), error patterns, score 73→84 improvements |
| `Library_LOCALIZATION_PRIMER_VN.md` | Large | Unified handbook: Archetype profiles, formality, slang, flow types |

**Key Insight:** Library files = training data for MSL (Multi-Shot Learning), heavy datasets not embedded in core logic.

---

### Category 2: Reference Modules (Integrated/Lookup)

**Purpose:** Logic rules, quick references, validation tables

| File | Function | Integration Status |
|------|----------|-------------------|
| `Ref_VIETNAMESE_PRONOUN_SYSTEM.md` | Pronoun selection system (tôi/mình/em/anh), RTAS-driven | ✅ Active |
| `Ref_HYBRID_HONORIFIC_SYSTEM.md` | Dialogue (keep JP honorifics) vs Narration (VN pronouns) | ✅ Active |
| `Ref_BOLDNESS_MODULE_v1.0.md` | Emotional peak logic (RTAS ≥4.8 or ≤1.2): sentence shattering, vivid verbs | ✅ Integrated to Master Prompt |
| `Ref_SENSORY_LEXICON.md` | Weak→Strong verb replacement, onomatopoeia, Gen Z slang injection | ✅ Active & Authorized |
| `Ref_FORMATTING_STANDARDS.md` | Punctuation conversion (「」→""), bouten, ruby text handling | ✅ Critical (Apply to all output) |
| `Ref_VISUAL_PROXEMICS_QUICK_REFERENCE.md` | Text-based distance estimation (0-45cm/45-120cm/120+cm) for RTAS calibration | ✅ Active |
| `Ref_LONG_VOWEL_ROMANIZATION.md` | Romaji rules for Japanese long vowels (おう→ou/ō, えい→ei) | ✅ Active & Authorized |
| `Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md` | Contrastive ICL: Bad AI output vs Good human output patterns | ✅ Critical |
| `Ref_RUBY_TEXT_PARSING_ICL.md` | Furigana parsing logic, avoid kanji mismatching | ✅ High Priority |
| `Ref_SAFETY_COMPLIANCE_MATRIX.md` | Content reframing for CSAM/self-harm/violence triggers | ⚠️ Optional (load for sensitive content) |
| `Ref_THINKING_LOG_ICL.md` | Good vs Bad reasoning examples, first-person narrative style | ✅ Active |
| `Ref_VIETNAMESE_EXPRESSION_MAPPING.md` | Interjection variety (Ơ?/Ủa?/Vãi!), anti-repetition, rotation rules | ✅ High Priority (lookup on dialogue) |

---

## Organizational Principles

### 1. Naming Convention
- **Library_** prefix: Heavy external data (RAG/KB)
- **Ref_** prefix: Quick lookup, integrated logic

### 2. Integration Strategy
Per README.md analysis:
- **Brain (RAM):** Logic compressed in `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml` (17KB)
- **Book (HDD):** Reference/*.md files, on-demand RAG lookup

### 3. Priority Tiers
**Must-Have (Core):**
- Library_KANJI_KNOWLEDGE_BASE.md (12,559 Kanji)
- Ref_SENSORY_LEXICON.md (vivid verbs)
- Library_GOLDEN_SAMPLES.md (19 S-Tier examples)

**Recommended (Extended):**
- Ref_BOLDNESS_MODULE_v1.0.md (detailed techniques)
- Ref_VISUAL_PROXEMICS_QUICK_REFERENCE.md (RTAS calibration)
- Ref_VIETNAMESE_PRONOUN_SYSTEM.md (full pronoun system)
- Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (quality guardrails)

---

## Content Highlights

### Library_KANJI_KNOWLEDGE_BASE.md
- 12,559 entries, structured format:
  ```
  ### 日
  - Readings: On: ニチ, ジツ | Kun: ひ, -び, -か
  - Hán-Việt: nhật
  - Meaning: day, sun, Japan
  - Meta: Freq: 1 | JLPT: N4
  ```

### Ref_BOLDNESS_MODULE_v1.0.md
- Activation: RTAS ≥ 4.8 (emotional peak) or ≤ 1.2 (extreme negative)
- Techniques: Sentence shattering, vivid verb replacement, Gen Z slang
- Coordinates with: RTAS, Proxemics, Sensory Lexicon
- **Does NOT override:** Pronoun PAIR_ID (locked)

### Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md
- Contrastive ICL: Side-by-side bad/good examples
- Mental checklist before translation:
  1. Sounds like native speaker or machine?
  2. Natural in conversation?
  3. Using dictionary words or living language?

### Library_GOLDEN_SAMPLES.md
- Format: SOURCE (JP) → ENG → VIỆT + REASONING
- Teaches: Style consistency, cultural adaptation, reasoning patterns
- 19 curated S-Tier examples

### Ref_VIETNAMESE_EXPRESSION_MAPPING.md
- Rotation tables for interjections (avoid repetition)
- Surprise levels: Ơ?/Ủa? (light) → Vãi!/Điêu! (strong Gen Z)
- Context-driven selection

---

## Architecture Insights

### Hybrid Brain-Book Model
```
VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml (17KB)
├── Embedded Logic: RTAS calculation, Boldness rules, Proxemics
└── External RAG Calls → Reference/*.md

Execution Flow:
1. Parse input JP text
2. Calculate RTAS (baseline 3.0 + modifiers)
3. Select pronoun pair from Ref_VIETNAMESE_PRONOUN_SYSTEM.md
4. Query Library_KANJI_KNOWLEDGE_BASE.md for kanji
5. Apply Boldness if RTAS triggers
6. Lookup Ref_SENSORY_LEXICON.md for verb enhancement
7. Validate with Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md
```

### Module Status Tracking
Files explicitly mark operational status:
- ✅ HOẠT ĐỘNG & ƯU TIÊN CAO (Active & High Priority)
- ✅ HOẠT ĐỘNG & UỶ QUYỀN (Active & Authorized)
- ⚠️ OPTIONAL (Load only when needed)

---

## Unresolved Questions

1. **Update frequency:** How often are Library files (Kanji/Golden Samples) updated?
2. **Ref_SAFETY_COMPLIANCE_MATRIX.md usage:** Criteria for "sensitive content" triggering this module?
3. **Version sync:** How to ensure Reference/*.md versions match XML core logic version (currently v10.0)?

---

**End of Report**
