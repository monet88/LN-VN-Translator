---
**Ref_LONG_VOWEL_ROMANIZATION.md — HƯỚNG DẪN PHIÊN ÂM NGUYÊN ÂM DÀI TIẾNG NHẬT**
**Trạng thái Module:** HOẠT ĐỘNG & UỶ QUYỀN
**Mục đích:** Phiên âm chính xác nguyên âm dài tiếng Nhật trong tên và thuật ngữ
---

# 07_LONG_VOWEL_ROMANIZATION

## PHẦN 1: CƠ BẢN VỀ NGUYÊN ÂM DÀI

### 1.1 NGUYÊN ÂM DÀI LÀ GÌ?

Trong tiếng Nhật, nguyên âm dài (長音, chōon) kéo dài thời lượng của một âm nguyên âm. Chúng rất quan trọng để phiên âm tên chính xác và phải được bảo tồn để duy trì tính xác thực.

**Các mẫu nguyên âm dài phổ biến:**
- **おう (ou)** → Phiên âm thành **-ou** hoặc **-ō** (ví dụ: みどう → Midou, こうじ → Kouji)
- **おお (oo)** → Phiên âm thành **-oo** hoặc **-ō** (ví dụ: おおの → Oono, とおる → Tooru)
- **えい (ei)** → Phiên âm thành **-ei** (ví dụ: けいこ → Keiko, せんせい → sensei)
- **いい (ii)** → Phiên âm thành **-ii** (ví dụ: にいな → Niina)
- **うう (uu)** → Phiên âm thành **-uu** (ví dụ: ゆうき → Yuuki)

---

### 1.2 HỆ THỐNG ƯU TIÊN CHO PHIÊN ÂM

**ƯU TIÊN 1: Ruby Text (Furigana)**
- Nếu có ruby text trong nguồn, **tuân theo chính xác**
- Ruby text đại diện cho ý định phiên âm của tác giả
- Ví dụ: Nếu 御堂 có ruby みどう, phiên âm thành **Midou** (không phải Mido)

**ƯU TIÊN 2: Chính tả Katakana**
- Đối với tên katakana, tuân theo katakana chính xác
- ミドウ → **Midou**, ミド → **Mido**

**ƯU TIÊN 3: Quy tắc phiên âm chuẩn**
- Khi không có ruby/katakana, áp dụng phiên âm Hepburn chuẩn
- Bảo tồn nguyên âm dài bằng định dạng **-ou/-oo/-ei/-ii/-uu**

---

## PHẦN 2: QUY TẮC PHIÊN ÂM THEO LOẠI NGUYÊN ÂM

### 2.1 MỞ RỘNG NGUYÊN ÂM O (Phổ biến nhất)

#### **Mẫu: おう (ou)**
**Quy tắc:** Phiên âm thành **-ou** (ưu tiên) hoặc **-ō** (thay thế macron)

**Tên phổ biến:**
- みどう (御堂) → **Midou** (không phải Mido)
- こうじ (浩二) → **Kouji** (không phải Koji)
- そうた (颯太) → **Souta** (không phải Sota)
- りょう (涼) → **Ryou** (không phải Ryo)

**Tại sao -ou thay vì -ō:**
- Dễ tiếp cận hơn (không cần ký tự đặc biệt)
- Hướng dẫn phát âm rõ ràng hơn cho người đọc tiếng Anh
- Phù hợp với quy ước phiên âm tiếng Nhật phổ biến

#### **Mẫu: おお (oo)**
**Quy tắc:** Phiên âm thành **-oo** (ưu tiên) hoặc **-ō** (thay thế macron)

**Tên phổ biến:**
- おおの (大野) → **Oono** (không phải Ono)
- とおる (徹) → **Tooru** (không phải Toru)
- もも (桃) → **Momo** (đã có double-o)

---

### 2.2 MỞ RỘNG NGUYÊN ÂM E

