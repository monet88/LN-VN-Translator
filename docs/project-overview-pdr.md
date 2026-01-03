# Project Overview & PDR (Product Development Requirements)

## 1. Tổng quan Dự án

### 1.1 Định vị

**LN VN-Translator** là hệ thống Prompt Engineering chuyên dụng để dịch Light Novel Nhật→Việt chất lượng cao, được tối ưu hóa cho Google Gemini với context window 1M+ tokens.

**Mục tiêu cốt lõi:** Tạo ra bản dịch Light Novel đạt chất lượng "professional transcreation" thay vì "machine translation", với khả năng:
- Duy trì tính cách nhân vật nhất quán xuyên suốt tập truyện dài
- Xử lý văn phong Otaku đặc thù (Chuunibyou, Tsundere, Yandere...)
- Loại bỏ văn phong "dịch máy" (translationese)
- Điều chỉnh độ táo bạo/ngôn ngữ theo cảm xúc ngữ cảnh

### 1.2 Tại sao chọn Gemini?

1. **1M+ Token Context Window:** Duy trì nhất quán về xưng hô, tính cách, thuật ngữ xuyên suốt Volume mà không bị amnesia
2. **Complex Instruction Following:** Xử lý kiến trúc XML đa lớp với logic điều kiện (If-Then) phức tạp
3. **RAG Stability:** Tra cứu Knowledge Base 12,559 Kanji mà không hallucination
4. **Native LN Understanding:** Được huấn luyện trên Syosetsu/Kakuyomu, hiểu sâu tropes và văn phong Otaku (Zero-shot)

### 1.3 Target Users

**Primary:**
- Dịch giả Light Novel chuyên nghiệp (tăng tốc workflow)
- Fan translator muốn nâng cao chất lượng
- Nhóm dịch cần consistency checker

**Secondary:**
- Độc giả muốn dịch truyện chưa có bản Việt
- Publisher cần prototype nhanh

---

## 2. Functional Requirements

### 2.1 Core Translation Features

#### FR-001: RTAS-Based Pronoun Selection
**Mô tả:** Hệ thống tự động tính toán RTAS (Relationship Tension & Affection Score) từ 1.0-5.0 để chọn cặp đại từ phù hợp.

**Input:** Câu thoại Nhật có đại từ/kính ngữ/trợ từ cuối câu
**Output:** Cặp đại từ Việt (Tớ-Cậu, Em-Anh, Tao-Mày...)
**Logic:**
```
RTAS = 3.0 (baseline) + Σ(Modifiers)
Modifiers: Pronoun JP (+0.3~+0.7), Honorifics (-0.8~+0.5),
           Sentence Ending (+0.2~+0.4), Context Keywords (-2.0~+1.5),
           Proxemics (-0.5~+1.2)
```

**Acceptance Criteria:**
- [ ] RTAS 2.0-3.5 → Tớ-Cậu (bạn bè)
- [ ] RTAS 4.2-5.0 → Em-Anh (tình cảm)
- [ ] Family context → Override thành Anh/Chị/Em/Ba/Mẹ
- [ ] Yandere Paradox (殺す + 好き) → RTAS = 5.0

#### FR-002: Boldness Module
**Mô tả:** Khi RTAS ≥ 4.8 hoặc ≤ 1.2, kích hoạt các kỹ thuật "táo bạo" để tăng cường cảm xúc.

**Techniques:**
1. **Sentence Shattering:** Bẻ gãy câu dài thành đoạn ngắn
   ```
   Before: "Tớ thích cậu từ lâu rồi"
   After:  "Tớ thích cậu.\nTừ lâu rồi... tớ đã thích cậu."
   ```

2. **Vivid Verb Replacement:** Thay động từ yếu bằng từ mạnh
   ```
   表示された → "hiện số" (thay vì "được hiển thị")
   ```

3. **Slang Injection:** Chèn lóng Gen Z theo cấp độ (1-5)
   ```
   Cấp 1: "nha", "nè"
   Cấp 3: "toang", "die"
   Cấp 5: "cày", "flex"
   ```

**Acceptance Criteria:**
- [ ] Level 1-2: Safe cho publisher
- [ ] Level 3-5: Web novel style
- [ ] Không inject slang khi RTAS 2.5-4.0 (neutral zone)

#### FR-003: Hybrid Honorifics System
**Mô tả:** Xử lý kính ngữ Nhật theo ngữ cảnh.

**Rules:**
- **Trong hội thoại:** Giữ nguyên JP (`Senpai`, `Sensei`, `-san`)
- **Trong trần thuật:** Dùng VN (`Tiền bối`, `Thầy`, `Anh/Chị`)
- **Family terms:** LUÔN dùng VN (`Anh/Chị/Em/Ba/Mẹ`)

