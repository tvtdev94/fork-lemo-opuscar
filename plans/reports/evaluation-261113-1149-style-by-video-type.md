# Đánh giá 66 phong cách Lemo-Opuscar theo loại video

Ngày 13/11/2026. Báo cáo dựa trên ba nguồn:

- **Mã nguồn và tài liệu của thư viện.** Đã đọc toàn bộ 66 file `styles/<folder>/STYLE.md` và `style.json`, kèm kết quả làm 60 clip mẫu 5 giây. Bản tóm tắt chi tiết, có số dòng nguồn, nằm ở [`scout-261113-1140-style-digest.md`](scout-261113-1140-style-digest.md).
- **Tìm kiếm web.** Gồm số liệu nền tảng (Vidyard, Wistia, Reuters), nghiên cứu học thuật (Mayer, Guo 2014, các tổng quan về video y khoa) và bài xu hướng 2025–2026 của các studio. Bản đầy đủ, có link, nằm ở [`researcher-261113-1140-video-types-styles.md`](researcher-261113-1140-video-types-styles.md).
- **Kinh nghiệm thực tế trong dự án.** Gồm 60 clip mẫu, 7 phim đã làm, và style riêng của bạn là Isometric Whiteboard.

## 1. Kết luận chính

1. **Nên nhóm theo mục đích video, không nên nhóm theo định dạng.** Gần như phong cách nào cũng cắt được thành clip ngắn hay clip dọc, nên chia theo định dạng thì phong cách nào cũng rơi vào mọi nhóm. Tôi chia 66 phong cách thành **14 nhóm mục đích**. Mỗi phong cách có 1 nhóm chính và tối đa 2 nhóm phụ, kèm một **nhãn tông**: nghiêm túc, trung tính hoặc vui nhộn. Nhãn tông là thứ chặn được lỗi chọn sai nặng nhất, ví dụ dùng hoạt hình nhí nhố cho chủ đề y tế hay tài chính.
2. **Chưa có nghiên cứu nào chứng minh "phong cách X hiệu quả nhất cho loại Y".**
   - Bằng chứng cứng chỉ có ở mức tổng quát:
     - Video ngắn được xem hết nhiều hơn.
     - Hoạt hình có lời đọc giúp hiểu và nhớ tốt hơn chữ hoặc người nói trước máy quay. Bằng chứng mạnh nhất là ở video giáo dục bệnh nhân.
     - Biểu đồ động chỉ hiệu quả khi lời đọc chỉ vào chỗ thay đổi.
     - Phụ đề giúp người xem tắt tiếng vẫn hiểu.
   - Mọi ghép cặp phong cách–loại video trong báo cáo này là **nhận định chuyên môn**, không phải số liệu đo được.
   - Số liệu nổi tiếng "whiteboard giúp nhớ hơn 15%" do chính một hãng bán phần mềm whiteboard đặt làm và chưa được bình duyệt.
3. **Thư viện đang đi đúng xu hướng 2025–2026.** Các phong cách thủ công, in ấn, giấy, cổ điển và "phim tài liệu đồ hoạ" đang lên. Ngược lại, hình minh hoạ phẳng kiểu "Corporate Memphis", motion graphics làm theo template và hình bóng bẩy kiểu AI đang bão hoà. Khảo sát 2025–2026 cho thấy người xem tin quảng cáo trông như AI làm ít hơn. Vì vậy cái chất "dựng bằng code, có tay nghề" của thư viện là lợi thế, nên nói rõ khi giới thiệu.
4. **Ba lỗ hổng lớn của thư viện:**
   - **Clip dọc 9:16:** chỉ Caption News có bố cục dọc được viết sẵn. Công cụ render nhận `--size 1080x1920`, nhưng 65 phong cách còn lại chưa ai kiểm tra ở khung dọc.
   - **Phong cách Việt Nam:** chưa có phong cách nào thuần Việt như múa rối nước hay tranh Đông Hồ. Các phong cách Á Đông hiện có đều mang thẩm mỹ Trung Quốc hoặc Nhật Bản.
   - **Chữ chuyển động cho MV lời bài hát và mạng xã hội:** chưa có phong cách nào. Swiss Motion ghi rõ nó *không phải* chữ động kiểu lời bài hát.

## 2. Cách đọc bảng

- **Tông:** 🟦 nghiêm túc · ⬜ trung tính · 🟨 vui nhộn. Với chủ đề y tế, tài chính, tai nạn hay mất mát, không dùng phong cách 🟨.
- **Đầu vào cần có:**
  - **Code:** máy tự vẽ toàn bộ, chỉ cần ý tưởng.
  - **Số liệu:** cần dữ liệu thật có giấy phép mở.
  - **Ảnh/scan:** cần ảnh thật, ảnh vệ tinh hoặc bản scan lưu trữ.
  - **Footage:** cần video quay thật.
- **Render:** Nhẹ là Canvas 2D hoặc SVG. Vừa là 2D có thêm WebGL hoặc phải xử lý footage. Nặng là cảnh 3D three.js, sẽ chậm trên card GTX 950 vì máy chỉ render tuần tự được một luồng. Mức nặng nhẹ là tôi suy ra từ loại engine, không có số đo thời gian.
- **Đánh giá** (nhận định của tôi, gộp độ phù hợp, độ dễ làm, xu hướng và kết quả clip mẫu):
  - ★★★ Nên dùng trước: hợp nhiều việc, chỉ cần code, đã chạy ổn.
  - ★★ Tốt khi dùng đúng việc.
  - ★ Chuyên biệt, đầu vào khó hoặc có rủi ro.

