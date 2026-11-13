# Tư vấn cập nhật: kênh Reels "Built That Way" với thư viện 2.0.0

Ngày 13/11/2026. Bản này cập nhật [tư vấn của kongming](kongming-261113-1406-facebook-reels-us.md), sau khi thư viện lên 2.0.0 và có thêm 33 phong cách. Cách chấm điểm từng phong cách nằm trong [bản scout](scout-261113-1450-new-styles-reels-fit.md).

## Kết luận

- Vẫn làm kênh **"Built That Way"**: clip dọc 25–40 giây, giải thích vì sao đồ vật quanh ta được thiết kế như vậy, cho người xem Mỹ.
- Bản 2.0.0 có một phong cách hợp với kênh hơn mọi phong cách cũ: **Color-Coded Mechanism (`precise-mechanism`)**. Vì vậy tôi đề xuất **dùng hai lối hình, mỗi series một lối**, thay vì một lối duy nhất như bản tư vấn trước.
- Trở ngại thật sự là **chưa phong cách nào làm sẵn khung dọc 9:16**. Mọi demo, kể cả Isometric Whiteboard của bạn, đều cố định 1920×1080 trong code. Phải làm bộ khung dọc trước khi sản xuất.

## Phong cách mới hợp với kênh (thang 0–3)

| Phong cách | Điểm | Vì sao | Lưu ý |
|---|---|---|---|
| `precise-mechanism` · Color-Coded Mechanism | 3 | Cơ cấu 3D thật, mỗi hệ thống một màu, đúng tỷ lệ. Động tác sẵn có: cắt ngang, tháo theo từng hệ thống, theo đường đi của lực, quay chậm một điểm tiếp xúc. Ví dụ nó tự liệt kê: ổ khoá, van, bánh cóc, líp xe (`STYLE.md:82-86`) | Render nặng (three.js) |
| `hardcore-info` · Line-Art Cutaway | 3 | Bản vẽ cắt lớp nét đen, đúng kích thước milimét, một màu nhấn cho đường đi | Chữ mặc định nhỏ (21 px), phải phóng to cho điện thoại |
| `instruction-manual` · Instruction Manual Art | 2–3 | Trang hướng dẫn lắp ráp, có vòng kính lúp và ô nên/không nên | Không được có thương hiệu, logo hay khuôn mặt |
| `security-xray` · Security X-ray | 2 | Soi bên trong đồ vật | Bảng điều khiển máy quét dễ làm chật khung dọc |
| `marker-paper` · Marker on Paper | 2 | Rẻ nhất (Canvas 2D), nét dày, dễ đọc trên điện thoại | — |
| `assembly-line-diagram` · Assembly-Line Diagram | 2 | Quy trình từng bước, như bồn cầu xả nước hay máy rửa bát | Tối đa khoảng 7 cụm chữ mỗi khung |

**Loại ra:**
- 4 phong cách cần công cụ tạo ảnh (✦), vì phải đăng nhập Codex và cũng không hợp kênh.
- `neon-tubes`, vì STYLE.md ghi rõ không có thanh phụ đề (`STYLE.md:43`).
- `firefly-pointillism` và `oscilloscope-math`, vì khung 1920×1080 cố định trong code.

**Bản 2.0.0 không làm hỏng gì của bạn.** Isometric Whiteboard và các phong cách trong kế hoạch cũ (whiteboard, iso-infographic, halftone-dossier, engraving, midcentury-toon, woodcut) chỉ đổi dữ liệu catalog, không đổi engine, khung hay giọng.

## Đề xuất

1. **Hai lối hình, mỗi series một lối.**
   - *Hidden Design* và *Wrong Since School*: **Isometric Whiteboard**. Render nhẹ, rẻ, đã kiểm chứng qua phim máy bay, hợp nhịp đăng hằng ngày.
   - *Cut It Open*: **precise-mechanism**. Tô màu từng hệ thống nên người xem hiểu cả khi tắt tiếng. Render nặng, nên chỉ làm 1–2 tập mỗi tuần.
   - Phương án thay thế cho *Cut It Open* nếu precise-mechanism không ổn ở khung dọc: `hardcore-info`.
2. **Bước 0: khung dọc.**
   - Dựng lại bố cục 1080×1920 cho Isometric Whiteboard. Kích thước đang cố định ở `demo/index.html:5` và `frame.js:77,114`.
   - Đổi font chữ sang font tiếng Anh (hiện là Be Vietnam Pro).
   - Đặt chữ ở vùng giữa phía trên, tránh phần trên khoảng 15% và dưới khoảng 35–45% mà giao diện app che.
   - Render thử precise-mechanism ở 1080×1920, kiểm tra vật thể và màu còn rõ không.
3. **Hai tập mẫu đầu tiên:**
   - *"The tiny hole in every airplane window"* bằng Isometric Whiteboard, tận dụng kinh nghiệm phim máy bay.
   - *"How a pin-tumbler lock actually works"* bằng precise-mechanism; ổ khoá nằm đúng trong danh sách ví dụ của style.
   - Cả hai dài 25–40 giây, giọng Kokoro giọng Mỹ, có phụ đề, đăng Facebook và YouTube Shorts cùng lúc. Sau 10 tập, lối hình nào giữ người xem tốt hơn thì nghiêng về lối đó.
4. **Giữ nguyên nguyên tắc của bản tư vấn trước:**
   - mỗi tập có `FACTS.md` ghi nguồn, dùng đơn vị Mỹ;
   - khung cuối lặp lại khung đầu;
   - đăng 7–9 giờ sáng giờ Việt Nam;
   - tiền chủ yếu đến từ YouTube, vì Facebook chưa mở kiếm tiền cho Việt Nam.

## Giấy phép

Từ 2.0.0, các file tài liệu của style chuyển sang CC BY-NC 4.0, nhưng phim bạn làm bằng thư viện là của bạn, dùng thương mại được (`LICENSE`, mục "FILMS YOU MAKE"). Kênh có kiếm tiền không bị ảnh hưởng.

## Câu hỏi còn mở

1. Dùng hai lối hình như trên, hay giữ một lối duy nhất? Hai lối thì kênh có chiều sâu hơn nhưng tốn công hơn.
2. Có bắt đầu Bước 0 (khung dọc cho Isometric Whiteboard và render thử precise-mechanism) rồi làm hai tập mẫu ngay không?
