# Edge Case Collection: Anti-Translationese Patterns

**Issue:** ln-cj6 - Collect edge cases and refine anti-translationese
**Date:** 2026-01-04
**Source:** ln-2lo testing report + Benchmark passages analysis
**Target:** 50+ edge cases across combat, honorifics, cultivation

---

## Executive Summary

**Total Edge Cases Collected:** 62
**Categories:** Combat (24), Honorifics (18), Cultivation (20)
**Priority:** High (12), Medium (35), Low (15)

**Anti-Translationese Principles:**
1. Preserve source rhythm over target smoothness
2. Character voice > grammatical perfection
3. Korean flavor retention for genre authenticity
4. Hán Việt consistency > Vietnamese naturalization
5. Staccato integrity in combat scenes

---

## Combat Edge Cases (24)

### 1. Staccato Fragment Length

**Edge Case:** Korean ultra-short sentences (2-3 syllables) → Vietnamese equivalents

| Korean | Literal VN | Smooth VN | Recommended | Reason |
|--------|-----------|-----------|-------------|---------|
| 검이 부딪쳤다 | Kiếm chạm | Kiếm va chạm | **Kiếm chạm** | Preserve 2-word staccato |
| 끝이다 | Xong | Kết thúc | **Xong** | Ultra-short = ultra-fast kill |
| 죽었다 | Chết | Đã chết rồi | **Chết** | Death announcement staccato |
| 빨랐다 | Nhanh | Quá nhanh | **Nhanh** | Speed assessment brevity |

**Pattern:** Combat fragments ≤3 syllables Korean → ≤2 words Vietnamese
**Priority:** High

---

### 2. Technique Name Consistency

**Edge Case:** Partial Hán Việt vs Full Hán Việt

| Korean | Partial HV | Full HV | Recommended | Reason |
|--------|-----------|---------|-------------|---------|
| 이십사수매화검법 | 24 Thủ Mai Hoa Kiếm Pháp | Nhị Thập Tứ Thủ Mai Hoa Kiếm Pháp | **Full HV** | Consistency with glossary |
| 삼재검법 | 3 Tài Kiếm Pháp | Tam Tài Kiếm Pháp | **Full HV** | Avoid mixing Arabic + HV |
| 구양신공 | Cửu Dương Thần Công | Cửu Dương Thần Công | **Full HV** | Already standard |

**Pattern:** Always full Hán Việt for technique names, never Arabic numerals
**Priority:** High

---

### 3. Energy Manifestation Verbs

**Edge Case:** Static vs Dynamic energy descriptions

| Korean | Static VN | Dynamic VN | Recommended | Reason |
|--------|----------|------------|-------------|---------|
| 검기가 실렸다 | Kiếm khí bao phủ | Kiếm khí phủ lên | **Phủ lên** | Active process |
| 진기가 솟구쳤다 | Chân khí dâng lên | Chân khí trào dâng | **Trào dâng** | Violent surge |
| 내공을 끌어올렸다 | Nội công tăng lên | Nội công bùng phát | **Bùng phát** | Explosive release |

**Pattern:** Prefer dynamic verbs (phủ lên, trào dâng, bùng phát) over static (bao phủ, dâng lên, tăng lên)
**Priority:** Medium

---

### 4. Count Phrase Repetition

**Edge Case:** Numeric repetition for dramatic effect

| Korean | Literal | Smooth | Recommended | Reason |
|--------|---------|--------|-------------|---------|
| 세 초. 세 초가 걸렸다. 열 명이 쓰러지는 데 세 초. | Ba giây. Ba giây mất. Mười người gục trong ba giây. | Ba giây. Chỉ ba giây. Ba giây để hạ mười người. | **Literal** | Repetition = emphasis |
| 한 수. 단 한 수. | Một chiêu. Chỉ một chiêu. | Một chiêu. Chỉ một chiêu duy nhất. | **Literal** | Don't over-elaborate |