## 3. 14 nhóm theo loại video

Mỗi nhóm ghi chuẩn định dạng thường gặp, phong cách nên dùng (nhóm chính), phong cách dùng được (nhóm phụ) và điều cần lưu ý.

### G1 · Giải thích kiến thức, bài giảng
- **Chuẩn:**
  - Video giải thích để marketing dài 60–120 giây. Bài giảng nên chia đoạn dưới 6 phút, vì Guo 2014 đo trên 6,9 triệu lượt xem thấy thời gian xem trung vị không vượt 6 phút.
  - Khung 16:9, gần như luôn có lời đọc.
  - Mỗi ý một nhịp, hình vẽ dần theo lời.
- **Nên dùng:**
  - **Isometric Whiteboard**: style riêng của bạn, ★★★.
  - Whiteboard ★★★, Isometric Infographic ★★★, Isometric Picture Book ★★★.
  - Chalkboard ★★, Pictogram Motion ★★.
- **Dùng được:** Mid-century Cartoon, One-line, Blueprint, Circuit Board, Memphis Diorama, Desktop Flythrough.
- **Lưu ý:**
  - Theo nguyên tắc của Mayer, mũi tên, tô sáng và vẽ dần theo lời giúp người xem học tốt hơn. Họa tiết trang trí đè lên thông tin chính thì làm hại.
  - Chalkboard được xây quanh thứ tự nét chữ Hán, nên với chữ Việt chỉ dùng được một phần đặc trưng.

### G2 · Ra mắt sản phẩm, keynote
- **Chuẩn:**
  - Phim chính dài 1–3 phút, cắt thêm bản 6, 15 và 30 giây.
  - Thường dẫn bằng nhạc, lời đọc ít.
  - Mở ra chậm rồi chuyển nhanh qua các thông số.
- **Nên dùng:**
  - Dark Tech Keynote ★★★ cho phần mềm.
  - Glass Product ★★, Sci-fi Hologram HUD ★★, Blueprint ★★.
  - Exploded Teardown ★, vì cần file CAD.
- **Dùng được:** Data Physicalization, Circuit Board, Live Countdown, Desktop Flythrough, Brick Toy.
- **Lưu ý:**
  - **Glass Product chỉ cho phép vật thể hư cấu** (STYLE.md dòng 6). Muốn quảng cáo sản phẩm thật thì dùng Teardown (cần CAD), Living Screencast (cho phần mềm) hoặc Blueprint.
  - Lối ra mắt kiểu Apple, với render 3D trên nền đen, vẫn là chuẩn ngành năm 2026. Đây là nhận định của các studio, không có số liệu.

### G3 · Hướng dẫn sử dụng, onboarding, đào tạo nội bộ
- **Chuẩn:**
  - Video demo 60 giây đến 3 phút. Bài đào tạo 2–5 phút, mỗi bài một mục tiêu.
  - Có lời đọc. Nêu vấn đề trong 10 giây đầu, phóng to vào thao tác và giữ 2–3 giây.
- **Nên dùng:**
  - Mid-century Cartoon ★★★: chính style này liệt kê các việc hướng dẫn lắp đặt, thẻ an toàn, công thức nấu ăn và onboarding ứng dụng.
  - Living Screencast ★★, Desktop Flythrough ★★, ASCII/CRT ★★ (cho công cụ lập trình viên).
- **Dùng được:** Isometric Picture Book, Whiteboard, Microgame (onboarding kiểu trò chơi), Briefing Board.
- **Lưu ý:**
  - Năm 2026, giao diện bịa hoặc dashboard chung chung trong video demo làm người xem mất tin tưởng.
  - Living Screencast bắt buộc vẽ lại giao diện **thật** của sản phẩm.

### G4 · Phim thương hiệu, câu chuyện doanh nghiệp
- **Chuẩn:** dài 1–3 phút, có tuyên ngôn hoặc chỉ dùng nhạc, đi theo một mạch cảm xúc.
- **Nên dùng:**
  - One-line ★★★, Impasto ★★, Risograph ★★, Art Deco ★★ (sang trọng, khách sạn), Swiss Motion ★★ (nhận diện thương hiệu).
  - Constructivist Montage ★: cần footage lưu trữ, và quyền sử dụng tư liệu trong clip mẫu chỉ suy luận chứ chưa xác minh.
- **Dùng được:** Archive Light Table (lịch sử thương hiệu), Woodcut (thương hiệu thủ công), Urban Sketch (lifestyle), Watercolor, Paper-cut Lightbox, Glass Product.
- **Lưu ý:** tránh lối minh hoạ phẳng chung chung. Khi bài là về *con người* thật, người xem thường tin video quay thật hơn hoạt hình.

### G5 · Tin tức, thời sự, thể thao, sự kiện trực tiếp
- **Chuẩn:**
  - Bản cho mạng xã hội dài 30–90 giây, dọc hoặc vuông, chỉ có phụ đề. Phóng sự truyền hình 1,5–3 phút, khung 16:9, có giọng đọc.
  - Đòi hỏi chính xác, có nguồn, giọng trung lập.
