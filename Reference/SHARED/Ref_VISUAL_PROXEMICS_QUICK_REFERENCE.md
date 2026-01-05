# CÔNG CỤ PROXEMICS VĂN BẢN — Hướng Dẫn Tham Khảo Nhanh
**LN VN-Translator v10.0 — Text-Based Distance Estimation**

---

## 🎯 PROXEMICS VĂN BẢN LÀ GÌ?

**Proxemics** là khoa học về khoảng cách vật lý trong giao tiếp. Trong bối cảnh dịch Light Novel, chúng ta **ước tính khoảng cách giữa các nhân vật dựa trên từ vựng và ngữ cảnh** để điều chỉnh tông giọng cảm xúc và lựa chọn đại từ.

**Lưu ý:** Module này hoạt động hoàn toàn dựa trên **text-based cues** (không cần hình ảnh).

---

## 📍 BA VÙNG KHÔNG GIAN

### VÙNG THÂN MẬT (0–45cm)

**Từ vựng gợi ý (Text Cues):**
- Động từ tiếp xúc: 触れる (chạm), 抱く (ôm), 握る (nắm tay), 撫でる (vuốt ve)
- Mô tả hơi thở: 息が触れる (hơi thở chạm vào), 吐息 (tiếng thở)
- Vị trí: 耳元で (bên tai), 顔を近づける (ghé mặt lại gần)
- Cảm giác nhiệt độ: 体温を感じる (cảm nhận thân nhiệt), 温もり (hơi ấm)

**Ví dụ văn bản:**
```
「...好きだ」と耳元で囁いた。
→ Thì thầm bên tai: "...Tớ thích cậu."
[Proxemics: THÂN MẬT - "耳元で" = bên tai]
```

**Những gì bạn làm:**
- **ĐẨY RTAS lên ≥3.5** (ngay cả khi văn bản gợi ý sự trang trọng)
- Mở khóa các đại từ ấm áp nhất: *Anh-Em*, *Cậu-Tớ*, *Tôi-Em*
- Thêm các trợ từ làm mềm: *-à*, *-nhé*, *-ơi*
- Ví dụ: "Thưa Công chúa" → "Công chúa à" (chức danh + sự yêu mến)

**Cảm xúc:** Dễ bị tổn thương tối đa, tin tưởng, hoặc thu hút

---

### VÙNG CÁ NHÂN (45cm–1.2m)

**Từ vựng gợi ý (Text Cues):**
- Vị trí: 隣に座る (ngồi bên cạnh), 向かい合う (đối diện), 並んで歩く (đi cạnh nhau)
- Hành động chung: 一緒に読む (đọc cùng nhau), 肩を並べる (sát vai)
- Giao tiếp mắt: 目を合わせる (nhìn vào mắt nhau), 視線を交わす (trao đổi ánh mắt)
- Không gian: 近くに (gần đó), そばに (bên cạnh)

**Ví dụ văn bản:**
```
二人は並んで歩いていた。
→ Hai người đi cạnh nhau.
[Proxemics: CÁ NHÂN - "並んで" = cạnh nhau]
```

**Những gì bạn làm:**
- **Giữ RTAS như được tính toán** từ văn bản
- Mở khóa các biến thể cảm xúc trong tông giọng đối thoại
- Cho phép sự trêu chọc, quan tâm ẩn giấu, từ chối vui vẻ
- Ví dụ: "Hứ!" (bĩu môi) thêm *-nha*, *-chứ*, *-kìa* để tạo hương vị Gen Z

**Cảm xúc:** Gần gũi nhưng có ranh giới xã hội; có thể thể hiện tính cách

---

### VÙNG XÃ HỘI (1.2m–3.6m)

**Từ vựng gợi ý (Text Cues):**
- Rào cản vật lý: 机を挟んで (qua bàn), 扉の向こう (bên kia cửa)
- Vị trí xa: 離れた場所 (nơi xa), 遠くから (từ xa)
- Bối cảnh công cộng: 教室で (trong lớp), 会議室 (phòng họp), 廊下 (hành lang)
- Quan sát: 見つめる (nhìn chằm chằm từ xa), 眺める (ngắm nhìn)

**Ví dụ văn bản:**
```
机を挟んで向かい合って座った。
→ Ngồi đối diện nhau qua bàn.
[Proxemics: XÃ HỘI - "机を挟んで" = qua bàn = rào cản]
```

**Những gì bạn làm:**
- **Khóa chế độ ghi đè trang trọng** ngay cả khi văn bản có vẻ ấm áp
- Sử dụng đại từ kính trọng: *Vương nữ-Thần*, *Tiểu thư-Tôi*
- Tránh các trợ từ thân mật
- Duy trì khoảng cách chuyên nghiệp trong giọng văn

