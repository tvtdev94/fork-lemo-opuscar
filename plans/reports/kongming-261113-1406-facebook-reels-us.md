# Tư vấn: kênh Facebook Reels cho khán giả Mỹ, làm bằng Lemo-Opuscar

Ngày 13/11/2026 (giờ Sài Gòn). Chỉ tư vấn, không code, không render.
Nhãn dùng trong bài: **[SỐ LIỆU]** là số có nguồn, **[BÊN THỨ BA]** là blog hoặc công cụ tổng hợp chứ không phải Meta, **[NHẬN ĐỊNH]** là ý kiến của tôi, **[CHƯA KIỂM CHỨNG]** là tôi không đọc được nguồn gốc.

## 1. Kết luận ngắn

1. **Làm một kênh giải thích "đồ vật quanh ta được thiết kế thế nào và vì sao"**, 25–40 giây, dọc 9:16, một phong cách chữ ký duy nhất là **Isometric Whiteboard** của bạn. Tên đề xuất: **Built That Way**.
2. **Đừng kỳ vọng sống bằng tiền quảng cáo Reels.** Việt Nam **không có** trong danh sách quốc gia của chương trình Facebook Content Monetization, và RPM Reels cho view Mỹ chỉ khoảng 0,05–0,20 USD mỗi 1.000 lượt xem [BÊN THỨ BA]. Một triệu view Mỹ là khoảng 50–200 USD.
3. **Vì vậy dùng Facebook để phân phối, và đăng cùng file lên YouTube Shorts ngay từ ngày đầu.** YouTube Partner Program có Việt Nam trong danh sách chính thức (đã kiểm tra, mục 7).
4. **Nút thắt của bạn là công viết code cho mỗi tập, không phải máy.** Một phim 50 giây phong cách 2D nhẹ render mất 57–167 giây trên máy này (mục 5). Phải dựng một "engine tập phim" dùng lại, mỗi tập chỉ là dữ liệu.
5. **Việc đầu tiên phải làm** là kiểm tra khung dọc cho 5 phong cách, trước khi viết tập nào.

## 2. Thực tế về kiếm tiền (đọc trước khi quyết)

| Điều | Nội dung | Nguồn, ngày | Loại |
|---|---|---|---|
| Chương trình | Facebook Content Monetization, gộp ads on reels, in-stream và bonus. Chỉ vào được bằng **thư mời**. Form "quan tâm" trong tab Monetization không phải đơn đăng ký. Meta không công bố ngưỡng follower hay view. | clip-short.com (cập nhật 29/10/2026, đọc trang Meta ngày 08/10/2026); streamclipping.ai (18/10/2026) | BÊN THỨ BA |
| Việt Nam | **Không có** trong 70 quốc gia và vùng lãnh thổ. Tiếng Việt nằm trong 37 ngôn ngữ được hỗ trợ, nhưng ngôn ngữ không đủ. | clip-short.com (08/10/2026); insighthive.app (rà lại 02/11/2026) | BÊN THỨ BA |
| Ngoại lệ | "Nhiều chủ page ở Việt Nam được báo là đã nhận thư mời" dù không có trong danh sách. Đây là ngoại lệ được kể lại, không phải quyền chính thức. Blog Việt cũng nói mỗi nơi một kiểu. | insighthive.app (02/11/2026); các blog Việt 2026 | BÊN THỨ BA, yếu |
| Trang gốc của Meta | Tôi mở trang Help Center nhưng chỉ đọc được tiêu đề, không đọc được danh sách. | facebook.com/business/help/1884527914934148 (13/11/2026) | CHƯA KIỂM CHỨNG |
| RPM Reels view Mỹ | 0,02–0,20 USD mỗi 1.000 view, trung vị khoảng 0,05–0,10. Riêng view Mỹ 0,10–0,20. Một số đo thật: 0,050 USD trên 5,96 triệu view (tháng 6/2026, 14 page tiếng Anh). Con số 1–5 USD là của video dài có quảng cáo chèn giữa, không phải Reels. | contentmonetizing.com (09/10/2026); schedpilot.com; postplanify.com | BÊN THỨ BA |
| Điều kiện nội dung | Reel dài ít nhất 10 giây, một ngôn ngữ mỗi reel, lượt xem dưới 5 giây không tính tiền. | clip-short.com (29/10/2026) | BÊN THỨ BA |
| Nội dung không gốc | Từ 14/07/2025, tài khoản đăng lại nội dung người khác nhiều lần sẽ mất kiếm tiền tạm thời và bị giảm phân phối toàn bộ. Ghép clip hoặc thêm watermark không tính là "cải tiến". Nửa đầu 2025 Meta phạt khoảng 500.000 tài khoản spam, xoá khoảng 10 triệu hồ sơ giả mạo. | creators.facebook.com/blog/combating-unoriginal-content (14/07/2025) | SỐ LIỆU, nguồn gốc |
| Lời khuyên của Meta | Tự làm nội dung, kể chuyện, tránh video quá ngắn ít giá trị, không có watermark của bên khác, caption không link, tối đa 5 hashtag. | cùng bài trên | SỐ LIỆU, nguồn gốc |
| AI | Meta phạt nội dung dùng lại, không cấm công cụ AI. Bài gốc không nhắc tới AI. | techcrunch.com (14/07/2025); bài gốc Meta | SỐ LIỆU |
| Nhãn "AI info" | Hoạt hình kiểu vẽ không cần gắn nhãn. **Giọng đọc AI nghe như người thật thì nằm trong ví dụ cần gắn nhãn.** | binai.it, vidpal.ai (2026), tóm tắt Help Center của Meta | BÊN THỨ BA |
| YouTube | Việt Nam có trong danh sách YouTube Partner Program. Ngưỡng: 1.000 sub cộng 10 triệu view Shorts trong 90 ngày, hoặc 4.000 giờ xem video dài. RPM Shorts 0,01–0,07 USD, view Mỹ 0,10–0,25. | support.google.com/youtube/answer/7101720 (đọc 13/11/2026); makeviral.ai (09/2026) | Danh sách: SỐ LIỆU. RPM: BÊN THỨ BA |
| TikTok | Creator Rewards chỉ có 8 nước (Mỹ, Anh, Đức, Nhật, Hàn, Pháp, Mexico, Brazil). Tài khoản Việt Nam không vào được dù view Mỹ. | shortsfast.com, makeviral.ai (15/09/2026) | BÊN THỨ BA |

