# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Trần Ngọc Huy
- **MSSV:** 125001758
- **Tên đề tài Website:** Review Game — Khám phá và đánh giá game indie
- **Công cụ AI đã sử dụng:** OpenAI Codex
- **Repository:** Huy_TranNgoc_125001758
- **Ngày thực hiện:** 19/10/2026
- **Nguồn phát triển:** Dự án Indieverse của cùng chủ sở hữu. Bản này tái sử dụng giao diện, nội dung và tính năng, sau đó chuyển thành website tĩnh bốn file. Không trình bày đây là toàn bộ mã được tạo mới trong một buổi thi 120 phút.

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> làm thêm một trang web "indieverse" trên github của tôi nhưng ở một dự án khác, đổi tên thành review game và chỉ nên có những file giống ảnh 1 thôi, những yêu cầu thì giống đề thi kiểm tra giữa kì. Yêu cầu vẫn phải giữ được bản sắc hình hài và tính toàn vẹn của trang, làm sao dù còn nhiêu đó file nhưng trang web vẫn phải có hình hài giống bản gốc

Ảnh tham chiếu yêu cầu đúng `.gitignore`, `PROMPT_LOG.md`, `index.html`, `style.css`. Tài liệu tham chiếu là đề kiểm tra giữa kỳ học phần Thiết kế Web, Trường Đại học Lạc Hồng.

**Làm rõ trực tiếp của sinh viên:**

> Tên repo theo đề, website Review Game

> Trần Ngọc Huy - 125001758

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

Các bước dưới đây là nhật ký triển khai của trợ lý theo yêu cầu trên. Không bịa thêm prompt, lời nhận xét hay trải nghiệm cá nhân của sinh viên.

### Lần 1: Dựng khung Semantic HTML & CSS Variables

- **Prompt đã dùng:** Yêu cầu ban đầu ở mục 1; giữ toàn vẹn Indieverse trong đúng bốn file.
- **Kết quả AI tạo ra:** Giữ cấu trúc `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`; gộp các lớp CSS theo đúng thứ tự để giữ màu tối, tím pastel, bố cục bài nổi bật, thẻ game và các trang bên trong.
- **CSS Variables:** Duy trì biến màu `--bg`, `--panel`, `--text`, `--purple`; bổ sung `--primary-color`, `--font-body`, `--font-display`, `--space-sm`, `--space-md`, `--space-lg`, `--space-xl` và sử dụng trong giao diện. Giữ Grid/Flexbox và các breakpoint responsive.
- **Nhận xét & tinh chỉnh của SV:** Sinh viên yêu cầu giữ hình hài bản gốc; sau đó chọn tên repository theo đúng mẫu đề. Chưa có nhận xét nghiệm thu khác trong cuộc trao đổi tại thời điểm tạo nhật ký.

### Lần 2: Tích hợp thư viện Animate.css & AOS

- **Prompt đã dùng:** “những yêu cầu thì giống đề thi kiểm tra giữa kì” trong yêu cầu ban đầu.
- **Kết quả AI tạo ra:** Nhúng Animate.css 4.1.1 và AOS 2.3.4 vào hai file mã nguồn. Tiêu đề dùng `animate__animated animate__fadeInUp`; các khối nội dung dùng `data-aos="fade-up"`.
- **Thách thức gặp phải:** Nội dung các trang được dựng bằng JavaScript, nên chỉ khởi tạo AOS một lần sẽ không theo kịp các trang mới. Bốn file không cho phép giữ thư viện thành các file riêng.
- **Cách xử lý của AI:** Giữ mã thư viện và thông tin giấy phép trong bundle, gọi `AOS.refreshHard()` sau mỗi lần dựng trang. Tôn trọng `prefers-reduced-motion`, giữ nút bỏ qua màn mở đầu, bổ sung hover và focus rõ ràng.
- **Debug prompt riêng của sinh viên:** Chưa có; đây là xử lý kỹ thuật do trợ lý thực hiện theo yêu cầu chung.

### Lần 3: Giữ nội dung và điều hướng trên GitHub Pages

- **Ràng buộc từ prompt:** Chỉ bốn file, nhưng phải giữ toàn vẹn các trang và luồng sử dụng.
- **Kết quả AI tạo ra:** Nhúng danh mục 250 game, các bài biên tập và 11 ảnh nội bộ trong `index.html`. Các ảnh Steam/nhà phát triển và Google Fonts tiếp tục sử dụng nguồn ngoài như bản gốc.
- **Thách thức:** GitHub Pages không xử lý các đường dẫn ứng dụng như `/games/hollow-knight` khi tải trực tiếp nếu không có file hoặc cấu hình phụ.
- **Cách xử lý:** Dùng đường dẫn fragment như `#/games/hollow-knight`, giữ tìm kiếm, bộ lọc, mục lục, Back/Forward và tải lại trang mà không cần `404.html`.
- **Dữ liệu cá nhân:** Sổ tay, hồ sơ, cảm nhận và bộ sưu tập lưu trong trình duyệt bằng khóa riêng của Review Game. Không dùng chung dữ liệu với Indieverse.
- **Giới hạn minh bạch:** Không có máy chủ tài khoản, diễn đàn, gửi email hoặc CMS trong bản tĩnh. Các giao diện liên quan ghi rõ chưa kết nối; nội dung và điểm biên tập vẫn được ghi là minh họa.

