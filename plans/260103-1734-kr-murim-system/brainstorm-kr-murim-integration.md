# Brainstorm: Korean Murim Translation System

**Date:** 2026-01-03 17:34
**Objective:** Design separate KR_MURIM_TRANSLATOR.xml system parallel to JP-LN
**Reference Novel:** Return of the Mount Hua Sect (화산귀환)

---

## Phase 1: Research Findings

### Return of Mount Hua Sect Characteristics

**Genre:** Korean Murim (무림) - Martial World fiction
**Translation Context:** Korean→Vietnamese (KR-VN)
**Setting:** Chinese-inspired martial arts world (Gangho 강호)

**Key Differentiators from JP Light Novels:**

1. **Narrative Pacing**
   - **KR Murim:** Staccato, rapid-fire action sequences
   - **JP LN:** Emotional beats, relationship-focused, slower buildup
   - **Impact:** Sentence structure needs shorter, punchier fragments

2. **Power System**
   - **KR:** Internal energy (내공), cultivation stages (선천/후천), Qi flow descriptions
   - **JP:** Power levels abstract, focus on character abilities rather than energy
   - **Impact:** Need technical terminology for martial arts cultivation

3. **Faction Structure**
   - **KR:** Just Sects (정파) vs Evil Sects (사파), rigid hierarchy
   - **JP:** School clubs, guilds, flexible organizations
   - **Impact:** Different honorific systems and organizational terms

4. **Combat Style**
   - **KR:** Extended technical choreography, internal energy flow, martial arts forms
   - **JP:** Emotional stakes, brief action descriptions, focus on character reactions
   - **Impact:** Lexicon needs martial arts terminology, energy descriptions

---

## Phase 2: Gap Analysis - KR Murim vs JP Light Novel

### A. Terminology Systems

| Category | JP Light Novel | KR Murim | VN Translation Strategy |
|----------|----------------|----------|-------------------------|
| **World** | 異世界 (isekai) | 강호 (Gangho) | Giang hồ / Võ lâm |
| **Power** | スキル (skill) | 내공 (nae-gong) | Nội công |
| **Rank** | Sランク (S-rank) | 선천/후천 (realm) | Tiên thiên / Hậu thiên |
| **Factions** | ギルド (guild) | 파 (sect/faction) | Phái / Bang hội |
| **Hierarchy** | 先輩 (senpai) | 사형 (sahyeong) | Sư huynh |

### B. Honorific Systems

**JP System (Current):**
- Dialogue: Keep Japanese (-san, -senpai, -kun)
- Narration: Translate to Vietnamese (anh, chị, em)
- RTAS-driven pronoun selection

**KR System (Needed):**
- Within sect: 사형 (sahyeong) → Sư huynh, 사제 (saje) → Sư đệ
- Formal: 소협 (sohyeop) → Thiếu hiệp, 대협 (daehyeop) → Đại hiệp
- Master: 장문인 (jangmunin) → Chưởng môn
- **Critical:** Korean honorifics integrated into speech, not separate suffixes

### C. Romanization Differences

**JP Hepburn (Current):**
- おう → -ou (long vowel)
- えい → -ei
- Pattern: Preserve kana-to-romaji

**KR Revised Romanization (Needed):**
- 이무기 → Imugi (NOT Lee-mu-gi)
- 화산 → Hwasan (NOT Hwa-san)
- 청명 → Chung Myung (NOT Cheong-myeong)
- Pattern: Official Korean romanization rules

### D. Ruby Text vs Hanja

**JP Ruby (Current):**
- Kanji with furigana: 綿貫(わたぬき)
- Parse kanji individually, extract reading
- Clean output: "Watanuki"

**KR Hanja (Needed):**
- Rare: Korean novels rarely use Hanja annotations
- Pattern: 화산파(華山派) → usually written as 화산파 only
- Strategy: NO ruby parsing needed, but need Hanja-to-Hán Việt mapping
  - 華山派 → Hoa Sơn Phái
  - 매화검법 (梅花劍法) → Mai Hoa Kiếm Pháp