**Hệ quả [NHẬN ĐỊNH]:**
- Tiền quảng cáo Reels chỉ là phần thưởng thêm. Mục tiêu năm đầu nên là **khán giả và danh mục tác phẩm**, rồi kiếm bằng video dài trên YouTube, tài trợ, và nhận làm phim giải thích cho khách Mỹ.
- **Không** thuê tài khoản Mỹ, không dùng VPN hay danh tính người khác để nhận tiền. Lệch quốc gia giữa người quản lý page và thông tin thanh toán là lý do khoá kiếm tiền quen thuộc. Tôi chưa đọc nguyên văn điều khoản này, nhưng rủi ro mất cả page là có thật.
- Phương thức nhận tiền của Meta về Việt Nam: **chưa kiểm chứng**. Chỉ xem được khi tab Monetization mở.

## 3. Kênh nên làm

### 3.1. So sánh các ngách (đều là nhận định của tôi)

| Ngách | Hợp thư viện | Cạnh tranh | RPM | Rủi ro bị xem là AI rác | Chi phí trên máy này |
|---|---|---|---|---|---|
| **Thiết kế và cơ chế của đồ vật thường ngày** | Rất cao (isometric, whiteboard, cutaway) | Cao, nhưng đa số là 3D bóng bẩy | Trung bình | Thấp nếu giữ nét vẽ tay | Thấp |
| Khoa học "bạn học sai từ nhỏ" | Rất cao | Cao | Trung bình | Thấp | Thấp |
| Lịch sử và hoài niệm đời thường Mỹ | Cao (woodcut, engraving, halftone) | Trung bình | Trung bình khá | Trung bình | Vừa |
| Hài "hồ sơ vụ án" chuyện vặt, thú cưng | Cao (halftone-dossier) | Trung bình | Thấp | Thấp | Thấp |
| Loop thoả mãn, không lời | Trung bình (memphis, lowpoly là 3D) | Rất cao | Thấp | Cao | Cao |
| Truyện thiếu nhi | Trung bình (crayon) | Rất cao | Thấp, nhiều hạn chế cho nội dung trẻ em | Cao | Vừa |
| Tài chính nhẹ | Thấp (sai tông với hoạt hình vui) | Cao | Cao | Cao, lại cần chính xác tuyệt đối | Thấp |
| Bí ẩn, vụ án có thật | Thấp (cần tư liệu thật) | Rất cao | Trung bình | Rất cao | Vừa |

Căn cứ: người dùng Facebook ở Mỹ lệch về 35 tuổi trở lên, khoảng 57% theo một bảng 2026 (resourcera.com, BÊN THỨ BA); Pew 2025 đo tỉ lệ dùng 80% ở nhóm 30–49 và 74% ở nhóm 50–64. Nhóm này chia sẻ kiểu "giờ tôi mới biết". Với ngách lịch sử, một nguồn chấm clip "sự thật lịch sử" chung chung giữ chân kém (2/5) và khuyên chọn ngách hẹp (overseeros.com, 2026, Ý KIẾN).