- **Nên dùng:**
  - Broadcast News Package ★★: dựng hoàn toàn bằng code được, footage không bắt buộc.
  - Caption News ★★: phong cách duy nhất có bố cục 9:16, nhưng cần footage.
  - Sports Telestrator ★★, cần footage trận đấu và quyền dùng hình.
  - Live Countdown ★: cần footage nhiều góc của cùng một sự kiện.
- **Dùng được:** Satellite Briefing, Visual Investigation.
- **Lưu ý:** theo Reuters 2025, tin tức dạng video trên mạng xã hội tăng từ 52% lên 65%, và TikTok là nguồn tin tăng nhanh nhất ở Đông Nam Á. Vì vậy bản dọc rất quan trọng với khán giả Việt.

### G6 · Phim tài liệu, điều tra
- **Chuẩn:** 5–20 phút trên YouTube hoặc 2–5 phút cho mạng xã hội. Khung 16:9, có lời đọc, giữ hình lâu trên bằng chứng.
- **Nên dùng:**
  - Satellite Briefing ★★.
  - Visual Investigation ★, LiDAR Survey ★, Projection on White Model ★. Cả ba đều cần dữ liệu hoặc footage thật, công sức lớn.
- **Dùng được:** Archive Light Table, 1920s Newsreel, Halftone Dossier (điều tra mang tính hài), Microscope.
- **Lưu ý:**
  - Nghiên cứu về mảng Visual Investigations của NYT cho thấy người xem tin vì *bằng chứng hiện trên màn hình*, không phải vì hình đẹp.
  - Dữ liệu toà nhà 3D mở ở Việt Nam có thể hiếm, nên White Model khó dùng cho địa danh Việt. Điều này chưa kiểm chứng.

### G7 · Dữ liệu, báo cáo, báo cáo thường niên
- **Chuẩn:** dài 1–4 phút. Mỗi chuyển động của biểu đồ gắn với một câu thoại. Kết thúc bằng một khung hình tĩnh dễ đọc.
- **Nên dùng:**
  - Data Storytelling ★★★, nếu có số liệu thật.
  - Data Physicalization ★★, Engineering Briefing Board ★★, Circuit Board ★★.
  - Transit Map ★★: hợp với tăng trưởng theo thời gian, mạng lưới, lộ trình.
- **Dùng được:** Isometric Infographic, Game Show Flat (tổng kết năm), Caption News (clip dữ liệu ngắn), Tilt-Shift.
- **Lưu ý:**
  - Biểu đồ động không có lời chỉ vào chỗ thay đổi khiến người xem đọc sai nhiều hơn (Robertson 2008).
  - Không bịa số liệu: Data Storytelling và Data Physicalization đều bắt buộc dùng dữ liệu thật và ghi nguồn.

### G8 · Thiếu nhi
- **Chuẩn:** bài hát hoặc đoạn ngắn 2–4 phút, truyện 5–11 phút. Khung 16:9, có lời đọc hoặc bài hát. Nên để nhịp chậm.
- **Nên dùng:** Crayon Picture Book ★★★, Paper Pop-up Book ★★, Brick Toy ★★.
- **Dùng được:**
  - Red Paper-cut (truyện dân gian), 1930s Rubber Hose, Low-poly Island (nội dung êm), Shadow Puppetry, Mid-century Cartoon.
  - HD-2D và Stained Glass hợp với truyện cổ tích.
- **Lưu ý:**
  - Bằng chứng về việc nhịp nhanh có hại cho trẻ chưa thống nhất, nhưng phụ huynh và giới nhi khoa phản đối mạnh.
  - Mặc định nên để cảnh dài và màu dịu.
  - Brick Toy không được dùng tên, logo hay minifig LEGO.

### G9 · Mở màn sự kiện, title sequence, trailer, game
- **Chuẩn:**
  - Phần mở màn dài 30–90 giây, trailer khoảng 2 phút.
  - Dẫn bằng nhạc và chữ, nhịp tăng dần đến cao trào.
  - Màn LED sự kiện thường siêu rộng, nên thiết kế đúng khung màn hình thật.
- **Nên dùng:**
  - 60s Spy Titles ★★, HD-2D ★★, 16-bit Pixel RPG ★★, Low-poly Island ★★.
  - Liminal Found Footage ★: ngách kinh dị, bí ẩn, trò chơi ARG.
- **Dùng được:** Art Deco (gala), Live Countdown, Swiss Motion, Woodcut (trailer sách), Microgame, 80s Cel Anime, Paper Pop-up, ASCII/CRT, Hologram HUD, Silkscreen Poster (poster sự kiện).
- **Lưu ý:** pixel art đang bão hoà (một studio chấm 9/10 về độ bão hoà), nên Pixel RPG cần một góc kể chuyện riêng mới nổi bật.

### G10 · Âm nhạc, MV, loop không khí
- **Chuẩn:**
  - Cả bài hát 2,5–4 phút. Spotify Canvas là loop 3–8 giây. Đoạn hook cho mạng xã hội 15–30 giây.
  - Không có lời đọc. Cắt theo nhịp nhạc.
