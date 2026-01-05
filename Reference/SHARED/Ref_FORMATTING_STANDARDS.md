# MODULE 07: TIÊU CHUẨN ĐỊNH DẠNG & THỰC THI

> **Trạng thái:** HOẠT ĐỘNG
> **Ưu tiên:** QUAN TRỌNG (Phải Áp dụng cho Tất cả Đầu ra)

## 1. CHUYỂN ĐỔI DẤU CÂU & KÝ HIỆU
Chuẩn hóa tất cả ký hiệu Light Novel Nhật Bản sang các tương đương xuất bản Việt Nam/Anh.

| Gốc (JP) | Đích (Chuẩn VN) | Quy tắc / Ngữ cảnh |
| :--- | :--- | :--- |
| `「` ... `」` | `“` ... `”` | Standard Dialogue Quotes. |
| `『` ... `』` | `『` ... `』` | Retain for Screen Text, Telepathy, or Magic Chants. |
| `（` ... `）` | `(` ... `)` | Convert full-width parens to half-width. |
| `……` (Ellipsis) | `...` | Convert 2-char ellipsis to 3 standard dots. |
| `——` (Dash) | `—` | Em-dash (Alt+0151). Do not use double hyphens `__`. |
| `〜` (Wave) | `~` | Convert to standard tilde or delete if tone is serious. |
| `!` `?` | `!` `?` | Remove space before punctuation (e.g., `Why ?` -> `Why?`). |

## 2. NHẤN MẠNH & KẾT CẤU
Xử lý các thẻ định dạng đặc biệt của Nhật Bản (`bouten`, `ruby`).

### 2.1 Bouten (Dấu chấm Nhấn mạnh)
- **Nguồn:** Dấu chấm đặt phía trên/bên cạnh ký tự để nhấn mạnh.
- **Chiến lược:** Chuyển đổi sang **Đậm** hoặc *Nghiêng*.
    - *Tác động Mạnh:* **Đậm** (ví dụ: "**Chạy mau!**").
    - *Tinh tế/Nội tâm:* *Nghiêng* (ví dụ: "*Có cái gì đó sai sai...*").
- **Ràng buộc:** Không lạm dụng. Chỉ áp dụng nếu nhấn mạnh thay đổi giọng điệu tự sự.

### 2.2 Ruby (Furigana)
- **Chuẩn:** Sử dụng giao thức **Ghost Ruby** (Mục 3.1 của Master Prompt).
- **Định dạng:** `Kanji (Reading)` -> Tích hợp ý nghĩa tự nhiên hoặc sử dụng thuật ngữ địa phương hóa cụ thể.

## 3. NGẮT CẢNH & PHÂN ĐOẠN
- **Ký hiệu:** Sử dụng `***` căn giữa trên dòng mới.
- **Điều kiện:** Khi cảnh chuyển thời gian, địa điểm, hoặc POV.
- **Khoảng cách:** Một dòng trống trước và sau `***`.

## 4. HIỆU ỨNG ÂM THANH (SFX)
- **Chiến lược:** Tích hợp vào dòng chảy tự sự hoặc sử dụng ký hiệu rời rạc.
- **Tham chiếu:** **Module 06 (Thư viện SFX)**.
- **Định dạng:**
    - *Tích hợp:* "Tiếng *ầm* vang lên dữ dội." (In nghiêng âm thanh).
    - *Rời rạc:* `*Cốp*` (Dòng độc lập để tác động).

## 5. THƠ & VẦN ("KHÓA DỌC")
Ngay cả khi văn bản gốc hoặc UI đối thoại ngụ ý một dòng duy nhất, **THƠ PHẢI THỞ**.

### 5.1 Quy tắc Xếp chồng Dọc
- **Bắt buộc:** NGẮT DÒNG thủ công cho mỗi câu thơ.
- **Cấm:** Không bao giờ sử dụng dấu phẩy, khoảng trắng, hoặc dấu gạch chéo để phân tách câu thơ trong đầu ra cuối cùng.

**Đúng:**
```text
Mạnh mẽ hay yếu đuối
Anh đều kể em nghe
Chỉ trừ hai chữ "Thích".
```

**Sai:**
```text
Mạnh mẽ hay yếu đuối, Anh đều kể em nghe, Chỉ trừ hai chữ "Thích".
```

### 5.2 Ngoại lệ UI/Chat
Nếu nhân vật gửi thơ qua tin nhắn văn bản:
- **Bỏ qua** ràng buộc hình ảnh của bong bóng.
- **Ưu tiên** khả năng nhìn thấy cấu trúc thơ của người đọc.

## 6. ĐỊNH DẠNG ĐỐI THOẠI
### 6.1 Dấu ngoặc kép vs. Gạch ngang
- **Mặc định:** Sử dụng dấu ngoặc kép `"`...`"` cho đối thoại nói.
- **Tùy chọn:** Sử dụng gạch ngang dài `—` cho đối thoại nói nếu phong cách đầu ra được yêu cầu là "Tiểu thuyết Việt Nam Truyền thống" (Kiểm tra sở thích người dùng). *Mặc định Dấu ngoặc kép cho Light Novel.*

### 6.2 Action Beats vs. Tags
- **Tag:** `..."anh nói."` (Chữ thường nếu là thẻ lời nói).
- **Action Beat:** `..."anh nói. Cậu ta đứng dậy."` (Viết hoa nếu là hành động riêng biệt).

## 7. PHÂN ĐOẠN
- **Quy tắc:** 1 Đoạn văn Đầu vào = 1 Đoạn văn Đầu ra.
- **Ngoại lệ:** Độc thoại nội tâm hoặc mô tả dài có thể được chia để dễ đọc nếu vượt quá 5-6 câu, nhưng nói chung tuân theo nhịp độ của tác giả.
- **Thụt lề:** Không thụt lề cho định dạng xuất bản web/txt trừ khi được chỉ định.
