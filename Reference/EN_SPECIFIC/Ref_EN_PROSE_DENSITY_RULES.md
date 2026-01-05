# English Prose Density Rules for Vietnamese Translation

**Version:** 1.1 (Refined from Week 5 Edge Cases)
**Target:** 60-70% word count reduction (minimum 50%, context-dependent)
**Context:** EN Murim novels are 2-3x more verbose than KR/CN sources
**Updated:** 2026-01-05 (ln-9bh.2: Added intensity preservation, context thresholds, semantic loss detection)

---

## 1. Overview

### The Problem

English translations of Murim novels tend to be significantly more verbose than their Korean or Chinese sources:

- **Korean/Chinese:** Concise, context-heavy, implicit subjects
- **English:** Explicit, redundant modifiers, verbose clause structures
- **Vietnamese:** Similar conciseness to Korean, benefits from compressed prose

### Translation Strategy

When translating EN → VN for Murim content, **aggressively condense** without losing meaning:

- **Target ratio:** 60-70% of original English word count
- **Minimum threshold:** 50% (for dialogue-heavy or action scenes)
- **Maximum threshold:** 80% (for poetic/emotional passages - see Exceptions)

---

## 2. Core Condensation Patterns

### Pattern 1: Remove Redundant Adjectives

**Rule:** English Murim prose over-uses stacked adjectives. Vietnamese prefers single, strong adjectives.

**Examples:**

1. **EN:** "He powerfully circulated his vast and mighty internal energy through his meridians."
   **VN:** "Hắn vận hành nội công hùng hậu qua kinh mạch."
   **Reduction:** 13 words → 7 từ (~46%)

2. **EN:** "The ancient and venerable master stroked his long white beard thoughtfully."
   **VN:** "Vị cao nhân vuốt râu trầm ngâm."
   **Reduction:** 11 words → 5 từ (~55%)

3. **EN:** "A fierce and overwhelming killing intent burst forth from his body."
   **VN:** "Sát khí dữ dội bùng phát từ thân hắn."
   **Reduction:** 12 words → 7 từ (~42%)

**Drop:** "powerfully", "vast and", "ancient and venerable" → keep strongest descriptor

---

### Pattern 2: Merge Subordinate Clauses

**Rule:** English uses complex clause structures. Vietnamese favors shorter, direct sentences or merged clauses.

**Examples:**

1. **EN:** "He channeled his qi through all twelve of his primary meridians, which were located throughout his body."
   **VN:** "Hắn vận khí qua thập nhị kinh mạch."
   **Reduction:** 17 words → 5 từ (~71%)

2. **EN:** "The sword technique that he had just used was one of the most profound skills of the Azure Cloud Sect."
   **VN:** "Chiêu kiếm vừa rồi là tuyệt kỹ của Thanh Vân Tông."
   **Reduction:** 20 words → 9 từ (~55%)

3. **EN:** "She stood at the edge of the cliff, which overlooked the vast valley below, and gazed into the distance."
   **VN:** "Nàng đứng bên vách núi nhìn ra thung lũng xa xôi."
   **Reduction:** 19 words → 9 từ (~53%)

**Drop:** Relative clauses ("which were", "that he had"), merge descriptions

---

### Pattern 3: Eliminate Filler Verbs

**Rule:** English uses "could feel/see/sense/notice" + main action. Vietnamese goes directly to the action or sensation.

**Examples:**

1. **EN:** "He could feel the energy surging powerfully through his body."
   **VN:** "Năng lượng dâng trào trong cơ thể."
   **Reduction:** 10 words → 5 từ (~50%)

2. **EN:** "She could sense that someone was approaching from behind."
   **VN:** "Có người đang tiếp cận từ phía sau."
   **Reduction:** 10 words → 6 từ (~40%)

3. **EN:** "He could clearly see that his opponent was growing weaker with each exchange."
   **VN:** "Đối thủ ngày càng yếu dần sau mỗi chiêu."
   **Reduction:** 13 words → 7 từ (~46%)

**Drop:** "could feel/sense/see", "clearly", subject often becomes implicit

---

### Pattern 4: Compress Prepositional Phrases

**Rule:** English uses verbose prepositional phrases. Vietnamese uses possessive markers or implicit context.

**Examples:**

1. **EN:** "The sword in his hand gleamed with a cold light."
   **VN:** "Thanh kiếm lóe ánh sáng lạnh lẽo."
   **Reduction:** 10 words → 5 từ (~50%)