### E. Lexicon Priorities

**Must-Have Terminology (Top 100):**

**Martial Arts Terms:**
- 검법 (geombeop) → Kiếm pháp (sword technique)
- 장법 (jangbeop) → Chưởng pháp (palm technique)
- 권법 (gwonbeop) → Quyền pháp (fist technique)
- 경공 (gyeonggong) → Khinh công (lightness skill)
- 내공 (naegong) → Nội công (internal energy)
- 검기 (geomgi) → Kiếm khí (sword qi)
- 검강 (geomgang) → Kiếm cương (sword energy - stronger)

**Cultivation/Energy:**
- 단전 (danjeon) → Đan điền (energy center)
- 경맥 (gyeongmaeg) → Kinh mạch (meridians)
- 기혈 (gihyeol) → Khí huyết (qi and blood)
- 진기 (jingi) → Chân khí (genuine qi)
- 혈도 (hyeoldo) → Huyệt đạo (acupoints)

**Sect Structure:**
- 장문인 (jangmunin) → Chưởng môn (sect leader)
- 대제자 (daejeja) → Đại đệ tử (first disciple)
- 사숙 (sasuk) → Sư thúc (martial uncle)
- 사백 (sabaek) → Sư bá (senior martial uncle)

**Faction Alignment:**
- 정파 (jeongpa) → Chính phái (righteous sects)
- 사파 (sapa) → Tà phái (evil sects)
- 마교 (magyo) → Ma giáo (demonic cult)

**Combat Descriptions:**
- 초식 (chosik) → Chiêu thức (technique/move)
- 절기 (jeolgi) → Tuyệt kỹ (ultimate skill)
- 비급 (bigeub) → Bí cấp (secret manual)

---

## Phase 3: Architecture Design

### Proposed Structure: Separate Fork

**File:** `KR_MURIM_TRANSLATOR.xml`
**Size Target:** ~50KB (similar to JP-LN system)
**Platform:** Google Gemini Advanced (Gems)

### Core Sections (1000+ lines)

```xml
<SYSTEM_INSTRUCTION version="1.0" model="korean-murim" lang="kr-vn">

  <!-- SECTION 1: MURIM_LOCALIZATION (LOC) -->
  <MURIM_LOC lines="1-450">
    - GANGHO_ARCHETYPES: Character types (Sword Saint, Demon, Hidden Master, Young Master)
    - FACTION_SYSTEM: Jeongpa vs Sapa alignment scoring
    - RANK_LEVELS: Cultivation realm mapping (초식 → 절기 → 비급)
    - HONORIFICS_KR: Sect hierarchy (사형, 사숙, 장문인)
    - HANJA_ROMANIZATION: Korean name preservation (Chung Myung, Baek Cheon)
    - TECHNIQUE_NAMING: Martial arts term translation patterns
  </MURIM_LOC>

  <!-- SECTION 2: COMBAT_MODULE (COMBAT) -->
  <COMBAT lines="451-650">
    - ACTION_PACING: Staccato sentence shattering for fight scenes
    - QI_DESCRIPTION: Internal energy flow narration
    - CHOREOGRAPHY_DETAIL: Extended technical combat sequences
    - POWER_SCALING: Cultivation realm impact on language intensity
    - ENERGY_LEXICON: 내공, 검기, 검강 terminology
  </COMBAT>

  <!-- SECTION 3: FORMATTING_STANDARDS (FMT) -->
  <FMT lines="651-750">
    - PUNCT_KR: 「」→ "", ellipsis handling
    - TECHNIQUE_FORMAT: <Mai Hoa Kiếm Pháp> style markers
    - HANJA_DISPLAY: When to show Hanja (華山派 → Hoa Sơn Phái)
    - TL_NOTE: Martial arts term annotations
  </FMT>

  <!-- SECTION 4: ANTI_TRANSLATIONESE (GUARD) -->
  <GUARD lines="751-850">
    - Reuse from JP-LN system
    - Add KR-specific: Ban "đánh nhau" → use "giao chiến", "tỷ thí"
  </GUARD>

  <!-- SECTION 5: HANJA_PROTOCOL (REF) -->
  <HANJA_PROTOCOL lines="851-920">
    - Hanja-to-Hán Việt mapping triggers
    - When to romanize vs translate
    - Consistency lock for character names
  </HANJA_PROTOCOL>

  <!-- SECTION 6: IO_PROTOCOL -->
  <IO_PROTOCOL lines="921-970">
    - Dual-output: Chatbox (metadata) + Canvas (clean translation)
  </IO_PROTOCOL>

  <!-- SECTION 7: LEXICON (Embedded) -->
  <COMBAT_LEXICON lines="971-1150">
    - Vivid verbs for martial arts (weak → strong)
    - 검을 휘두르다 → vung kiếm (neutral) → chém giáng (vivid)
  </COMBAT_LEXICON>

</SYSTEM_INSTRUCTION>
```