#### **Mẫu: えい (ei)**
**Quy tắc:** Phiên âm thành **-ei** (bảo tồn cả hai ký tự)

**Tên phổ biến:**
- けいこ (恵子) → **Keiko** (không phải Keko)
- れいな (玲奈) → **Reina** (không phải Rena)
- せいじ (誠司) → **Seiji** (không phải Seji)

**Ngoại lệ:** Từ phổ biến như せんせい (sensei) giữ **-ei**

---

### 2.3 MỞ RỘNG NGUYÊN ÂM I

#### **Mẫu: いい (ii)**
**Quy tắc:** Phiên âm thành **-ii** (double-i)

**Tên phổ biến:**
- にいな (新奈) → **Niina** (không phải Nina)
- しいな (椎名) → **Shiina** (không phải Shina)

---

### 2.4 MỞ RỘNG NGUYÊN ÂM U

#### **Mẫu: うう (uu)**
**Quy tắc:** Phiên âm thành **-uu** (double-u)

**Tên phổ biến:**
- ゆうき (勇気) → **Yuuki** (không phải Yuki)
- りゅう (竜) → **Ryuu** (không phải Ryu)
- しゅう (秋) → **Shuu** (không phải Shu)

---

## PHẦN 3: ỨNG DỤNG THỰC TẾ

### 3.1 QUY TRÌNH PHÁT HIỆN

**Bước 1: Kiểm tra Ruby Text**
```
Nguồn: 御堂<ruby>みどう</ruby>
Hành động: Sử dụng ruby → **Midou**
```

**Bước 2: Kiểm tra chính tả Katakana**
```
Nguồn: ミドウ・トモヤ
Hành động: Tuân theo katakana → **Midou Tomoya**
```

**Bước 3: Phân tích Hiragana/Kanji**
```
Nguồn: みどう (không có ruby)
Hành động: Áp dụng quy tắc chuẩn → **Midou**
```

---

### 3.2 QUY TẮC NHẤT QUÁN

**Quy tắc 1: Một khi đã thiết lập, khóa lại**
- Lần xuất hiện đầu tiên thiết lập phiên âm cho toàn bộ tác phẩm
- Ví dụ: Nếu "Midou" xuất hiện ở Chương 1, sử dụng "Midou" xuyên suốt

**Quy tắc 2: Đăng ký tên nhân vật**
- Duy trì đăng ký tinh thần của tất cả tên nhân vật
- Đảm bảo nhất quán qua các chương

**Quy tắc 3: Tránh trộn lẫn phong cách**
- Không trộn **-ou** và **-ō** trong cùng một tác phẩm
- Chọn một phong cách và tuân thủ

---

### 3.3 LỖI PHỔ BIẾN CẦN TRÁNH

❌ **SAI:** Bỏ nguyên âm dài hoàn toàn
```
みどう → Mido (SAI)
こうじ → Koji (SAI)
```

✅ **ĐÚNG:** Bảo tồn nguyên âm dài
```
みどう → Midou (ĐÚNG)
こうじ → Kouji (ĐÚNG)
```

❌ **SAI:** Phiên âm không nhất quán
```
Chương 1: Midou
Chương 2: Mido (KHÔNG NHẤT QUÁN)
```

✅ **ĐÚNG:** Nhất quán đã khóa
```
Chương 1: Midou
Chương 2: Midou (NHẤT QUÁN)
```

---

## PHẦN 4: TRƯỜNG HỢP ĐẶC BIỆT

### 4.1 TÊN GHÉP

**Quy tắc:** Phiên âm từng thành phần riêng biệt, sau đó kết hợp

**Ví dụ:**
- 御堂友也 (みどう ともや)
  - 御堂 (みどう) → Midou
  - 友也 (ともや) → Tomoya
  - **Kết quả: Midou Tomoya**

---

### 4.2 TÊN LỊCH SỬ/TRUYỀN THỐNG

**Quy tắc:** Một số tên truyền thống có phiên âm đã được thiết lập