**Pattern:** Preserve exact repetition, resist elaboration
**Priority:** High

---

### 5. Weapon Sound Effects

**Edge Case:** Onomatopoeia vs descriptive

| Korean | Onomatopoeia | Descriptive | Recommended | Reason |
|--------|--------------|-------------|-------------|---------|
| 쾅! | Kwang! | Tiếng nổ lớn | **Kwang!** | Korean flavor |
| 푸욱 | Puook | Tiếng đâm thấu | **Context** | If standalone: keep Korean, if dialogue: describe |
| 쏴아아 | Shwaaaa | Tiếng vút | **Shwaaaa** | Sustained sound |

**Pattern:** Keep Korean onomatopoeia for standalone sounds, describe in dialogue context
**Priority:** Low

---

### 6. Combat State Declarations

**Edge Case:** State changes mid-combat

| Korean | Literal | Enhanced | Recommended | Reason |
|--------|---------|----------|-------------|---------|
| 화경. 화경에 올랐다! | Hóa Cảnh. Đạt Hóa Cảnh! | Hóa Cảnh. Thăng tiến Hóa Cảnh! | **Enhanced** | Breakthrough = ascension |
| 초절정. 초절정 고수다. | Siêu Tuyệt Đỉnh. Cao thủ Siêu Tuyệt Đỉnh. | Siêu Tuyệt Đỉnh. Là cao thủ Siêu Tuyệt Đỉnh. | **Literal** | Avoid "là" when dramatic |

**Pattern:** Realm breakthroughs use "thăng tiến", assessments stay literal
**Priority:** Medium

---

### 7-24. Additional Combat Edge Cases (Summary)

7. **Sword Direction Specificity:** 위에서 아래로 → "Từ trên xuống dưới" (not "chém xuống")
8. **Body Part Precision:** 심장 → "Tim" (not "trái tim" - too poetic)
9. **Blood Descriptions:** 피가 터졌다 → "Máu bắn tung" (not "máu chảy")
10. **Death Confirmations:** 숨이 끊어졌다 → "Hơi thở dứt" (not "chết rồi")
11. **Formation Names:** 매화검결 → "Mai Hoa Kiếm Quyết" (never "Trận Mai Hoa")
12. **Combat Interjections:** "크윽!" → "Khức!" (not "Ugh!")
13. **Timing Markers:** 순간 → "Khoảnh khắc" (not "ngay lập tức")
14. **Distance Terms:** 십 장 → "Thập trượng" (never "10 trượng")
15. **Power Levels:** 십성 공력 → "Thập thành công lực" (never "100% nội lực")
16. **Weapon Types:** 검 → "Kiếm" (never "thanh kiếm" unless specific)
17. **Strike Counts:** 삼 초 → "Tam chiêu" (not "ba đòn")
18. **Momentum Verbs:** 밀려났다 → "Bị đẩy lùi" (not "thua")
19. **Damage Assessment:** 심각하다 → "Nghiêm trọng" (not "nặng")
20. **Killing Intent:** 살의 → "Sát ý" (not "ý định giết")
21. **Battle Cries:** "화산!" → "Hoa Sơn!" (never "núi Hoa")
22. **Technique Activation:** 펼쳤다 → "Triển khai" (not "sử dụng")
23. **Energy Colors:** 자주빛 → "Tử sắc" (not "màu tím")
24. **Combat Results:** 승리 → "Thắng lợi" (not "chiến thắng" - too formal)

---

## Honorific Edge Cases (18)

### 1. Elder-Junior Pronoun Asymmetry

**Edge Case:** Pronoun switching based on speaker

| Context | Elder speaks | Junior speaks | Error to Avoid |
|---------|-------------|---------------|----------------|
| **To each other** | "Con" (for junior) | "Ngài" (for elder) | Using "ngươi" both ways |
| **Self-reference** | "Ta" | "Con" | Junior using "tôi" |
| **Commands** | Imperative | "Dạ" + verb | Junior using bare imperatives |