### 3.2. Ba phương án kênh

| | **A. Built That Way (chọn)** | B. The Old Way | C. Petty Case Files |
|---|---|---|---|
| Một câu | Câu trả lời 30 giây cho những thứ bạn nhìn cả nghìn lần mà chưa từng hỏi | Đời thường nước Mỹ trước khi mọi thứ dễ dàng, kể bằng tranh khắc | Hồ sơ điều tra nghiêm trang cho chuyện vặt vãnh |
| Khán giả Mỹ | 30–60 tuổi, tò mò, thích sửa đồ, phụ huynh, giáo viên | 45 tuổi trở lên, thích hoài niệm | 18–40 tuổi, thích hài khô |
| Phong cách | `iso-whiteboard` (của bạn) | `woodcut`, `engraving` | `halftone-dossier` |
| Điểm mạnh | Kiến thức vật lý, cơ khí đúng ở mọi nước, dễ dẫn nguồn. Bạn đã làm 4 phim máy bay cùng loại. Render nhẹ. | Ít người làm bằng hoạt hình thủ công. Hợp tuổi Facebook nhất. | Dễ lan nhất nếu hài trúng. |
| Điểm yếu | Nhiều kênh cùng chủ đề | Cần hiểu văn hoá Mỹ, sai một chi tiết là bị bắt lỗi | Viết hài tiếng Anh là việc khó nhất với người không bản ngữ |
| Rủi ro với bạn | Thấp | Trung bình | Cao |

**Vì sao chọn A:**
- Rủi ro thấp nhất đúng ở chỗ bạn yếu nhất: tiếng Anh và văn hoá Mỹ. Một cái khoá kéo hoạt động giống nhau ở Hà Nội và Ohio.
- Dùng phong cách riêng của bạn làm nhận diện. Hình khối isometric gần vuông nên đặt vào khung dọc dễ hơn tranh ngang (suy luận, chưa kiểm tra).
- Phong cách vẽ bút lông trên bảng trắng nhìn rõ là "có người làm", khác hẳn 3D bóng bẩy do AI sinh. Khảo sát 2025–2026 cho thấy người xem mất tin với thứ trông như AI (IAB 2026, NIQ 2024, đã dẫn trong báo cáo nghiên cứu ngày 13/11).
- B không bị bỏ: nó thành một series thử nghiệm bên trong kênh A (series 4).

**Tên khác:** Tiny Why · The Why Board · Cutaway Minute · Drawn to Explain. Tôi chưa kiểm tra tên nào còn trống trên Facebook, Instagram, YouTube hay đã có nhãn hiệu.
**Dòng giới thiệu page:** "30-second answers to things you've seen a thousand times. Every frame is drawn in code by a small studio. Sources in the comments."

### 3.3. Một quyết định hay bị làm sai

**Đừng đổi phong cách mỗi video.** 66 phong cách là để chọn, không phải để khoe trên một kênh. Kênh cần người xem nhận ra trong nửa giây, và engine dùng lại chỉ tiết kiệm công khi phong cách cố định. Cả kênh dùng tối đa hai phong cách: `iso-whiteboard` cho ba series chính, và một phong cách in ấn cho series 4.

## 4. Hệ thống nội dung: 4 series

Chung cho mọi tập: 25–40 giây, 1080×1920, 24 fps, tiếng Anh Mỹ, đơn vị Mỹ (feet, miles, °F), chữ trên hình và caption đều tiếng Anh. Mọi ý tưởng dưới đây **phải qua `FACTS.md` có nguồn** trước khi làm; tôi liệt kê theo hiểu biết, chưa đối chiếu từng cái.

**Khung nhịp chung (30 giây):**

| Giây | Nhịp | Trên hình |
|---|---|---|
| 0–2 | Hook | Vật thể đã hiện sẵn ở khung đầu tiên, một vòng bút đỏ khoanh chi tiết, một dòng chữ lớn 4–7 từ. Không logo, không màn mở đầu. |
| 2–8 | Câu hỏi và điều người ta tưởng | Bút viết câu hỏi, một dấu gạch chéo lên đáp án sai phổ biến. |
| 8–22 | Giải thích | Cắt lớp hoặc tách chi tiết, mỗi câu thoại một chuyển động, mũi tên chỉ đúng chỗ đang nói. |
| 22–28 | Kết | Vật thể hoạt động trọn một lần, một câu chốt. |
| 28–30 | Vòng lặp | Khung cuối trùng bố cục khung đầu để clip tự lặp. Một dòng nhỏ: "Follow for one of these every day". |

