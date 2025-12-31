# HỆ THỐNG ĐẠI TỪ TIẾNG VIỆT v9.1 (VIETNAMESE PRONOUN SYSTEM)
**Vai Trò:** Hướng Dẫn Chọn Đại Từ cho Dịch Thuật Tiếng Việt
**Phạm Vi:** Hệ thống đại từ lai Nhật/Việt dựa trên động lực mối quan hệ
**Triết Lý:** Giữ kính ngữ Nhật cho sự trang trọng, chuyển sang đại từ Việt cho sự thân mật

---

## 🆕 PHẦN 0: ĐẠI TỪ NGÔI THỨ NHẤT CHO MC/NGƯỜI KỂ CHUYỆN (ICL)

### 0.1 NGUYÊN TẮC CƠ BẢN

**Mặc định:** Sử dụng **"tôi"** cho tất cả nhân vật MC/Narrator cho đến khi archetype được xác định.

```
MẶC ĐỊNH: "tôi" (trung tính, phổ quát)
         ↓ (sau khi archetype được định hình)
CHUYỂN: "mình" (thân mật, nội tâm, đặc biệt cho nữ POV)
```

### 0.2 QUY TẮC CHỌN ĐẠI TỪ NGÔI THỨ NHẤT

| Tình huống | Đại từ | Lý do |
|------------|--------|-------|
| **Chương 1-2 (chưa biết archetype)** | "tôi" | Trung tính, an toàn |
| **MC Nam - chuẩn mực** | "tôi" | Formal, trưởng thành |
| **MC Nam - casual/otaku** | "mình" hoặc "tớ" | Tùy độ casual |
| **MC Nữ - sau khi định hình** | "mình" | Mềm mại, nội tâm |
| **MC Nữ - tsundere/mạnh mẽ** | "tôi" | Defensive, cold |
| **POV thay đổi (chương nữ chính)** | "mình" | Nữ tính, soft |

### 0.3 ICL EXAMPLES

**[ICL_PRONOUN_01] MẶC ĐỊNH: Dùng "tôi"**
```
INPUT: 僕は教室に向かって歩いていた。
OUTPUT_ĐÚNG: "Tôi đang đi về phía lớp học."
OUTPUT_SAI: "Mình đang đi về phía lớp học."
LÝ DO: Chương đầu, chưa biết archetype → MẶC ĐỊNH "tôi"
```

**[ICL_PRONOUN_02] NHẤT QUÁN TRONG CHƯƠNG**
```
ĐOẠN 1: "Tôi cảm thấy buồn ngủ."
ĐOẠN 2: "Tôi nhìn cô ấy từ xa."
ĐOẠN 3: "Điều đó khiến tôi ngạc nhiên."

❌ SAI:
ĐOẠN 1: "Tôi cảm thấy buồn ngủ."
ĐOẠN 2: "Mình nhìn cô ấy từ xa." ← KHÔNG NHẤT QUÁN!
ĐOẠN 3: "Điều đó khiến tôi ngạc nhiên."

NGUYÊN TẮC: Một khi đã chọn "tôi" hoặc "mình", LOCK xuyên suốt chương.
```

**[ICL_PRONOUN_03] NỮ POV - Chuyển sang "mình"**
```
CONTEXT: Chương kể từ góc nhìn nữ chính (sau khi đã giới thiệu)

INPUT: 私は彼のことが気になっていた。
OUTPUT_ĐÚNG: "Mình đã để ý đến anh ấy."
OUTPUT_CHẤP_NHẬN: "Tôi đã để ý đến anh ấy." (cũng OK nếu đã lock "tôi")

LÝ DO: Nữ POV + đã định hình archetype → "mình" tự nhiên hơn
```

**[ICL_PRONOUN_04] TSUNDERE NỮ - Giữ "tôi"**
```
CONTEXT: Nhân vật nữ tsundere/cold/defensive

INPUT: 「私は別にあなたのことなんか…！」
OUTPUT_ĐÚNG: "Tôi đâu có quan tâm đến anh hay gì đâu...!"
OUTPUT_SAI: "Mình đâu có quan tâm đến anh hay gì đâu...!"

LÝ DO: Tsundere dùng "tôi" để tạo khoảng cách/defensive
```

**[ICL_PRONOUN_05] NAM MC CASUAL/OTAKU**
```
CONTEXT: MC nam là otaku, casual, không formal

INPUT: 俺は疲れた。ゲームやりすぎたわ。
OUTPUT_ĐÚNG: "Mình mệt quá. Chơi game nhiều quá rồi."
OUTPUT_CŨNG_OK: "Tớ mệt quá. Chơi game nhiều quá rồi."

LÝ DO: Casual archetype → "mình" hoặc "tớ" tự nhiên hơn "tôi"
```

### 0.4 QUYẾT ĐỊNH LOCK ĐẠI TỪ

```
CHO MỖI TÁC PHẨM:
1. Xác định archetype MC từ đoạn đầu tiên
2. LOCK đại từ ngôi thứ nhất:
   - Default: "tôi"
   - Nữ POV soft: "mình"  
   - Nam casual: "mình" hoặc "tớ"
   - Tsundere/defensive: "tôi"
3. GIỮ NHẤT QUÁN xuyên suốt tác phẩm
4. CHỈ THAY ĐỔI khi POV chuyển nhân vật khác
```

### 0.5 MULTI-POV (Nhiều góc nhìn)

```
VÍ DỤ: Truyện có cả nam chính và nữ chính kể chuyện

CHƯƠNG 1 (Nam MC - Touya):
→ LOCK: "tôi" (default, formal)
"Tôi bước vào cửa hàng tiện lợi."

CHƯƠNG 2 (Nữ chính - Watanuki):
→ LOCK: "mình" (nữ POV, đã định hình)
"Mình không ngờ lại gặp cậu ấy ở đây."

CHƯƠNG 3 (Quay lại Nam MC):
→ DÙNG LẠI: "tôi" (nhất quán với Chương 1)
```