### Reference Modules (External RAG)

**New KR-Specific Modules:**

| File | Size | Purpose |
|------|------|---------|
| Library_HANJA_MURIM_TERMS.md | ~500KB | 3000+ common Murim Hanja → Hán Việt |
| Library_ROTMHS_GLOSSARY.md | ~150KB | Return of Mount Hua Sect official terms |
| Library_MURIM_GOLDEN_SAMPLES.md | ~50KB | 15-20 S-tier KR-VN translation examples |
| Ref_KR_HONORIFIC_SYSTEM.md | ~30KB | Sect hierarchy + speech patterns |
| Ref_CULTIVATION_STAGES.md | ~25KB | Realm naming conventions |
| Ref_COMBAT_CHOREOGRAPHY.md | ~20KB | Extended fight scene patterns |
| Ref_HANJA_ROMANIZATION_KR.md | ~15KB | Korean name romanization rules |

**Reusable from JP-LN:**
- Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (with KR additions)
- Ref_FORMATTING_STANDARDS.md (adapted for KR punctuation)
- Ref_SAFETY_COMPLIANCE_MATRIX.md

---

## Phase 4: Reusable Components

### ✅ Direct Reuse (80% compatible)

1. **Anti-Translationese Guardrails**
   - Ban list: "một cách + adj", "của + pronoun", passive spam
   - Works identically for KR-VN translation

2. **Formatting Standards**
   - Double newline mandate
   - Punctuation normalization (with KR adaptations)

3. **Safety Compliance**
   - Content filtering matrix
   - Harm reduction protocols

4. **IO Protocol**
   - Dual-output (Chatbox + Canvas)
   - Markdown metadata structure

### 🔶 Needs Adaptation (50% compatible)

1. **RTAS System → FACTION_ALIGNMENT System**
   - **From:** Relationship Tension Score (1.0-5.0)
   - **To:** Jeongpa-Sapa Alignment Score (-5.0 to +5.0)
     - +5.0: Hardcore righteous (Shaolin, Wudang)
     - 0.0: Neutral / Pragmatic
     - -5.0: Demonic cult / Pure evil
   - **Triggers:** Different pronoun selection, combat language intensity

2. **Honorific System**
   - **From:** JP suffixes (-san, -senpai) in dialogue, VN in narration
   - **To:** KR integrated terms (사형 → sư huynh) in both dialogue + narration
   - **Logic:** Korean honorifics are part of the word, not suffix

3. **Romanization**
   - **From:** Hepburn (おう → -ou)
   - **To:** Revised Romanization (이 → I-, 어 → eo)
   - **New rules:** No long vowel markers, different consonant clusters

4. **Sensory Lexicon**
   - **From:** Romance-focused (blush, heart flutter, intimate)
   - **To:** Combat-focused (slash, pierce, qi surge, energy clash)
   - **Expansion:** 200+ martial arts verbs