- **Nên dùng:**
  - 80s Cel Anime ★★.
  - Time-lapse Symphony ★★: cần footage, hoàn toàn không lời đọc.
  - Memphis Diorama ★★: loop nền, nhạc tập trung, chuỗi theo mùa. Bắt buộc 60 fps.
- **Dùng được:** Impasto, Constructivist Montage, Swiss Motion, Risograph, Chinese Ink Wash, Low-poly Island.
- **Lưu ý:** thư viện **chưa có phong cách chữ chuyển động cho lời bài hát**, trong khi các nguồn coi đây là dạng phổ biến nhất của lyric video.

### G11 · Du lịch, địa danh, giới thiệu thành phố
- **Chuẩn:**
  - Dài 30 giây đến 2 phút, có cả bản 16:9 và 9:16.
  - Thường là nhạc kèm chữ, lời đọc tuỳ chọn. Nhịp trữ tình.
- **Nên dùng:**
  - Silkscreen Travel Poster ★★★, Urban Sketch ★★★.
  - Paper-cut Lightbox ★★, Tilt-Shift Miniature ★★.
  - Printed Long Take ★★: clip mẫu bị đá che một phần chữ tiêu đề.
- **Dùng được:** Watercolor, Transit Map, Time-lapse Symphony, Ukiyo-e, Memphis Diorama.
- **Lưu ý:**
  - Các chiến dịch du lịch 2025 thiên về lối vẽ phóng đại, cảnh dựng tay kiểu stop-motion và "du lịch chậm" dẫn bằng âm thanh.
  - Không tìm thấy chiến dịch 2025 nào dùng kiểu poster du lịch, nên Silkscreen là một canh bạc về tay nghề, chưa phải công thức đã được chứng minh.

### G12 · Lịch sử, văn hoá, di sản, lễ hội
- **Chuẩn:** dài 2–10 phút, khung 16:9, có lời đọc. Kể chuyện chậm rãi, tôn trọng nguồn gốc văn hoá.
- **Nên dùng:**
  - Woodcut ★★★: phim *Giấy dó* đã làm bằng phong cách này.
  - Red Paper-cut ★★★: hợp Tết, Trung thu. Clip mẫu đèn ông sao chạy ổn.
  - Archive Light Table ★★, Shadow Puppetry ★★, Chinese Ink Wash ★★.
  - 1920s Newsreel ★, Stained Glass ★, Ukiyo-e ★.
- **Dùng được:** Copperplate Engraving, Constructivist Montage, LiDAR Survey (khảo cổ), Paper-cut Lightbox.
- **Lưu ý:**
  - Dùng thủy mặc, ukiyo-e hay cắt giấy Trung Hoa cho chủ đề *thuần Việt* dễ bị xem là lệch văn hoá. Đây là nhận định, chưa có nguồn đo. Ví dụ, ngoài Ink Wash thì Ukiyo-e cũng đã được dùng cho vịnh Hạ Long.
  - Shadow Puppetry gần với múa rối, nhưng là rối bóng da kiểu Trung Quốc.
  - Font bút lông gợi ý cho Ukiyo-e thiếu dấu tiếng Việt.
  - Newsreel có giọng hớn hở, không dùng cho thảm hoạ.
  - Stained Glass chỉ cho nội dung thế tục.

### G13 · Khoa học, sức khoẻ, y khoa
- **Chuẩn:** dài 2–6 phút, khung 16:9, có lời đọc. Đi bình tĩnh từng bước. Chính xác, không gây sợ, không đùa cợt.
- **Nên dùng:**
  - Watercolor ★★★: phim tài liệu thiên nhiên.
  - Microscope Story ★★: cần ảnh hiển vi có giấy phép.
  - Copperplate Engraving ★★: nhãn bảo tàng, "một phút về…", hình minh hoạ sách giáo khoa.
- **Dùng được:** Whiteboard, Data Storytelling, Satellite Briefing (khí hậu), Isometric Infographic, Printed Long Take (động vật hoang dã).
- **Lưu ý:**
  - Đây là nhóm có **bằng chứng mạnh nhất**: tổng quan 38 thử nghiệm năm 2022 và bản cập nhật 2026 cho thấy hoạt hình có lời đọc giúp bệnh nhân hiểu tốt hơn tài liệu in.
  - Lợi ích này đến từ *hoạt hình có lời đọc*, không đến từ một phong cách cụ thể.
  - Microscope chỉ mô tả, không bao giờ chẩn đoán.

### G14 · Hài, giải trí, clip mạng xã hội ngắn
- **Chuẩn:**
  - Dài 15–60 giây, khung 9:16. Hook trong 1–3 giây. Chạy được khi tắt tiếng và có thể lặp lại.
  - 63% quảng cáo top của TikTok đặt thông điệp trong 3 giây đầu. Số liệu này lấy gián tiếp qua bên thứ ba.
- **Nên dùng:**
  - Halftone Dossier ★★★: "hồ sơ vụ án" nghiêm trang cho chuyện vặt, hợp clip viral.
  - Sci-Fi Sitcom ★★, Game Show Flat ★★, Microgame ★★, 1930s Rubber Hose ★★.
  - 1920s Silent Film ★★: không lời đọc.
