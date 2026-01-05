# 11_RUBY_TEXT_PARSING_ICL
**Trạng thái Module:** HOẠT ĐỘNG & ƯU TIÊN CAO
**Mục đích:** Hướng dẫn xử lý chính xác Ruby Text (Furigana) để tránh lỗi ghép sai kanji

---

## PHẦN 1: TỔNG QUAN

### 1.1 VẤN ĐỀ

Ruby text (振り仮名/furigana) cung cấp cách đọc cho kanji. Khi xử lý không cẩn thận, có thể xảy ra:
- Ghép sai kanji liền kề
- Mất thông tin đọc
- Dịch sai tên/thuật ngữ

### 1.2 MỤC TIÊU

- **Parsing chính xác** từng cặp kanji-furigana
- **Tránh ghép sai** các kanji khác nhau
- **Output clean** không có ruby format tràn vào bản dịch

---

## PHẦN 2: QUY TẮC PARSING RUBY TEXT

### 2.1 FORMAT RUBY TEXT THƯỜNG GẶP

```
Format 1: HTML style
<ruby>漢字<rt>かんじ</rt></ruby>

Format 2: Simplified
漢字《かんじ》

Format 3: Inline
漢字(かんじ)

Format 4: Bracket style
[漢字|かんじ]
```

### 2.2 NGUYÊN TẮC XỬ LÝ

**NGUYÊN TẮC 1: Tách riêng từng cặp kanji-ruby**
```
INPUT: 綾小路凛々子
ĐÚNG: 
- 綾小路(あやのこうじ) = Ayanokouji (họ)
- 凛々子(りんりんこ) = Rinrinko (tên)

SAI: 
- 綾小路凛(りん) + 々子 = Ghép sai!
```

**NGUYÊN TẮC 2: Không ghép kanji khi không có ruby chung**
```
INPUT: 御堂友也
- 御堂(みどう) = Midou
- 友也(ともや) = Tomoya

SAI: 御堂友(みどうとも) - Ghép sai boundary!
```

**NGUYÊN TẮC 3: Xử lý lặp kanji (々)**
```
凛々 = りんりん (rin + rin)
時々 = ときどき (toki + doki)
色々 = いろいろ (iro + iro)

KHÔNG dịch 々 riêng lẻ!
```

---

## PHẦN 3: ICL EXAMPLES

### 3.1 XỬ LÝ TÊN NHÂN VẬT

**[ICL_RUBY_01] TÊN ĐƠN GIẢN**
```
INPUT: 凛(りん)
OUTPUT_ĐÚNG: "Rin"
OUTPUT_SAI: "凛 (rin)" hoặc "りん"
LÝ DO: Ruby chỉ dùng để xác định đọc, output phải là romanji clean
```

**[ICL_RUBY_02] TÊN CÓ KANJI LẶP**
```
INPUT: 凛々子(りんりんこ)
OUTPUT_ĐÚNG: "Rinrinko"
OUTPUT_SAI: "凛(rin)然(zen)子(ko)" - Ghép sai!

LÝ DO: 々 lặp lại kanji trước, không phải kanji 然
```

**[ICL_RUBY_03] HỌ + TÊN**
```
INPUT: 綿月(わたぬき)凛(りん)
OUTPUT_ĐÚNG: "Watanuki Rin"
OUTPUT_SAI: "Watanukin" (ghép họ-tên)
OUTPUT_SAI: "凛(rin)然(zen)" (thêm kanji không có)

LÝ DO: Họ và tên là 2 đơn vị riêng biệt
```

---

### 3.2 XỬ LÝ THUẬT NGỮ

**[ICL_RUBY_04] THUẬT NGỮ ĐẶC BIỆT**
```
INPUT: 宝塚(たからづか)
OUTPUT_ĐÚNG: "Takarazuka" (địa danh/kịch nổi tiếng)
OUTPUT_SAI: "kịch Bảo mẫu" - Dịch sai hoàn toàn!

LÝ DO: Takarazuka là tên riêng, giữ nguyên
```

**[ICL_RUBY_05] TỪ GHÉP**
```
INPUT: 高校生(こうこうせい)
OUTPUT_ĐÚNG: "học sinh cao trung" hoặc "học sinh cấp 3"
OUTPUT_SAI: "高(cao)校(trường)生(sinh viên)" - Dịch từng kanji

LÝ DO: Dịch nghĩa, không dịch từng thành phần
```

---

### 3.3 TRÁNH LỖI GHÉP SAI

**[ICL_RUBY_06] LỖI GHÉP BOUNDARY**
```
INPUT: その凛(りん)とした姿
PHÂN TÍCH:
- その = "cái đó"
- 凛(りん)とした = "rin/lạnh lùng"
- 姿 = "dáng vẻ"

OUTPUT_ĐÚNG: "dáng vẻ lạnh lùng/kiêu sa đó"
OUTPUT_SAI: "tiền bối凛(rin)然(zen) đó" - Ghép sai với ký tự sau!

LÝ DO: 凛 đứng một mình, không ghép với 然
```