### Series 1 · Hidden Design (chi tiết nhỏ có lý do)
- **Phong cách:** `iso-whiteboard`. Vật thể đặt trên bệ, bút khoanh chi tiết.
- **Hook mẫu:** "This tiny hole is keeping you alive." · "You've touched this bump 10,000 times."
- **Tập:**
  1. The tiny hole in every airplane window
  2. The bumps on your F and J keys
  3. Why pen caps have a hole in the top
  4. The little arrow next to your gas gauge
  5. Why the bottom of a soda can curves inward
  6. Why golf balls have dimples
  7. The hole in the bottom of a padlock
  8. The extra top eyelet on your running shoes
  9. Why coins have ridged edges
  10. The tiny pocket inside your jeans pocket
  11. Why manhole covers are round
  12. The loop on the back of a dress shirt

### Series 2 · Cut It Open (cơ chế bên trong)
- **Phong cách:** `iso-whiteboard`, dùng động tác cắt lớp của `iso-infographic` (đã có trong phim máy bay bản isometric).
- **Hook mẫu:** "Here's what happens inside a lock when you turn the key."
- **Tập:**
  1. How a zipper actually holds together
  2. Inside a lock: what your key really does
  3. What happens when you flush a toilet
  4. How a ballpoint pen never runs dry on the tip
  5. How a thermos keeps coffee hot for 12 hours
  6. How noise-cancelling headphones erase sound
  7. How your phone screen knows where your finger is
  8. How GPS finds you with four satellites
  9. How a microwave heats food (not from the inside out)
  10. How a refrigerator moves heat instead of making cold
  11. The brake that stops a falling elevator
  12. How a scanner reads a QR code

### Series 3 · Wrong Since School (sửa điều học sai)
- **Phong cách:** `iso-whiteboard`. Mở bằng hình minh hoạ kiểu sách giáo khoa bị gạch chéo đỏ.
- **Hook mẫu:** "Your science teacher got this one wrong."
- **Lợi thế:** tập 1 bạn đã có sẵn nghiên cứu (`films/iso-whiteboard-test/FACTS.md:11`, NASA gọi thuyết "thời gian bằng nhau" là sai).
- **Tập:**
  1. Planes don't fly the way your textbook said
  2. Summer isn't when Earth is closest to the Sun
  3. Lightning does strike the same place twice
  4. A hammer and a feather fall at the same speed
  5. The "tongue map" was never real
  6. Old window glass isn't slowly flowing
  7. There is no dark side of the Moon
  8. You can't see the Great Wall from space
  9. Your blood is never blue
  10. Bats aren't blind
  11. You have far more than five senses
  12. Goldfish remember for months, not seconds

### Series 4 · Why America Does It This Way (thử nghiệm, lai với phương án B)
- **Phong cách:** `halftone-dossier` dạng "hồ sơ", hoặc `engraving`. Chọn cái đọc rõ hơn trên điện thoại sau khi kiểm tra khung dọc. Halftone tương phản thấp là rủi ro đã ghi trong báo cáo đánh giá (mục 6.2).
- **Hook mẫu:** "School buses are yellow because of one meeting in 1939."
- **Vì sao có series này:** chủ đề Mỹ thì người Mỹ chia sẻ nhiều hơn, và nó đo luôn phương án B mà không cần mở kênh thứ hai.
- **Tập:**
  1. Why every school bus is the same yellow
  2. Why stop signs have eight sides
  3. How interstate highway numbers secretly tell you direction
  4. Why American barns are red
  5. The day the railroads invented time zones
  6. What the colors on a fire hydrant mean
  7. Why dollar bills are green
  8. Why ZIP codes have five digits
  9. Why America never switched to metric
  10. Why your keyboard starts with QWERTY (nêu rõ đây là điều sử gia còn tranh luận)
- **Tránh:** bầu cử, tôn giáo, súng, chủng tộc, chiến tranh. Page do người nước ngoài quản lý mà đăng chủ đề chính trị Mỹ là tự chuốc rủi ro.

### Giọng đọc
- **Dùng giọng đọc cộng caption đốt vào hình.** Hình phải tự hiểu được khi tắt tiếng; giọng là lớp thêm.
- **Chọn Kokoro, giọng Mỹ (`am_*` hoặc `af_*`), không chọn edge-tts cho kênh này.**
  - Kokoro là mặc định tiếng Anh của thư viện, chạy trên máy, không cần mạng (`TECHNIQUE.md:98`).
  - edge-tts là thư viện gọi dịch vụ đọc của Microsoft Edge; quyền dùng thương mại không rõ ràng [NHẬN ĐỊNH, chưa đọc điều khoản]. Kênh định kiếm tiền thì không nên đặt trên nền đó.
  - Nghe thử 3–4 giọng trên cùng một kịch bản, chọn một, giữ suốt kênh. Lệnh `tts.py` với tên giọng sai sẽ in ra danh sách (`TECHNIQUE.md:98`).