### 0.6 CHECKLIST ĐẠI TỪ NGÔI THỨ NHẤT

- [ ] Xác định POV của chương (nam/nữ)
- [ ] Xác định archetype (formal/casual/tsundere/soft)
- [ ] LOCK đại từ ngôi thứ nhất phù hợp
- [ ] Kiểm tra NHẤT QUÁN xuyên suốt chương
- [ ] Không trộn lẫn "tôi" và "mình" trong cùng POV

---

## 🚨 PHẦN 0.7: ICL QUAN HỆ GIA ĐÌNH (CRITICAL!)

### **NGUYÊN TẮC BẤT BIẾN:**
Quan hệ gia đình **LUÔN ƯU TIÊN CAO NHẤT**, không bao giờ dùng "tao/mày" cho anh chị em!

### **[ICL_FAMILY_01] CHỊ GÁI → EM TRAI**
```
CONTEXT: Mei (chị, 17 tuổi) nói với Touya (em, 16 tuổi)
QUAN HỆ: Chị gái → Em trai (Onee-san → Otouto)

INPUT: 「ねぇ冬也ぁ、アイス買ってきてぇ」

OUTPUT_SAI (tao/mày):
"Nè Touya, mua kem về cho tao đi"
→ SAI! "tao/mày" chỉ dùng cho bạn bè, KHÔNG dùng cho gia đình!

OUTPUT_ĐÚNG (chị/em):
"Nè em ơi, mua kem về cho chị đi"
hoặc "Touya ơi, mua kem về cho chị đi"

LOGIC: Dù Mei có nhõng nhẽo/casual thế nào, chị gái PHẢI dùng "chị/em"
```

### **[ICL_FAMILY_02] EM TRAI → CHỊ GÁI**
```
CONTEXT: Touya (em) nói với Mei (chị)
QUAN HỆ: Em trai → Chị gái (Otouto → Onee-san)

INPUT: 「やだよ。この時間に心臓バクバクしたくないんだけど」

OUTPUT_SAI (tao/mày):
"Hả, không đời nào. Giờ này mà tao không muốn tim đập nhanh đâu"
→ SAI! Em trai KHÔNG nói "tao" với chị gái!

OUTPUT_ĐÚNG (em/chị):
"Hả, không đời nào. Giờ này mà em không muốn tim đập nhanh đâu"
"Với lại chị nghĩ giờ là mấy giờ rồi?"

LOGIC: Em trai PHẢI dùng "em" khi nói với chị, xưng "chị" cho chị gái
```

### **[ICL_FAMILY_03] NARRATOR ĐỀ CẬP CHỊ GÁI**
```
CONTEXT: Touya (người kể chuyện) đề cập đến Mei

INPUT: 芽衣は本当に俺より一つ年上なのか...姉なのか?

OUTPUT_SAI:
"Mei thật sự sinh trước tôi một năm sao... là chị gái hơn tôi một tuổi sao?"
→ SAI! Không dùng "Mei" trống không, phải có "chị"

OUTPUT_ĐÚNG:
"Chị Mei thật sự sinh trước em/tôi một năm sao... là chị gái em/tôi thật sao?"
hoặc "Chị ấy thật sự sinh trước mình một năm sao..."

LOGIC: Khi đề cập chị gái trong tường thuật, PHẢI có prefix "Chị"
```

### **[ICL_FAMILY_04] CHỊ GÁI NHÕNG NHẼO VẪN DÙNG CHỊ/EM**
```
CONTEXT: Mei nhõng nhẽo, làm nũng - VẪN LÀ CHỊ GÁI!

INPUT: 「えー、むりむりー。お姉ちゃん幼稚園のときから成長してないんだもん」

OUTPUT_SAI:
"Ehh, không không chịu được, tao từ hồi mẫu giáo đến giờ vẫn không lớn mà"
→ SAI! Dù nhõng nhẽo, Mei vẫn là chị gái!

OUTPUT_ĐÚNG:
"Ehh, không không chịu được đâu, chị đây từ hồi mẫu giáo đến giờ có lớn thêm tí nào đâu"
"Nếu không làm nũng với đứa em trai trưởng thành thì chị không sống nổi đâu."

LOGIC: Tính cách KHÔNG thay đổi quan hệ gia đình! Nhõng nhẽo ≠ bạn bè
```

### **BẢNG THAM CHIẾU NHANH - GIA ĐÌNH**

| Quan hệ | Người nói | Tự xưng | Gọi đối phương |
|---------|-----------|---------|----------------|
| Chị → Em | Mei | "chị" | "em" / tên |
| Em → Chị | Touya | "em" | "chị" / "chị Mei" |
| Anh → Em | - | "anh" | "em" / tên |
| Em → Anh | - | "em" | "anh" / "anh [Tên]" |

### **🔴 CẤM KỴ:**
- ❌ KHÔNG BAO GIỜ dùng "tao/mày" cho anh chị em ruột
- ❌ KHÔNG BAO GIỜ dùng "tớ/cậu" cho anh chị em ruột  
- ❌ KHÔNG BAO GIỜ bỏ prefix "Chị/Anh" khi đề cập tên
- ❌ Tính cách nhõng nhẽo/casual KHÔNG thay đổi quy tắc gia đình