2. **EN:** "The energy within his dantian began to circulate rapidly."
   **VN:** "Nội lực trong đan điền vận hành mau lẹ."
   **Reduction:** 10 words → 6 từ (~40%)

3. **EN:** "The disciples of the sect all bowed respectfully to the elder."
   **VN:** "Đệ tử cung kính hành lễ với trưởng lão."
   **Reduction:** 11 words → 6 từ (~45%)

**Drop:** "in his hand" (possession clear from context), "of the sect" when redundant

---

### Pattern 5: Condense Action Descriptions

**Rule:** English describes actions step-by-step. Vietnamese compresses multi-step actions into single phrases.

**Examples:**

1. **EN:** "He raised his hand and gathered his internal energy before striking out with his palm."
   **VN:** "Hắn tụ khí xuất chương."
   **Reduction:** 14 words → 4 từ (~71%)

2. **EN:** "She leaped into the air and twisted her body, slashing down with her sword in a graceful arc."
   **VN:** "Nàng bay lên xoay người chém kiếm."
   **Reduction:** 17 words → 5 từ (~71%)

3. **EN:** "He took a deep breath, steadied his mind, and then launched himself forward."
   **VN:** "Hắn ổn định tâm thần lao về phía trước."
   **Reduction:** 13 words → 7 từ (~46%)

**Drop:** Conjunctions ("and", "before"), merge sequential actions

---

### Pattern 6: Remove Intensifiers and Hedges

**Rule:** English overuses intensifiers (very, extremely, quite) and hedges (somewhat, rather, a bit). Vietnamese rarely needs them.

**Examples:**

1. **EN:** "His cultivation base was extremely powerful and far exceeded that of ordinary martial artists."
   **VN:** "Tu vi hắn mạnh mẽ vượt xa võ giả thường."
   **Reduction:** 14 words → 7 từ (~50%)

2. **EN:** "The technique was rather difficult to master, even for very talented disciples."
   **VN:** "Võ công khó luyện, kể cả với thiên tài."
   **Reduction:** 13 words → 7 từ (~46%)

3. **EN:** "She was quite beautiful, with features that were somewhat delicate."
   **VN:** "Nàng xinh đẹp với nét mặt thanh tú."
   **Reduction:** 11 words → 6 từ (~45%)

**Drop:** "extremely", "far", "rather", "quite", "somewhat", "even for very"

---

### Pattern 7: Simplify Dialogue Tags

**Rule:** English uses elaborate dialogue tags. Vietnamese uses simple "nói" or removes tag when speaker is clear.

**Examples:**

1. **EN:** "I will definitely defeat you," he declared with fierce determination in his voice.
   **VN:** "Ta nhất định sẽ đánh bại ngươi," hắn nói quyết tâm.
   **Reduction:** 12 words → 8 từ (~33%)

2. **EN:** "Please forgive this disciple's rudeness," she said apologetically as she bowed her head.
   **VN:** "Xin sư phụ tha tội cho đệ tử," nàng cúi đầu.
   **Reduction:** 13 words → 8 từ (~38%)

3. **EN:** The old master responded thoughtfully, stroking his beard, "That is a good question."
   **VN:** Cao nhân vuốt râu: "Câu hỏi hay."
   **Reduction:** 13 words → 5 từ (~62%)

**Drop:** "with fierce determination", "apologetically as she", elaborate actions → merge or remove

---

### Pattern 8: Compress Explanatory Clauses

**Rule:** English explains context that Vietnamese readers can infer from genre knowledge.

**Examples:**

1. **EN:** "He activated his movement technique, a high-level lightness skill that allowed him to move like the wind."
   **VN:** "Hắn thi triển khinh công tuyệt đỉnh."
   **Reduction:** 17 words → 5 từ (~71%)

2. **EN:** "The technique required circulating internal energy through specific meridian pathways in a precise sequence."
   **VN:** "Võ công yêu cầu vận khí qua kinh mạch theo trình tự chính xác."
   **Reduction:** 14 words → 10 từ (~29%)

3. **EN:** "The hall was filled with martial artists from various sects, all of whom had come to witness the tournament."
   **VN:** "Đại điện đầy võ lâm nhân sĩ đến xem đại hội."
   **Reduction:** 18 words → 8 từ (~56%)

**Drop:** Explanatory clauses ("that allowed him to", "all of whom had come"), genre-common knowledge

---

### Pattern 9: Eliminate Temporal Redundancy