- **Bật nhãn "AI info" cho giọng đọc** khi đăng. Hình vẽ không cần nhãn, giọng AI nghe như thật thì cần (mục 2).
- **Nâng cấp sau này:** khi có một series thắng, thuê một người Mỹ đọc theo lô. Đây là cách giảm cảm giác "AI" rẻ nhất. Giá: chưa kiểm chứng.

## 5. Kế hoạch sản xuất trên máy này

**Số đo thật từ log render của bạn** (1920×1080, một worker):

| Phim | Số khung | Thời gian render | Nguồn |
|---|---|---|---|
| Mid-century, 48 giây | 1.152 | 57 giây | `films/may-bay-midcentury/out/render.log` |
| Isometric, 50 giây | 1.210 | 79 giây | `films/may-bay-isometric/out/render.log` |
| Whiteboard, 48 giây | 1.140 | 167 giây | `films/may-bay-whiteboard/out/render.log` |

Khung 1080×1920 có cùng số điểm ảnh nên tôi đoán thời gian tương đương; chưa đo. Kết luận: với 2D nhẹ, GTX 950 không phải vấn đề. Tiền và thời gian nằm ở công viết code từng tập.

### Bước 0 · Kiểm tra khung dọc (làm trước tiên, 1–2 ngày)
Kiểm tra 5 phong cách theo thứ tự: `iso-whiteboard` (của bạn) → `whiteboard` → `halftone-dossier` → `engraving` → `midcentury-toon`.
- Với mỗi cái: render 3 khung tĩnh ở `--size 1080x1920`, dựng trang theo `innerWidth × innerHeight` (`TECHNIQUE.md:69`). Không cắt từ bản ngang.
- Đạt khi:
  - Chữ nhỏ nhất cao từ 80 px trở lên (4–5% chiều cao, theo hướng dẫn phụ đề BBC 2024, dẫn gián tiếp).
  - Không có chữ hay chi tiết chính ở 15% trên cùng, 35% dưới cùng, 20% bên phải. Các số này không chính thức (Strike Social, dẫn trong báo cáo nghiên cứu §1).
  - Mỗi dòng caption tối đa khoảng 30 ký tự, nhiều nhất 2 dòng.
  - `readcheck.mjs` vẫn qua ở khung dọc.
- Xem ảnh trên điện thoại thật, không xem trên màn hình máy tính.

### Bước 1 · Engine tập phim (làm một lần, 3–5 ngày)
- Một thư mục dự án cho series, ví dụ `films/built-that-way/`, chứa: sân khấu dọc, bệ và bảng trắng, bút viết chữ, vòng khoanh đỏ, dấu gạch chéo, mũi tên, động tác cắt lớp, caption theo từng từ (lấy từ `words.json` của `asr_check.py`), bố cục vùng an toàn.
- Mỗi tập là một tệp dữ liệu: câu thoại, nhịp, vật thể nào, chi tiết nào được khoanh, camera dừng ở đâu.
- **Thư viện vật thể dùng lại:** mỗi tập chỉ vẽ mới một vật thể. Vật đã vẽ (bàn phím, lon nước, ổ khoá) dùng lại cho tập sau.
- **Một nhạc nền chữ ký:** một mô-típ 4–6 nốt, vài biến thể, cùng bộ tiếng bút. Không soạn nhạc mới cho từng tập.
- Việc này nằm trong dự án phim, không sửa `core/` hay `styles/` (AGENTS.md).

### Ngân sách thời gian mỗi tập (ước lượng của tôi, sau khi có engine)

| Việc | Tập 1–5 | Từ tập 10 |
|---|---|---|
| Kịch bản 60–80 từ và `FACTS.md` có 2 nguồn | 25 phút | 15 phút |
| Vẽ một vật thể mới và dữ liệu tập | 60 phút | 25 phút |
| Giọng, kiểm tra bằng Whisper, mix | 10 phút | 5 phút |
| Render và các bước kiểm tra | 10 phút | 10 phút |
| Bạn xem trên điện thoại và sửa | 15 phút | 10 phút |
| **Tổng** | **khoảng 2 giờ** | **khoảng 1 giờ** |

### Làm theo lô
- **Lô 5 tập cùng series.** Viết 5 kịch bản và 5 `FACTS.md` một lượt, rồi vẽ 5 vật thể, rồi làm 5 giọng, rồi render lần lượt qua khe render (`RENDER_SLOTS=1`, như `films/may-bay-isometric/build.sh`).
- Render ban đêm bằng một script chạy tuần tự. Không chạy hai trình render cùng lúc: log cũ ghi GPU này trộn khung giữa các lần render song song.
- Luôn có sẵn 5 tập dự trữ trước khi đăng tập đầu.