**Cảm xúc:** Trang trọng, quan sát, ý thức về quyền lực

---

## 🔍 TỪ KHÓA TIẾP XÚC VẬT LÝ (PHYSICAL CONTACT KEYWORDS)

### Chạm Tóc (Điểm Nhấn Quan Trọng)

| Từ vựng Nhật | Nghĩa | Tác động RTAS | Thay đổi Tông giọng |
|---|---|---|---|
| 髪に触れる | Chạm vào tóc | Tăng +2.0 | Cực kỳ nhẹ nhàng, che chở |
| 髪を撫でる | Vuốt tóc | Tăng +2.5 | Tình cảm đỉnh điểm |
| 髪をいじる | Nghịch tóc | Tăng +1.5 | Thân mật, tinh nghịch |

**Ví dụ:**
```
彼女の髪に触れた。
→ Anh chạm vào tóc cô ấy.
[RTAS Boost: +2.0 → Chuyển sang đại từ Em-Anh nếu context cho phép]
```

---

### Nắm Tay / Ôm

| Từ vựng Nhật | Nghĩa | Tác động RTAS | Vùng |
|---|---|---|---|
| 手を握る | Nắm tay | +1.5 | Thân mật |
| 手を繋ぐ | Nắm tay (dài hạn) | +2.0 | Thân mật |
| 抱きしめる | Ôm chặt | +2.5 | Thân mật |
| 肩を抱く | Ôm vai | +1.0 | Cá nhân → Thân mật |

---

### Tư Thế / Nghiêng Người

| Từ vựng Nhật | Nghĩa | Ý nghĩa | Tác động Đại từ |
|---|---|---|---|
| 身を寄せる | Nghiêng người vào | Chủ động yếu đuối, tìm kiếm sự gần gũi | Chuyển sang *Cậu*, *Em*, *Anh* |
| 身を引く | Lùi lại | Ngại ngùng, phòng thủ | Áp dụng giọng Tsundere |
| 服を掴む | Nắm chặt quần áo | Phụ thuộc, bám víu | Đại từ dễ bị tổn thương (*Tôi-Anh*) |
| 顔を背ける | Quay mặt đi | Tsundere, xấu hổ | Gắt gỏng + ấm áp ẩn giấu |

---

## 📋 BẢNG TRA CỨU NHANH: TỪ VỰNG → VÙNG KHÔNG GIAN

| Từ khóa Nhật | Vùng | RTAS Adjustment | Ví dụ Dịch |
|---|---|---|---|
| 耳元で囁く | Thân mật | +2.0 | "Thì thầm bên tai" |
| 抱きしめる | Thân mật | +2.5 | "Ôm chặt" |
| 並んで歩く | Cá nhân | +0.5 | "Đi cạnh nhau" |
| 向かい合う | Cá nhân | 0 | "Đối diện nhau" |
| 机を挟んで | Xã hội | -1.0 | "Qua bàn" (trang trọng) |
| 遠くから見る | Xã hội | -1.5 | "Nhìn từ xa" |

---

## 🧮 CÔNG THỨC PROXEMICS VĂN BẢN

```
RTAS CƠ BẢN (từ phân tích hội thoại)
    ↓
+ ĐIỀU CHỈNH VÙNG KHÔNG GIAN (từ từ vựng vị trí)
    ↓
+ TĂNG CƯỜNG TIẾP XÚC VẬT LÝ (từ động từ chạm/ôm)
    ↓
+ ĐIỀU CHỈNH TƯ THẾ (nghiêng vào/ra, quay mặt)
    ↓
= RTAS CUỐI CÙNG CHO QUYẾT ĐỊNH ĐẠI TỪ
```

**Ví dụ:**
```
Input: 「姫様...」と彼女の髪に触れながら囁いた。

Phân tích:
- Văn bản: "姫様" (Công chúa) → RTAS cơ bản = 2.0 (trang trọng)
- Vùng: "囁いた" (thì thầm) → Thân mật → +1.5
- Tiếp xúc: "髪に触れる" (chạm tóc) → +2.0
- RTAS Cuối: 2.0 + 1.5 + 2.0 = 5.5 → Giới hạn tối đa 5.0

Output: "Công chúa à..." anh thì thầm, nhẹ nhàng chạm vào tóc cô.
[Đại từ: Anh-Cô (thay vì Thần-Vương nữ) vì RTAS = 5.0]
```

---

## ✅ DANH SÁCH KIỂM TRA PHÂN TÍCH

Trước khi dịch một đoạn văn:

- [ ] **Quét từ khóa vị trí:** 隣, 向かい, 遠く, 近く, そば
- [ ] **Kiểm tra động từ tiếp xúc:** 触れる, 抱く, 握る, 撫でる
- [ ] **Ghi chú tư thế:** 身を寄せる, 身を引く, 顔を背ける
- [ ] **Xác định vùng không gian:** Thân mật / Cá nhân / Xã hội
- [ ] **Tính toán RTAS Adjustment:** Cộng/trừ điểm dựa trên bảng tra cứu
- [ ] **Chốt quyết định đại từ:** Dựa trên RTAS cuối cùng
- [ ] **Ghi lại khối PHÂN TÍCH PROXEMICS** (nếu cần)

---

## 📝 MẪU NHẬT KÝ TƯ DUY (THINKING LOG)

Khi thực hiện phân tích Proxemics, ghi lại như sau:

```
[PHÂN TÍCH PROXEMICS VĂN BẢN]

**Từ khóa Vị trí:** [vd: 耳元で = bên tai]
**Vùng Không gian:** [Thân mật/Cá nhân/Xã hội]

**Động từ Tiếp xúc:**
- [vd: 髪に触れる = chạm tóc → +2.0]

**Tư thế/Ngôn ngữ Cơ thể:**
- [vd: 身を寄せる = nghiêng vào → tìm kiếm sự gần gũi]

**Tính toán RTAS:**
- Cơ bản (từ hội thoại): 2.0
- Vùng (Thân mật): +1.5
- Tiếp xúc (Chạm tóc): +2.0
- **RTAS Cuối cùng: 5.5 → Giới hạn 5.0**

**Quyết định Đại từ:**
- Văn bản gốc: "姫様" (Công chúa - trang trọng)
- Proxemics cho phép: "Công chúa à" (trang trọng + hậu tố dịu dàng)
- Cặp đại từ: Anh-Cô (thay vì Thần-Vương nữ)
- Tông giọng: Nhẹ nhàng, che chở, tình cảm
```

---

## 🎓 QUY TẮC TỐI THƯỢNG

**Khi từ vựng gợi ý khoảng cách gần (Thân mật/Cá nhân), HÃY TIN VÀO TỪ VỰNG.**

Các động từ tiếp xúc (触れる, 抱く, 握る) và từ vị trí (耳元, そば, 隣) là bằng chứng khách quan về khoảng cách vật lý. Ngay cả khi đối thoại có vẻ trang trọng, hãy điều chỉnh tông giọng để phản ánh sự thân mật thực tế.

---

## 🔄 SO SÁNH: TRƯỚC VÀ SAU KHI ÁP DỤNG PROXEMICS

### Ví dụ 1: Chạm tóc

**Input:**
```
「姫様...」と彼女の髪に触れた。
```

**Trước (Không Proxemics):**
```
"Công chúa..." anh chạm vào tóc cô ấy.
[RTAS: 2.0 - Trang trọng thuần túy]
```

**Sau (Có Proxemics):**
```
"Công chúa à..." anh thì thầm, nhẹ nhàng chạm vào tóc cô.
[RTAS: 5.0 - Trang trọng + Tình cảm đỉnh điểm]
[Proxemics Boost: +3.0 từ "髪に触れる"]
```

---

### Ví dụ 2: Ngồi đối diện qua bàn

**Input:**
```
机を挟んで向かい合って座った。
```

**Trước:**
```
Ngồi đối diện nhau.
[RTAS: 3.0 - Bình thường]
```

**Sau (Có Proxemics):**
```
Ngồi đối diện nhau qua bàn.
[RTAS: 2.0 - Xã hội, có rào cản]
[Proxemics Penalty: -1.0 từ "机を挟んで" = qua bàn]
[Giữ tông giọng trang trọng hơn]
```

---

## 📚 TỪ VỰNG BỔ SUNG: KHOẢNG CÁCH & VỊ TRÍ

### Thân mật (0-45cm)
- 耳元で (bên tai)
- 顔を近づける (ghé mặt lại gần)
- 抱き合う (ôm nhau)
- 頬を寄せる (ghé má vào)
- 息が触れる (hơi thở chạm vào)

### Cá nhân (45cm-1.2m)
- 隣に座る (ngồi bên cạnh)
- 並んで (cạnh nhau)
- 向かい合う (đối diện)
- そばに (bên cạnh)
- 肩を並べる (sát vai)

### Xã hội (1.2m-3.6m)
- 離れた場所 (nơi xa)
- 遠くから (từ xa)
- 机を挟んで (qua bàn)
- 扉の向こう (bên kia cửa)
- 廊下の端 (cuối hành lang)

---

**Cập nhật lần cuối:** 31 Tháng 12, 2024 — LN VN-Translator v10.0 (Text-Based Proxemics)