**Rule:** English over-specifies time. Vietnamese uses context or minimal markers.

**Examples:**

1. **EN:** "After he finished cultivating for three hours, he finally opened his eyes."
   **VN:** "Tu luyện ba giờ xong, hắn mở mắt."
   **Reduction:** 12 words → 6 từ (~50%)

2. **EN:** "At that very moment, just as he was about to strike, he suddenly sensed danger."
   **VN:** "Lúc sắp ra đòn, hắn chợt cảm thấy nguy hiểm."
   **Reduction:** 15 words → 8 từ (~47%)

3. **EN:** "It had been a full month since he had last seen his master."
   **VN:** "Đã một tháng kể từ lần cuối gặp sư phụ."
   **Reduction:** 13 words → 8 từ (~38%)

**Drop:** "After...finished", "At that very moment", "just as", "suddenly", "It had been a full"

---

### Pattern 10: Condense Internal Monologue

**Rule:** English internal thoughts are often wordy. Vietnamese compresses to essential thought.

**Examples:**

1. **EN:** "He thought to himself, 'If I can just break through to the next realm, I'll finally be strong enough.'"
   **VN:** "Hắn nghĩ: 'Nếu đột phá được, ta sẽ đủ mạnh.'"
   **Reduction:** 18 words → 9 từ (~50%)

2. **EN:** "She wondered silently whether or not her training had been sufficient to face this challenge."
   **VN:** "Nàng tự hỏi liệu tu luyện đã đủ để đối mặt thử thách này."
   **Reduction:** 15 words → 11 từ (~27%)

3. **EN:** "He couldn't help but feel a growing sense of excitement as the battle drew nearer."
   **VN:** "Hắn càng ngày càng phấn khích khi trận chiến đến gần."
   **Reduction:** 15 words → 9 từ (~40%)

**Drop:** "He thought to himself", "wondered silently", "couldn't help but feel"

---

### Pattern 11: Remove Physical State Descriptions

**Rule:** English repeatedly describes physical reactions. Vietnamese implies or omits when obvious.

**Examples:**

1. **EN:** "His eyes widened in shock and his face turned pale as he witnessed the devastating attack."
   **VN:** "Hắn sửng sốt chứng kiến đòn tấn công hủy diệt."
   **Reduction:** 15 words → 7 từ (~53%)

2. **EN:** "She clenched her fists tightly and gritted her teeth in frustration."
   **VN:** "Nàng siết chặt nắm đấm bực bội."
   **Reduction:** 11 words → 5 từ (~55%)

3. **EN:** "A cold sweat broke out on his forehead as he realized the danger he was in."
   **VN:** "Mồ hôi lạnh rịn khi nhận ra nguy hiểm."
   **Reduction:** 15 words → 6 từ (~60%)

**Drop:** Redundant physical cues when emotion/state is already clear

---

### Pattern 12: Compress Combat Descriptions

**Rule:** English blow-by-blow descriptions. Vietnamese uses dynamic action verbs.

**Examples:**

1. **EN:** "He swung his sword in a wide arc, aiming for his opponent's head, but his opponent ducked and countered with a thrust."
   **VN:** "Hắn vung kiếm chém ngang, đối thủ né đâm ngược."
   **Reduction:** 21 words → 8 từ (~62%)

2. **EN:** "The two fighters exchanged dozens of rapid blows, their weapons clashing with tremendous force."
   **VN:** "Hai người trao đổi hàng chục chiêu, binh khí va chạm dữ dội."
   **Reduction:** 15 words → 11 từ (~27%)

3. **EN:** "She channeled her energy into her palm and released it in a powerful strike that sent her enemy flying backwards."
   **VN:** "Nàng tụ khí vào lòng bàn tay đánh văng kẻ địch."
   **Reduction:** 19 words → 9 từ (~53%)

**Drop:** Play-by-play details, merge into compressed action sequences

---

## 2A. Intensity Preservation Rules (Week 5 Refinement)

### **CRITICAL:** Don't Sacrifice Emotional/Combat Intensity for Brevity

**Problem from Week 4 Testing:**
```
EN: "vast, mighty, overwhelming power"
FAIL (70% condensation): "sức mạnh" (too bare, lost ALL intensity)
FIXED (65%): "sức mạnh hùng hậu áp đảo" (preserve cumulative effect)
```

### Rule 2A.1: Multi-Adjective Qualifiers