- **Dùng được:** Risograph, Pixel RPG, ASCII/CRT, Caption News, Pictogram Motion, 1920s Newsreel.
- **Lưu ý:**
  - Sci-Fi Sitcom cần hội thoại hai giọng có khớp khẩu hình, tốn công làm giọng nhất. Không nhái phim có bản quyền: đây cũng là lý do bản "Family Guy" trước đây được làm thành nhân vật gốc.
  - Đây là nhóm có tông 🟨 cao nhất, không dùng cho chủ đề nghiêm túc.

## 4. Bảng tra đủ 66 phong cách và style riêng của bạn

Cột "Nhóm chính" và "Nhóm phụ" dùng mã nhóm ở mục 3.

| # | Phong cách (folder) | Nhóm chính | Nhóm phụ | Tông | Đầu vào | Render | Đánh giá | Ghi chú |
|---|---|---|---|---|---|---|---|---|
| ★ | Isometric Whiteboard (`~/lemo-my-styles/iso-whiteboard`) | G1 | G3, G13 | ⬜ | Code | Nhẹ | ★★★ | Style riêng của bạn, đã dùng cho phim máy bay |
| 1 | Caption News (`caption-news`) | G5 | G7, G14 | ⬜ | Footage + tài liệu nguồn | Vừa | ★★ | Duy nhất có bố cục 9:16 |
| 2 | 1920s Newsreel (`newsreel`) | G12 | G14 | 🟨 | Footage lưu trữ | Vừa | ★ | Không dùng cho thảm hoạ; khung 1.37:1 |
| 3 | Live Countdown (`countdown`) | G5 | G2, G9 | ⬜ | Footage nhiều góc | Vừa | ★ | Đầu vào khó nhất thư viện |
| 4 | Time-lapse Symphony (`city-symphony`) | G10 | G11, G9 | ⬜ | Footage địa điểm | Vừa–nặng | ★★ | Không lời đọc; khung 1.85:1 |
| 5 | Visual Investigation (`visual-investigation`) | G6 | G5 | 🟦 | Footage + ảnh + tài liệu | Vừa | ★ | Công sức tư liệu lớn |
| 6 | Constructivist Montage (`kino-montage`) | G4 | G12, G10 | ⬜ | Footage lưu trữ | Vừa | ★ | Quyền dùng tư liệu chỉ suy luận (clip mẫu) |
| 7 | Sports Telestrator (`telestrator`) | G5 | — | ⬜ | Footage trận đấu | Vừa | ★★ | Cần quyền dùng hình trận đấu |
| 8 | Broadcast News Package (`news-package`) | G5 | G7 | 🟦 | Số liệu nguồn; hình tuỳ chọn | Nhẹ–vừa | ★★ | Làm hoàn toàn bằng code được |
| 9 | Satellite Briefing (`satellite-briefing`) | G6 | G5, G13 | 🟦 | Ảnh vệ tinh mở | Vừa | ★★ | Landsat/Sentinel, không dùng Google |
| 10 | Engineering Briefing Board (`briefing-board`) | G7 | G2, G3 | 🟦 | Ảnh thật đồ vật | Nhẹ–vừa | ★★ | So sánh phương án kỹ thuật |
| 11 | LiDAR Survey (`lidar-survey`) | G6 | G12, G13 | 🟦 | Dữ liệu LiDAR | Nặng | ★ | Cần thêm gói Python; loudness sát ngưỡng |
| 12 | Projection on White Model (`white-model`) | G6 | G7, G11 | ⬜ | Dữ liệu toà nhà 3D mở | Nặng | ★ | Dữ liệu VN có thể hiếm (chưa kiểm chứng) |
| 13 | Data Physicalization (`data-physical`) | G7 | G2, G4 | ⬜ | Số liệu thật | Nặng | ★★ | Báo cáo thường niên, nhà đầu tư |
| 14 | Exploded Teardown (`teardown`) | G2 | G3 | ⬜ | CAD/BOM | Nặng | ★ | Clip mẫu phải dùng mô hình thay CAD |
| 15 | Microscope Story (`microscope`) | G13 | G6 | 🟦 | Ảnh hiển vi có giấy phép | Vừa | ★★ | Không chẩn đoán |
| 16 | Archive Light Table (`archive-lighttable`) | G12 | G4, G6 | 🟦 | Scan lưu trữ có catalog | Vừa | ★★ | Lịch sử thương hiệu, bảo tàng |
| 17 | Crayon Picture Book (`crayon-book`) | G8 | G3 | 🟨 | Code | Vừa | ★★★ | Truyện trước giờ ngủ, học cho bé |
| 18 | Watercolor Brush (`watercolor`) | G13 | G11, G4 | ⬜ | Code | Vừa | ★★★ | Thiên nhiên, du lịch, khoa học |
| 19 | Chinese Ink Wash (`ink-wash`) | G12 | G10, G4 | ⬜ | Code | Vừa | ★★ | Thẩm mỹ Trung Hoa; cân nhắc chủ đề Việt |
| 20 | Impasto Oil Painting (`impasto`) | G4 | G10 | ⬜ | Code | Vừa–nặng | ★★ | MV, quảng cáo cảm xúc |
| 21 | One-line Drawing (`one-line`) | G4 | G1 | ⬜ | Code | Nhẹ | ★★★ | Câu chuyện thương hiệu, cột mốc đời người |
| 22 | Whiteboard Explainer (`whiteboard`) | G1 | G3, G13 | ⬜ | Code | Nhẹ | ★★★ | Đã làm phim máy bay |
| 23 | Urban Sketch (`urban-sketch`) | G11 | G4 | ⬜ | Code | Vừa | ★★★ | Chạy tốt cả khi không có lời đọc |
| 24 | Chalkboard (`chalkboard`) | G1 | — | ⬜ | Code | Vừa | ★★ | Xây quanh nét chữ Hán |
| 25 | Shadow Puppetry (`shadow-puppet`) | G12 | G8 | ⬜ | Code | Vừa | ★★ | Rối bóng kiểu Trung Quốc |
| 26 | Ukiyo-e (`ukiyoe`) | G12 | G11 | ⬜ | Code | Nhẹ–vừa | ★ | Nhật; font bút lông thiếu dấu tiếng Việt |
| 27 | Red Paper-cut (`papercut-red`) | G12 | G8 | 🟨 | Code | Nhẹ | ★★★ | Tết, Trung thu; clip đèn ông sao ổn |
| 28 | Paper-cut Lightbox (`paper-lantern`) | G11 | G12, G4 | ⬜ | Code | Nặng | ★★ | Hành trình, kỷ niệm |
| 29 | Risograph Print (`risograph`) | G4 | G14 | 🟨 | Code | Vừa | ★★ | Thương hiệu indie, zine |
| 30 | Halftone Dossier (`halftone-dossier`) | G14 | G6 | 🟨 | Code | Nhẹ | ★★★ | Clip hài viral, thú cưng |
| 31 | Woodcut Print (`woodcut`) | G12 | G4, G9 | ⬜ | Code | Vừa | ★★★ | Đã làm *Giấy dó* |
| 32 | Copperplate Engraving (`engraving`) | G13 | G12 | 🟦 | Code | Nhẹ–vừa | ★★ | Nhãn bảo tàng, hình sách giáo khoa |
| 33 | Silkscreen Travel Poster (`silkscreen-poster`) | G11 | G9 | ⬜ | Code | Nhẹ | ★★★ | Điểm đến, poster sự kiện |
| 34 | Printed Long Take (`printed-long-take`) | G11 | G13 | ⬜ | Code | Nặng | ★★ | Clip mẫu: đá che chữ tiêu đề |
| 35 | Swiss Motion (`swiss-motion`) | G4 | G9 | ⬜ | Code | Nhẹ | ★★ | Nhận diện thương hiệu, sự kiện |
| 36 | 60s Spy Titles (`spy-titles`) | G9 | G4 | ⬜ | Code | Nhẹ | ★★ | Title sequence |
| 37 | Art Deco (`art-deco`) | G4 | G9 | ⬜ | Code | Nhẹ | ★★ | Sang trọng, gala, thiệp mời |
| 38 | Blueprint (`blueprint`) | G2 | G1 | ⬜ | Code | Vừa | ★★ | Phần cứng, kỹ thuật |
| 39 | Stained Glass (`stained-glass`) | G12 | G8 | ⬜ | Code | Vừa | ★ | Chỉ nội dung thế tục |
| 40 | Pictogram Motion (`pictogram-motion`) | G1 | G4 | ⬜ | Code | Nhẹ | ★★ | Dòng chữ song ngữ là một phần style |
| 41 | ASCII / CRT Terminal (`ascii-crt`) | G3 | G9, G14 | ⬜ | Code | Vừa | ★★ | Công cụ lập trình, sci-fi |
| 42 | Data Storytelling (`dataviz`) | G7 | G13, G6 | 🟦 | Số liệu thật | Nhẹ | ★★★ | Rất mạnh nếu có dữ liệu |
| 43 | Isometric Infographic (`iso-infographic`) | G1 | G7, G3 | ⬜ | Code | Nhẹ | ★★★ | Đã làm phim máy bay |
| 44 | Dark Tech Keynote (`dark-keynote`) | G2 | G3 | ⬜ | Code | Nhẹ | ★★★ | SaaS, ra mắt phần mềm |
| 45 | Living Screencast (`living-screencast`) | G3 | G2 | ⬜ | Giao diện sản phẩm thật | Nhẹ | ★★ | Không bịa tính năng |
| 46 | Sci-fi Hologram HUD (`hologram-hud`) | G2 | G9 | ⬜ | Code | Nhẹ–vừa | ★★ | Thông số, màn hình hội chợ |
| 47 | Transit Map (`transit-map`) | G7 | G11 | ⬜ | Dữ liệu mạng lưới thật | Vừa | ★★ | Clip mẫu: còn chữ Anh, nhịp quá nhanh |
| 48 | Isometric Picture Book (`isometric-picture-book`) | G1 | G3 | ⬜ | Code | Nhẹ | ★★★ | Quy tắc đời thường, so sánh |
| 49 | Circuit Board (`circuit-board`) | G7 | G1, G2 | ⬜ | Code | Nhẹ | ★★ | Năng lượng, chuỗi cung ứng |
| 50 | 1930s Rubber Hose (`rubber-hose`) | G14 | G8 | 🟨 | Code | Nhẹ | ★★ | Đồ ăn uống, quảng cáo cổ điển |
| 51 | 80s Cel Anime (`cel-anime-80s`) | G10 | G9 | ⬜ | Code | Vừa | ★★ | Đã làm *Tần số 98* |
| 52 | Sci-Fi Sitcom Toon (`scifi-toon`) | G14 | G4 | 🟨 | Code + 2 giọng thoại | Nhẹ | ★★ | Đã làm *Phơi đồ đa vũ trụ* |
| 53 | Mid-century Cartoon (`midcentury-toon`) | G3 | G1, G8 | ⬜ | Code | Nhẹ | ★★★ | Đã làm phim máy bay; mạnh nhất cho hướng dẫn |
| 54 | 16-bit Pixel RPG (`pixel-rpg`) | G9 | G14 | 🟨 | Code | Nhẹ | ★★ | Pixel art bão hoà, cần góc riêng |
| 55 | HD-2D (`hd-2d`) | G9 | G8 | ⬜ | Code | Nặng | ★★ | Fantasy, trailer game |
| 56 | Microgame Frenzy (`microgame`) | G14 | G3, G9 | 🟨 | Code | Vừa–nặng | ★★ | Onboarding kiểu trò chơi |
| 57 | Game Show Flat (`game-show`) | G14 | G7 | 🟨 | Code | Nhẹ | ★★ | Tổng kết năm, gameshow |
| 58 | 1920s Silent Film (`silent-film`) | G14 | G4 | 🟨 | Code | Vừa | ★★ | Không lời đọc; khung 4:3 |
| 59 | Liminal Found Footage (`backrooms`) | G9 | — | 🟦 | Code | Nặng | ★ | Ngách kinh dị, bí ẩn |
| 60 | Brick Toy (`brick-toy`) | G8 | G2 | 🟨 | Code | Nặng | ★★ | Không dùng tên/logo LEGO |
| 61 | Paper Pop-up Book (`paper-popup`) | G8 | G9 | 🟨 | Code | Nặng | ★★ | Sách thiếu nhi, trailer |
| 62 | Tilt-Shift Miniature (`tilt-shift`) | G11 | G7 | ⬜ | Code | Nặng | ★★ | Quảng bá thành phố, bất động sản |
| 63 | Low-poly Island (`lowpoly-island`) | G9 | G8, G10 | ⬜ | Code | Nặng | ★★ | Xây thế giới, nội dung êm |
| 64 | Glass Product Render (`glass-product`) | G2 | G4 | ⬜ | Code (vật thể hư cấu) | Nặng | ★★ | Không dùng được cho sản phẩm thật |
| 65 | Memphis Diorama (`memphis-diorama`) | G10 | G1, G11 | 🟨 | Code | Nặng | ★★ | Loop nền, 60 fps bắt buộc |
| 66 | Desktop Flythrough (`desktop-flythrough`) | G3 | G2, G1 | ⬜ | Code | Nặng | ★★ | Giải thích ứng dụng, quy trình |