**[ICL_RUBY_07] KANJI LIỀN KỀ KHÁC NGHĨA**
```
INPUT: 凛として + 然り
PHÂN TÍCH:
- 凛として(りんとして) = "một cách kiêu hãnh"
- 然り(しかり) = "đúng vậy" (từ riêng)

OUTPUT_ĐÚNG: Dịch riêng từng phần
OUTPUT_SAI: "凛然(りんぜん)" - Ghép thành từ không tồn tại!
```

---

## PHẦN 4: CHECKLIST XỬ LÝ RUBY

### 4.1 TRƯỚC KHI DỊCH

- [ ] Xác định tất cả cặp kanji-ruby trong câu
- [ ] Phân biệt ranh giới từ (word boundary)
- [ ] Kiểm tra kanji lặp (々) và xử lý đúng
- [ ] Xác định nghĩa của từ ghép

### 4.2 TRONG KHI DỊCH

- [ ] Dịch theo nghĩa, không phải từng kanji
- [ ] Giữ nguyên tên riêng (romanji)
- [ ] Không ghép kanji không liên quan
- [ ] Loại bỏ ruby format trong output

### 4.3 OUTPUT

- [ ] Không còn ký tự Nhật trong output (trừ exception)
- [ ] Tên riêng ở dạng romanji clean
- [ ] Không có format `kanji(furigana)` tràn vào

---

## PHẦN 5: EXCEPTION RULES

### 5.1 KHI NÀO GIỮ KANJI + RUBY

```
EXCEPTION 1: Thuật ngữ văn hóa quan trọng
宝塚(Takarazuka) - OK nếu cần context

EXCEPTION 2: Từ không có equivalent VN
異世界(isekai) - Giữ romanji

EXCEPTION 3: Stylistic choice của tác giả
当て字(ateji) - Giữ nếu quan trọng cho plot
```

### 5.2 KHI NÀO DỊCH HOÀN TOÀN

```
Đa số trường hợp: Dịch sang VN hoàn toàn
高校生 → "học sinh cao trung" (không giữ kanji)
```

---

## PHẦN 6: LỖI THƯỜNG GẶP

### 6.1 BẢNG LỖI VÀ SỬA

| Lỗi | Ví dụ SAI | Ví dụ ĐÚNG |
|-----|----------|-----------|
| Ghép kanji sai | 凛(rin)然(zen) | Rin (chỉ 凛) |
| Giữ ruby format | "tiền bối凛(rin)" | "tiền bối Rin" |
| Dịch sai tên | "kịch Bảo mẫu" | "Takarazuka" |
| Dịch từng kanji | "cao-trường-sinh" | "học sinh cao trung" |
| Ghép 々 sai | 凛 + 然 | 凛々 = りんりん |

---

## PHẦN 7: QUY TRÌNH XỬ LÝ

```
1. DETECT: Tìm tất cả kanji có ruby
      ↓
2. PARSE: Tách từng cặp kanji-ruby
      ↓
3. VERIFY: Kiểm tra ranh giới từ
      ↓
4. TRANSLATE: Dịch/romanize theo ngữ cảnh
      ↓
5. CLEAN: Loại bỏ ruby format trong output
      ↓
6. VALIDATE: Kiểm tra không có ký tự lạ
```

---

## PHẦN 8: TÓM TẮT

🔴 **KHÔNG BAO GIỜ** ghép kanji không có ruby chung

🔴 **KHÔNG BAO GIỜ** để ruby format `kanji(furigana)` tràn vào output

🔴 **LUÔN LUÔN** kiểm tra ranh giới từ trước khi xử lý

🔴 **LUÔN LUÔN** xử lý 々 như lặp kanji trước đó

🔴 **PRIORITY:** Tên riêng → Romanji clean, Từ thường → Dịch nghĩa

---

## 🆕 PHẦN 9: TL NOTE CHO THUẬT NGỮ ĐẶC THÙ

### 9.1 NGUYÊN TẮC CHÍNH

Khi **NGHI NGỜ** về cách dịch một thuật ngữ đặc thù Nhật Bản:
1. **KHÔNG** cố dịch nghĩa đen (sẽ gây sai)
2. **OUTPUT** romanji nguyên bản
3. **CHÈN** TL Note ở cuối đoạn/chương

### 9.2 DANH SÁCH THUẬT NGỮ CẦN TL NOTE