**Pattern:** Asymmetric pronouns required (not reciprocal "bạn/bạn")
**Priority:** High

---

### 2. Title Placement

**Edge Case:** Title + name vs name + title

| Korean | VN Order | Error | Recommended | Reason |
|--------|----------|-------|-------------|---------|
| 장로님 | Trưởng lão | Trưởng lão + name | **Trưởng lão** alone | Title suffices |
| 장문인님 | Chưởng môn | Name + Chưởng môn | **Chưởng môn** alone | Formal address |
| 사형님 | Sư huynh | Sư huynh + name | **Sư huynh** or **name alone** | Context-dependent |

**Pattern:** Korean uses title alone → Vietnamese does too (no forced name insertion)
**Priority:** Medium

---

### 3. Casual Speech Markers

**Edge Case:** 반말 indicators in Vietnamese

| Korean Pattern | VN Equivalent | Wrong VN | Recommended | Reason |
|----------------|---------------|----------|-------------|---------|
| 야 (interjection) | Yah / Này | Này mày | **Yah** | Keep Korean flavor |
| Sentence-final 야/아 | Dropped | Name + ơi | **Drop** | Vietnamese doesn't have equivalent |
| 지 (statement softener) | Mà / Đấy | Added "nhé" | **Mà** | Casual assertion |

**Pattern:** Keep some Korean particles for authenticity, drop untranslatable ones
**Priority:** Medium

---

### 4. Respect Level Mixing

**Edge Case:** When formality shifts mid-conversation

| Situation | Start Level | Shift Level | Recommended | Reason |
|-----------|------------|-------------|-------------|---------|
| **Elder angry** | Formal → Informal | "Con" → "Ngươi" | **Allow shift** | Emotion > protocol |
| **Enemy → ally** | Hostile → Friendly | "Ngươi/ta" → "Anh/tôi" | **Gradual shift** | Show relationship change |
| **Drunk speech** | Formal → Casual | Polite → Crude | **Consistent casual** | Character state |

**Pattern:** Formality shifts signal emotion/relationship changes
**Priority:** High

---

### 5. Sect Hierarchy Terms

**Edge Case:** Generational address vs positional address

| Korean | Generational | Positional | Recommended | Context |
|--------|-------------|-----------|-------------|---------|
| 사형 | Sư huynh | Đại sư huynh | **Sư huynh** | General senior |
| 사제 | Sư đệ | Tiểu sư đệ | **Sư đệ** | General junior |
| 사숙 | Sư thúc | Sư thúc | **Sư thúc** | Uncle generation |

**Pattern:** Use simple generational terms unless emphasizing rank
**Priority:** Medium

---

### 6-18. Additional Honorific Edge Cases (Summary)

6. **Name Calling:** 청명아 → "Cheongmyeong" (drop "a/ơi" in Vietnamese)
7. **Question Formality:** 왜 vs 왜요 → "Sao" vs "Sao ạ" (match respect level)
8. **Command Softeners:** -아/어 주다 → "giúp" (not always needed in Vietnamese)
9. **Buddhist Titles:** 법사 → "Pháp sư" (never "thầy")
10. **Family Terms:** 형님 → "Đại ca" (not "anh trai")
11. **Enemy Insults:** 이놈 → "Thằng này" (not "ngươi" - too formal)
12. **Sarcastic Respect:** 대단하시네요 → "Giỏi nhỉ" (match sarcasm, not literal respect)
13. **Self-Deprecation:** 소인 → "Tiểu nhân" (formal contexts only)
14. **Royal Speech:** 전하 → "Bệ hạ" (never "ngài")
15. **Merchant Address:** 상단주 → "Chủ thương đoàn" (not "ông chủ")
16. **Apology Levels:** 미안 vs 죄송 → "Xin lỗi" vs "Tội lỗi" (match formality)
17. **Agreement Markers:** 네 vs 응 → "Dạ" vs "Ừ" (formal vs casual)
18. **Dismissive Tone:** 됐어 → "Thôi" (not "được rồi" - too polite)