**Ví dụ:**
- 東京 (とうきょう) → **Tokyo** (không phải Toukyou, quy ước đã thiết lập)
- 大阪 (おおさか) → **Osaka** (không phải Oosaka, quy ước đã thiết lập)

**Đối với Tên Nhân Vật:** Tuân theo quy tắc chuẩn trừ khi tên là nhân vật lịch sử nổi tiếng

---

### 4.3 KHI RUBY TEXT XUNG ĐỘT VỚI QUY TẮC CHUẨN

**Ưu tiên:** Ruby text LUÔN LUÔN thắng

**Ví dụ:**
```
Kanji: 御堂
Cách đọc chuẩn: みどう (Midou)
Ruby text: みど (Mido)
Hành động: Sử dụng **Mido** (tuân theo ruby)
```

**Lý do:** Ruby text của tác giả đại diện cho ý định sáng tạo của họ

---

## PHẦN 5: BẢNG THAM KHẢO NHANH

| Tiếng Nhật | Romaji | Tên ví dụ | Dịch |
|------------|--------|-----------|------|
| おう | -ou | こうじ | Kouji |
| おお | -oo | おおの | Oono |
| えい | -ei | けいこ | Keiko |
| いい | -ii | にいな | Niina |
| うう | -uu | ゆうき | Yuuki |
| そう | sou | そうた | Souta |
| とう | tou | とうや | Touya |
| のう | nou | のうみ | Noumi |
| ほう | hou | ほうじ | Houji |
| もう | mou | もうり | Mouri |
| よう | you | ようこ | Youko |
| ろう | rou | ろうた | Routa |

---

## PHẦN 6: DANH SÁCH KIỂM TRA TRIỂN KHAI

### 6.1 DANH SÁCH KIỂM TRA TRƯỚC DỊCH

- [ ] Quét nguồn cho tất cả tên nhân vật
- [ ] Kiểm tra ruby text ở lần xuất hiện đầu tiên
- [ ] Ghi chú chính tả katakana nếu được cung cấp
- [ ] Tạo đăng ký tên nhân vật
- [ ] Khóa phiên âm cho mỗi nhân vật

### 6.2 TRONG QUÁ TRÌNH DỊCH

- [ ] Áp dụng quy tắc nguyên âm dài nhất quán
- [ ] Tham chiếu chéo với đăng ký nhân vật
- [ ] Đánh dấu bất kỳ trường hợp mơ hồ nào để xem xét
- [ ] Duy trì định dạng -ou/-oo/-ei/-ii/-uu

### 6.3 XEM XÉT SAU DỊCH

- [ ] Xác minh tất cả tên khớp với lần xuất hiện đầu tiên
- [ ] Kiểm tra việc bỏ nguyên âm vô tình
- [ ] Đảm bảo không trộn lẫn phong cách (-ou vs -ō)
- [ ] Xác thực với ruby text nếu có

---

## PHẦN 7: VÍ DỤ TỪ LIGHT NOVEL THỰC TẾ

### Ví dụ 1: "I Became Friends With The Second Cutest Girl"
```
Nhân vật: 御堂友也
Ruby: みどう ともや
Phiên âm: **Midou Tomoya**
Lý do: Ruby text hiển thị みどう (nguyên âm dài có mặt)
```

### Ví dụ 2: Generic Fantasy LN
```
Nhân vật: 剣士・光二
Ruby: けんし・こうじ
Phiên âm: Kenshi **Kouji**
Lý do: こうじ có nguyên âm dài (mẫu ou)
```

### Ví dụ 3: School Romance LN
```
Nhân vật: 白洲結花
Ruby: しらす ゆいか
Phiên âm: Shirasu **Yuika**
Lý do: ゆいか không có nguyên âm dài (phiên âm chuẩn)
```

---

## PHẦN 8: NHẮC NHỞ QUAN TRỌNG

🔴 **KHÔNG BAO GIỜ bỏ nguyên âm dài mà không có lý do ruby text rõ ràng**