```
🎭 VĂN HÓA GIẢI TRÍ:
- 宝塚 → Takarazuka [TL: Đoàn kịch nữ nổi tiếng Nhật Bản]
- 歌舞伎 → Kabuki [TL: Kịch truyền thống Nhật Bản]
- 落語 → Rakugo [TL: Nghệ thuật kể chuyện hài Nhật Bản]

🏫 HỌC ĐƯỜNG:
- 先輩/後輩 → Senpai/Kouhai [TL: Tiền bối/Hậu bối]
- 部活 → Bukatsu [TL: Hoạt động câu lạc bộ sau giờ học]
- 帰宅部 → Kitakubu [TL: "CLB về nhà" - chỉ học sinh không tham gia CLB nào]

🍜 ẨM THỰC:
- おでん → Oden [TL: Món hầm kiểu Nhật]
- たこ焼き → Takoyaki [TL: Bánh bạch tuộc viên]

🎮 OTAKU/GAME:
- 異世界 → Isekai [TL: Thế giới khác]
- チート → Cheat [TL: Kỹ năng bá đạo trong game/truyện]
- 俺TUEEE → Ore TUEEE [TL: "Tôi mạnh quá!" - thể loại MC siêu mạnh]
```

### 9.3 ICL EXAMPLES

**[ICL_TL_01] NÊN DÙNG TL NOTE**
```
INPUT: 宝塚みたいだ
CONTEXT: So sánh với điều gì đó lộng lẫy

OUTPUT_SAI: "Như kịch Bảo mẫu vậy" 
→ SAI! Dịch nghĩa đen kanji 宝=báu vật, 塚=mả → vô nghĩa!

OUTPUT_ĐÚNG: 
"Như kịch Takarazuka* vậy."
---
*TL: Takarazuka - Đoàn kịch nữ nổi tiếng Nhật Bản, nổi tiếng với các buổi biểu diễn lộng lẫy.

LÝ DO: Takarazuka là danh từ riêng, không dịch được
```

**[ICL_TL_02] THUẬT NGỮ KHÔNG CÓ EQUIVALENT**
```
INPUT: 凛とした姿
CONTEXT: Miêu tả dáng vẻ kiêu hãnh

OUTPUT_ĐÚNG 1 (Dịch nghĩa): "dáng vẻ kiêu sa/lẫm liệt"
OUTPUT_ĐÚNG 2 (Giữ cảm xúc): "dáng vẻ rin* như thế"
---
*TL: Rin (凛) - tính từ JP miêu tả sự kiêu hãnh, lạnh lùng, đường hoàng.

LÝ DO: 凛 có thể dịch hoặc giữ tùy context
```

**[ICL_TL_03] KHÔNG CẦN TL NOTE**
```
INPUT: 高校生
OUTPUT: "học sinh cao trung" or "học sinh cấp 3"
→ Có equivalent VN, KHÔNG cần TL Note

INPUT: 友達
OUTPUT: "bạn bè"
→ Có equivalent VN, KHÔNG cần TL Note
```

### 9.4 FORMAT TL NOTE

**INLINE (cho thuật ngữ đơn lẻ):**
```
"Cứ như diễn viên Takarazuka* vậy."
[Cuối đoạn]
*TL: Takarazuka - Đoàn kịch nữ nổi tiếng Nhật Bản.
```

**FOOTNOTE STYLE (cho nhiều thuật ngữ):**
```
[Cuối chương]
---
📝 GHI CHÚ DỊCH GIẢ:
- Takarazuka: Đoàn kịch nữ nổi tiếng Nhật Bản
- Senpai: Tiền bối, người học/làm trước
- Kitakubu: "CLB về nhà" - học sinh không tham gia CLB
```

### 9.5 CHECKLIST KHI NGHI NGỜ

- [ ] Thuật ngữ này có equivalent VN không?
- [ ] Dịch nghĩa đen có hợp lý không?
- [ ] Người đọc VN có hiểu được không?
- [ ] Có phải tên riêng/địa danh không?

**NẾU trả lời "KHÔNG" cho bất kỳ câu nào → Dùng TL Note!**

### 9.6 QUY TRÌNH QUYẾT ĐỊNH

```
Gặp thuật ngữ lạ
       ↓
Có equivalent VN? ──YES──→ Dịch bình thường
       │NO
       ↓
Là tên riêng? ──YES──→ Romanji clean (không TL Note)
       │NO
       ↓
Văn hóa đặc thù JP? ──YES──→ Romanji + TL Note
       │NO
       ↓
Dịch nghĩa đen có ổn? ──YES──→ Dịch nghĩa
       │NO
       ↓
Romanji + TL Note
```

---

## PHẦN 10: TÓM TẮT TOÀN BỘ

🔴 **RUBY:** Không ghép kanji sai ranh giới

🔴 **OUTPUT:** Không để kanji/ruby format tràn vào

🔴 **TÊN RIÊNG:** Romanji clean không TL Note

🔴 **THUẬT NGỮ ĐẶC THÙ:** Romanji + TL Note cuối đoạn/chương

🔴 **KHI NGHI NGỜ:** Giữ romanji + giải thích, ĐỪNG đoán mò dịch!

---

**(Hết Module 11 v2.0)**