### ❌ Not Applicable (0% compatible)

1. **JP Archetypes** (Ojou, Gyaru, Tsundere)
   - Replace with: Sword Saint, Hidden Master, Young Master, Demonic Cultivator

2. **Ruby Text Parsing**
   - KR rarely uses Hanja annotations
   - Replace with: Hanja-to-Hán Việt lookup table

3. **JP Cultural References**
   - Takarazuka, school system, onsen
   - Replace with: Chinese martial world (Shaolin, Wudang, Jianghu)

---

## Phase 5: Sample Transformation Pipeline

### Input (Korean Source - Return of Mount Hua Sect Ch.1 excerpt)

```korean
"청명아."
"예, 사형."
백천의 목소리에 청명이 고개를 들었다.
"이번 마교와의 전투, 조심해라. 검강을 다룰 수 있는 적이 많다."
"걱정 마십시오, 사형. 제 매화검법이면 충분합니다."
청명의 눈에 검기가 서렸다. 그의 내공은 이미 후천 경지에 이르렀다.
```

### Expected Output (Vietnamese Translation)

```vietnamese
"Thanh Minh."
"Vâng, sư huynh."
Thanh Minh ngẩng đầu khi nghe tiếng Bạch Thiên.
"Trận chiến với Ma Giáo lần này, phải cẩn thận. Kẻ địch có nhiều người có thể sử dụng Kiếm Cương."
"Sư huynh đừng lo. Với Mai Hoa Kiếm Pháp của em là đủ rồi."
Kiếm khí thoáng hiện trong mắt Thanh Minh. Nội công của hắn đã đạt đến cảnh giới Hậu Thiên.
```

### Translation Logic Breakdown

1. **Names:** 청명 → Thanh Minh (Hanja 清明), 백천 → Bạch Thiên (Hanja 白天)
2. **Honorifics:** 사형 → sư huynh (same-generation senior in sect)
3. **Factions:** 마교 → Ma Giáo (Demonic Cult)
4. **Techniques:** 검강 → Kiếm Cương (sword energy), 매화검법 → Mai Hoa Kiếm Pháp
5. **Energy:** 검기 → Kiếm khí (sword qi), 내공 → Nội công
6. **Realm:** 후천 → Hậu Thiên (post-heaven stage)

### Metadata (Chatbox Output)

```markdown
## Translation Metadata

**Faction Alignment:** Jeongpa +4.5 (Mount Hua Sect - righteous)
**Honorific Mode:** Sect hierarchy (사형 → sư huynh)
**Cultivation Realm:** Hậu Thiên (Thanh Minh)
**Techniques Applied:**
- Hanja romanization: 清明 → Thanh Minh
- Martial arts term lock: 매화검법 → Mai Hoa Kiếm Pháp (consistency)
- Combat lexicon: 검기가 서렸다 → "Kiếm khí thoáng hiện" (vivid)

**TL Notes:**
- [Kiếm Cương 劍罡]: Advanced sword energy, stronger than Kiếm Khí
- [Hậu Thiên 後天]: Cultivation realm above Tiên Thiên
```

---

## Phase 6: Implementation Roadmap

### Step 1: Lexicon Extraction (Week 1)
- [ ] Extract 3000+ Hanja terms from Return of Mount Hua Sect glossary
- [ ] Map to Hán Việt equivalents
- [ ] Build `Library_HANJA_MURIM_TERMS.md`

### Step 2: Architecture Foundation (Week 2)
- [ ] Create `KR_MURIM_TRANSLATOR.xml` base structure (7 sections)
- [ ] Implement FACTION_ALIGNMENT system (replace RTAS)
- [ ] Build Korean honorific logic

### Step 3: Combat Module (Week 3)
- [ ] Design COMBAT_LEXICON (200+ vivid verbs)
- [ ] Implement qi description templates
- [ ] Create extended choreography patterns