🔴 **LUÔN LUÔN ưu tiên ruby text hơn phiên âm chuẩn**

🔴 **DUY TRÌ nhất quán qua tất cả các chương**

🔴 **KHÓA phiên âm ở lần xuất hiện nhân vật đầu tiên**

---

## PHẦN 9: CHUYỂN ĐỔI TRAILING SOUNDS (ÂM KÉO DÀI CUỐI CÂU)

### 9.1 TỔNG QUAN

Trong tiếng Nhật, nhân vật thường kéo dài âm cuối để thể hiện cảm xúc (nhõng nhẽo, nũng nịu, mệt mỏi, phấn khích...). Những âm này thường được viết bằng hiragana nhỏ hoặc ký tự kéo dài.

**MỤC TIÊU:** Chuyển đổi trailing sounds từ format `text ぇ (ee)` thành format tự nhiên Việt Nam `texttt` hoặc `texteee`.

---

### 9.2 BẢNG CHUYỂN ĐỔI TRAILING SOUNDS

| JP Trailing | Romaji | Chuyển thành VN | Ví dụ JP | Ví dụ VN |
|-------------|--------|-----------------|----------|----------|
| **ぁ / ァ** | aa | Kéo dài nguyên âm cuối | nha ぁ | nhaa / nhaaa |
| **ぃ / ィ** | ii | Kéo dài nguyên âm cuối | đi ぃ | điii |
| **ぅ / ゥ** | uu | Kéo dài nguyên âm cuối | sao ぅ | saooo |
| **ぇ / ェ** | ee | Kéo dài nguyên âm cuối | Nè ぇ | Nèee |
| **ぉ / ォ** | oo | Kéo dài nguyên âm cuối | alo ぉ | alooo |
| **ー** | (kéo dài) | Kéo dài nguyên âm/phụ âm cuối | nha ー | nhaaa |
| **～** | (wave) | Kéo dài nguyên âm cuối | nè ～ | nèee～ |

---

### 9.3 QUY TẮC CHUYỂN ĐỔI

#### **QUY TẮC 1: Xác định nguyên âm cuối của từ Việt**

```
Từ VN kết thúc bằng: a, e, ê, i, o, ô, ơ, u, ư, y
                       ↓
Kéo dài nguyên âm đó 2-3 lần
```

#### **QUY TẮC 2: Số lần kéo dài**

- **1 trailing mark:** Kéo dài 2 lần (ee, aa)
- **2+ trailing marks hoặc ー:** Kéo dài 3 lần (eee, aaa)
- **Kết hợp với ～:** Giữ ～ ở cuối

#### **QUY TẮC 3: Xử lý tên riêng**

```
Touya ぁ → Touyaaa (kéo dài 'a' cuối)
Mei ぇ → Meiii (kéo dài 'i' cuối)
```

---

### 9.4 VÍ DỤ THỰC TẾ - ICL (In-Context Learning)

#### **❌ SAI (Giữ nguyên format ruby):**
```
「Nè ぇ (ee) Touya ぁ (aa), mua kem cho chị đi ぃ (ii). 
Nhớ chạy nhanh đó nha ぁ (aa).」
```

#### **✅ ĐÚNG (Chuyển thành VN tự nhiên):**
```
「Nèee Touyaaa, mua kem cho chị điii. 
Nhớ chạy nhanh đó nhaaa.」
```

---

#### **Ví dụ chi tiết:**

| Nguyên văn JP | SAI (Giữ ruby) | ĐÚNG (VN tự nhiên) |
|---------------|----------------|-------------------|
| 「ねぇ ねぇ」 | "Nè ぇ Nè ぇ" | "Nèee nèee" |
| 「お願いぃ」 | "Làm ơn đi ぃ" | "Làm ơn điii" |
| 「ありがとうぅ」 | "Cảm ơn ぅ" | "Cảm ơnnn" hoặc "Cảm ơn nhaaa" |
| 「えー」 | "Hả ー" | "Hảaa" hoặc "Ơơơ" |
| 「むりむり～」 | "Không không ～" | "Khônggg khônggg～" |
| 「行くよー」 | "Đi thôi ー" | "Đi thôiii" hoặc "Đi thôi nàooo" |