**Số phong cách theo nhóm chính:** G1 5 (cộng style riêng của bạn) · G2 5 · G3 4 · G4 6 · G5 4 · G6 4 · G7 5 · G8 3 · G9 5 · G10 3 · G11 5 · G12 8 · G13 3 · G14 6. Tổng là 66.

## 5. Gợi ý nhanh: muốn làm gì thì chọn gì

Ưu tiên các phong cách chỉ cần code, render nhẹ hoặc vừa, và đã chạy ổn trên máy này.

| Bạn muốn làm | Chọn đầu tiên | Phương án 2 |
|---|---|---|
| Giải thích một kiến thức | Isometric Whiteboard (của bạn) | Whiteboard hoặc Isometric Infographic |
| Hướng dẫn dùng sản phẩm hay ứng dụng | Mid-century Cartoon | Living Screencast (cần giao diện thật) |
| Ra mắt phần mềm | Dark Tech Keynote | Desktop Flythrough |
| Ra mắt sản phẩm phần cứng | Blueprint | Hologram HUD |
| Clip hài cho TikTok hay Reels | Halftone Dossier | Game Show Flat |
| Văn hoá, nghề truyền thống Việt | Woodcut | Urban Sketch |
| Tết, Trung thu, lễ hội | Red Paper-cut | Paper-cut Lightbox |
| Du lịch, địa danh | Silkscreen Travel Poster | Urban Sketch |
| Báo cáo có số liệu | Data Storytelling | Isometric Infographic |
| Truyện cho trẻ em | Crayon Picture Book | Paper Pop-up Book |
| Thiên nhiên, khoa học | Watercolor | Copperplate Engraving |
| Câu chuyện thương hiệu | One-line Drawing | Impasto |
| Mở màn sự kiện | 60s Spy Titles | Art Deco |