### Step 4: Reference Modules (Week 4)
- [ ] Write `Ref_KR_HONORIFIC_SYSTEM.md`
- [ ] Write `Ref_CULTIVATION_STAGES.md`
- [ ] Write `Ref_HANJA_ROMANIZATION_KR.md`

### Step 5: Golden Samples (Week 5)
- [ ] Translate 15-20 benchmark passages from Return of Mount Hua Sect
- [ ] Create `Library_MURIM_GOLDEN_SAMPLES.md`
- [ ] Validate translation quality

### Step 6: Testing & Refinement (Week 6)
- [ ] Test with 5 different KR Murim novels
- [ ] Collect edge cases
- [ ] Refine anti-translationese rules for KR-VN

---

## Critical Success Factors

### 1. Hanja-Hán Việt Accuracy
- **Challenge:** 3000+ terms need precise mapping
- **Solution:** Use Return of Mount Hua Sect official glossary as ground truth
- **Quality Gate:** 95%+ consistency with established translations

### 2. Combat Pacing Difference
- **Challenge:** KR action scenes 3x longer, more technical than JP
- **Solution:** Sentence shattering module + qi flow templates
- **Validation:** Fight scene A/B test vs human translator

### 3. Honorific Integration
- **Challenge:** KR honorifics embedded in speech, not suffixes
- **Solution:** Context-aware term substitution (사형 always → sư huynh in dialogue)
- **Edge Case:** Handle modern vs historical contexts

### 4. Romanization Consistency
- **Challenge:** Multiple romanization systems exist (RR vs McCune-Reischauer)
- **Solution:** Lock to Revised Romanization 2000 standard
- **Example:** 청 → Cheong (NOT Ch'ŏng or Chung unless character-specific)

---

## Unresolved Questions

1. **Gen Z Slang Applicability?**
   - JP-LN Boldness Module uses "vãi", "toang"
   - Does this fit Korean Murim (usually historical fantasy)?
   - **Proposal:** Create separate "Modern Murim" variant for contemporary settings

2. **Visual Proxemics?**
   - JP-LN uses image analysis for emotional peaks
   - KR Murim rarely has visual novels (mostly text)
   - **Proposal:** Deprecate for KR system, focus on text-only cues

3. **Faction Alignment Auto-Detection?**
   - How to score Jeongpa-Sapa alignment from text alone?
   - **Proposal:** Keyword triggers (정파, 사파, 마교) + manual override

4. **Translation Memory Integration?**
   - Should we maintain glossary lock across multiple novels?
   - **Proposal:** Per-novel consistency, cross-novel suggestions

5. **Bilingual Output Option?**
   - Some readers want Hanja displayed: "Mai Hoa Kiếm Pháp (梅花劍法)"
   - **Proposal:** Add toggle in IO_PROTOCOL

---

## ✅ Final Decisions (Confirmed 2026-01-03 17:48)

1. **Scope:** ✓ Generic KR Murim system + ROTMHS glossary module
   - Core system xử lý mọi Korean Murim novel
   - ROTMHS-specific terms trong `Library_ROTMHS_GLOSSARY.md`

2. **Gen Z Slang:** ✓ NO for historical fantasy, YES for Modern Murim variant
   - Historical Murim: Formal language only
   - Modern Murim (Solo Leveling, ORV): Separate variant với slang module

3. **Hanja Display:** ✓ Toggle option in IO_PROTOCOL
   - Default: "Mai Hoa Kiếm Pháp" (clean)
   - Optional: "Mai Hoa Kiếm Pháp (梅花劍法)" (bilingual)

4. **Testing Strategy:** ✓ Pure Murim first → Modern Dungeon later
   - Phase 1: Return of Mount Hua Sect, Legend of Northern Blade
   - Phase 2: Solo Leveling, Nano Machine, ORV

---

**STATUS:** Proceeding to Step 1: Lexicon Extraction 🚀
