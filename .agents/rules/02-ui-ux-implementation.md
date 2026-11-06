# Rule 02: Triển khai Giao diện & Trải nghiệm Người dùng (UI/UX Implementation Rules)

Tài liệu quy tắc này áp dụng cho toàn bộ các thành phần giao diện, layout và kiểu dáng của **NAM ENGINEERING**.

## 1. Bảo toàn Thiết kế Stitch
- Mọi giao diện, màu sắc, phông chữ, khoảng cách và cấu trúc component phải tuân thủ nghiêm ngặt thiết kế đã được phê duyệt từ Google Stitch (`StitchMCP`).
- Tuyệt đối không tự ý thay đổi, chỉnh sửa kiểu dáng hoặc làm lệch thiết kế Stitch đã được người dùng chốt.

## 2. Tiêu chuẩn Kỹ thuật Giao diện
- **Framework Styling:** Sử dụng Tailwind CSS chuẩn theo hệ thống token đã thống nhất từ thiết kế. Không viết CSS inline tùy tiện hoặc cài thêm UI framework ngoài luồng khi chưa xin phép.
- **HTML Ngữ nghĩa (Semantic HTML):** Bắt buộc sử dụng đúng các thẻ ngữ nghĩa của HTML5 (`<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`) để tối ưu hóa khả năng tiếp cận và SEO.
- **Tiêu chuẩn Tiếp cận (A11y):** Đảm bảo độ tương phản màu sắc đạt chuẩn WCAG 2.1 AA trên cả hai chế độ sáng/tối; hỗ trợ điều hướng bằng bàn phím (focus states rõ ràng); ảnh phải có thuộc tính `alt` mô tả chuẩn xác.
- **Trải nghiệm Đọc Bài viết Kỹ thuật:**
  - Chiều rộng cột đọc tối ưu cho mắt người đọc bài viết dài (65–75 ký tự mỗi dòng).
  - Khối code (code blocks) hiển thị monospace rõ nét, có chỉ báo ngôn ngữ, hỗ trợ thanh cuộn ngang khi dòng code dài.
  - Tránh hiện tượng giật nhảy layout (Cumulative Layout Shift - CLS = 0) khi tải font chữ hoặc hình ảnh.

## 3. Ranh giới
- Quy tắc này chỉ quản lý tầng hiển thị và tương tác người dùng; không can thiệp vào logic xử lý nội dung backend hoặc bảo mật server.