### **[ICL_FAMILY_05] CẤM TỚ/CẬU CHO CHỊ EM** ⚠️
```
CONTEXT: Mei (chị gái) nói với Touya (em trai)
INPUT: 「最近はダイエットまぁじ頑張ってるから...」

OUTPUT_SAI (tớ/cậu):
"Dạo này tớ cố gắng giảm cân dữ lắm đó, lâu lâu cũng muốn được tự thưởng cho mình chứ!"
"tớ cho cậu ăn một ngụm kem..."
→ SAI! "tớ/cậu" là đại từ dùng cho BẠN BÈ, KHÔNG PHẢI gia đình!

OUTPUT_ĐÚNG (chị/em):
"Dạo này chị cố gắng giảm cân dữ lắm đó, lâu lâu cũng muốn được tự thưởng cho mình chứ!"
"Chị cho em ăn một ngụm kem..."

PHÂN BIỆT:
- tớ/cậu = Bạn bè thân (同級生, 友達)
- chị/em = Chị em ruột (姉弟, 兄妹)
- tao/mày = Bạn bè rất thân hoặc cãi nhau
- Mei + Touya = CHỊ EM RUỘT → PHẢI dùng chị/em!
```

### **[ICL_FAMILY_06] NHẬN DIỆN QUAN HỆ GIA ĐÌNH** 🔍
```
CÁC TỪ KHÓA XÁC ĐỊNH QUAN HỆ CHỊ EM TRONG RAW:
- 姉 (ane) = chị gái
- 弟 (otouto) = em trai  
- お姉ちゃん (onee-chan) = chị (gọi thân mật)
- 年上 (toshiue) = người lớn tuổi hơn
- 一つ年上 (hitotsu toshiue) = hơn một tuổi

KỊCH BẢN:
Nếu văn bản có: "芽衣は...姉なんだよな" (Mei... là chị gái nhỉ)
→ XÁC ĐỊNH: Mei = CHỊ GÁI
→ KHÓA: Mei dùng "chị", Touya dùng "em"
→ KHÔNG BAO GIỜ dùng tớ/cậu/tao/mày cho dialogue 2 người này!
```

---

## 🆕 HỆ THỐNG MÃ CẶP ĐẠI TỪ (PRONOUN PAIR ID SYSTEM)

**Mục Đích:** Loại bỏ sự đoán mò. Khi RTAS đã được tính, PAIR_ID được xác định. Gemini chọn cặp đúng một cách máy móc.

**Bảng Tham Chiếu Chính:**

### CẤP ĐỘ GIA ĐÌNH (Cố Định, Không Phụ Thuộc RTAS)

| PAIR_ID | Loại Cặp | Đại Từ | RTAS | Ngữ Cảnh | Ví Dụ |
|---|---|---|---|---|---|
| **PAIR_FAM_1** | Anh Chị Lớn | Anh/Chị (họ) + Em (mình) | N/A (Cố định) | Em → Anh/Chị | "Anh ơi, anh làm gì thế?" |
| **PAIR_FAM_2** | Em Nhỏ | Em (họ) + Anh/Chị (mình) | N/A (Cố định) | Anh/Chị → Em | "Em đang học chưa?" |
| **PAIR_FAM_3** | Cha Mẹ (Trẻ em) | Ba/Mẹ (họ) + Con (mình) | N/A (Cố định) | Con → Cha Mẹ | "Con xin lỗi ba ạ" |
| **PAIR_FAM_4** | Cha Mẹ (Người lớn) | Con (họ) + Ba/Mẹ (mình) | N/A (Cố định) | Cha Mẹ → Con lớn | "Con thế nào rồi?" |

**Quy Tắc:** Các cặp gia đình **LUÔN ĐƯỢC DÙNG** bất kể các yếu tố khác. Kiểm tra quan hệ gia đình TRƯỚC TIÊN.

---

### CẤP ĐỘ LÃNG MẠN/THÂN MẬT (Phụ Thuộc RTAS)

| PAIR_ID | Loại Cặp | Đại Từ | Phạm Vi RTAS | Giai Đoạn Quan Hệ | Ví Dụ |
|---|---|---|---|---|---|
| **PAIR_1** | Bạn Bè Xã Giao | Tớ (mình) + Cậu (họ) | 2.0–3.5 | Bạn bè, cặp đôi mới, lảng tránh | "Cậu yên tâm đi." |
| **PAIR_2** | Thân Mật Chuyển Tiếp | Tớ (mình) + Anh (họ) | 3.5–4.2 | Tổn thương nhẹ, phụ thuộc | "Anh, tớ sợ lắm." |
| **PAIR_3** | Thân Mật Đỉnh Điểm | Em (mình) + Anh (họ) | 4.2–5.0 | Tổn thương tối đa, chăm sóc, yêu | "Em ở đây, đừng lo." |
| **PAIR_4** | Khoảng Cách Trang Trọng | Cô/Anh (họ) + (Tôi ngầm) | 1.0–2.0 | Người lạ, gặp lần đầu, tôn trọng | "Anh có thời gian không?" |
| **PAIR_5** | Tsundere/Kháng Cự | Tôi (mình) + Anh (họ) | 1.5–2.5 | Phòng thủ, che giấu cảm xúc | "Tôi không cần anh lo!" |

---

### CẤP ĐỘ PHÂN CẤP XÃ HỘI (Dựa Trên Ngữ Cảnh)

| PAIR_ID | Loại Cặp | Đại Từ | Ngữ Cảnh | Ghi Đè RTAS | Ví Dụ |
|---|---|---|---|---|---|
| **PAIR_SOCIAL_1** | Senpai (RTAS < 4.0) | Senpai (giữ tiếng Nhật) | Cách biệt tuổi học đường, chưa hẹn hò | Giữ kính ngữ Nhật | "Senpai, xem cái này đi" |
| **PAIR_SOCIAL_2** | Senpai (RTAS ≥ 4.0) | Anh/Chị (chuyển sang tiếng Việt) | Hẹn hò, vượt ngưỡng RTAS | Chuyển sang tiếng Việt | "Anh ơi, cùng về nhé" |
| **PAIR_SOCIAL_3** | Giáo Viên/Học Sinh | Thầy/Cô (họ) + Em (mình) | Ngữ cảnh học thuật | N/A (ngữ cảnh) | "Em xin lỗi thầy ạ" |
| **PAIR_SOCIAL_4** | Trang Trọng/Chính Thức | Ngài (họ) + Tôi (mình) | Tòa án, chính phủ, nghi lễ | Trang trọng cao nhất | "Tôi xin tuân mệnh, ngài." |