### Phong cách nên tránh vì chi phí
- **15 phong cách 3D three.js:** `brick-toy`, `paper-popup`, `tilt-shift`, `lowpoly-island`, `glass-product`, `memphis-diorama` (bắt buộc 60 fps), `desktop-flythrough`, `hd-2d`, `backrooms`, `paper-lantern`, `printed-long-take`, `data-physical`, `teardown`, `lidar-survey`, `white-model`.
- **Các phong cách cần tư liệu thật:** cả nhóm Edit & Documentary và Evidence Films. Dùng footage người khác còn đụng luôn luật nội dung không gốc.
- **`scifi-toon`:** cần hai giọng thoại khớp khẩu hình, tốn công giọng nhất thư viện.

## 6. Kế hoạch thử 30 ngày

**Chuẩn bị (ngày −10 đến 0):** bước 0, bước 1, 6 tập dự trữ, lập Page mới (đừng dùng trang cá nhân), điền About thật, bật xác minh hai lớp.

**Lịch đăng:** 5 reel mỗi tuần trong 4 tuần, tổng 20 tập.
- Tuần 1–2: xoay vòng series 1, 2, 3 (mỗi series 3–4 tập).
- Tuần 3: thêm 3 tập series 4.
- Tuần 4: 5 tập đều thuộc series đang dẫn đầu.
- Giờ đăng: 19–21 giờ miền Đông nước Mỹ, thứ Hai đến thứ Sáu. Tháng 11 đến tháng 3 là **7–9 giờ sáng hôm sau giờ Việt Nam**; khi Mỹ đổi giờ mùa hè là 6–8 giờ sáng. Hẹn giờ bằng Meta Business Suite. Lưu ý: không có nghiên cứu lớn nào về giờ đăng riêng cho Reels; Buffer (14 triệu bài) và Sprout 2026 chỉ thống nhất là ngày thường hơn cuối tuần. Sau 2 tuần, theo số của chính page.
- Đăng cùng file lên YouTube Shorts và Instagram Reels, tải file gốc lên từng nơi, không dùng bản tải về có watermark.

**Chỉ số và ngưỡng** (ngưỡng do tôi đặt để ra quyết định, không phải số của Meta; so sánh giữa các series của chính bạn mới là phép đo đáng tin):

| Chỉ số | Tốt | Kém | Nó nói gì |
|---|---|---|---|
| Giữ chân 3 giây | từ 60% | dưới 45% | Khung đầu và dòng hook |
| Phần trăm xem trung bình (tập 30 giây) | từ 60% | dưới 40% | Nhịp giải thích |
| Lượt chia sẻ mỗi 1.000 view | từ 5 | dưới 2 | Chủ đề có đáng kể lại không |
| Lượt theo dõi mỗi 1.000 view | từ 2 | dưới 0,5 | Lời hứa của kênh có rõ không |
| View trung vị mỗi reel, tuần 4 so với tuần 1 | gấp 3 | không đổi | Facebook có mở rộng phân phối không |

**Quy tắc quyết định sau 20 tập:**
1. **Một series đạt mức tốt ở ít nhất 2 trong 4 chỉ số đầu:** dồn 70% số tập tháng sau cho series đó, giữ 30% để thử.
2. **Giữ chân 3 giây kém ở mọi series:** lỗi ở 2 giây đầu, không phải ở ngách. Làm lại khung đầu của 5 tập và đăng lại dưới dạng tập mới với hook khác.
3. **Giữ chân tốt nhưng chia sẻ kém:** lỗi ở chủ đề. Tăng series 4. Nếu series 4 cũng kém, chuyển sang phương án B với 5 tập `woodcut`.
4. **Mọi reel dưới khoảng 500 view dù số giữ chân tốt:** nghi vấn nằm ở tài khoản. Xem mục Support trên Page có cảnh báo không, và so với YouTube, Instagram. Cùng file mà nơi khác chạy thì nội dung ổn, Page có vấn đề.
5. **Series 4 thắng rõ:** kênh nghiêng về hoài niệm Mỹ, đổi phong cách chữ ký của series đó thành chính.
6. **Không thay đổi gì trước tập thứ 10.** Dưới 10 tập thì số liệu chỉ là nhiễu.

## 7. Đường kiếm tiền và mốc thời gian

| Giai đoạn | Việc | Tiền thực tế |
|---|---|---|
| Tháng 0–1 | Thử 20 tập | 0 |
| Tháng 2–4 | Dồn vào series thắng, 5–7 reel mỗi tuần. Bấm form quan tâm trong tab Monetization và kiểm tra hằng tuần. | 0, trừ khi có thư mời |
| Tháng 3–6 | Ghép 8–10 tập cùng series thành video dài 4–6 phút cho YouTube, hướng tới 4.000 giờ xem | 0 cho tới khi đạt ngưỡng |
| Từ tháng 6 | Nếu có kiếm tiền ở một trong hai nơi | Xem bảng dưới |