**When EN uses 3+ adjectives for cumulative effect → Keep 2-3 strongest in VN**

**✅ DO:**
```
EN (3 adj): "vast, mighty, and overwhelming power"
VN (2 adj): "sức mạnh hùng hậu áp đảo"

EN (4 adj): "incredibly powerful and absolutely devastating strike"
VN (2 adj): "đòn tấn công tuyệt mạnh hủy diệt"
```

**❌ DON'T:**
```
EN: "vast, mighty, overwhelming"
WRONG: "sức mạnh" (dropped ALL qualifiers)
WRONG: "sức mạnh mạnh mẽ" (kept only 1, lost cumulative intensity)
```

**Pattern:**
- 3+ English adjectives → 2-3 Vietnamese Hán Việt terms
- Merge similar: "vast + mighty" → "hùng hậu" (combined meaning)
- Keep most specific: "overwhelming" → "áp đảo" (strongest descriptor)

---

### Rule 2A.2: Unprecedented/Unique Qualifiers

**Preserve qualifiers that signal narrative milestones:**

**ALWAYS KEEP:**
```
"unprecedented" → "chưa từng thấy"
"never before seen" → "chưa hề thấy"
"for the first time" → "lần đầu tiên"
"unlike anything" → "chưa từng có"
```

**Example:**
```
EN: "His dantian filled with unprecedented energy."
KEEP: "Đan điền tràn đầy năng lượng chưa từng thấy."
NOT: "Đan điền đầy năng lượng." (lost milestone marker)
```

**Rationale:** "Unprecedented" marks power-up moments—critical to plot, cannot drop.

---

### Rule 2A.3: Emotional State Descriptors (Death/Farewell/Breakthrough Scenes)

**DO NOT condense emotional vocabulary:**

**Example from Week 4 FAIL:**
```
EN: "His heart heavy with regret and sorrow for all the words left unsaid."
FAIL (55%): "Lòng nặng." (lost "regret", "sorrow", "unsaid")
FIXED (70%): "Lòng nặng trĩu hối hận và bi thương về những lời chưa nói."
```

**Emotional Keywords → FULL Expression:**
```
"regret and sorrow" → "hối hận và bi thương" (both kept)
"joy and pride" → "vui mừng và tự hào"
"fear and desperation" → "sợ hãi và tuyệt vọng"
```

**Rule:** Emotional scenes = preserve 80-90% word count (see Section 2B.4).

---

## 2B. Context-Sensitive Condensation Thresholds (NEW)

### **Different Scene Types → Different Compression Targets**

**Problem:** Week 4 applied uniform 60% to all scenes → failed on combat staccato and poetry.

### 2B.1 Combat Scenes: 70-80% Word Count (Minimal Condensation)

**Detection Keywords:**
```
fought, struck, blade, blood, kill, dodge, parry, attack, defend, sword, palm
```

**Priority:** Preserve staccato rhythm, urgency

