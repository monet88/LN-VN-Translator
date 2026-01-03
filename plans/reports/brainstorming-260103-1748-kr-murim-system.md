# Brainstorming Session Report: Korean Murim Translation System

**Date:** 2026-01-03 17:48
**Session Duration:** ~45 minutes
**Objective:** Design separate KR_MURIM_TRANSLATOR.xml system for Korean Murim novels

---

## Session Summary

### Deliverables Created

1. ✅ **Brainstorm Specification** (`brainstorm-kr-murim-integration.md`)
   - Comprehensive research findings
   - Gap analysis: KR Murim vs JP Light Novel
   - XML architecture design (7 sections, ~50KB)
   - Reusability matrix from JP-LN system
   - Sample transformation pipeline
   - 6-week implementation roadmap

2. ✅ **ROTMHS Glossary Extraction** (`ROTMHS-glossary-extraction.md`)
   - 300+ core terms extracted
   - 8 categories: Gangho, Sects, Techniques, Energy, Factions, Honorifics, Places, Misc
   - Structured Hanja → Hán Việt mapping
   - Official translator glossary (95% Hanja coverage)

---

## Key Decisions Finalized

| Decision Point | Outcome |
|----------------|---------|
| **System Scope** | Generic KR Murim + ROTMHS-specific glossary module |
| **Gen Z Slang** | NO for historical fantasy, separate Modern Murim variant |
| **Hanja Display** | Toggle option in IO_PROTOCOL (default clean, optional bilingual) |
| **Testing Strategy** | Pure Murim first (ROTMHS, Legend of Northern Blade) → Modern later |

---

## Architecture Highlights

### Core Differences from JP-LN System

**Pacing:** Staccato action (KR) vs Emotional beats (JP)
**Power:** Internal energy cultivation (KR) vs Abstract abilities (JP)
**Combat:** Extended technical (KR) vs Brief emotional (JP)
**Honorifics:** Integrated terms (KR) vs Suffix-based (JP)

### KR_MURIM_TRANSLATOR.xml Structure

```
7 Sections (~1000 lines, ~50KB):
1. MURIM_LOCALIZATION (Archetypes, Faction Alignment, Honorifics)
2. COMBAT_MODULE (Qi flow, Choreography, Power scaling)
3. FORMATTING (KR punctuation, Hanja display, TL notes)
4. ANTI_TRANSLATIONESE (Reused + KR additions)
5. HANJA_PROTOCOL (Mapping triggers, Romanization)
6. IO_PROTOCOL (Dual-output: metadata + clean text)
7. COMBAT_LEXICON (200+ martial arts vivid verbs)
```

### Reference Modules Needed

**New KR-Specific:**
- Library_HANJA_MURIM_TERMS.md (~500KB, 3000+ terms)
- Library_ROTMHS_GLOSSARY.md (~150KB)
- Library_MURIM_GOLDEN_SAMPLES.md (~50KB)
- Ref_KR_HONORIFIC_SYSTEM.md (~30KB)
- Ref_CULTIVATION_STAGES.md (~25KB)
- Ref_COMBAT_CHOREOGRAPHY.md (~20KB)
- Ref_HANJA_ROMANIZATION_KR.md (~15KB)

**Reusable from JP-LN:**
- Anti-Translationese Guardrails (80% reuse)
- Formatting Standards (adapted)
- Safety Compliance Matrix (100% reuse)

---

## Sample Translation Quality

**Input (Korean):**
```
"청명아." "예, 사형."
백천의 목소리에 청명이 고개를 들었다.
"이번 마교와의 전투, 조심해라. 검강을 다룰 수 있는 적이 많다."
```

**Output (Vietnamese):**
```
"Thanh Minh." "Vâng, sư huynh."
Thanh Minh ngẩng đầu khi nghe tiếng Bạch Thiên.
"Trận chiến với Ma Giáo lần này, phải cẩn thận. Kẻ địch có nhiều người có thể sử dụng Kiếm Cương."
```