**Tiền quảng cáo Reels theo RPM 0,05–0,20 USD** [BÊN THỨ BA]:

| View Mỹ mỗi tháng | Thu nhập mỗi tháng |
|---|---|
| 300.000 | 15–60 USD |
| 1 triệu | 50–200 USD |
| 5 triệu | 250–1.000 USD |
| 20 triệu | 1.000–4.000 USD |

**Lưu ý cứng:**
- Con số trên chỉ có nếu Page được mời, mà Việt Nam không ở trong danh sách chính thức. Có thể bạn không bao giờ được mời.
- Video dài trên YouTube được ước tính RPM 4–9 USD cho khoa học và lịch sử (youtubeniches.com, 2026, BÊN THỨ BA, tôi đánh giá độ tin thấp). Dù vậy, hướng đi đúng: tiền nằm ở video dài, Reels để kéo người xem.
- Nguồn thu đáng tin hơn quảng cáo [NHẬN ĐỊNH]: nhận làm phim giải thích cho doanh nghiệp Mỹ, với kênh làm danh mục; tài trợ khi có 50.000 người theo dõi trở lên; bán bản quyền dùng clip cho trang giáo dục.

## 8. Rủi ro và cách tránh

| Rủi ro | Cách tránh |
|---|---|
| **Bị xem là AI rác** | Một phong cách vẽ tay nhất quán. Ghi nguồn ở bình luận ghim. Thỉnh thoảng đăng clip hậu trường "this frame is 2,000 lines of code". Không dùng ảnh hay video do AI sinh. Không đăng quá 1–2 reel mỗi ngày. |
| **Nội dung không gốc** | Mọi hình tự vẽ bằng code, nhạc tự soạn. Không lấy footage, ảnh, clip của ai. Không đăng lại chính tập cũ nhiều lần. Đăng chéo sang page của chính mình thì Meta cho phép. |
| **Bản quyền nhân vật, thương hiệu** | Không nhái phim hay kênh nào (đã có tiền lệ Family Guy). Không logo, không tên hãng trên hình: nói "a ballpoint pen", không nói tên hãng. Không bắt chước bố cục và giọng của một kênh giải thích đang nổi. |
| **Nhạc, mẫu âm, font** | Chỉ CC0, CC BY, OFL (`TECHNIQUE.md:145`). Ưu tiên bộ mẫu CC0 để khỏi phải ghi công. Nếu dùng Salamander (CC BY 3.0) hay MuldjordKit (CC BY 4.0) thì phải ghi công (`core/audio/INSTRUMENTS.md:119,125`): đặt trong caption hoặc bình luận ghim, và giữ tệp `CREDITS` của từng tập. |
| **Sai kiến thức** | Mỗi tập một `FACTS.md`, ít nhất 2 nguồn gốc (NASA, NOAA, Smithsonian, hãng sản xuất, tiêu chuẩn). Khi giới chuyên môn còn tranh luận thì nói rõ trong lời đọc. Một tập sai bị bắt lỗi trong bình luận thì sửa công khai, không xoá bình luận. |
| **Tiếng Anh** | Câu ngắn, tối đa 12 từ, không thành ngữ. Chính tả và đơn vị Mỹ. Cho một mô hình ngôn ngữ soát với vai "biên tập viên người Mỹ", rồi `asr_check.py` khớp từng từ. Nếu được, nhờ một người Mỹ đọc 20 kịch bản đầu. Trả lời bình luận ngắn, lịch sự, không tranh cãi. |
| **Uy tín Page** | Mục minh bạch của Page có thể hiện quốc gia người quản lý [CHƯA KIỂM CHỨNG lần này]. Đừng giả làm người Mỹ. Viết thật: một studio nhỏ vẽ mọi khung hình bằng code. Không mua follower, không mua like, không tham gia nhóm kéo tương tác: đó chính là thứ Meta phạt năm 2025. |
| **Phụ thuộc một nền tảng** | Giữ file gốc và đăng ba nơi từ ngày đầu. |
| **Chi phí token** | Engine dùng lại, làm theo lô, mỗi tập một vật thể mới. Không làm lại phong cách hay nhạc cho từng tập. |

## 9. Danh sách việc