---

## TRA CỨU MÃ CẶP ĐẠI TỪ (Cây Quyết Định)

**Sử dụng lưu đồ này để chọn PAIR_ID đúng:**

```
BẮT ĐẦU: Xác định loại mối quan hệ
  │
  ├─→ QUAN HỆ GIA ĐÌNH?
  │   ├─ CÓ → Kiểm tra loại gia đình
  │   │   ├─ Em → Anh/Chị? → DÙNG PAIR_FAM_1
  │   │   ├─ Anh/Chị → Em? → DÙNG PAIR_FAM_2
  │   │   ├─ Con → Cha Mẹ? → DÙNG PAIR_FAM_3
  │   │   └─ Cha Mẹ → Con? → DÙNG PAIR_FAM_4
  │   └─ KHÔNG → Tiếp tục kiểm tra
  │
  ├─→ NGỮ CẢNH LÃNG MẠN?
  │   ├─ CÓ → Tính toán RTAS
  │   │   ├─ RTAS 2.0–3.5? → DÙNG PAIR_1 (Tớ-Cậu)
  │   │   ├─ RTAS 3.5–4.2? → DÙNG PAIR_2 (Tớ-Anh)
  │   │   └─ RTAS 4.2–5.0? → DÙNG PAIR_3 (Em-Anh)
  │   └─ KHÔNG → Tiếp tục kiểm tra
  │
  ├─→ BỐI CẢNH TRANG TRỌNG/CHÍNH THỨC?
  │   ├─ CÓ → DÙNG PAIR_SOCIAL_4 (Ngài/Tôi)
  │   └─ KHÔNG → Tiếp tục kiểm tra
  │
  ├─→ SENPAI/KOUHAI hoặc CÁCH BIỆT TUỔI?
  │   ├─ CÓ → Kiểm tra RTAS
  │   │   ├─ RTAS < 4.0? → DÙNG PAIR_SOCIAL_1 (Giữ "Senpai")
  │   │   └─ RTAS ≥ 4.0? → DÙNG PAIR_SOCIAL_2 (Chuyển sang tiếng Việt)
  │   └─ KHÔNG → Tiếp tục kiểm tra
  │
  ├─→ GIÁO VIÊN/HỌC SINH?
  │   ├─ CÓ → DÙNG PAIR_SOCIAL_3 (Thầy/Cô + Em)
  │   └─ KHÔNG → Tiếp tục kiểm tra
  │
  ├─→ NHÂN VẬT LÀ TSUNDERE hoặc PHÒNG THỦ?
  │   ├─ CÓ → DÙNG PAIR_5 (Tôi-Anh)
  │   └─ KHÔNG → Tiếp tục
  │
  └─→ MẶC ĐỊNH: DÙNG PAIR_4 (Cô/Anh - Khoảng Cách Trang Trọng)
```

---

## QUY TẮC GÁN CẶP TỰ ĐỘNG (Giao Thức Gemini)

**Khi Gemini gặp đối thoại, nó tuân theo quy trình này:**

### Bước 1: Xác định Người Nói và Mục Tiêu
```
Ví dụ: Umi nói với Maki
Người nói: Umi
Mục tiêu: Maki
```

### Bước 2: Kiểm tra Quan Hệ Gia Đình
```
Umi có phải là gia đình của Maki không? KHÔNG
→ Tiếp tục kiểm tra
```

### Bước 3: Kiểm tra Ngữ Cảnh Lãng Mạn
```
Đây có phải là cảnh lãng mạn không? CÓ
Tính toán RTAS(Umi → Maki) = 4.6
RTAS 4.6 rơi vào khoảng 4.2–5.0
→ Gán PAIR_3 (Em-Anh)
```

### Bước 4: KHÓA PAIR_ID cho Cảnh
```
Umi-Maki trong cảnh này: PAIR_3
CHỈ dùng Em-Anh cho tất cả đối thoại Umi→Maki
```

### Bước 5: Xuất Đối Thoại Dùng PAIR_3
```
Umi: "Em ở đây, anh đừng lo." (Em-Anh bị khóa)
Maki: [Đáp lại Umi dùng đại từ tương ứng]
```

**KHÔNG LỆCH HƯỚNG** cho đến khi RTAS được tính lại sang một phạm vi mới.

---

## MA TRẬN CẶP CẢNH ĐA NHÂN VẬT

**Với cảnh có 3+ nhân vật, tạo tham chiếu này:**

```
VÍ DỤ: Cảnh Maki + Umi + Yuu + Nitta

NGƯỜI NÓI → MỤC TIÊU | RTAS | PAIR_ID | ĐẠI TỪ | KHÓA |
─────────────────────────────────────────────────────────
Maki → Umi     | 4.6  | PAIR_3  | Em-Anh  | ✓
Umi → Maki     | 4.6  | PAIR_3  | Em-Anh  | ✓
Maki → Yuu     | 2.1  | PAIR_4  | Cô-Anh  | ✓
Yuu → Maki     | 2.1  | PAIR_4  | Cô-Anh  | ✓
Umi → Yuu      | 2.3  | PAIR_4  | Cô-Anh  | ✓
Yuu → Umi      | 2.3  | PAIR_4  | Cô-Anh  | ✓
Nitta → All    | 1.5  | PAIR_4  | Cô-Anh  | ✓
```