### Lần 4: Kiểm thử và bàn giao

- Kiểm tra 21 loại đường dẫn ở desktop 1440px và di động 390px: trang chủ, danh sách game/review, chi tiết, bộ sưu tập, chuyên đề, tìm kiếm, thư viện, hồ sơ, tác giả, thông tin và không tìm thấy. Không có tràn ngang.
- Dựng và kiểm tra đủ 500 đường dẫn chi tiết (250 game + 250 bài review), không có lỗi JavaScript.
- Kiểm tra bằng thao tác giao diện: tìm kiếm Celeste, bộ lọc không có kết quả, sửa trạng thái/ghi chú sổ tay rồi tải lại, menu mobile, mở URL chi tiết trực tiếp, Back/Forward.
- Chặn tài nguyên ngoài để xác nhận dữ liệu nhúng vẫn đọc được khi ảnh/phông bên ngoài không tải được. Kiểm tra hiệu ứng ở chế độ thường và reduced motion.
- Chụp và đối chiếu trang chủ với Indieverse; xem bố cục kho game, bài đánh giá, Góc indie và thư viện trên desktop/mobile. Đã kiểm tra dấu tiếng Việt qua ảnh tiêu đề và đoạn văn.
- Hai lần kiểm thử ban đầu dùng sai bộ chọn: nút lưu nhanh chỉ thêm vào wishlist, còn nút sửa sổ tay mới mở hộp thoại. Đã sửa kịch bản kiểm thử theo đúng hành vi giao diện; không coi đây là lỗi sản phẩm.

### Lần 5: Tối ưu tốc độ và thêm chuyển động theo phản hồi

**Prompt bổ sung thực tế:**

> tôi mới check lại trang web nó đang bị lỗi là load hơi lâu bạn cải thiện điều đó giúp tôi đồng thời làm animation cho trang web luôn

- Nén 11 ảnh JPEG nội bộ từ tổng 3.793 MB còn 0.327 MB WebP; giữ ảnh minh họa và tỷ lệ, giới hạn chiều rộng 1280px.
- Nén dữ liệu danh mục bằng gzip, nhúng base64 rồi giải nén bằng `DecompressionStream` có sẵn trong các trình duyệt hiện đại. Dữ liệu văn bản vẫn đầy đủ 250 game; không phải gọi API để tải danh mục.
- HTML giảm từ 7.533 MB còn 1.055 MB (khoảng 86%). CSS khoảng 0.241 MB. Đây là kích thước file, không phải cam kết thời gian tải trên mọi mạng.
- Phông Google tải bất đồng bộ; ưu tiên ảnh hero, giải mã ảnh bất đồng bộ, trì hoãn ảnh bên dưới màn hình. Màn mở đầu giảm từ 1700ms xuống 650ms và luôn có nút bỏ qua.
- Giữ animation của bản gốc, thêm Animate.css cho tiêu đề và AOS cho các section. Tắt chuyển động khi người dùng bật reduced motion.
- Kiểm thử lại 500 đường dẫn và các luồng tương tác sau tối ưu: đạt, không có lỗi JavaScript.

## 3. Đánh giá cá nhân về quá trình Vibe Coding

**Phần sinh viên tự hoàn thiện sau khi đọc mã và dùng thử sản phẩm.** Trợ lý không viết thay trải nghiệm hoặc nhận xét cá nhân chưa được cung cấp.

- AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất? **Chưa được sinh viên cung cấp.**
- Bài học rút ra khi đặt câu hỏi cho AI trong thiết kế web? **Chưa được sinh viên cung cấp.**
- Gợi ý để tự đánh giá: so sánh giao diện trước/sau; giải thích vì sao bốn file vẫn có nhiều trang; giải thích AOS khi điều hướng và giới hạn localStorage.

## 4. Cấu trúc, cách chạy và nguồn

| File | Vai trò |
| --- | --- |
| `index.html` | Khung HTML, dữ liệu game, mã JavaScript, AOS và ảnh nội bộ nhúng |
| `style.css` | Giao diện gốc, responsive, Animate.css, AOS CSS, hover/focus |
| `PROMPT_LOG.md` | Nhật ký yêu cầu, quyết định, kiểm thử và giới hạn |
| `.gitignore` | Chỉ cho phép bốn file bàn giao vào repository |

Mở `index.html` bằng trình duyệt hiện đại hỗ trợ `DecompressionStream` (Chrome/Edge/Firefox/Safari hiện đại), hoặc truy cập GitHub Pages. Không cần npm, cài thư viện hay bước build. Cần Internet cho các ảnh bên ngoài và Google Fonts; dữ liệu văn bản và thư viện hiệu ứng đã nhúng. File HTML chứa dữ liệu nén và ảnh WebP, đổi lại không cần thư mục assets hoặc file JavaScript riêng.

- Repository bài nộp: https://github.com/tranngochuyc-cyber/Huy_TranNgoc_125001758
- Live preview: https://tranngochuyc-cyber.github.io/Huy_TranNgoc_125001758/

- Indieverse gốc: https://github.com/tranngochuyc-cyber/indieverse
- Animate.css 4.1.1, MIT: https://github.com/animate-css/animate.css
- AOS 2.3.4, MIT: https://github.com/michalsnik/aos
- Ảnh game và các nguồn thông tin được giữ ở liên kết Steam/nhà phát triển trong từng hồ sơ game; không tuyên bố sở hữu artwork.
