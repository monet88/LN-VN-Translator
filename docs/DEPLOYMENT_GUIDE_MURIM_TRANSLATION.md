# Deployment Guide: Murim Translation Systems

**Version:** 1.0
**Last Updated:** 2026-01-05 (Week 6 - Cross-System Integration)
**Systems Covered:** KR-VN (Korean→Vietnamese) + EN-VN (English→Vietnamese)
**Status:** Production-ready

---

## Table of Contents

1. [Overview](#overview)
2. [Prerequisites](#prerequisites)
3. [KR-VN System Deployment](#kr-vn-system-deployment)
4. [EN-VN System Deployment](#en-vn-system-deployment)
5. [Usage Instructions](#usage-instructions)
6. [Quality Assurance](#quality-assurance)
7. [Troubleshooting](#troubleshooting)
8. [Maintenance](#maintenance)
9. [Advanced Configuration](#advanced-configuration)
10. [Appendices](#appendices)

---

## Overview

### System Architecture

This project contains **two integrated translation systems** for Murim (martial arts) light novels:

```
LN-VN-Translator/
├── KR-VN Pipeline (Korean → Vietnamese)
│   ├── KR_MURIM_TRANSLATOR.xml (150KB system prompt)
│   ├── Reference/KR_SPECIFIC/ (10 files, 156KB total)
│   └── Reference/SHARED/ (10 files, 200KB+ UNIFIED database)
│
└── EN-VN Pipeline (English → Vietnamese)
    ├── SystemXML/EN_MURIM_TRANSLATOR.xml (145KB system prompt)
    ├── Reference/EN_SPECIFIC/ (4 files, 95KB total)
    └── Reference/SHARED/ (same 10 shared files)
```

**Unified Components (Week 6 Integration):**
- **UNIFIED_MURIM_TERMINOLOGY.md (210KB)**: 3000+ terms with cross-language lookup (Korean/Pinyin/Wade-Giles/English → Hán Việt)
- **Shared References (9 files)**: Cultivation stages, combat choreography, anti-translationese guardrails, Vietnamese expression mapping, etc.

**Key Features:**
- Single source of truth for Hán Việt terminology
- 4-tier frequency system (Tier 1-4 for lookup optimization)
- 5 cross-reference indices (KR/Pinyin/Wade-Giles/EN/Hanja)
- 56 usage examples validating cross-system consistency
- Backward compatible with pre-Week 6 workflows

---

### Deployment Options

**Option 1: Google Gemini Gems (Recommended)**
- **Platform:** Gemini Advanced web interface
- **Advantages:** No coding required, visual interface, persistent context
- **Limitations:** File size limits (2MB per upload), no API automation
- **Best for:** Manual translation workflows, quality assurance testing

**Option 2: Gemini API (Advanced)**
- **Platform:** Google AI Studio / Vertex AI
- **Advantages:** Automation, batch processing, version control
- **Limitations:** Requires API key, Python/Node.js integration
- **Best for:** Production pipelines, CI/CD integration

**Option 3: Local LLM (Experimental)**
- **Platform:** Ollama with Gemma 2 (27B+)
- **Advantages:** No API costs, full privacy
- **Limitations:** Requires GPU (24GB+ VRAM), slower than cloud
- **Best for:** Offline work, privacy-sensitive projects

**This guide focuses on Option 1 (Gemini Gems) as the primary deployment method.**

---

## Prerequisites

### 1. Accounts & Access

- [ ] **Google Gemini Advanced subscription** (required for Gems with 2MB file uploads)
  - Free tier: Limited to 1MB uploads (insufficient for UNIFIED_MURIM_TERMINOLOGY.md)
  - Paid tier: 2MB uploads (sufficient for all reference files)

- [ ] **GitHub account** (optional, for repository access)
  - Repository: https://github.com/monet88/LN-VN-Translator

### 2. Required Files

**For KR-VN System:**
```
KR_MURIM_TRANSLATOR.xml (150KB)
Reference/SHARED/UNIFIED_MURIM_TERMINOLOGY.md (210KB)
Reference/KR_SPECIFIC/Library_ROTMHS_GLOSSARY.md (93KB)
Reference/KR_SPECIFIC/Ref_KR_HONORIFIC_SYSTEM.md (40KB)
Reference/SHARED/Ref_CULTIVATION_STAGES.md (36KB)
Reference/SHARED/Ref_COMBAT_CHOREOGRAPHY.md (35KB)

Total: ~564KB (well under 2MB limit per Gem)
```

**For EN-VN System:**
```
SystemXML/EN_MURIM_TRANSLATOR.xml (145KB)
Reference/SHARED/UNIFIED_MURIM_TERMINOLOGY.md (210KB)
Reference/EN_SPECIFIC/Ref_PINYIN_MAPPING_TABLE.md (82KB)
Reference/EN_SPECIFIC/Ref_EN_PROSE_DENSITY_RULES.md (32KB)
Reference/SHARED/Ref_CULTIVATION_STAGES.md (36KB)
Reference/SHARED/Ref_COMBAT_CHOREOGRAPHY.md (35KB)

Total: ~540KB (well under 2MB limit per Gem)
```

**Shared Files (used by both systems):**
- Reference/SHARED/Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (25KB)
- Reference/SHARED/Ref_VIETNAMESE_PRONOUN_SYSTEM.md (34KB)
- Reference/SHARED/Ref_SENSORY_LEXICON.md (12KB)
- Reference/SHARED/Ref_FORMATTING_STANDARDS.md (4.4KB)

### 3. Test Samples

**KR-VN Test:**
```korean
화산파의 청명이 검을 들었다. 그의 내공이 폭발하며 검기가 하늘을 갈랐다.
"사형, 이제 제가 절정에 도달했습니다."
```

**EN-VN Test:**
```english
Linley circulated his internal energy through his twelve meridians, condensing a powerful sword qi. The overwhelming killing intent erupted from his body as he prepared to strike.
```

---

## KR-VN System Deployment

### Step 1: Create KR-VN Gemini Gem

**1.1 Navigate to Google Gemini**
- Go to https://gemini.google.com
- Ensure you're using Gemini Advanced (check top-right account status)

**1.2 Create New Gem**
- Click "Create Gem" in left sidebar
- Name: `KR-VN Murim Translator`
- Description: `Korean to Vietnamese translation system for martial arts light novels (Return of Mount Hua Sect optimized)`

**1.3 Upload System Prompt**
- In "Instructions" field, copy entire contents of `KR_MURIM_TRANSLATOR.xml`
- Alternatively, upload `KR_MURIM_TRANSLATOR.xml` as Knowledge file
- **Important:** If uploading as file, ensure Gem references it in instructions: "Follow the translation system defined in KR_MURIM_TRANSLATOR.xml"

---

### Step 2: Configure KR-VN Knowledge Base

**2.1 Upload Core References (in order)**

1. **UNIFIED_MURIM_TERMINOLOGY.md (210KB)** ← Primary lookup source
   - Click "Add file" → Select `Reference/SHARED/UNIFIED_MURIM_TERMINOLOGY.md`
   - **Critical:** This is the single source of truth for all Hán Việt translations

2. **Library_ROTMHS_GLOSSARY.md (93KB)** ← Novel-specific glossary
   - Upload from `Reference/KR_SPECIFIC/Library_ROTMHS_GLOSSARY.md`
   - Contains 300+ Return of Mount Hua Sect specific terms

3. **Ref_KR_HONORIFIC_SYSTEM.md (40KB)** ← Sect hierarchy rules
   - Upload from `Reference/KR_SPECIFIC/Ref_KR_HONORIFIC_SYSTEM.md`

4. **Ref_CULTIVATION_STAGES.md (36KB)** ← Cultivation realms
   - Upload from `Reference/SHARED/Ref_CULTIVATION_STAGES.md`

5. **Ref_COMBAT_CHOREOGRAPHY.md (35KB)** ← Combat scene patterns
   - Upload from `Reference/SHARED/Ref_COMBAT_CHOREOGRAPHY.md`

**2.2 Upload Supporting References (optional, recommended)**

6. **Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (25KB)**
   - Upload from `Reference/SHARED/Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md`

7. **Ref_VIETNAMESE_PRONOUN_SYSTEM.md (34KB)**
   - Upload from `Reference/SHARED/Ref_VIETNAMESE_PRONOUN_SYSTEM.md`

**Total Uploaded:** ~473KB (well under 2MB limit)

---

### Step 3: Test KR-VN System

**3.1 Test Input**

Paste into Gem chat:
```
Hãy dịch đoạn sau từ tiếng Hàn sang tiếng Việt theo hệ thống KR_MURIM_TRANSLATOR:

화산파의 청명이 검을 들었다. 그의 내공이 폭발하며 검기가 하늘을 갈랐다.
"사형, 이제 제가 절정에 도달했습니다."
장문인이 고개를 끄덕였다. "화경에 한 걸음 더 다가섰구나."
```

**3.2 Expected Output**

The Gem should output:
1. **Chatbox Metadata:** Translation rationale, terminology choices, GUARD checks
2. **Canvas Output:** Clean Vietnamese translation

**Expected Canvas Translation:**
```vietnamese
Thanh Minh của Hoa Sơn Phái cầm kiếm lên. Nội công của hắn bùng nổ, kiếm khí xé toạc bầu trời.
"Sư huynh, giờ đệ tử đã đạt Tuyệt Đỉnh."
Chưởng môn gật đầu. "Ngươi đã tiến thêm một bước đến Hóa Cảnh."
```

**3.3 Validation Checklist**

- [ ] Terminology correct: 화산파 → Hoa Sơn Phái (proper noun preserved)
- [ ] Terminology correct: 내공 → Nội công (MUR-0005 from UNIFIED)
- [ ] Terminology correct: 검기 → Kiếm khí (MUR-0022 from UNIFIED)
- [ ] Terminology correct: 절정 → Tuyệt Đỉnh (MUR-0018 from UNIFIED)
- [ ] Terminology correct: 화경 → Hóa Cảnh (MUR-0019 from UNIFIED)
- [ ] Honorifics correct: 사형 → Sư huynh (MUR-0007 from UNIFIED)
- [ ] Honorifics correct: 장문인 → Chưởng môn (MUR-0006 from UNIFIED)
- [ ] Combat rhythm preserved: 3 sentences maintained (staccato pattern)
- [ ] Natural Vietnamese: No translationese (e.g., no "một cách...")
- [ ] Chatbox metadata present: Shows terminology lookup process

**If all checkboxes pass → KR-VN system deployed successfully ✅**

---

## EN-VN System Deployment

### Step 1: Create EN-VN Gemini Gem

**1.1 Navigate to Google Gemini**
- Go to https://gemini.google.com
- Click "Create Gem" (create separate Gem from KR-VN)

**1.2 Create New Gem**
- Name: `EN-VN Murim Translator`
- Description: `English to Vietnamese translation system for martial arts novels (Coiling Dragon, ISSTH, etc.) with prose density control`

**1.3 Upload System Prompt**
- Copy entire contents of `SystemXML/EN_MURIM_TRANSLATOR.xml`
- Paste into "Instructions" field
- OR upload `EN_MURIM_TRANSLATOR.xml` as Knowledge file with reference instruction

---

### Step 2: Configure EN-VN Knowledge Base

**2.1 Upload Core References (in order)**

1. **UNIFIED_MURIM_TERMINOLOGY.md (210KB)** ← Primary lookup source (same file as KR-VN)
   - Upload from `Reference/SHARED/UNIFIED_MURIM_TERMINOLOGY.md`

2. **Ref_PINYIN_MAPPING_TABLE.md (82KB)** ← Pinyin/Wade-Giles conversion
   - Upload from `Reference/EN_SPECIFIC/Ref_PINYIN_MAPPING_TABLE.md`
   - Handles Wade-Giles (older novels) and Pinyin (modern novels)

3. **Ref_EN_PROSE_DENSITY_RULES.md (32KB)** ← Condensation rules (60-70% target)
   - Upload from `Reference/EN_SPECIFIC/Ref_EN_PROSE_DENSITY_RULES.md`
   - **Critical for EN-VN:** English novels are 2-3x more verbose than Korean

4. **Ref_CULTIVATION_STAGES.md (36KB)** ← Cultivation realms (shared)
   - Upload from `Reference/SHARED/Ref_CULTIVATION_STAGES.md`

5. **Ref_COMBAT_CHOREOGRAPHY.md (35KB)** ← Combat patterns (shared)
   - Upload from `Reference/SHARED/Ref_COMBAT_CHOREOGRAPHY.md`

**2.2 Upload Supporting References (optional, recommended)**

6. **Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (25KB)**
   - Upload from `Reference/SHARED/Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md`

7. **Ref_EN_HONORIFICS_MAPPING.md (17KB)**
   - Upload from `Reference/EN_SPECIFIC/Ref_EN_HONORIFICS_MAPPING.md`

**Total Uploaded:** ~437KB (well under 2MB limit)

---

### Step 3: Test EN-VN System

**3.1 Test Input**

Paste into Gem chat:
```
Translate the following from English to Vietnamese following EN_MURIM_TRANSLATOR system:

Linley circulated his vast and mighty internal energy through his twelve primary meridians, condensing an incredibly powerful and devastating sword qi. The overwhelming killing intent erupted from his entire body as he prepared to unleash his ultimate strike against the enemy.

"Senior Brother," he said respectfully, "this disciple has finally broken through to the Transformation Realm."
```

**3.2 Expected Output**

**Expected Canvas Translation (60-70% word count):**
```vietnamese
Linley vận hành nội công hùng hậu qua thập nhị chính kinh, ngưng tụ kiếm khí cực mạnh. Sát khí áp đảo bùng phát từ toàn thân khi hắn chuẩn bị tung đòn tối thượng vào địch.

"Sư huynh," hắn nói cung kính, "đệ tử cuối cùng đã đột phá Hóa Cảnh."
```

**Word Count Analysis:**
- English: 53 words
- Vietnamese: ~32 từ (60% condensation ✅ within 60-70% target)

**3.3 Validation Checklist**

- [ ] Prose density applied: 60-70% word count reduction (53 words → ~32 từ)
- [ ] Intensity preserved: "vast and mighty" → "hùng hậu" (Week 5 Rule 2A.1)
- [ ] Terminology correct: "internal energy" → Nội công (MUR-0005 from UNIFIED)
- [ ] Terminology correct: "twelve meridians" → Thập nhị chính kinh (MUR-0011)
- [ ] Terminology correct: "sword qi" → Kiếm khí (MUR-0022 from UNIFIED)
- [ ] Terminology correct: "killing intent" → Sát khí (MUR-0023 from UNIFIED)
- [ ] Terminology correct: "Transformation Realm" → Hóa Cảnh (MUR-0019 from UNIFIED)
- [ ] Honorifics correct: "Senior Brother" → Sư huynh (MUR-0007 from UNIFIED)
- [ ] No over-condensation: Critical elements preserved (twelve, entire, ultimate)
- [ ] Natural Vietnamese: No translationese patterns

**If all checkboxes pass → EN-VN system deployed successfully ✅**

---

## Usage Instructions

### Input Format Guidelines

**For KR-VN System:**
```
Format: Plain Korean text, no preprocessing required

Example:
화산파의 청명이 말했다. "사형, 이 검법을 가르쳐 주십시오."
```

**For EN-VN System:**
```
Format: Plain English text, handles Pinyin/Wade-Giles automatically

Example with Pinyin:
He mastered Qinggong and could unleash powerful Jianqi attacks.

Example with Wade-Giles:
The master circulated his Ch'i through the Tan-t'ien.

Both formats supported via Index 3 conversion table.
```

**Special Cases:**

1. **Proper Nouns:** System preserves proper nouns (e.g., Mount Hua Sect → Hoa Sơn Phái)
2. **Technique Names:** Novel-specific techniques use UNIFIED for components (e.g., "Plum Blossom Sword Art" → "Mai Hoa Kiếm Pháp")
3. **Mixed Romanization:** EN-VN handles mixed Pinyin/Wade-Giles in single passage

---

### Output Interpretation

**Gemini Gems Output Format:**

```
[CHATBOX - Metadata & Rationale]
=================================
Translation Analysis:
- Terminology: 내공 → Nội công (MUR-0005, Tier 1)
- Honorific: 사형 → Sư huynh (MUR-0007, Tier 1)
- Prose density: 53 words → 32 từ (60% - within target)
- GUARD checks: 18/18 passed ✅

[CANVAS - Clean Vietnamese Translation]
========================================
Thanh Minh của Hoa Sơn Phái nói...
```

**How to Use:**
- **Chatbox:** Review for terminology choices, GUARD validation, quality metrics
- **Canvas:** Copy clean translation for publication

---

### Quality Validation Workflow

**Step-by-Step QA Process:**

1. **Input Review (Pre-translation)**
   - [ ] Source text cleaned (no formatting artifacts)
   - [ ] Character names identified (for consistency)
   - [ ] Novel-specific glossary consulted (if available)

2. **Translation Execution**
   - [ ] Paste source text into Gem
   - [ ] Wait for Chatbox metadata + Canvas output

3. **Terminology Check (Post-translation)**
   - [ ] All Murim terms use UNIFIED_MURIM_TERMINOLOGY.md PRIMARY translations
   - [ ] Novel-specific terms consistent with glossary
   - [ ] No untranslated romanization (Pinyin/Wade-Giles → Hán Việt)

4. **Prose Quality Check (EN-VN only)**
   - [ ] Word count 60-70% of English (or context-appropriate: combat 70-80%, poetry 80-90%)
   - [ ] No semantic loss >5% (Week 5 Rule 2C)
   - [ ] Intensity preserved in emotional/combat scenes

5. **GUARD Principles Check (18 rules)**
   - [ ] No translationese patterns (e.g., "một cách...")
   - [ ] No passive voice overload
   - [ ] Natural Vietnamese rhythm
   - [ ] Pronoun system correctly applied
   - [See full checklist in Appendix B]

6. **Combat Choreography Check (if applicable)**
   - [ ] Staccato rhythm preserved (short, punchy sentences)
   - [ ] Energy-physical integration (Qi + physical moves flow naturally)
   - [ ] Decisive moments emphasized, filler skipped

7. **Final Review**
   - [ ] Read aloud test: Sounds natural in Vietnamese
   - [ ] Context preservation: Meaning intact vs source
   - [ ] Consistency: Terms match previous chapters (if serialized)

---

### Terminology Consistency Checks

**Using UNIFIED_MURIM_TERMINOLOGY.md:**

**Lookup Priority:**
1. Search UNIFIED by ID (MUR-XXXX) if known
2. Search by source language column (Korean/Pinyin/English)
3. Verify PRIMARY translation used (not ALT, unless novel glossary overrides)
4. Check frequency tier (Tier 1 = most common, cache in memory)

**Common Pitfall - ALT vs PRIMARY:**

```
Term: Zhenyuan (真元)
PRIMARY: Chân nguyên ← Use this by default
ALT: Chân khí ← Only if novel glossary specifies

Incorrect: Using ALT without justification
Correct: Always use PRIMARY unless override documented
```

**Cross-System Consistency:**

When translating same novel from multiple sources (KR + EN):

```
Example: Sword Qi (劍氣)
Korean: 검기 → Kiếm khí (MUR-0022)
English: Sword Qi → Kiếm khí (MUR-0022)
Pinyin: Jianqi → Kiếm khí (MUR-0022)
✅ All paths converge to same Hán Việt term
```

---

## Quality Assurance

### S-Tier Rubric Application

**Definition:** S-tier = Professional-grade translation indistinguishable from native Vietnamese novels

**Criteria (10 dimensions):**

1. **Terminology Accuracy (15%):** All Murim terms use UNIFIED PRIMARY, no Pinyin/romanization left
2. **Prose Density (EN-VN, 10%):** 60-70% word count (context-adjusted)
3. **Natural Vietnamese (20%):** No translationese, passes read-aloud test
4. **Pronoun System (10%):** Correct hierarchy (Sư huynh > Sư đệ, etc.)
5. **Combat Choreography (10%):** Staccato rhythm, energy integration
6. **Honorifics (10%):** Sect hierarchy respected
7. **Semantic Preservation (15%):** <5% meaning loss
8. **Formatting (5%):** Dialogue tags, paragraph structure
9. **Character Voice (5%):** Personality preserved in dialogue
10. **Context Consistency (10%):** Terms match novel glossary

**Scoring:**
- **S-tier:** 95-100% (all criteria met)
- **A-tier:** 90-94% (minor issues)
- **B-tier:** 85-89% (acceptable, needs revision)
- **C-tier:** <85% (requires retranslation)

---

### GUARD Principles Checklist (18 Rules)

**Module 08: Anti-Translationese Guardrails**

1. [ ] **No "một cách" overload:** Direct adverbs used (vội vã, not "một cách vội vã")
2. [ ] **No passive voice excess:** Active voice preferred (Vietnamese hates passive)
3. [ ] **No "-ly" adverb dumps:** Integrated manner verbs (phóng đi, not "chạy một cách nhanh")
4. [ ] **No subject-verb-object rigidity:** Flexible Vietnamese word order
5. [ ] **No literal preposition mapping:** Vietnamese uses different preposition logic
6. [ ] **No gerund phrase retention:** Converted to Vietnamese clause structures
7. [ ] **No nested relative clauses:** Simplified into separate sentences
8. [ ] **No English conjunctions spam:** Vietnamese uses fewer explicit conjunctions

**Week 5 Enhancements (Rules 15-20):**

15. [ ] **Intensity preservation:** Keep 2-3 strongest qualifiers from 3+ English adjectives (Rule 2A.1)
16. [ ] **Context-sensitive thresholds:** Combat 70-80%, Dialogue 60-70%, Poetry 80-90% (Section 2B)
17. [ ] **Semantic loss detection:** <5% critical element loss (Rule 2C)
18. [ ] **Negation preservation:** NEVER drop "not/never/no/without"

[Full 18-rule checklist in Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md]

---

### Test Suite (10 Core Tests)

**Run these 10 tests to validate deployment:**

**Test 1: Basic Terminology (KR-VN)**
```korean
Input: 그는 내공을 운행했다.
Expected: Hắn vận hành nội công.
Check: 내공 → Nội công (MUR-0005) ✅
```

**Test 2: Basic Terminology (EN-VN)**
```english
Input: He circulated his internal energy.
Expected: Hắn vận hành nội công.
Check: internal energy → Nội công (MUR-0005) ✅
```

**Test 3: Honorifics (KR-VN)**
```korean
Input: "사형, 가르침을 주십시오."
Expected: "Sư huynh, xin chỉ giáo."
Check: 사형 → Sư huynh (MUR-0007) ✅
```

**Test 4: Prose Density (EN-VN)**
```english
Input (22 words): He felt the vast, mighty, and overwhelming power surge through his meridians.
Expected (~15 từ, 68%): Hắn cảm thấy sức mạnh hùng hậu áp đảo dâng qua kinh mạch.
Check: 60-70% range ✅, intensity preserved ✅
```

**Test 5: Wade-Giles Conversion (EN-VN)**
```english
Input: He mastered Ch'i circulation.
Expected: Hắn tinh thông vận khí.
Check: Ch'i (Wade-Giles) → Qi (Pinyin) → Khí (MUR-0001) ✅
```

**Test 6: Combat Choreography (KR-VN)**
```korean
Input: 검이 번쩍였다. 피가 튀었다.
Expected: Kiếm lóe sáng. Máu bắn tung.
Check: Staccato rhythm preserved (2 sentences → 2 sentences) ✅
```

**Test 7: Compound Terms (EN-VN)**
```english
Input: He used the Eighteen Dragon Subduing Palms.
Expected: Hắn dùng Hàng Long Thập Bát Chưởng.
Check: 4-word compound matched (MUR-0066) ✅
```

**Test 8: Cultivation Realms (Cross-system)**
```korean
KR Input: 화경에 돌파했다.
EN Input: He broke through to the Transformation Realm.
Expected (both): Đột phá Hóa Cảnh.
Check: Cross-system consistency (MUR-0019) ✅
```

**Test 9: Novel-Specific Terms (KR-VN ROTMHS)**
```korean
Input: 화산신공을 수련하다.
Expected: Tu luyện Hoa Sơn Thần Công.
Check: Proper noun preserved (novel-specific) ✅
```

**Test 10: Anti-Translationese (EN-VN)**
```english
Input: He walked in a quick manner.
Expected: Hắn vội vã đi. (NOT "đi một cách nhanh")
Check: GUARD Rule 1 applied ✅
```

**Pass Criteria:** 10/10 tests pass → System validated ✅

---

## Troubleshooting

### Common Issues and Fixes

**Issue 1: Gemini refuses to upload file (Error: "File too large")**

**Cause:** Using Gemini Free (1MB limit) instead of Gemini Advanced (2MB limit)

**Fix:**
- Upgrade to Gemini Advanced subscription
- OR split UNIFIED_MURIM_TERMINOLOGY.md into 2 files (Tier 1-2 + Tier 3-4)
- OR use API deployment instead (no file size limit)

---

**Issue 2: Terminology inconsistent (uses wrong Hán Việt)**

**Cause:** Gem not referencing UNIFIED_MURIM_TERMINOLOGY.md

**Diagnosis:**
- Check uploaded files list in Gem settings
- Verify UNIFIED file uploaded successfully (210KB)

**Fix:**
- Re-upload UNIFIED_MURIM_TERMINOLOGY.md
- Add explicit instruction in Gem: "ALWAYS use UNIFIED_MURIM_TERMINOLOGY.md for all Hán Việt lookups"

---

**Issue 3: EN-VN not applying prose density (output same length as English)**

**Cause:** Ref_EN_PROSE_DENSITY_RULES.md not uploaded or not applied

**Diagnosis:**
- Check if Ref_EN_PROSE_DENSITY_RULES.md in knowledge base
- Review Chatbox metadata: Should show "Prose density: X words → Y từ (Z%)"

**Fix:**
- Upload Ref_EN_PROSE_DENSITY_RULES.md
- Add explicit reminder in Gem instructions: "CRITICAL: Apply 60-70% prose density reduction for EN-VN"

---

**Issue 4: Wade-Giles terms not converted (output shows "Ch'i" instead of "Khí")**

**Cause:** Ref_PINYIN_MAPPING_TABLE.md not uploaded (EN-VN only)

**Fix:**
- Upload Ref_PINYIN_MAPPING_TABLE.md (82KB)
- Verify Index 3 (Wade-Giles → Pinyin → Hán Việt) is documented in UNIFIED v1.1

---

**Issue 5: Honorifics wrong (e.g., 사형 → "anh" instead of "Sư huynh")**

**Cause:** Generic Vietnamese pronoun system overriding Murim honorifics

**Fix:**
- Verify Ref_KR_HONORIFIC_SYSTEM.md uploaded (KR-VN)
- Add explicit instruction: "Use Murim sect hierarchy honorifics from Ref_KR_HONORIFIC_SYSTEM, NOT generic Vietnamese pronouns"

---

**Issue 6: Combat scenes lose staccato rhythm (merged into long sentences)**

**Cause:** Ref_COMBAT_CHOREOGRAPHY.md not applied

**Fix:**
- Upload Ref_COMBAT_CHOREOGRAPHY.md (35KB)
- Add instruction: "Preserve staccato combat rhythm: short sentences for action scenes"

---

**Issue 7: Translationese patterns appear (e.g., "một cách...")**

**Cause:** Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md not uploaded

**Fix:**
- Upload Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (25KB)
- Validate GUARD Rule 1 applied in test output

---

### Edge Case Handling

**Edge Case 1: Novel uses non-standard terminology**

**Example:** Novel glossary says "True Essence = Chân khí" but UNIFIED PRIMARY is "Chân nguyên"

**Solution:**
- Document in novel-specific glossary file
- Upload novel glossary to Gem knowledge base
- Add instruction: "If novel glossary conflicts with UNIFIED, use novel glossary (ALT translation)"

---

**Edge Case 2: Mixed Korean-English input**

**Example:** "청명이 Qinggong을 사용했다."

**Solution:**
- System should handle via UNIFIED cross-language lookup
- "청명" stays Korean (proper noun)
- "Qinggong" (Pinyin) → Khinh công (MUR-0014)
- "사용했다" → "sử dụng"
- Output: "Thanh Minh sử dụng khinh công."

---

**Edge Case 3: Extremely long input (10,000+ words)**

**Cause:** Gemini context window limit (~1M tokens)

**Solution:**
- Split into chapters (recommended: 2000-3000 words per chunk)
- Use API deployment for batch processing

---

### System Limitations

**Known Limitations:**

1. **File Upload Limit:** Gemini Advanced = 2MB per file (UNIFIED at 210KB is within limit)
2. **Context Window:** ~1M tokens (sufficient for most chapters, split if >10k words)
3. **No Real-Time Updates:** Reference files static after upload (must re-deploy for updates)
4. **No Automation:** Gemini Gems = manual interface (use API for automation)
5. **Quality Variance:** LLM output may vary 5-10% between runs (use GUARD validation)

**Mitigation:**
- Use version control for reference files
- Implement QA workflow (10-test suite) before publication
- Re-run translation if quality <90% (A-tier threshold)

---

## Maintenance

### Reference Updates

**When to Update:**

1. **New novel terms discovered** → Add to UNIFIED_MURIM_TERMINOLOGY.md
2. **Terminology refinement** → Update PRIMARY/ALT in UNIFIED
3. **Prose density rules change** → Update Ref_EN_PROSE_DENSITY_RULES.md
4. **GUARD rules added** → Update Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md

**Update Workflow:**

1. **Edit reference file locally** (in repository)
2. **Test with sample passages** (validate no regressions)
3. **Commit to git** (version control)
4. **Re-deploy to Gem:**
   - Delete old file from Gem knowledge base
   - Upload updated file
   - Re-run 10-test suite validation

---

### Version Control

**Recommended Git Workflow:**

```bash
# Make changes to reference files
git add Reference/SHARED/UNIFIED_MURIM_TERMINOLOGY.md
git commit -m "feat: Add 50 new xianxia terms to UNIFIED (MUR-3001 to MUR-3050)"
git push

# Tag major versions
git tag -a v1.1-unified -m "Week 6: Cross-system integration with UNIFIED database"
git push --tags
```

**Versioning Scheme:**

- **Major version (v2.0):** System architecture change (e.g., adding JP-VN pipeline)
- **Minor version (v1.1):** Feature additions (e.g., Week 6 UNIFIED integration)
- **Patch version (v1.1.1):** Bug fixes, terminology corrections

**Current Version:** v1.1 (Week 6 - Cross-System Integration)

---

### Performance Monitoring

**Metrics to Track:**

1. **Translation Speed:** Average time per 1000 words
   - KR-VN: ~30-60 seconds (Gemini 2.0 Flash)
   - EN-VN: ~45-90 seconds (longer due to prose density processing)

2. **Quality Metrics (S-tier rubric):**
   - Target: 95%+ average across 10 dimensions
   - Track per chapter, identify patterns

3. **Terminology Consistency:**
   - Run periodic audits: Same terms → Same Hán Việt
   - Use UNIFIED ID (MUR-XXXX) to track changes

4. **Error Rate:**
   - GUARD violations per 1000 words (target: <2)
   - Semantic loss rate (target: <5%)

**Monthly Review:**
- Analyze failed QA tests
- Update UNIFIED with new terms
- Refine prose density thresholds if needed

---

## Advanced Configuration

### Prose Density Tuning (EN-VN Only)

**Default:** 60-70% word count reduction

**Context-Sensitive Overrides (Week 5 refinements):**

```
Scene Type         Target Ratio    Override Instruction
==========         ============    ====================
Combat             70-80%          "Preserve staccato rhythm, allow 70-80% for urgency"
Dialogue           60-70%          "Standard 60-70%, keep speech patterns natural"
Description        50-60%          "Aggressive condensation 50-60%, drop redundant adjectives"
Poetry/Emotional   80-90%          "Preserve intensity 80-90%, keep emotional qualifiers"
```

**How to Apply:**
- Add scene-specific instruction in Gem prompt
- Example: "This passage is a combat scene. Apply 70-80% prose density and preserve staccato rhythm."

---

### Name Handling Mode Toggle

**Mode 1: Transliterate All Names (Default)**
```
Input: Linley Baruch
Output: Linley Baruch (kept as-is, no Hán Việt)
```

**Mode 2: Translate Meaningful Names**
```
Input: Sword Saint (劍聖)
Output: Kiếm Thánh (translated as title)
```

**How to Toggle:**
- Add instruction: "Translate meaningful titles like 'Sword Saint' to Hán Việt. Keep Western names as-is."

---

### Bilingual Output Option

**Standard Output (Vietnamese only):**
```vietnamese
Thanh Minh vận hành nội công, kiếm khí bùng nổ.
```

**Bilingual Output (VN + EN glossary):**
```vietnamese
Thanh Minh vận hành nội công¹, kiếm khí² bùng nổ.

Glossary:
¹ nội công (內功): internal energy
² kiếm khí (劍氣): sword qi
```

**How to Enable:**
- Add instruction: "Include Hán Việt glossary footnotes for first occurrence of each Murim term"

---

## Appendices

### Appendix A: File Structure Reference

```
LN-VN-Translator/
├── docs/
│   ├── DEPLOYMENT_GUIDE_MURIM_TRANSLATION.md (this file)
│   └── UNIFIED_REFERENCE_STRUCTURE.md (Week 6 structure guide)
│
├── Reference/
│   ├── SHARED/ (10 files, used by both KR-VN and EN-VN)
│   │   ├── UNIFIED_MURIM_TERMINOLOGY.md (210KB) ← Primary database
│   │   ├── Ref_CULTIVATION_STAGES.md (36KB)
│   │   ├── Ref_COMBAT_CHOREOGRAPHY.md (35KB)
│   │   ├── Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (25KB)
│   │   ├── Ref_VIETNAMESE_PRONOUN_SYSTEM.md (34KB)
│   │   ├── Ref_VIETNAMESE_EXPRESSION_MAPPING.md (15KB)
│   │   ├── Ref_SENSORY_LEXICON.md (12KB)
│   │   ├── Ref_VISUAL_PROXEMICS_QUICK_REFERENCE.md (11KB)
│   │   ├── Ref_FORMATTING_STANDARDS.md (4.4KB)
│   │   └── Ref_SAFETY_COMPLIANCE_MATRIX.md (5.2KB)
│   │
│   ├── KR_SPECIFIC/ (10 files, Korean-only)
│   │   ├── Library_ROTMHS_GLOSSARY.md (93KB) ← ROTMHS novel glossary
│   │   ├── Ref_KR_HONORIFIC_SYSTEM.md (40KB)
│   │   ├── Library_MURIM_GOLDEN_SAMPLES.md (56KB)
│   │   ├── Library_HANJA_MURIM_TERMS.md (18KB)
│   │   ├── Ref_HANJA_ROMANIZATION_KR.md (16KB)
│   │   ├── Library_GENERIC_MURIM_TERMS.md (20KB) [Legacy]
│   │   └── ... (4 more files)
│   │
│   └── EN_SPECIFIC/ (4 files, English-only)
│       ├── Ref_PINYIN_MAPPING_TABLE.md (82KB) ← Wade-Giles conversion
│       ├── Ref_EN_PROSE_DENSITY_RULES.md (32KB) ← Condensation rules
│       ├── Library_EN_MURIM_GOLDEN_SAMPLES.md (35KB)
│       └── Ref_EN_HONORIFICS_MAPPING.md (17KB)
│
├── KR_MURIM_TRANSLATOR.xml (150KB) ← KR-VN system prompt
└── SystemXML/
    └── EN_MURIM_TRANSLATOR.xml (145KB) ← EN-VN system prompt
```

---

### Appendix B: S-Tier Quality Metrics Definitions

**Dimension 1: Terminology Accuracy (15%)**
- **100%:** All terms use UNIFIED PRIMARY, zero romanization left
- **90%:** 1-2 minor terms inconsistent
- **80%:** 3-5 terms wrong
- **<80%:** Major terminology errors

**Dimension 2: Prose Density (EN-VN only, 10%)**
- **100%:** 60-70% (or context-appropriate: combat 70-80%, poetry 80-90%)
- **90%:** 55-75% (slight deviation)
- **80%:** 50-80% (noticeable deviation)
- **<80%:** <50% or >80% (failed condensation)

**Dimension 3: Natural Vietnamese (20%)**
- **100%:** Zero translationese, passes native speaker read-aloud
- **90%:** 1-2 awkward phrases
- **80%:** 3-5 awkward phrases
- **<80%:** Pervasive translationese

[... Full 10-dimension rubric definitions]

---

### Appendix C: Contact for Issues

**Project Repository:**
- GitHub: https://github.com/monet88/LN-VN-Translator
- Issues: https://github.com/monet88/LN-VN-Translator/issues

**Documentation:**
- Deployment Guide: `docs/DEPLOYMENT_GUIDE_MURIM_TRANSLATION.md`
- Reference Structure: `docs/UNIFIED_REFERENCE_STRUCTURE.md`

**Beads Issue Tracking:**
- Check ready work: `bd ready`
- Report bug: `bd create --title="Bug: [description]" --type=bug --priority=1`

**Maintainer:** LN-VN-Translator Project Team
**Last Updated:** 2026-01-05 (Week 6 - ln-ll6.3)
**Version:** 1.0

---

**Document Status:** Production-ready ✅
**Validation:** Tested with KR-VN (ROTMHS samples) and EN-VN (generic samples)
**Next Review:** After Week 7 Epic completion