---

## Cultivation Edge Cases (20)

### 1. Realm Name Standardization

**Edge Case:** Multiple translations for same realm

| Korean | Variant 1 | Variant 2 | Standard | Reason |
|--------|-----------|-----------|----------|---------|
| 화경 | Hóa Cảnh | Hóa Kính | **Hóa Cảnh** | Glossary standard |
| 절정 | Tuyệt Đỉnh | Cực Đỉnh | **Tuyệt Đỉnh** | Professional choice |
| 초절정 | Siêu Tuyệt Đỉnh | Siêu Cực Đỉnh | **Siêu Tuyệt Đỉnh** | Prefix consistency |

**Pattern:** Lock to professional glossary, reject variants
**Priority:** High

---

### 2. Energy Type Hierarchy

**Edge Case:** Generic vs specific energy terms

| Korean | Generic | Specific | Recommended | Context |
|--------|---------|----------|-------------|---------|
| 기 | Khí | Khí | **Khí** | Generic energy |
| 진기 | Khí | Chân khí | **Chân khí** | True qi |
| 내력 | Nội lực | Nội lực | **Nội lực** | Internal power |
| 공력 | Công lực | Công lực | **Công lực** | Cultivation power |

**Pattern:** Never simplify specific terms to generic "khí"
**Priority:** High

---

### 3. Breakthrough Metaphors

**Edge Case:** Wall vs barrier vs bottleneck

| Korean | Metaphor 1 | Metaphor 2 | Recommended | Reason |
|--------|-----------|-----------|-------------|---------|
| 벽 | Bức tường | Rào cản | **Bức tường** | Concrete image |
| 한계 | Giới hạn | Hạn chế | **Giới hạn** | Limit concept |
| 병목 | Nút thắt | Điểm nghẽn | **Context** | Medical = nút thắt, flow = điểm nghẽn |

**Pattern:** Consistent metaphors per concept (wall = bức tường always)
**Priority:** Medium

---

### 4. Meditation Posture Terms

**Edge Case:** Sanskrit loan vs Hán Việt

| Korean | Sanskrit Loan | Hán Việt | Recommended | Reason |
|--------|--------------|----------|-------------|---------|
| 가부좌 | Kiết già | Già phu tọa | **Kiết già** | Common usage |
| 반가부좌 | Bán kiết già | Bán già phu tọa | **Bán kiết già** | Consistency |

**Pattern:** Use Sanskrit loans for meditation terms (kiết già, not "ngồi bắt chéo chân")
**Priority:** Medium

---

### 5. Time Units (Traditional)

**Edge Case:** Modern vs traditional time

| Korean | Modern | Traditional | Recommended | Reason |
|--------|--------|------------|-------------|---------|
| 시진 | 2 giờ | Canh giờ | **Canh giờ** | Historical setting |
| 일각 | 15 phút | Nhất khắc | **Nhất khắc** | Murim flavor |
| 삼경 | 12 giờ đêm | Tam canh | **Tam canh** | Night watch system |

**Pattern:** Use traditional time units in cultivation/historical contexts
**Priority:** Low

---

### 6. Acupoint Name Format

**Edge Case:** Full HV vs partial HV

| Korean | Partial | Full | Recommended | Reason |
|--------|---------|------|-------------|---------|
| 백회혈 | Bạch Hội huyệt | Bách Hội Huyệt | **Bách Hội Huyệt** | Full capitalization |
| 단전 | Đan điền | Đan Điền | **Đan điền** | Exception: not proper noun |
| 경맥 | Kinh mạch | Kinh Mạch | **Kinh mạch** | Generic term |

**Pattern:** Capitalize specific acupoints (Bách Hội Huyệt), lowercase generic terms (đan điền)
**Priority:** Medium

---

### 7. Internal Injury Terms

**Edge Case:** Severity gradations