**✅ DO:**
- Keep short sentences separate (DON'T merge)
- Preserve action sequence clarity
- Use dynamic verbs

**❌ DON'T:**
- Merge staccato fragments
- Smooth over intentional choppiness

**Example from Week 4 FAIL:**
```
EN: "He struck. The enemy dodged. Too slow. Blood sprayed." (4 sentences)
FAIL: "Hắn chém nhưng địch né chậm, máu bắn tung." (merged → 1 sentence)
FIXED: "Hắn chém. Địch né. Chậm quá. Máu bắn tung." (4 sentences preserved)
```

**Threshold:** 70-80% word count (less condensation than dialogue/description)

---

### 2B.2 Dialogue Scenes: 60-70% Word Count (Moderate)

**Detection:**
```
Quotation marks, said, asked, replied, shouted, whispered
```

**Priority:** Natural conversation flow, character voice

**✅ DO:**
- Condense dialogue tags aggressively
- Keep honorifics/formality explicit
- Preserve character speech patterns

**❌ DON'T:**
- Over-condense emotional dialogue
- Flatten character personality

**Example:**
```
EN: "Senior Brother, please be very careful. There are many extremely powerful enemies."
CONDENSE TAGS: "sư huynh" tags → minimal
KEEP SPEECH: "Sư huynh, hãy cẩn thận. Có nhiều kẻ địch mạnh."
Result: 65% word count
```

**Threshold:** 60-70%

---

### 2B.3 Description Scenes: 50-60% Word Count (Aggressive)

**Detection:**
```
was, were, had, seemed, appeared, looked (state-of-being verbs)
```

**Priority:** Economy, visual clarity

**✅ DO:**
- Aggressively remove filler
- Merge redundant clauses
- Drop state-of-being verbs

**Example:**
```
EN: "The mountain was tall and imposing, with peaks that seemed to reach into the very heavens themselves." (17 words)
CONDENSE: "Núi cao chót vút, đỉnh nhấp trời." (6 từ = 53%)
```

**Threshold:** 50-60% (most aggressive)

---

### 2B.4 Poetry/Emotional Scenes: 80-90% Word Count (Preserve Prose)

**Detection Keywords:**
```
tears, sorrow, regret, memory, farewell, death, blood-soaked, witness, like snow, silent
```

**Priority:** Atmosphere, emotional impact

**Exception:** Quoted poetry → 90-100% (near-literal)

**Example from Edge Case 1.3:**
```
EN: "The plum blossoms fell like snow, each petal a silent witness to the blood-soaked battlefield where heroes once stood tall and proud."

PRESERVE (85%): "Mai rơi như tuyết, từng cánh hoa im lặng chứng kiến chiến trường đẫm máu nơi anh hùng từng đứng sừng sững."

NOT (60%): "Mai rơi như tuyết trên chiến trường đẫm máu." (lost all poetry)
```

**Threshold:** 80-90% (preserve metaphors, parallel structure, emotional vocab)

---

## 2C. Semantic Loss Detection (NEW)

### Critical Semantic Elements (NEVER Drop)

**Formula:**
```
Semantic Loss % = (Dropped Critical Elements / Total Critical Elements) × 100
Threshold: 0-5% = Safe | 5-10% = Caution | 10%+ = REJECT
```

### 2C.1 Negations (CRITICAL)

**MUST PRESERVE:** "not", "never", "no", "without"

**Impact:** Reverses meaning

**Example:**
```
EN: "He could not defeat the enemy."
MUST KEEP: "Hắn không thể đánh bại kẻ địch."
FAIL: "Hắn đánh bại kẻ địch." (opposite meaning!)
```

---

### 2C.2 Quantifiers (CRITICAL in Cultivation Context)

**MUST PRESERVE:** Specific numbers (12 meridians, 3 years, etc.)

**Example:**
```
EN: "twelve primary meridians"
KEEP: "thập nhị kinh mạch" (NOT "kinh mạch")

EN: "three years of cultivation"
KEEP: "tam niên tu luyện" (NOT "nhiều năm")
```

**Rationale:** Numbers mark cultivation milestones, cannot generalize.

---

### 2C.3 Technical Terms (CRITICAL)

**Glossary terms = LOCKED, no abbreviation**

**Example from Week 4 FAIL:**
```
EN: "Transformation Realm"
FAIL: "Hóa" (abbreviated)
FIXED: "Hóa Cảnh" (full term required)
```

**Rule:** All terms in `Library_GENERIC_MURIM_TERMS.md` → full Hán Việt, no shortcuts.

---

### 2C.4 Causality Markers

**PRESERVE:** "because", "therefore", "thus", "since"

**Impact:** Logical connections critical for comprehension

**Example:**
```
EN: "He couldn't attack because his energy was depleted."
KEEP: "Hắn không thể tấn công vì nội công cạn kiệt."
NOT: "Hắn không tấn công. Nội công cạn kiệt." (lost causation → ambiguous)
```

---

### 2C.5 Semantic Loss Calculation Example

```
EN: "He powerfully [ADV] circulated his vast [ADJ1] and mighty [ADJ2] internal energy [TERM] through all [FILLER] of his twelve [QUANT] primary [REDUNDANT] meridians [TERM]."

Critical Elements Count:
- Intensity: ADV + ADJ1-2 (3 elements)
- Terms: TERM x2 (2 elements)
- Quantifier: QUANT (1 element)
TOTAL: 6 critical elements

Condensation:
DROPPED: "all of his" (FILLER), "primary" (redundant)
KEPT: "powerfully" → implicit in "hùng hậu", "vast/mighty" → "hùng hậu" (merged), TERMs (full), QUANT

VN: "Nội công hùng hậu vận qua thập nhị kinh mạch."

Lost Elements: 0/6 = 0% semantic loss (SAFE ✅)
```

---

## 3. New Condensation Patterns from Edge Cases (Week 5)

### Pattern 13: Intensifier Cascades

**EN Pattern:** 3+ intensifiers for single concept

**Solution:** Merge to 2 strongest Hán Việt terms

**Examples:**
```
EN: "incredibly powerful, absolutely devastating, and utterly unstoppable"
VN: "tuyệt mạnh hủy diệt bất khả kháng" (3 terms max)

EN: "vast, mighty, overwhelming, tremendous power"
VN: "sức mạnh hùng hậu áp đảo" (merge 4 → 2)
```

**Rule:** Max 2-3 intensifiers in VN, even if EN has 5+

---

### Pattern 14: Gerund Phrase Reduction

**EN Pattern:** "by doing X" constructions

**Solution:** Convert to simple verb or drop

**Examples:**
```
EN: "by circulating his qi through his meridians"
VN: "vận khí qua kinh mạch" (gerund → simple verb)

EN: "through the use of his sword technique"
VN: "dùng kiếm pháp" (streamlined)

EN: "by means of activating his energy"
VN: "kích hoạt nội công" (drop "by means of")
```

**Reduction:** ~60%

---

### Pattern 15: Measurement Elaboration

**EN Pattern:** Excessive measurement qualifiers

**Solution:** Keep number + unit, drop modifiers

**Examples:**
```
EN: "approximately twelve primary meridians"
VN: "thập nhị kinh mạch" (drop "approximately", "primary")

EN: "exactly three full years of intense cultivation"
VN: "tam niên tu luyện" (drop "exactly", "full", "intense")

EN: "a total of ten complete circulation cycles"
VN: "thập chu thiên" (drop "total", "complete")
```

**Rule:** In cultivation context, numbers already signify importance. Don't over-qualify.

---

### Pattern 16: Mental State Verbs

**EN Pattern:** "he thought", "he felt", "he realized"

**Solution:** Often implicit in VN, can drop if obvious

**Examples:**
```
EN: "He felt the power surge through him."
VN: "Sức mạnh dâng qua cơ thể." ("felt" implicit)

EN: "He realized the enemy was stronger."
VN: "Kẻ địch mạnh hơn." (realization implicit in statement)

BUT KEEP if marking important character insight:
EN: "For the first time, he realized the true meaning of the Dao."
VN: "Lần đầu tiên, hắn ngộ ra chân ý của Đạo." (KEEP "ngộ ra" = enlightenment)
```

**Rule:** Drop routine mental verbs, KEEP breakthrough/enlightenment moments.

---

### Pattern 17: Parenthetical Clarifications (Pinyin Footnotes)

**EN Pattern:** Author footnotes, Pinyin glosses

**Solution:** Strip entirely (assume reader knows genre)

**Examples:**
```
EN: "He used Jianqi (Sword Qi) to attack."
VN: "Hắn dùng Kiếm khí tấn công." (drop Pinyin parenthetical)

EN: "The Dantian (energy center below the navel) was full."
VN: "Đan điền đầy." (drop explanation)

EN: "Neigong (internal energy cultivation) reached peak."
VN: "Nội công đạt đỉnh." (drop English gloss)
```

**Rule:** English novels explain Murim terms for Western readers. Vietnamese readers already know them—strip ALL parenthetical glosses.

---

## 3. Exception Cases: When NOT to Condense

### 3.1 Poetic/Philosophical Passages

**Preserve verbose prose** when the writing is intentionally lyrical or philosophical.

**Example:**

> **EN:** "The Dao is like water—it flows ceaselessly, adapting to every vessel, yet never losing its essential nature. To understand the Dao is to understand the rhythm of the universe itself."

**VN:** Should retain ~70-80% length to preserve contemplative tone:
> "Đạo như nước—trôi chảy không ngừng, thích nghi với mọi bình chứa, nhưng không bao giờ mất đi bản chất. Hiểu Đạo là hiểu nhịp điệu của vũ trụ."

### 3.2 Emotional Climax Scenes

**Retain more words** (60-75%) for pivotal emotional moments where pacing matters.

**Example:**

> **EN:** "Master! No! Please don't leave me! I... I haven't... I still have so much to learn from you!"

**VN:** Keep stutter/repetition for emotional impact:
> "Sư phụ! Không! Đừng bỏ đệ tử! Đệ tử... đệ tử vẫn... vẫn còn nhiều thứ phải học từ sư phụ!"

### 3.3 Technical Cultivation Instructions

**Preserve detail** when describing specific cultivation techniques (readers need clarity).

**Example:**

> **EN:** "First, gather the qi at your lower dantian. Then, circulate it through the Governing Vessel up to the Crown Point, hold it there for three breaths, and finally release it back down through the Conception Vessel."

**VN:** Retain ~65-70% for technical accuracy:
> "Đầu tiên, tụ khí tại hạ đan điền. Sau đó, vận khí qua Đốc mạch lên đến Bách Hội huyệt, giữ ba hơi thở, cuối cùng thả xuống qua Nhâm mạch."

---

## 4. Quality Gates

### 4.1 Word Count Metrics

**Automated checks:**

- **Ideal:** 60-70% of source word count
- **Acceptable:** 50-80%
- **Flag for review:** <50% (possible meaning loss) or >80% (insufficient condensation)

**Per-section targets:**

| Section Type | Target Reduction |
|--------------|------------------|
| Action/Combat | 60-70% |
| Dialogue | 50-60% (tags compress more than speech) |
| Description | 65-75% |
| Technical/Cultivation | 60-70% |
| Poetic/Emotional | 70-80% (retain more) |

### 4.2 Meaning Preservation Check

**Manual validation (spot-check 10% of passages):**

- [ ] All plot-critical information preserved
- [ ] Character relationships clear
- [ ] Technical details accurate
- [ ] Emotional tone maintained
- [ ] No ambiguity introduced

### 4.3 Readability Check

**Vietnamese should feel natural:**

- [ ] No awkward word order from over-condensation
- [ ] Proper subject/object clarity (even when implicit)
- [ ] Sentence rhythm flows smoothly
- [ ] Genre conventions followed (Murim terminology)

---

## 5. Implementation Workflow

### Step 1: Initial Translation (Literal)

Translate EN → VN without condensation (establish meaning baseline).

### Step 2: Apply Condensation Patterns

Work through 12 core patterns systematically:
1. Remove redundant adjectives
2. Merge clauses
3. Eliminate filler verbs
4. Compress prepositions
5. Condense actions
6. Remove intensifiers
7. Simplify dialogue tags
8. Compress explanations
9. Eliminate temporal redundancy
10. Condense internal monologue
11. Remove physical state descriptions
12. Compress combat descriptions

### Step 3: Check Exceptions

Review for poetic/emotional/technical passages → retain more words if needed.

### Step 4: Quality Gate Validation

- Run word count check (60-70% target)
- Spot-check meaning preservation (10% sample)
- Read aloud for naturalness

### Step 5: Final Polish

Adjust for rhythm and genre conventions.

---

## 6. Quick Reference Table

| Pattern | Before (EN) | After (VN) | Reduction |
|---------|-------------|------------|-----------|
| Redundant adjectives | "vast and mighty energy" | "nội công hùng hậu" | ~50% |
| Merged clauses | "through all twelve of his primary meridians" | "qua thập nhị kinh mạch" | ~70% |
| Filler verbs | "could feel the energy surging" | "năng lượng dâng trào" | ~50% |
| Prepositional phrases | "the sword in his hand" | "thanh kiếm" | ~50% |
| Action descriptions | "raised hand, gathered energy, struck with palm" | "tụ khí xuất chương" | ~70% |
| Intensifiers | "extremely powerful" | "mạnh mẽ" | ~50% |
| Dialogue tags | "he declared with fierce determination" | "hắn nói quyết tâm" | ~40% |
| Explanatory clauses | "technique that allowed him to move like wind" | "khinh công tuyệt đỉnh" | ~70% |
| Temporal redundancy | "At that very moment, just as he was about to" | "Lúc sắp" | ~60% |
| Internal monologue | "He thought to himself, 'If I can just...'" | "Hắn nghĩ: 'Nếu...'" | ~50% |
| Physical state | "eyes widened, face turned pale" | "sửng sốt" | ~60% |
| Combat | "swung sword wide arc, opponent ducked, countered thrust" | "vung kiếm chém ngang, đối thủ né đâm" | ~60% |

---

## 7. Common Pitfalls

### ❌ Over-Condensation

**Problem:** Losing critical information or creating ambiguity.

**Example:**
- **EN:** "He used the Azure Dragon technique that his master had taught him."
- **BAD VN:** "Hắn dùng Thanh Long." (Whose technique? When learned?)
- **GOOD VN:** "Hắn dùng Thanh Long kỹ mà sư phụ truyền."

### ❌ Under-Condensation

**Problem:** Retaining English verbosity.

**Example:**
- **EN:** "The energy surged powerfully through his meridians."
- **BAD VN:** "Năng lượng dâng trào một cách mạnh mẽ qua các kinh mạch của hắn."
- **GOOD VN:** "Năng lượng dâng trào qua kinh mạch."

### ❌ Incorrect Pattern Application

**Problem:** Using condensation on exception passages.

**Example (Emotional Scene):**
- **EN:** "Master... no... please... I... I can't..."
- **BAD VN:** "Sư phụ... không... đừng..." (Lost stuttering emotion)
- **GOOD VN:** "Sư phụ... không... xin... đệ tử... đệ tử không thể..."

---

## 8. Metrics Dashboard

Track performance per batch/chapter:

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Overall word count ratio | 60-70% | ___ | ✅/⚠️/❌ |
| Action scenes | 60-70% | ___ | ✅/⚠️/❌ |
| Dialogue | 50-60% | ___ | ✅/⚠️/❌ |
| Descriptions | 65-75% | ___ | ✅/⚠️/❌ |
| Meaning preservation (spot-check) | 100% | ___ | ✅/⚠️/❌ |
| Readability score (1-5) | ≥4 | ___ | ✅/⚠️/❌ |

---

**File size:** ~15.3KB
**Last updated:** 2026-01-04
**Related references:**
- `Ref_PINYIN_MAPPING_TABLE.md` (romanization)
- `Library_GENERIC_MURIM_TERMS.md` (terminology)
- `EN_MURIM_TRANSLATOR.xml` (implementation)

## 7A. Week 5 Failed Passage Tests

### Test 1: Emotional Over-Condensation (FAILED Week 4)

**EN Input:**
```
He looked at his fallen comrades, his heart heavy with regret and sorrow for all the words left unsaid and battles unfought.
```

**Week 4 Output (55% - FAIL):**
```vietnamese
Hắn nhìn đồng môn, lòng nặng.
```
**Issues:** Lost "fallen" (death), "regret and sorrow", "unsaid/unfought"

**Fixed with v1.1 (70% - PASS):**
```vietnamese
Hắn nhìn những đồng môn đã ngã, lòng nặng trĩu hối hận và bi thương về những lời chưa nói, những trận chưa đấu.
```
**Applied:** Rule 2A.3 (emotional descriptors), Section 2B.4 (80-90% threshold)

---

### Test 2: Combat Staccato Merged (FAILED Week 4)

**EN Input:** "He struck. The enemy dodged. Too slow. Blood sprayed." (4 sentences)

**Week 4 Output (FAIL):** "Hắn chém nhưng địch né chậm, máu bắn tung." (merged to 1)

**Fixed with v1.1 (PASS):** "Hắn chém. Địch né. Chậm quá. Máu bắn tung." (4 sentences)

**Applied:** Section 2B.1 (combat 70-80%), Quality Gate 4.4 (staccato integrity)

---

### Test 3: Technical Term Abbreviated (FAILED Week 4)

**EN:** "His internal energy reached the peak of the Transformation Realm."

**Week 4 (FAIL):** "Nội công đạt đỉnh Hóa." (abbreviated "Hóa Cảnh" → "Hóa")

**Fixed v1.1 (PASS):** "Nội công đạt đỉnh Hóa Cảnh."

**Applied:** Section 2C.3 (technical terms locked), Semantic loss detection

---

## 8A. Updated Metrics Dashboard (v1.1)

| Metric | Old Target | **NEW Target (v1.1)** | Status |
|--------|-----------|----------------------|--------|
| Combat scenes | 60-70% | **70-80%** | ✅/⚠️/❌ |
| Dialogue | 50-60% | **60-70%** | ✅/⚠️/❌ |
| Description | 65-75% | **50-60%** | ✅/⚠️/❌ |
| Poetry/Emotional | 70-80% | **80-90%** | ✅/⚠️/❌ |
| Semantic loss | N/A | **<5%** (CRITICAL) | ✅/⚠️/❌ |
| Intensity match | N/A | **>50%** (combat/emotional) | ✅/⚠️/❌ |
| Staccato integrity | N/A | **±1 sentence** (combat) | ✅/⚠️/❌ |

---

**Version:** 1.1 (Week 5 Refinement Complete)
**File size:** ~32KB (expanded from 15.3KB)
**Last updated:** 2026-01-05
**Issue:** ln-9bh.2
**Additions:** Intensity preservation rules, context-sensitive thresholds, semantic loss detection, 5+ new patterns (13-17), failed passage tests