**Cách dùng:** Trước khi viết bất kỳ dòng thoại nào, tham khảo ma trận này để tìm PAIR_ID bị khóa.

---



Dịch thuật tiếng Việt sử dụng **phương pháp lai động** dựa trên RTAS (Điểm Căng Thẳng & Tình Cảm Quan Hệ):

### Quy Tắc Chuyển Đổi (The Switching Rule)

```
┌─────────────────────────────────────────────────────────────┐
│ RTAS < 4.0 (Người lạ/Người quen/Bạn bè)                    │
│ → GIỮ NGUYÊN kính ngữ Nhật (-san, -kun, Senpai, v.v.)      │
│ → Lý do: Sự trang trọng, khoảng cách, hương vị văn hóa     │
├─────────────────────────────────────────────────────────────┤
│ RTAS ≥ 4.0 (Hẹn hò/Người yêu/Thân mật sâu sắc)             │
│ → CHUYỂN SANG đại từ tiếng Việt (Em/Anh, v.v.)             │
│ → Lý do: Biểu đạt sự thân mật tự nhiên trong tiếng Việt    │
└─────────────────────────────────────────────────────────────┘
```

### Các Ví Dụ về Hệ Thống Lai

**RTAS 2.0 (Bạn cùng lớp):**
```
RAW: 「田中さん、これ見て」
VN:  "Tanaka-san, xem cái này đi"
```
→ Giữ "-san" (khoảng cách trang trọng)

**RTAS 3.5 (Cảm nắng nhưng chưa hẹn hò):**
```
RAW: 「先輩、一緒に帰りませんか？」
VN:  "Senpai, cùng về nhé?"
```
→ Giữ "Senpai" (chưa đủ thân mật)

**RTAS 4.5 (Hẹn hò/Chấp nhận lời tỏ tình):**
```
RAW: 「好きだよ、美咲」
VN:  "Anh thích em, Misaki"
```
→ Chuyển sang "Anh/Em" (mở khóa thân mật lãng mạn)

**NGOẠI LỆ: Quan hệ gia đình LUÔN dùng đại từ tiếng Việt bất kể RTAS**
```
RAW: 「お兄ちゃん」
VN:  "Anh ơi" (KHÔNG PHẢI "Onii-chan")
```
→ Gia đình = Đại từ tiếng Việt (cố định)

---

## NGUYÊN TẮC CỐT LÕI: ĐẠI TỪ LÀ DẤU HIỆU QUAN HỆ

Đại từ tiếng Việt mã hóa:
1. **Khoảng Cách Tuổi** (lớn/nhỏ)
2. **Giới Tính** (nam/nữ)
3. **Mức Độ Thân Mật** (người lạ → gia đình)
4. **Địa Vị Xã Hội** (ngang bằng/cấp trên/cấp dưới)
5. **Trạng Thái Cảm Xúc** (trang trọng/suồng sã/tình cảm)

---

## QUAN HỆ GIA ĐÌNH (Ưu Tiên Cao Nhất)

### Anh Chị Em (Ruột/Thân thiết)

| Tiếng Nhật | Bối Cảnh | Đại Từ Tiếng Việt | Ví Dụ |
|----------|---------|---------------------|---------|
| お兄ちゃん | Em gái → Anh trai | **Anh** (họ) / **Em** (mình) | "Anh ơi, anh đang làm gì thế?" |
| お姉ちゃん | Em → Chị gái | **Chị** (họ) / **Em** (mình) | "Chị ơi, em muốn đi cùng!" |
| 弟 | Anh/Chị → Em trai | **Em** (họ) / **Anh/Chị** (mình) | "Em đang học à?" |
| 妹 | Anh/Chị → Em gái | **Em** (họ) / **Anh/Chị** (mình) | "Em ăn cơm chưa?" |

**Quy Tắc:** Đại từ gia đình là **CỐ ĐỊNH** bất kể thay đổi về mức độ thân mật.

### Cha Mẹ & Con Cái

| Tiếng Nhật | Tiếng Việt (Con → Cha Mẹ) | Tiếng Việt (Cha Mẹ → Con) |
|----------|----------------------------|----------------------------|
| お父さん | **Ba/Bố** (họ) / **Con** (mình) | **Con** (con) / **Ba/Bố** (mình) |
| お母さん | **Mẹ/Má** (họ) / **Con** (mình) | **Con** (con) / **Mẹ/Má** (mình) |

---

## QUAN HỆ LÃNG MẠN (HỆ THỐNG LAI DỰA TRÊN RTAS)

### Thang RTAS: 1.0 (Người Lạ) → 5.0 (Tri Kỷ)

**🔑 QUAN TRỌNG: RTAS 4.0 là ngưỡng chuyển đổi**

| RTAS | Giai Đoạn Quan Hệ | Chiến Lược Dịch Tiếng Việt | Ví Dụ |
|------|-------------------|--------------------------------|---------|
| 1.0-1.5 | Người lạ/Bạn cùng lớp | **Giữ Tiếng Nhật** (-san, -kun) | "Tanaka-san" |
| 2.0-2.5 | Người quen | **Giữ Tiếng Nhật** (Senpai, -kun) | "Senpai" |
| 3.0-3.5 | Bạn bè/Cảm nắng | **Giữ Tiếng Nhật** (tên-kun, Senpai) | "Yamada-kun" |
| **4.0-4.5** | **Hẹn hò/Tỏ tình** | **CHUYỂN SANG Tiếng Việt** (Anh/Em) | "Anh/Em" |
| 5.0 | Cam kết/Kết hôn | **Tiếng Việt** (Anh/Em) | "Anh/Em" |