## 6. Cạm bẫy khi chọn phong cách

1. **Sai tông:** dùng hoạt hình vui nhộn (🟨) cho y tế, tài chính, tai nạn hay mất mát. Các studio đều đồng ý điểm này, dù chưa có nghiên cứu đo trên khán giả.
2. **Khó đọc trên điện thoại:** nét khắc mảnh, chữ viết tay, risograph hay halftone tương phản thấp, chữ HUD nhỏ.
   - Chữ trên clip dọc nên cao khoảng 4–5% chiều cao khung (hướng dẫn phụ đề BBC 2024, lấy gián tiếp).
   - Tránh vùng trên khoảng 15% và dưới khoảng 35–45% của clip dọc, vì giao diện ứng dụng che mất.
   - Thiết kế ở 16:9 rồi cắt sang 9:16 sẽ mất chữ.
3. **Lệch văn hoá:** dùng phong cách Trung Quốc hoặc Nhật Bản cho chủ đề thuần Việt.
4. **Biểu đồ động không có lời dẫn:** người xem đọc sai nhiều hơn. Nên kết bằng một khung tĩnh dễ đọc.
5. **Trang trí lấn át nội dung:** các phong cách nhiều chất liệu đang hợp xu hướng, nhưng họa tiết đè lên thông tin chính thì làm giảm hiệu quả học.
6. **Font thiếu dấu tiếng Việt:** clip mẫu đã gặp với Ukiyo-e và phải sửa ô chữ của ASCII/CRT. Phải kiểm tra từng glyph trước khi render.
7. **Chữ tiếng Anh còn sót:** Transit Map và Pictogram Motion có cấu trúc chữ song ngữ, nên phải chủ động thay hoặc bỏ dòng thứ hai.
8. **Render chậm:** 15 phong cách 3D (three.js) chạy chậm trên GTX 950. Với phim dài, nên chọn bản 2D tương đương nếu nội dung cho phép.