**Acceptance Criteria:**
- [ ] "田中さんが言った" → "Tanaka-san nói"
- [ ] "先輩は優しい人だ" (narration) → "Tiền bối là người tốt bụng"
- [ ] "お姉ちゃん!" (dialogue) → "Chị ơi!"

#### FR-004: Anti-Translationese Guardrails
**Mô tả:** Loại bỏ các cấu trúc "dịch máy".

**Banned Patterns:**
- ❌ "Một cách [adv]" → ✅ [Vivid verb]
- ❌ "Có vẻ như..." → ✅ Direct statement
- ❌ "[Noun] của [pronoun]" → ✅ "[Pronoun]... [noun] [verb]"

**Acceptance Criteria:**
- [ ] Pass 90% anti-translationese test cases
- [ ] Zero "một cách" in final output

#### FR-005: Ruby Text Parsing (Furigana)
**Mô tả:** Xử lý furigana (振り仮名) với 3 chiến lược.

**Strategies:**
1. **Semantic Override:** `魔法<マホウ>` → "Ma pháp" (giữ nghĩa Hán)
2. **Sound Clash:** `愛<アイ>` vs `愛<ラブ>` → Detect và chọn âm phù hợp
3. **Chuunibyou Names:** `聖剣<エクスカリバー>` → "Thánh kiếm Excalibur"

**Acceptance Criteria:**
- [ ] Semantic override cho 95% Kanji thông dụng
- [ ] Sound clash detection accuracy ≥ 90%

---

### 2.2 Output Features

#### FR-006: Dual-Output Protocol
**Mô tả:** Xuất 2 luồng thông tin song song.

**Chatbox (Metadata):**
```
[RTAS: 4.9 | Cặp đại từ: Tớ-Cậu]
[Kỹ thuật: Sentence Shattering, Vivid Verb]
[Lý do: お前 (+0.7) + 好き (+1.0) + だ (+0.2) = 4.9]
```

**Canvas (Translation):**
```
Tớ thích cậu.
Từ lâu rồi... tớ đã thích cậu.
```

**Acceptance Criteria:**
- [ ] Chatbox xuất trong <thinking> tag
- [ ] Canvas xuất clean translation (no metadata)

---

## 3. Non-Functional Requirements

### 3.1 Performance

**NFR-001: Token Efficiency**
- Core logic ≤ 50KB (hiện tại: 48KB XML)
- Total context usage ≤ 1.5M tokens (including Knowledge Base)

**NFR-002: Response Time**
- Average response time ≤ 15 seconds/đoạn (50-100 chữ)

### 3.2 Quality

**NFR-003: Translation Accuracy**
- Human eval score ≥ 8/10 (professional translator rating)
- Consistency score ≥ 9/10 (across full chapter)

**NFR-004: Safety Compliance**
- NSFW detection accuracy ≥ 95%
- Auto-flag content ≥ Level 4 (sexual/violent)

### 3.3 Maintainability

**NFR-005: Modularity**
- Tách biệt Logic (XML) và Data (Knowledge Base .md files)
- Mỗi module có responsibility rõ ràng

**NFR-006: Documentation**
- 100% modules có inline XML comments
- User guide cho mỗi feature

---

## 4. System Architecture Requirements

### 4.1 Brain-Book Hybrid Model

**Brain (RAM):**
- `VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml` (48KB)
- Chứa: RTAS logic, Boldness Module, Anti-Translationese rules
- Load vào System Instruction của Gemini

**Book (HDD):**
- `Library_KANJI_KNOWLEDGE_BASE.md` (2.4MB, 12,559 entries)
- `Library_GOLDEN_SAMPLES.md` (19 S-Tier examples)
- `Ref_SENSORY_LEXICON.md` (200+ vivid verbs)
- Tra cứu on-demand via RAG

### 4.2 Module Dependencies

```
VN_TRANSLATOR_MASTER_INSTRUCTION_MINIFIED.xml (Core)
  ├── Integrated Modules (Self-contained in XML)
  │   ├── RTAS Calculation v2.0
  │   ├── Boldness Module v1.0
  │   ├── Ruby Text Parsing v2.0
  │   ├── Romanization v2.0
  │   └── Conflict Resolution
  │
  └── Reference Modules (External .md, loaded via Knowledge Base)
      ├── Library_KANJI_KNOWLEDGE_BASE.md (Essential)
      ├── Library_GOLDEN_SAMPLES.md (Essential)
      ├── Ref_VIETNAMESE_PRONOUN_SYSTEM.md (Lookup)
      ├── Ref_SENSORY_LEXICON.md (Lookup)
      └── Ref_ANTI_TRANSLATIONESE_GUARDRAILS.md (Lookup)
```