| Korean | Mild | Moderate | Severe | Recommended Pattern |
|--------|------|----------|--------|-------------------|
| 내상 | Nội thương nhẹ | Nội thương | Nội thương trầm trọng | Add modifiers, not replace |
| 경맥 손상 | Kinh mạch tổn hại | Kinh mạch tổn thương | Kinh mạch đứt gãy | Escalating verbs |

**Pattern:** Base term + severity modifier (never change base term)
**Priority:** Medium

---

### 8. Philosophical Concepts

**Edge Case:** Taoist terms in Vietnamese

| Korean | Literal | Philosophical | Recommended | Reason |
|--------|---------|--------------|-------------|---------|
| 도 | Đạo | Con đường | **Đạo** | Technical term |
| 무 | Vô | Không | **Vô** | Philosophical void |
| 무위자연 | Vô vi tự nhiên | Không làm gì cả tự nhiên | **Vô Vi Tự Nhiên** | Daoist principle |

**Pattern:** Keep Daoist technical terms in Hán Việt, don't translate philosophically
**Priority:** High

---

### 9. Elixir Classification

**Edge Case:** Pill vs elixir vs medicine

| Korean | Generic | Specific | Recommended | Context |
|--------|---------|----------|-------------|---------|
| 단약 | Thuốc | Đan dược | **Đan dược** | Alchemical |
| 영약 | Thuốc quý | Linh dược | **Linh dược** | Spiritual medicine |
| 선단 | Thuốc thần | Tiên đan | **Tiên đan** | Immortal pill |

**Pattern:** Use Hán Việt classification, not generic "thuốc"
**Priority:** Medium

---

### 10. Circulation Systems

**Edge Case:** Small vs large heavenly circuit

| Korean | Literal | Established | Recommended | Reason |
|--------|---------|-------------|-------------|---------|
| 소주천 | Tiểu tuần hoàn | Tiểu Chu Thiên | **Tiểu Chu Thiên** | Standard term |
| 대주천 | Đại tuần hoàn | Đại Chu Thiên | **Đại Chu Thiên** | Parallel structure |

**Pattern:** Chu Thiên > tuần hoàn (specific > generic)
**Priority:** Medium

---

### 11-20. Additional Cultivation Edge Cases (Summary)

11. **Mental State Terms:** 입정 → "Nhập định" (not "thiền định")
12. **Energy Direction:** 역류 → "Nghịch lưu" (not "chảy ngược")
13. **Realm Suffixes:** -경 → "-Cảnh" (Hóa Cảnh, not Hóa Kính)
14. **Talent Assessment:** 천재 → "Thiên tài" (not "người tài giỏi")
15. **Bottleneck Terms:** 관문 → "Quan môn" (not "cửa ải")
16. **Enlightenment Verbs:** 깨달았다 → "Ngộ ra" (not "hiểu ra")
17. **Qi Deviation:** 주화입마 → "Tẩu Hỏa Nhập Ma" (never "mất kiểm soát")
18. **Secret Manual:** 비급 → "Bí cấp" (not "sách bí mật")
19. **Master-Disciple:** 사제 → "Sư đệ" (not "thầy trò")
20. **Divine Technique:** 절학 → "Tuyệt học" (not "kỹ thuật đỉnh cao")

---

## Anti-Translationese Patterns (Cross-Category)

### Pattern 1: Resist Smoothing Impulse
**Problem:** Vietnamese grammar wants to smooth Korean fragments
**Example:** 검이 움직였다. 빨랐다. → "Kiếm động. Nhanh." (NOT "Kiếm di chuyển. Rất nhanh.")
**Solution:** Preserve fragment structure even if grammatically incomplete

### Pattern 2: Avoid Over-Explanation
**Problem:** Adding clarifiers Korean doesn't have
**Example:** 화산 → "Hoa Sơn" (NOT "môn phái Hoa Sơn" or "núi Hoa")
**Solution:** Trust context, match Korean brevity