1. Chọn tên, kiểm tra tên còn trống trên Facebook, Instagram, YouTube.
2. Kiểm tra khung dọc cho 5 phong cách (bước 0), ghi kết quả.
3. Nghe thử 3–4 giọng Kokoro Mỹ, chọn một.
4. Dựng engine tập phim và nhạc chữ ký (bước 1).
5. Viết 20 kịch bản và `FACTS.md`, ưu tiên: lỗ cửa sổ máy bay, gờ phím F và J, khoá kéo, ổ khoá, máy bay bay thế nào, mùa hè và Mặt Trời.
6. Sản xuất 6 tập dự trữ, xem trên điện thoại.
7. Lập Page, YouTube, Instagram. Đăng theo lịch, ghi số liệu vào một bảng mỗi tuần.
8. Sau tập 20: áp quy tắc mục 6.

## 10. Giả định tôi đã đặt thay cho câu hỏi

| Giả định | Độ tin | Điều gì làm đổi lời khuyên |
|---|---|---|
| Bạn chưa có Page nào đã được mời kiếm tiền | Trung bình | Nếu đã có, dùng Page đó và ưu tiên Facebook hơn YouTube |
| Mục tiêu là thu nhập, không phải chỉ lượt xem | Cao | Nếu chỉ cần lượt xem, phương án C (hài) đáng thử sớm hơn |
| Bạn làm một mình, vài giờ mỗi ngày | Trung bình | Có người viết tiếng Anh bản ngữ thì phương án B và C bớt rủi ro nhiều |
| Phong cách `iso-whiteboard` chuyển sang khung dọc được với công sửa vừa phải | Trung bình | Nếu bước 0 thất bại, dùng `whiteboard` làm chữ ký |
| Render dọc nhanh như render ngang | Trung bình | Đo lại ở bước 0 |
| Danh sách quốc gia của Meta đúng như hai trang bên thứ ba ghi | Trung bình khá | Tab Monetization trên Page của bạn là nguồn cuối cùng |

## 11. Câu hỏi còn mở cho bạn

1. Bạn có Page cũ nào không, và tab Monetization của nó đang hiện gì?
2. Mục tiêu thu nhập sau 6 tháng là bao nhiêu? Nếu trên 500 USD mỗi tháng thì phải tính video dài và nhận việc làm phim ngay từ đầu.
3. Bạn có ai là người Mỹ, hoặc ngân sách nhỏ, để soát kịch bản hay đọc giọng không?
4. Mỗi tuần bạn dành được bao nhiêu giờ và bao nhiêu chi phí token? Lịch 5 tập mỗi tuần cần khoảng 5–10 giờ sau khi có engine.
5. Bạn có chấp nhận gắn nhãn "AI info" cho giọng đọc không? Nếu không, phải thuê người đọc.

## Nguồn (đọc ngày 13/11/2026)

- Meta, "Combating unoriginal content", 14/07/2025: https://creators.facebook.com/blog/combating-unoriginal-content
- TechCrunch, 14/07/2025: https://techcrunch.com/2025/07/14/following-youtube-meta-announces-crackdown-on-unoriginal-facebook-content
- Danh sách quốc gia Content Monetization (bên thứ ba): https://www.clip-short.com/guides/facebook-content-monetization · https://insighthive.app/resources/facebook-content-monetization-eligible-countries · https://streamclipping.ai/blog/facebook-reels-monetization
- Trang Meta không đọc được nội dung: https://www.facebook.com/business/help/1884527914934148
- RPM Reels: https://contentmonetizing.com/en/facebook-rpm-usa/ · https://schedpilot.com/how-much-facebook-reels-pay/ · https://postplanify.com/blog/how-much-does-facebook-reels-pay-per-1000-views
- YouTube Partner Program, danh sách quốc gia: https://support.google.com/youtube/answer/7101720
- Shorts và TikTok: https://www.makeviral.ai/blog/youtube-shorts-monetization · https://shortsfast.com/blog/tiktok-creator-rewards-2026-requirements/
- Nhãn AI: https://www.binai.it/en/blog/how-social-media-labels-ai-content · https://www.vidpal.ai/blog/ai-content-labels-tiktok-instagram-youtube-2026
- Nhân khẩu học: https://resourcera.com/data/social/facebook-statistics/ · https://sproutsocial.com/insights/facebook-stats-for-marketers/
- Giờ đăng: https://buffer.com/resources/best-time-to-post-on-facebook/ · https://socialk.it/en/best-time-to-post/facebook
- Ngách không lộ mặt: https://www.overseeros.com/blog/faceless-ai-history-channels · https://youtubeniches.com/blog/best-faceless-youtube-niches-2026
- Trong repo: `plans/reports/evaluation-261113-1149-style-by-video-type.md`, `plans/reports/researcher-261113-1140-video-types-styles.md`, `TECHNIQUE.md:69,98,145`, `core/README.md:42`, `core/audio/INSTRUMENTS.md`, `films/*/out/render.log`
