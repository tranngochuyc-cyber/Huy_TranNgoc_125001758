# Review Game — Thế giới nhỏ. Trải nghiệm lớn.

**Sinh viên:** Trần Ngọc Huy · **MSSV:** 125001758 · **Học phần:** Thiết kế Web

Website khám phá và đánh giá game indie bằng tiếng Việt, được triển khai dưới dạng website tĩnh trên GitHub Pages. Đây là bản nộp giữa kỳ phát triển từ dự án Indieverse của cùng chủ sở hữu; chi tiết nguồn gốc, các prompt thực tế và các lần tinh chỉnh nằm trong [PROMPT_LOG.md](PROMPT_LOG.md).

**Xem trực tiếp:** https://tranngochuyc-cyber.github.io/Huy_TranNgoc_125001758/

## Cấu trúc mã nguồn

| File | Chức năng |
| --- | --- |
| `index.html` | HTML semantic (header, nav, main, section/article, footer) và JavaScript điều hướng, tương tác |
| `style.css` | CSS Variables, Flexbox/Grid, responsive, hiệu ứng hover/focus, Animate.css 4.1.1, CSS của AOS 2.3.4 |
| `review-data.json` | Catalog game nén gzip/base64 cùng một số ảnh được nhúng; tải sau khi mở trang |
| `PROMPT_LOG.md` | Nhật ký prompt, giải pháp kỹ thuật, nhận xét cần xác nhận và giới hạn kiểm thử |
| `README.md` | Mô tả cấu trúc, cách chạy, phạm vi tính năng và nguồn tham khảo |
| `.gitignore` | Danh sách file được theo dõi trong bản nộp |
| `.gitattributes` | Hướng dẫn GitHub Linguist nhận diện stylesheet là CSS |

Yêu cầu ban đầu từng giới hạn bốn file. Bản nộp hiện dùng bảy file để dữ liệu tách khỏi mã nguồn và tài liệu khớp với cấu trúc thực tế. Đề thi không đặt giới hạn chỉ bốn file.

## Chạy thử

**Cách 1 — nhanh nhất:** mở link **Xem trực tiếp** ở đầu tài liệu. Repo là public và đã cấu hình GitHub Pages.

**Cách 2 — máy Windows, chạy bản local:**
1. Mở **Windows PowerShell** trên máy có Git và Python.
2. Nhập lần lượt:
   ```powershell
   git clone https://github.com/tranngochuyc-cyber/Huy_TranNgoc_125001758.git
   cd Huy_TranNgoc_125001758
   python -m http.server 8000
   ```
3. Mở trình duyệt vào `http://localhost:8000/`. Dừng server bằng **Ctrl+C** tại PowerShell.

Hoặc dùng VS Code với tiện ích Live Server. Không nhấp đúp `index.html` để chạy dưới dạng `file://`, vì trình duyệt có thể chặn lệnh `fetch('review-data.json')`. Không cần npm hay bước build.

## Đối chiếu các yêu cầu kỹ thuật

- **Semantic HTML5:** khung chính có `header`, `main`, `footer`; các component JavaScript tạo `nav`, `section`, `article` trong nội dung khi render.
- **CSS Variables:** `:root` quản lý palette (`--bg`, `--panel`, `--purple`, `--line`), font, spacing, chiều rộng bố cục; dùng cùng Flexbox, Grid và các media query.
- **Animate.css:** lớp `animate__animated` và `animate__fadeInUp` cho tiêu đề.
- **AOS:** khởi tạo bằng `AOS.init(...)` và cập nhật `AOS.refreshHard()` sau các lần đổi trang; tôn trọng `prefers-reduced-motion`.
- **Tương tác:** tìm kiếm, xem chi tiết, lưu game và sổ tay cá nhân. Các nút và liên kết chính có trạng thái hover/focus.

## Giới hạn cần biết khi giảng viên thử nghiệm

- URL trang con dùng hash route `#/games/...` để tải lại trực tiếp không báo 404 trên Pages.
- Danh sách yêu thích, hồ sơ, bộ sưu tập, ghi chú và cảm nhận chỉ lưu ở **localStorage** của trình duyệt; không đồng bộ, không tạo tài khoản thật.
- Form liên hệ/bản tin và các tính năng cần backend hiện **chưa hoạt động**, có thông báo tương ứng; không giả làm hệ thống gửi thư.
- Văn bản catalog sử dụng dữ liệu nén nên cần trình duyệt hiện đại hỗ trợ `DecompressionStream`. Ảnh bên ngoài và Google Fonts cần Internet.
- GitHub Pages báo deploy thành công không đồng nghĩa mọi tính năng đã được kiểm thử xuyên suốt trên mọi thiết bị. Những kiểm thử được ghi rõ theo từng thời điểm trong nhật ký.

## Nguồn và bản quyền

- Dự án nguồn do cùng chủ sở hữu quản lý: https://github.com/tranngochuyc-cyber/indieverse
- Animate.css 4.1.1 (MIT): https://github.com/animate-css/animate.css
- AOS 2.3.4 (MIT): https://github.com/michalsnik/aos
- Ảnh và dữ liệu các trò chơi trỏ đến Steam/nhà phát triển. Không tuyên bố sở hữu hình ảnh hoặc thương hiệu game.
- Tỷ lệ HTML/CSS trên GitHub được Linguist ước tính theo mã nguồn và quy tắc nhận diện, không phải tiêu chí chấm chất lượng hoặc yêu cầu 50/50.