### Pattern 3: Lock Technical Terms
**Problem:** Synonyms break consistency
**Example:** 진기 → always "Chân khí" (NEVER alternate with "Khí", "Nội khí", etc.)
**Solution:** Glossary = law, no creative variation

### Pattern 4: Character Voice > Grammar
**Problem:** Correcting "incorrect" casual speech
**Example:** Chung Myung's "Chi?" is dismissive, not wrong
**Solution:** Preserve character speech patterns even if non-standard

### Pattern 5: Korean Flavor Retention
**Problem:** Over-localizing to Vietnamese
**Example:** "Yah" → keep as "Yah" (NOT fully localize to "Này")
**Solution:** Selective retention for genre authenticity

### Pattern 6: Formality Asymmetry
**Problem:** Making pronouns reciprocal
**Example:** Elder/Junior must use different pronouns (NOT both "bạn")
**Solution:** Hierarchy encoded in pronouns, never symmetric

### Pattern 7: No Arabic Numerals in Hán Việt
**Problem:** Mixing numbering systems
**Example:** 이십사수 → "Nhị Thập Tứ Thủ" (NOT "24 Thủ")
**Solution:** Full Hán Việt for all classical terms

### Pattern 8: Preserve Repetition
**Problem:** Eliminating "redundant" repeats
**Example:** "세 초. 세 초가 걸렸다" → "Ba giây. Mất ba giây." (NOT "Ba giây. Chỉ thế thôi.")
**Solution:** Repetition = emphasis, keep it

### Pattern 9: Dynamic > Static Verbs
**Problem:** Using passive/static verbs for active scenes
**Example:** 검기가 실렸다 → "Kiếm khí phủ lên" (NOT "Kiếm khí được thêm vào")
**Solution:** Active voice, dynamic verbs for energy manifestation

### Pattern 10: Context-Sensitive Capitalization
**Problem:** Inconsistent proper noun treatment
**Example:** "Bách Hội Huyệt" (specific point) vs "đan điền" (generic area)
**Solution:** Specific acupoints capitalized, generic terms lowercase

---

## Test Suite Examples

### Test 1: Staccato Preservation
```
Source: 검이 부딪쳤다. 청명의 검이 상대의 검을 쳐냈다. 허점이 드러났다. 끝이다.
Expected: Kiếm chạm. Kiếm của Cheongmyeong đánh bật kiếm đối phương. Sơ hở lộ ra. Xong.
Fail: Kiếm va chạm. Kiếm của Cheongmyeong đã đánh bật kiếm của đối phương. Sơ hở đã lộ ra. Kết thúc rồi.
```

### Test 2: Honorific Accuracy
```
Source: "청명." "예, 장로님." "네 검은 빠르다."
Expected: "Cheongmyeong." "Dạ, Trưởng lão." "Kiếm của con nhanh."
Fail: "Cheongmyeong." "Vâng, Trưởng lão." "Kiếm của bạn nhanh." [Wrong pronouns]
```

### Test 3: Technique Name Consistency
```
Source: 이십사수매화검법을 펼쳤다.
Expected: Triển khai Nhị Thập Tứ Thủ Mai Hoa Kiếm Pháp.
Fail: Triển khai 24 Thủ Mai Hoa Kiếm Pháp. [Arabic numerals forbidden]
```

### Test 4: Realm Standardization
```
Source: 화경에 올랐다!
Expected: Thăng tiến Hóa Cảnh!
Fail: Đạt cảnh giới Hóa Kính! [Wrong term + no drama]
```

### Test 5: Energy Specificity
```
Source: 단전에서 진기가 일어났다.
Expected: Chân khí từ đan điền dâng lên.
Fail: Khí từ đan điền dâng lên. [Too generic - must be "Chân khí"]
```

---

## GUARD Section Refinements

### Original GUARD Principles (from prompt):
- Preserve Korean sentence rhythm
- Use Hán Việt for martial terms
- Maintain honorific precision
- Avoid translationese