**Các Bước Chuyển Đổi Chính:**
- **RTAS < 4.0:** Giữ nguyên kính ngữ Nhật (trang trọng, khoảng cách, phong vị văn hóa)
- **RTAS ≥ 4.0:** Chuyển sang đại từ tiếng Việt (biểu đạt thân mật tự nhiên)
- **Thời Điểm Chuyển Đổi:** Thường xảy ra khi chấp nhận lời tỏ tình hoặc nụ hôn đầu

### Khoảnh Khắc Tỏ Tình (RTAS 3.5 → 4.5) - ĐIỂM CHUYỂN ĐỔI

**Trước Tỏ Tình (RTAS 3.5):**
```
RAW: 「先輩、好きです」
VN:  "Senpai, em thích anh"
```
→ Vẫn dùng "Senpai" (chưa đủ thân mật)

**Sau Khi Chấp Nhận Tỏ Tình (RTAS 4.5):**
```
RAW: 「ありがとう。俺も好きだ」
VN:  "Cảm ơn em. Anh cũng thích em"
```
→ Chuyển sang "Anh/Em" (mở khóa thân mật lãng mạn)

**Ngày Hôm Sau (Đã Hẹn Hò):**
```
RAW: 「おはよう、美咲」
VN:  "Chào em, Misaki"
```
→ Không còn "Misaki-chan", dùng "Em" (đại từ bạn gái)

---

## HỌC ĐƯỜNG/PHÂN CẤP XÃ HỘI (HỆ THỐNG LAI)

### Hệ Thống Senpai/Kouhai

**Chiến Lược Mặc Định: Giữ nguyên kính ngữ Nhật**

| Tiếng Nhật | Tiếng Việt (RTAS < 4.0) | Tiếng Việt (RTAS ≥ 4.0) |
|----------|------------------------|------------------------|
| 先輩 (Senpai) | **"Senpai"** (giữ tiếng Nhật) | **"Anh/Chị"** (chuyển tiếng Việt) |
| 後輩 (Kouhai) | **"[Tên]-kun/-chan"** (giữ tiếng Nhật) | **"Em/Cậu"** (chuyển tiếng Việt) |

**Ví Dụ:**

**RTAS 2.5 (Kouhai cảm nắng Senpai):**
```
RAW: 「先輩、一緒に帰りませんか？」
VN:  "Senpai, cùng về nhé?"
```
→ Giữ "Senpai" (chưa hẹn hò)

**RTAS 4.5 (Đã hẹn hò):**
```
RAW: 「一緒に帰ろう」
VN:  "Cùng về nhé, em"
```
→ Chuyển sang "Em" (đại từ bạn gái/bạn trai)

### Giáo Viên/Học Sinh

| Ngữ Cảnh | Học Sinh → Giáo Viên | Giáo Viên → Học Sinh |
|---------|------------------|-------------------|
| Trang trọng | **Thầy/Cô** (gv) / **Em/Con** (mình) | **Em/Con** (hs) / **Thầy/Cô** (mình) |
| Thân mật | **Thầy/Cô** (gv) / **Em** (mình) | **Em** (hs) / **Thầy/Cô** (mình) |

**Ghi chú:** Giáo viên/học sinh luôn dùng tiếng Việt (không dùng kính ngữ Nhật).

---

## BẠN BÈ (Cùng Tuổi, Ngang Hàng)

### Các Kết Hợp Giới Tính

| Mối Quan Hệ | Nam → Nam | Nữ → Nữ | Nam → Nữ | Nữ → Nam |
|--------------|-------------|-----------------|---------------|---------------|
| Bạn Xã Giao | Tao/Mày (thận trọng) | Tớ/Cậu | Tớ/Cậu | Tớ/Cậu |
| Bạn Thân | Tao/Mày | Tao/Mày (hiếm) | Tớ/Cậu | Tớ/Cậu |
| Bạn Chí Cốt | Tao/Mày | Mình/Bạn | Mình/Bạn | Mình/Bạn |

**Thang Trang Trọng (Bạn Bè):**
1. **Tao/Mày** - Rất suồng sã, bạn thân cùng giới
2. **Tớ/Cậu** - Thân thiện nhưng lịch sự, an toàn cho khác giới
3. **Mình/Bạn** - Ấm áp, bao hàm, trung tính

---

## CÁC TRƯỜNG HỢP ĐẶC BIỆT

### Nhân Vật Tsundere (Biến Động Khoảng Cách Cảm Xúc)

| Trạng Thái Cảm Xúc | Đại Từ | Ví Dụ |
|----------------|----------|---------|
| Phòng thủ/Giận | Tôi/Anh (xa cách) | "Tôi không cần anh lo!" |
| Bình thường | Tớ/Cậu (trung tính) | "Cậu... đi đâu thế?" |
| Khoảnh khắc Dere | Em/Anh (mềm) | "Em... lo cho anh thôi." |

**Quy Tắc:** Đại từ thay đổi theo bức tường cảm xúc lên/xuống.

### Bối Cảnh Trang Trọng/Công Khai

| Bối Cảnh | Đại Từ | Ví Dụ |
|---------|----------|---------|
| Tòa án/Chính thức | Tôi/Ngài, Điện hạ | "Tôi xin tuân mệnh, điện hạ." |
| Chào cờ/Họp trường | Em/Thầy, Cô | "Em xin báo cáo với thầy." |
| Họp mặt gia đình | (Đại từ gia đình) | "Con chào bác ạ." |

**Quy Tắc:** Bối cảnh công khai → đại từ trang trọng hơn, ngay cả giữa người thân thiết.

---

## LƯU ĐỒ CHỌN ĐẠI TỪ (HỆ THỐNG LAI)

