---
name: mdx-content-engineering
description: Kỹ năng quản lý và xử lý cấu trúc tệp MDX, frontmatter và hiển thị nội dung tĩnh trong Next.js cho NAM ENGINEERING. Sử dụng khi thiết kế luồng đọc tệp MDX, ánh xạ thẻ MDX sang component và kiểm tra tính toàn vẹn cú pháp nội dung.
---

# MDX Content Engineering Skill

Kỹ năng này hướng dẫn Agent các nguyên tắc và kỹ thuật quản lý, xử lý và hiển thị các tệp nội dung Markdown/MDX trong dự án **NAM ENGINEERING**.

## 1. Trách nhiệm & Phạm vi
- Quản lý quy chuẩn tệp nội dung `.mdx`, cấu trúc metadata/frontmatter và quy ước đặt tên bài viết.
- Định hướng phương pháp đọc và render nội dung MDX trong kiến trúc Next.js App Router (sử dụng giải pháp tĩnh, tinh gọn phù hợp phạm vi MVP).
- Ánh xạ các phần tử Markdown chuẩn sang các component Tailwind CSS của dự án.
- **Ranh giới nghiêm ngặt:** Chỉ sử dụng giải pháp MDX thuộc phạm vi kiến trúc MVP đã duyệt. Tuyệt đối không tự ý cài đặt Shiki, KaTeX, Mermaid, Zod hay bất kỳ plugin AST phức tạp nào khi chưa có quyết định kiến trúc từ người dùng.

## 2. Tiêu chuẩn Quản lý Tệp MDX
1. **Quy ước Tệp & Thư mục:**
   - Tên tệp đặt theo chuẩn `kebab-case.mdx` (ví dụ: `nextjs-static-generation-deep-dive.mdx`).
   - Đường dẫn slug tương ứng phải ngắn gọn, phản ánh đúng chủ đề bài viết.
2. **Cấu trúc Frontmatter Chuẩn:**
   Mỗi tệp bắt đầu bằng khối YAML frontmatter hợp lệ:
   ```markdown
   ---
   title: "Tiêu đề bài viết kỹ thuật"
   description: "Mô tả súc tích nội dung bài viết phục vụ SEO và xem trước."
   date: "2026-11-06"
   slug: "tieu-de-bai-viet-ky-thuat"
   tags: ["Nextjs", "TypeScript", "Architecture"]
   published: true
   ---
   ```
3. **Tính Toàn vẹn Cú pháp MDX:**
   - Mọi thẻ JSX trong tệp MDX phải được đóng mở hợp lệ.
   - Các ký tự đặc biệt trong văn bản kỹ thuật (như `<`, `>`, `{`, `}`) cần được đặt trong khối mã inline (dấu backtick) để tránh làm hỏng quá trình phân tích cú pháp JSX của MDX.

## 3. Ánh xạ Thành phần Giao diện (Component Mapping)
Khi tích hợp MDX với giao diện Next.js:
- Ánh xạ các thẻ tiêu chuẩn (`h1`, `h2`, `h3`, `p`, `pre`, `code`, `blockquote`, `ul`, `ol`, `a`, `img`) sang các class Tailwind CSS tương ứng theo phong cách thiết kế đã định hình.
- Đảm bảo các khối code hiển thị rõ nét, có màu nền tương phản cao, và đoạn văn bản có kích thước và khoảng cách dòng dễ đọc.

## 4. Phối hợp
- Phối hợp với `frontend-development` để đảm bảo các component MDX hiển thị đồng bộ với layout chung.
- Phối hợp với `technical-writing` để hỗ trợ tác giả sử dụng đúng các cú pháp và khối nội dung chuẩn.
- Phối hợp với `testing-qa` để kiểm tra việc biên dịch và hiển thị bài viết trước khi xuất bản.