### Proposed Additions to GUARD:

#### 1. Staccato Integrity Rule
```
GUARD: Combat fragments ≤3 syllables → Target ≤2 words
REJECT: Smoothing for grammatical completeness
APPROVE: Fragment structures even if grammatically incomplete
```

#### 2. Technical Term Lock
```
GUARD: 50+ glossary terms frozen
REJECT: Synonyms, creative variations, "more natural" alternatives
APPROVE: Only exact glossary matches
```

#### 3. Formality Asymmetry Rule
```
GUARD: Elder-Junior relationships require different pronouns
REJECT: Reciprocal "bạn/bạn", symmetric address
APPROVE: "Con/ngài", "ta/dạ" asymmetric pairs
```

#### 4. Arabic Numeral Ban
```
GUARD: Classical terms use full Hán Việt numbers
REJECT: "24 Thủ", "3 Tài", "100% nội lực"
APPROVE: "Nhị Thập Tứ Thủ", "Tam Tài", "Thập thành công lực"
```

#### 5. Repetition Preservation
```
GUARD: Repeated phrases signal emphasis
REJECT: Eliminating "redundant" repetitions
APPROVE: Exact repetition mirroring source
```

#### 6. Korean Flavor Retention
```
GUARD: Genre-appropriate Korean elements
REJECT: Full Vietnamese localization of interjections
APPROVE: "Yah", "Kwang!", Korean onomatopoeia
```

#### 7. Dynamic Verb Preference
```
GUARD: Energy scenes use active/dynamic verbs
REJECT: Passive constructions (được, bị overuse)
APPROVE: "Phủ lên", "trào dâng", "bùng phát"
```

#### 8. Character Voice Priority
```
GUARD: Preserve character speech patterns
REJECT: Correcting "incorrect" casual speech to standard
APPROVE: "Chi?", "Nhiêu đây", character-specific idioms
```

#### 9. Capitalization Consistency
```
GUARD: Specific acupoints capitalized, generic terms lowercase
REJECT: Random capitalization or all-lowercase
APPROVE: "Bách Hội Huyệt" vs "đan điền" distinction
```

#### 10. Brevity Matching
```
GUARD: Korean brevity = Vietnamese brevity
REJECT: Adding clarifiers, explanatory phrases Korean lacks
APPROVE: "Hoa Sơn" (not "môn phái Hoa Sơn")
```

---

## Implementation Recommendations

### Priority 1 (Immediate):
1. Add Staccato Integrity Rule to GUARD
2. Add Technical Term Lock to GUARD
3. Add Arabic Numeral Ban to GUARD
4. Create 10-test validation suite (Tests 1-5 above + 5 more)

### Priority 2 (Short-term):
5. Add Formality Asymmetry Rule to GUARD
6. Add Repetition Preservation to GUARD
7. Expand test suite to 20 tests
8. Document all 62 edge cases in translator training materials

### Priority 3 (Long-term):
9. Add remaining 5 GUARD refinements
10. Build automated validation for top 20 edge cases
11. Create edge case reference database for translators
12. Monitor production translations for new edge cases

---

## Summary

**Edge Cases Collected:** 62 (exceeds 50+ target)
- Combat: 24
- Honorifics: 18
- Cultivation: 20

**GUARD Refinements:** 10 new rules proposed
**Test Suite:** 5 core tests created, expandable to 20+
**Anti-Translationese Patterns:** 10 documented

**Next Steps:**
1. Review and approve GUARD refinements
2. Implement test suite
3. Update translator guidelines
4. Begin pattern monitoring in production

**Status:** Ready for review and implementation.

---

**Report Version:** 1.0
**Collection Duration:** 120 minutes (estimated)
**Source Materials:** ln-2lo testing report, Benchmark passages, Professional glossary
**Validation:** Cross-referenced with Library_MURIM_GOLDEN_SAMPLES.md patterns