```
BẮT ĐẦU
  ↓
Là GIA ĐÌNH? → CÓ → Dùng đại từ gia đình VN (Anh/Chị/Em/Ba/Mẹ)
  ↓ KHÔNG
Là ngữ cảnh LÃNG MẠN?
  ↓ CÓ
  Kiểm tra RTAS:
    RTAS < 4.0? → Giữ kính ngữ Nhật (-san, -kun, Senpai)
    RTAS ≥ 4.0? → Dùng đại từ lãng mạn VN (Anh/Em)
  ↓ KHÔNG
Có KHOẢNG CÁCH TUỔI (senpai/kouhai)?
  ↓ CÓ
  Kiểm tra RTAS:
    RTAS < 4.0? → Giữ "Senpai" hoặc "[Tên]-kun/-chan"
    RTAS ≥ 4.0? → Dùng tiếng Việt (Anh/Chị/Em)
  ↓ KHÔNG
Là BỐI CẢNH TRANG TRỌNG? → CÓ → Dùng VN trang trọng (Tôi/Ngài, Điện hạ)
  ↓ KHÔNG
Bạn Cùng Tuổi NGƯỜI LẠ/XÃ GIAO? → CÓ → Giữ kính ngữ Nhật (-san, -kun)
  ↓ KHÔNG
Bạn Cùng Tuổi BẠN BÈ? → CÓ → Giữ Nhật hoặc dùng Tớ/Cậu (tùy ngữ cảnh)
  ↓
MẶC ĐỊNH: Giữ kính ngữ Nhật (an toàn, trang trọng)
```

**Các Điểm Quyết Định Chính:**
1. **Gia đình = Luôn là Tiếng Việt** (ưu tiên cao nhất)
2. **RTAS ≥ 4.0 = Chuyển sang Tiếng Việt** (ngưỡng thân mật)
3. **RTAS < 4.0 = Giữ Tiếng Nhật** (trang trọng, khoảng cách)
4. **Bối cảnh trang trọng = Tiếng Việt** (tòa án, chính thức)

---

## VÍ DỤ DỊCH THUẬT

### Ví Dụ 1: Đối thoại Anh Em
```
RAW: 「お兄ちゃん、何してるの？」
EN: "Onii-chan, what are you doing?"
VN: "Anh ơi, anh đang làm gì thế?"
```
**Lý do:** Quan hệ gia đình → "Anh" (anh trai) là cố định.

### Ví Dụ 2: Tỏ Tình (Chuyển đổi RTAS)
```
RAW: 「好きだ。ずっと前から、お前のことが好きだった」
EN: "I like you. I've liked you for a long time."
VN: "Tớ thích cậu. Từ lâu rồi... tớ đã thích cậu."
```
**Lý do:** Trước tỏ tình → vẫn dùng "Tớ/Cậu" (bạn bè). Sau khi chấp nhận, sẽ chuyển sang "Em/Anh".

### Ví Dụ 3: Senpai/Kouhai
```
RAW: 「先輩、一緒に帰りませんか？」
EN: "Senpai, would you walk home with me?"
VN: "Anh ơi, cùng về nhé?"
```
**Lý do:** Kouhai → Senpai = "Anh" (anh nam lớn hơn). Bản thân = "Em" (ngầm hiểu).

### Ví Dụ 4: Biến Động Tsundere
```
RAW: 「……バカ」(embarrassed/affectionate)
EN: "...Idiot."
VN: "...Đồ ngốc." (không cần đại từ - ngữ cảnh rõ ràng)
```
**Lý do:** Khoảnh khắc thân mật cao → lược bỏ đại từ (quy tắc zero-pronoun).

### Ví Dụ 5: Tòa Án Trang Trọng
```
RAW: 「殿下、評議会がお待ちしております」
EN: "Your Highness, the council awaits."
VN: "Điện hạ, hội đồng đang chờ ngài."
```
**Lý do:** Xưng hô hoàng gia → "Điện hạ", "ngài" (trang trọng).

---

## TÍCH HỢP VỚI MẪU VÀNG (GOLDEN SAMPLES)

Khi dịch sang tiếng Việt:
1. **Xác định loại mối quan hệ** (gia đình/lãng mạn/xã hội/trang trọng)
2. **Kiểm tra mức RTAS** (cho quan hệ lãng mạn)
3. **Xem xét trạng thái cảm xúc** (cho nhân vật tsundere/biến động)
4. **Áp dụng đại từ từ hướng dẫn này**
5. **Xác minh tính nhất quán** với cách dùng trước đó trong Kho Lưu Trữ Omni-Volume

---

## CÁC LỖI THƯỜNG GẶP CẦN TRÁNH

❌ **Dùng "Tôi/Bạn" cho bạn thân** (quá trang trọng)
❌ **Dùng "Tao/Mày" khác giới** (quá thô lỗ)
❌ **Giữ đại từ lãng mạn sau khi chia tay** (hồi quy RTAS)
❌ **Trộn lẫn đại từ gia đình và lãng mạn** (ví dụ: "Anh" cho cả anh trai và bạn trai - ngữ cảnh phải rõ ràng)
❌ **Lạm dụng đại từ** (Tiếng Việt lược bỏ đại từ khi ngữ cảnh rõ ràng)

---

## 🆕 HYBRID HONORIFIC SYSTEM (KÍNH NGỮ HYBRID)

### MỤC ĐÍCH

Xử lý kính ngữ Nhật Bản (-senpai, -san, -sama, -kun, -chan) một cách **nhất quán** và **chuẩn format**.

---

### QUY TẮC FORMAT CHUẨN

**NGUYÊN TẮC VÀNG:** Honorific đi SAU tên, nối bằng dấu gạch ngang `-`

| Input (RAW) | SAI ❌ | ĐÚNG ✅ |
|-------------|--------|---------|
| Watanuki先輩 | Senpai Watanuki | **Watanuki-senpai** |
| 綿貫さん | San Watanuki | **Watanuki-san** |
| 先輩が... | tiền bối | **senpai** (hoặc "tiền bối" tùy context) |