---

### 9.5 XỬ LÝ CẢM XÚC QUA TRAILING SOUNDS

| Cảm xúc | Pattern JP | Cách dịch VN |
|---------|-----------|--------------|
| **Nhõng nhẽo** | ぁ/ぃ kéo dài | Kéo dài nguyên âm + ngữ điệu mềm |
| **Phấn khích** | ー/～ nhiều | Kéo dài + thêm dấu chấm than |
| **Mệt mỏi** | ぁ nhẹ | Kéo dài nhẹ (2 lần) |
| **Van nài** | ぃ/ぇ | Kéo dài + ngữ điệu năn nỉ |
| **Bất ngờ** | えー | "Hảaa!?" hoặc "Ơơơ!?" |

---

### 9.6 ICL EXAMPLES CHO GEMINI

**[ICL_TRAILING_SOUND_01]**
```
INPUT: 「ねぇ とうやぁ、アイス買ってきてぇ」
OUTPUT_SAI: "Nè ぇ (ee) Touya ぁ (aa), mua kem đi ぇ (ee)"
OUTPUT_ĐÚNG: "Nèee Touyaaa, mua kem điii"
GIẢI THÍCH: Trailing sounds được chuyển thành nguyên âm kéo dài tự nhiên
```

**[ICL_TRAILING_SOUND_02]**
```
INPUT: 「えー、むりむりー！」
OUTPUT_SAI: "Ơ ー (ee), không được không được ー!"
OUTPUT_ĐÚNG: "Ơơơ, không đượccc không đượccc!"
GIẢI THÍCH: ー kéo dài âm cuối, thể hiện sự phản đối/than vãn
```

**[ICL_TRAILING_SOUND_03]**
```
INPUT: 「ありがとぅ～」
OUTPUT_SAI: "Cảm ơn ぅ (uu) ～"
OUTPUT_ĐÚNG: "Cảm ơnnn～" hoặc "Cảm ơn nhaaa～"
GIẢI THÍCH: Kéo dài âm cuối + giữ ～ để thể hiện ngữ điệu nhẹ nhàng
```

**[ICL_TRAILING_SOUND_04]**
```
INPUT: 「お兄ちゃぁん」
OUTPUT_SAI: "Anh trai ぁ (aa) ん"
OUTPUT_ĐÚNG: "Anh traiiii" hoặc "Anh ơiiii"
GIẢI THÍCH: Kéo dài nguyên âm cuối để thể hiện nhõng nhẽo
```

---

### 9.7 DANH SÁCH KIỂM TRA

- [ ] Phát hiện trailing sounds (ぁぃぅぇぉ, ー, ～)
- [ ] Xác định nguyên âm cuối của từ VN tương ứng
- [ ] Kéo dài nguyên âm 2-3 lần tùy cường độ
- [ ] Loại bỏ hoàn toàn format ruby `ぁ (aa)`
- [ ] Giữ ～ nếu có (thể hiện ngữ điệu)
- [ ] Kiểm tra tự nhiên khi đọc

---

### 9.8 LƯU Ý QUAN TRỌNG

🔴 **KHÔNG BAO GIỜ** output dạng `text ぁ (aa)` - đây là format raw, không phải bản dịch hoàn chỉnh

🔴 **LUÔN LUÔN** chuyển đổi thành dạng tự nhiên VN với nguyên âm kéo dài

🔴 **NGUYÊN TẮC:** Người đọc VN phải có thể đọc thoải mái mà không gặp ký tự lạ

🔴 **MỤC TIÊU:** Bản dịch phải "nghe" được đúng ngữ điệu mà tác giả muốn truyền tải

---

**KẾT THÚC MODULE**
