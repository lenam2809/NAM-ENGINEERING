# Rule 03: Quy chuẩn Nội dung và MDX (Content & MDX Rules)

Tài liệu quy tắc này áp dụng cho toàn bộ các bài viết kỹ thuật, tài liệu và quy trình xử lý MDX trong **NAM ENGINEERING**.

## 1. Cấu trúc Tệp và Frontmatter Bài viết
- Mỗi bài viết kỹ thuật được lưu trữ dưới định dạng `.mdx` hoặc `.md` với phần frontmatter mở đầu bằng `---` và khai báo tối thiểu các trường chuẩn:
  - `title`: Tiêu đề bài viết (rõ ràng, trực diện, thể hiện đúng chủ đề kỹ thuật).
  - `description`: Tóm tắt nội dung bài viết trong 1–2 câu (dùng cho SEO và xem trước).
  - `date`: Ngày xuất bản định dạng chuẩn ISO (YYYY-MM-DD).
  - `slug`: Đường dẫn bài viết viết thường theo chuẩn kebab-case.
  - `tags`: Danh sách từ khóa chuyên môn phân loại bài viết.
  - `published`: Trạng thái xuất bản (`true`/`false`).
- Không đưa các trường metadata phức tạp khi chưa thống nhất cấu hình schema.

## 2. Tiêu chuẩn Nội dung Bài viết Kỹ thuật
- **Độ chính xác và Khả năng Tái lập:** Mọi đoạn code, câu lệnh terminal và cấu hình minh họa trong bài viết phải chính xác về mặt kỹ thuật, có thể chạy hoặc kiểm chứng được.
- **Khối code (Code Blocks):** Phải luôn chỉ định định dạng ngôn ngữ (ví dụ: ```` ```typescript ````, ```` ```bash ````, ```` ```json ````).
- **Văn bản Kỹ thuật:** Sử dụng thuật ngữ chuyên môn chính xác, giải thích rõ nguyên nhân - kết quả, cấu trúc luận điểm rõ ràng (Vấn đề -> Bản chất -> Giải pháp -> Đánh đổi kỹ thuật).

## 3. Ranh giới
- Quy tắc này quản lý cấu trúc nội dung và định dạng tệp MDX; không tự ý cấu hình các plugin chuyển đổi AST mở rộng (như Shiki, KaTeX, Mermaid) khi chưa có quyết định kiến trúc.
