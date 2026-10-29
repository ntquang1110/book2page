# BOOK2PAGE

Skill package chuyển nội dung sách thành một trang HTML học sâu bằng tiếng Việt.

## Thành phần
- `SKILL.md`: mục tiêu, nguyên tắc, pipeline và QA gates.
- `prompt.md`: prompt điều phối agent.
- `schema.json`: JSON Schema kiểm tra dữ liệu đầu ra.
- `template.html`: HTML self-contained, CSS/JS inline, không CDN.
- `design.default.css`: token dự phòng.
- `DESIGN.md`: design system có thể chỉnh.
- `SOURCE_SPEC.txt`: bản yêu cầu nguồn được giữ lại để đối chiếu.

## Dùng nhanh
1. Đặt thư mục `book2page` ở vị trí agent có quyền đọc.
2. Cập nhật `DESIGN.md` nếu muốn thay đổi hệ thống thiết kế.
3. Đưa sách/PDF/EPUB hoặc TOC + trích đoạn cho agent.
4. Yêu cầu agent đọc `SKILL.md`, `prompt.md`, `schema.json`, `template.html`, `DESIGN.md`, sau đó chạy pipeline và xuất `book-<slug>.html`.
5. Không dùng Tier A nếu agent không thực sự đọc được file nguồn.

## Ghi chú
`template.html` hiện là template chạy độc lập với dữ liệu mẫu Tier C. Thay JSON trong `BOOK_DATA` bằng dữ liệu đã kiểm chứng để tạo trang sách cụ thể. Khi tự động hóa, hãy parse template, thay token/override từ `DESIGN.md`, validate JSON, rồi xuất file theo slug.