**Translation Logic:**
- Names: Hanja romanization (청명 清明 → Thanh Minh)
- Honorifics: 사형 → sư huynh (integrated, not suffix)
- Factions: 마교 → Ma Giáo (consistent terminology)
- Techniques: 검강 → Kiếm Cương (Hán Việt mapping)

---

## Implementation Roadmap (6 Weeks)

**Week 1:** Lexicon Extraction ← **CURRENT PHASE**
- [✅] Extract ROTMHS glossary (300+ terms)
- [🔄] Expand to 3000+ generic Murim terms
- [ ] Structure into Library_HANJA_MURIM_TERMS.md

**Week 2:** XML Architecture
- [ ] Create KR_MURIM_TRANSLATOR.xml base (7 sections)
- [ ] Implement FACTION_ALIGNMENT system
- [ ] Build Korean honorific logic

**Week 3:** Combat Module
- [ ] Design COMBAT_LEXICON (200+ verbs)
- [ ] Implement qi description templates
- [ ] Create choreography patterns

**Week 4:** Reference Modules
- [ ] Write Ref_KR_HONORIFIC_SYSTEM.md
- [ ] Write Ref_CULTIVATION_STAGES.md
- [ ] Write Ref_HANJA_ROMANIZATION_KR.md

**Week 5:** Golden Samples
- [ ] Translate 15-20 benchmark passages
- [ ] Create Library_MURIM_GOLDEN_SAMPLES.md
- [ ] Validate quality vs professional translation

**Week 6:** Testing & Refinement
- [ ] Test with 5 different KR Murim novels
- [ ] Collect edge cases
- [ ] Refine anti-translationese for KR-VN

---

## Critical Success Factors

1. **Hanja-Hán Việt Accuracy:** 3000+ terms need 95%+ consistency
2. **Combat Pacing:** KR action scenes 3x longer than JP (sentence shattering)
3. **Honorific Integration:** Korean terms embedded, not suffixes (사형 → sư huynh)
4. **Romanization:** Lock to Revised Romanization 2000 standard

---

## Terminology Statistics

**ROTMHS Glossary Extraction:**
- Total terms: ~300 core terms
- Hanja coverage: ~95%
- Categories: 8 (Gangho, Sects, Techniques, Energy, Factions, Honorifics, Places, Misc)
- Quality: Official translator glossary (high accuracy)

**Expansion Target:**
- Generic Murim vocabulary: +2700 terms
- Final database: 3000+ terms
- Frequency indexing for fast lookup

---

## Next Immediate Actions

1. **Expand Terminology Database**
   - Add generic Murim terms beyond ROTMHS
   - Cross-reference with other KR Murim glossaries
   - Structure into Library_HANJA_MURIM_TERMS.md

2. **Create Honorific Reference**
   - Document sect hierarchy patterns
   - Map speech level variations
   - Build Ref_KR_HONORIFIC_SYSTEM.md

3. **Cultivation Stages Reference**
   - Map realm naming (선천/후천/etc)
   - Power level language intensity scaling
   - Build Ref_CULTIVATION_STAGES.md

---

## Files Created This Session

```
plans/260103-1734-kr-murim-system/
├── brainstorm-kr-murim-integration.md      (~15KB, comprehensive spec)
├── ROTMHS-glossary-extraction.md            (~12KB, 300+ terms)
└── brainstorming-session-report.md          (this file)
```

---

## Unresolved Questions for Future Sessions

1. **Visual Proxemics:** Deprecate for KR system? (KR Murim rarely visual)
2. **Faction Auto-Detection:** Keyword triggers vs manual override?
3. **Translation Memory:** Per-novel vs cross-novel glossary lock?
4. **Cultivation Realm Detection:** Auto-detect from context or require annotation?

---

## Session Outcome: ✅ SUCCESS

**Status:** Design phase COMPLETE. Ready for implementation Week 1.

**Quality:** High-quality specification with:
- Clear architecture
- Concrete samples
- Reusability analysis
- 6-week roadmap

**Next Session:** Begin lexicon expansion to 3000+ terms.

---

**Report Generated:** 2026-01-03 17:48
**Approver:** [Awaiting user confirmation to proceed to implementation]