---

## 5. Feature Roadmap

### Phase 1: Core Translation (✅ Completed - v10.0)
- [x] RTAS v2.0 with conflict resolution
- [x] Boldness Module v1.0
- [x] Hybrid Honorifics
- [x] Anti-Translationese Guardrails
- [x] Dual-Output Protocol

### Phase 2: Advanced Features (🚧 In Progress)
- [ ] Genre-specific presets (Isekai, Romance, Action)
- [ ] Character archetype auto-detection
- [ ] Multi-speaker dialogue auto-tagging

### Phase 3: Tooling & Integration (📋 Planned)
- [ ] CLI tool for batch translation
- [ ] VS Code extension
- [ ] API wrapper for SaaS deployment

### Phase 4: Quality Assurance (📋 Planned)
- [ ] A/B testing framework
- [ ] Human-in-the-loop feedback system
- [ ] Automated regression testing

---

## 6. Success Metrics

### 6.1 Quality Metrics
- **Translation Quality:** Human eval score ≥ 8/10
- **Consistency:** Character voice consistency ≥ 9/10
- **Naturalness:** Anti-translationese compliance ≥ 95%

### 6.2 Adoption Metrics
- **User Retention:** 70% users return after first use
- **Translation Volume:** 50+ chapters translated/month by community

### 6.3 Technical Metrics
- **Token Efficiency:** ≤ 50KB core logic, ≤ 1.5M total context
- **Latency:** P95 response time ≤ 20 seconds/paragraph

---

## 7. Constraints & Dependencies

### 7.1 Platform Dependencies
- **Required:** Google Gemini Advanced (hoặc API key với Gemini Pro)
- **Feature:** Gems (Custom AI) hoặc API với System Instruction
- **Optional:** Canvas mode (cho clean output)

### 7.2 Technical Constraints
- Maximum System Instruction size: 200KB (hiện tại 48KB, buffer 75%)
- Knowledge Base size limit: 50MB (hiện tại 2.7MB, buffer 94%)

### 7.3 Content Constraints
- Chỉ hỗ trợ Light Novel (không phải manga, anime script)
- Văn phong Nhật hiện đại (không phải cổ điển)

---

## 8. Risk Assessment

### 8.1 Technical Risks

**RISK-001: Gemini API Breaking Changes**
- **Likelihood:** Medium
- **Impact:** High
- **Mitigation:** Maintain backward-compatible XML structure, version tagging

**RISK-002: Context Window Reduction**
- **Likelihood:** Low
- **Impact:** Critical
- **Mitigation:** Keep core logic ≤ 50KB, modular design for graceful degradation

### 8.2 Quality Risks

**RISK-003: Hallucination in Kanji Translation**
- **Likelihood:** Medium
- **Impact:** Medium
- **Mitigation:** Golden Samples với forced few-shot learning

**RISK-004: RTAS Drift Over Long Conversations**
- **Likelihood:** Medium
- **Impact:** Medium
- **Mitigation:** Periodic RTAS recalibration instructions

---

## 9. Future Considerations

### 9.1 Scalability
- **Gemini 1.5 Pro vs Flash:** Flash cho draft, Pro cho final polish
- **Batch processing:** API integration cho volume translation

### 9.2 Extensibility
- **Multi-language support:** Nhật→Anh template (reuse RTAS logic)
- **Novel type expansion:** Web novel, manga adaptation

### 9.3 Community Contribution
- **Open-source model:** AGPLv3 đảm bảo improvements được share lại
- **Golden Samples crowdsourcing:** Cộng đồng đóng góp mẫu dịch chất lượng

---

## 10. License Compliance (AGPLv3)

### 10.1 Usage Rights
✅ Free for personal use
✅ Modify and improve
✅ Commercial use (with AGPLv3 compliance)

### 10.2 Network Use Clause (CRITICAL)
Nếu deploy qua mạng (Web App, API, SaaS, Bot):
1. **PHẢI công khai toàn bộ mã nguồn** (kể cả phiên bản đã sửa đổi)
2. **PHẢI cung cấp link download** cho user
3. **PHẢI giữ nguyên license** AGPLv3
4. **PHẢI ghi rõ thay đổi**

### 10.3 Dual License Option
Nếu cần closed-source commercial license, liên hệ: thangdam7790@gmail.com

---

**Document Version:** 1.0
**Last Updated:** 2026-01-03
**Maintainer:** Thang (thangdam7790@gmail.com)
