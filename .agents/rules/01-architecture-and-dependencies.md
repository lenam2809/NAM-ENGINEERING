# Rule 01: Kiến trúc và Quản lý Phụ thuộc (Architecture & Dependency Rules)

Tài liệu quy tắc này áp dụng cho toàn bộ cấu trúc dự án và quản lý dependency của **NAM ENGINEERING**.

## 1. Định hướng Kiến trúc MVP
- **Công nghệ nền tảng:** Next.js (App Router), TypeScript, Tailwind CSS, MDX.
- **Trình quản lý gói:** Sử dụng duy nhất `npm` với tệp khóa đồng nhất `package-lock.json`.
- **Ranh giới công nghệ MVP:**
  - Không tích hợp ASP.NET Core, Database hệ thống, Supabase hoặc CMS trong giai đoạn MVP.
  - Cấu trúc ứng dụng chi tiết sẽ được quyết định tại milestone Architecture. Hiện tại không tự ý tạo source code ứng dụng hoặc cấu trúc thư mục rác.
  - Ưu tiên kiến trúc Static Generation (SSG) và React Server Components (RSC) cho các trang bài viết kỹ thuật để đảm bảo tốc độ tải tối đa.

## 2. Quy định Phụ thuộc (Dependency Management)
- **Quy trình Khởi tạo Stack:** Khi tiến hành khởi tạo dự án, Agent phải trình bày danh sách đầy đủ các package và phiên bản dự kiến (dependencies và devDependencies) để người dùng phê duyệt trước khi cài đặt.
- **Kiểm soát Dependency bổ sung:** Sau khi stack được khởi tạo, mọi package bổ sung ngoài danh sách đã duyệt đều phải xin phép trước.
- **Cấm tự ý cài đặt:** Không tự ý chạy `npm install <package>` khi chưa được người dùng xác nhận.
- **Không tự ý nâng cấp:** Không tự ý nâng cấp phiên bản lớn (major upgrade), không tự ý đổi sang package tương đương (ví dụ đổi thư viện styling hay chuyển sang pnpm/yarn/bun) khi chưa có yêu cầu.
- **Không mặc định thư viện phức tạp:** Không mặc định cài đặt Shiki, KaTeX, Mermaid, Zod hay bất kỳ thư viện xử lý AST nào khi chưa có quyết định kiến trúc cụ thể.

## 3. Ranh giới
- Quy tắc này chỉ quản lý kiến trúc mã nguồn và dependency; không điều phối văn phong bài viết hay thiết kế UI chi tiết.