## 7. Đánh giá tổng quan thư viện

- **Điểm mạnh:**
  - Phủ rộng 14 loại video.
  - 47/66 phong cách chỉ cần code, không cần tư liệu thật.
  - Gần như mọi phong cách đều nằm trong nhóm xu hướng đang lên: thủ công, in ấn, giấy, cổ điển có chủ đích, hay đồ hoạ kiểu phim tài liệu.
  - Các phong cách có kỷ luật "bằng chứng thật" (dữ liệu, ảnh vệ tinh, scan lưu trữ) hợp với nhu cầu tin tức và tài liệu đang tăng.
- **Điểm yếu:**
  - Hỗ trợ clip dọc 9:16 yếu: chỉ 1/66 phong cách có bố cục dọc viết sẵn.
  - Không có phong cách thuần Việt.
  - Không có phong cách chữ động cho lời bài hát hay mạng xã hội.
  - Ba nhóm G8, G10 và G13 chỉ có 3 phong cách chính mỗi nhóm.
  - 19 phong cách cần tư liệu hoặc dữ liệu thật, nên khó dùng cho người không có sẵn tư liệu.
- **Mức kiểm chứng của chính báo cáo này:**
  - Nhóm, tông và đánh giá sao là nhận định của tôi, dựa trên STYLE.md và clip mẫu.
  - Số liệu nghiên cứu được dẫn kèm mức độ tin cậy trong báo cáo nghiên cứu web.
  - 36 clip mẫu làm từ đợt đầu không có báo cáo lỗi, nên cột ghi chú của chúng chỉ phản ánh tài liệu, không phản ánh kết quả render.

## 8. Câu hỏi còn mở

1. Bạn có muốn kiểm tra khung 9:16 cho khoảng 10 phong cách hay dùng nhất (mục 5), để biết cái nào làm clip dọc được ngay không?
2. Bạn có muốn tạo phong cách riêng thuần Việt, như múa rối nước hay tranh Đông Hồ, theo cách đã làm với Isometric Whiteboard không?
3. Bạn có muốn đưa nhãn nhóm và tông vào `~/lemo-my-styles/README.md`, hay vào một bảng tra riêng, để lần sau chọn phong cách nhanh hơn không?

## Nguồn chính

Danh sách đầy đủ có link nằm trong báo cáo nghiên cứu web.

- Guo, Kim, Rubin 2014, nghiên cứu về sản xuất video MOOC: https://www.cs.rochester.edu/hci/pubs/pdfs/edX-MOOC-video-production-and-engagement_LAS-2014.pdf
- Mayer 2017 (JCAL) và meta-analysis 2025 (Educational Research Review): https://www.sciencedirect.com/science/article/pii/S1747938X25000673
- Robertson và cộng sự 2008, so sánh biểu đồ động và tĩnh: https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tvcg2008-trendvis.pdf
- Tổng quan về hoạt hình giáo dục sức khoẻ 2022: https://www.frontiersin.org/journals/digital-health/articles/10.3389/fdgth.2022.1010779/pdf
- Reuters Institute Digital News Report 2025: https://reutersinstitute.politics.ox.ac.uk/digital-news-report/2025/dnr-executive-summary
- Vidyard 2025 benchmark: https://www.vidyard.com/business-video-benchmarks/ · Wistia State of Video 2025: https://wistia.com/blog/video-marketing-statistics
- Người xem nhìn nhận quảng cáo do AI làm: IAB 2026 https://www.iab.com/insights/the-ai-gap-widens/ · NIQ 2024 https://nielseniq.com/global/en/news-center/2024/niq-research-uncovers-hidden-consumer-attitudes-toward-ai-generated-ads/
- Xu hướng 2026 (ý kiến studio): https://www.animationalerts.com/animation-trends/ · https://garagefarm.net/blog/animation-trends-to-watch
- Nghiên cứu về mảng Visual Investigations của NYT, Journalism Studies 2022: https://www.tandfonline.com/doi/full/10.1080/1461670X.2022.2061574