---

### ICL HYBRID HONORIFIC

**[ICL_HYBRID_01] TÊN + SENPAI FORMAT**

```
INPUT: 「ねえ、綿貫先輩じゃない?」
CONTEXT: Dialogue bình thường, nhắc đến tiền bối

OUTPUT_SAI:
「Nè, không phải Watanuki* senpai đó sao?」 ← Dấu * + cách space!
「Nè, không phải Senpai Watanuki đó sao?」 ← Senpai đứng trước!

OUTPUT_ĐÚNG:
「Nè, không phải Watanuki-senpai đó sao?」

FORMAT: Tên-honorific (không space, có dấu gạch ngang)
```

**[ICL_HYBRID_02] THỨ TỰ TRONG CÂU**

```
INPUT: 先輩の綿貫さんが...
CONTEXT: Narrator nhắc đến tiền bối

OUTPUT_SAI:
"Senpai Watanuki lại là người..." ← Senpai đứng trước!
"Watanuki senpai lại là người..." ← Thiếu gạch ngang!

OUTPUT_ĐÚNG:
"Watanuki-senpai lại là người..."

NGUYÊN TẮC: LUÔN đặt tên trước, honorific sau, nối bằng `-`
```

---

### BẢNG HONORIFIC CHUẨN

| Honorific JP | Romanji | Format chuẩn | Khi nào dùng tiếng Việt |
|--------------|---------|--------------|-------------------------|
| 先輩 | senpai | Tên-senpai | RTAS ≥ 4.0 → "anh/chị" |
| さん | san | Tên-san | Formal → "anh/chị/cô/chú" |
| 様 | sama | Tên-sama | Trang trọng → "ngài" |
| くん | kun | Tên-kun | Thân mật nam → tên không |
| ちゃん | chan | Tên-chan | Thân mật nữ/trẻ em → tên không |
| 先生 | sensei | Tên-sensei | Học thuật → "thầy/cô" |

---

### ANTI-ENGLISH LOANWORD (CHỐNG TỪ VỰNG ANH NGỮ)

**MỤC ĐÍCH:** Hạn chế tiếng Anh trong văn nói bình thường, trừ khi raw có chủ đích sử dụng (archetype sính ngoại).

**[ICL_ANTI_ENG_01] THAY THẾ TIẾNG ANH THƯỜNG GẶP**

```
INPUT: エナジードリンク (energy drink)
OUTPUT_SAI: "energy drink" ← Để nguyên tiếng Anh!
OUTPUT_ĐÚNG: "nước tăng lực"

INPUT: コンビニ (convenience store)  
OUTPUT_ĐÚNG: "cửa hàng tiện lợi" hoặc "tiện lợi" (ngắn gọn)

INPUT: スマホ (smartphone)
OUTPUT_ĐÚNG: "điện thoại" hoặc "máy" (informal)
```

**BẢNG THAY THẾ LOANWORD:**

| Tiếng Nhật (Katakana) | Tiếng Anh | Tiếng Việt (ƯU TIÊN) |
|-----------------------|-----------|----------------------|
| エナジードリンク | energy drink | nước tăng lực |
| コンビニ | convenience store | cửa hàng tiện lợi |
| スマホ | smartphone | điện thoại |
| パソコン | personal computer | máy tính |
| コーヒー | coffee | cà phê |
| サンドイッチ | sandwich | bánh mì sandwich |
| アイスクリーム | ice cream | kem |
| ゲーム | game | game (CHO PHÉP - đã Việt hóa) |
| バイト | part-time job | làm thêm |
| デート | date | hẹn hò |

**NGOẠI LỆ - CHO PHÉP TIẾNG ANH:**
- Thuật ngữ gaming (rank, buff, nerf) → giữ nguyên
- Thuật ngữ tech phổ biến (game, video, WiFi) → giữ nguyên
- Nhân vật có archetype "sính ngoại" → cho phép mix

---

### 🔮 [TƯƠNG LAI] PAISEN HANDLING (GAL ARCHETYPE)

**Paisen (パイセン):** Cách đọc ngược của Senpai, thường dùng bởi gal/gyaru characters.

```
INPUT: パイセン、まじウケる～
CONTEXT: Gal character nói

OUTPUT_ĐÚNG:
「Paisen ơi, tức cười thật đấy～」

NGUYÊN TẮC:
- Paisen = slang của Senpai
- Giữ nguyên "Paisen" cho gal characters
- Format: Tên-paisen (nếu có tên)
- KHÔNG dịch sang "tiền bối" (mất feel slang)
```

---

### ICL TỔNG HỢP VÍ DỤ THỰC TẾ

**[ICL_HYBRID_FULL] BA CHƯƠNG CÙNG NHÂN VẬT**

```
CHAPTER 1:
INPUT: 「ねえ、綿貫先輩じゃない?」
SAI: 「Nè, không phải Watanuki* senpai đó sao?」
ĐÚNG: 「Nè, không phải Watanuki-senpai đó sao?」

CHAPTER 2:
INPUT: 綿貫先輩がエナジードリンクを大量に買っていた
SAI: Senpai Watanuki lại là người mua cả đống energy drink
ĐÚNG: Watanuki-senpai lại là người mua cả đống nước tăng lực

CHAPTER 3:
INPUT: 嘘をついて、綿貫先輩にバレないように
SAI: mong là tiền bối Watanuki sẽ không phát hiện
ĐÚNG: mong là Watanuki-senpai sẽ không phát hiện

LOGIC ĐÃ ÁP DỤNG:
1. Tên-senpai format nhất quán
2. "energy drink" → "nước tăng lực"
3. Honorific đi sau tên, nối bằng `-`
```

---

**(Hết Hệ Thống Đại Từ Tiếng Việt v2.0 - Bổ sung Hybrid Honorific)**
