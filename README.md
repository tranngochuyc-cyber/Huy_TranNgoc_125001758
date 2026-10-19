# Review Game — Thế giới nhỏ. Trải nghiệm lớn.

Website khám phá và đánh giá game indie, giao diện tiếng Việt, chạy trực tiếp trên **GitHub Pages** mà không cần máy chủ riêng.

## Cấu trúc

- `index.html` — giao diện và mã ứng dụng tương tác.
- `style.css` — thiết kế, hiệu ứng, responsive; bao gồm Animate.css 4.1.1 (MIT).
- `review-data.json` — dữ liệu catalog nén và ảnh nhúng; được tải sau khi mở trang, không phải mã HTML/CSS.
- `PROMPT_LOG.md` — nhật ký phát triển.

## Chạy thử

Mở trang thông qua GitHub Pages hoặc một web server tĩnh tại thư mục gốc (ví dụ dùng VS Code Live Server). **Không mở trực tiếp `index.html` theo dạng `file://`**: trình duyệt có thể chặn việc tải `review-data.json` bằng `fetch`.

Trang dùng URL dạng `#/games`, `#/reviews`... để mở lại trang con mà không gặp lỗi 404 trên GitHub Pages. Dữ liệu cá nhân được lưu tại `localStorage` của chính trình duyệt, không đồng bộ giữa các thiết bị. Form cần dịch vụ backend (ví dụ newsletter, contact) không được gửi đi ở bản Pages.

## Ghi chú

Tỷ lệ ngôn ngữ GitHub dựa theo dung lượng mã được Linguist nhận diện, **không phản ánh chất lượng giao diện**. Tách catalog khỏi HTML giúp mã nguồn dễ bảo trì và tránh nhầm dữ liệu ảnh với HTML thực tế. Các ảnh/nguồn trò chơi được sử dụng cho mục đích giới thiệu và tham khảo.
