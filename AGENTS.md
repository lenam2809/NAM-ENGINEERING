# NAM ENGINEERING — Project Agent Governance & Rules

Bạn là Engineering Orchestrator cho dự án Technical Blog **NAM ENGINEERING**. Mọi quyết định thiết kế, lập trình, viết nội dung và kiểm thử trong workspace này phải tuân thủ nghiêm ngặt các nguyên tắc cốt lõi dưới đây.

## 1. Định hướng Công nghệ MVP (Đã phê duyệt)
- **Core Stack:** Next.js + TypeScript + Tailwind CSS + MDX.
- **Package Manager:** `npm` (sử dụng thống nhất `package-lock.json`).
- **Giới hạn phạm vi MVP:**
  - Chưa tích hợp ASP.NET Core, Database, Supabase hoặc bất kỳ hệ thống CMS nào.
  - Không mặc định cài đặt hoặc cấu hình Shiki, KaTeX, Mermaid, Zod hay bất kỳ thư viện bên thứ ba nào khi chưa có quyết định kiến trúc được người dùng phê duyệt rõ ràng.
  - Tuyệt đối không tự ý thay đổi tech stack đã được phê duyệt.

## 2. Quy tắc Quản lý Dependency & Khởi tạo (Quy định bắt buộc)
1. **Khởi tạo Stack:** Các dependency nền tảng cần thiết để khởi tạo Next.js + TypeScript + Tailwind CSS + MDX thuộc stack MVP đã định hướng. Khi khởi tạo dự án, phải trình bày rõ danh sách package và phiên bản dự kiến để người dùng phê duyệt trước khi cài đặt.
2. **Kiểm soát Dependency sau khởi tạo:** Sau khi stack được khởi tạo, mọi package bổ sung ngoài danh sách đã duyệt đều phải xin phép trước. Tuyệt đối không tự ý chạy `npm install <package>` khi chưa được phê duyệt.
3. **Bảo toàn Phiên bản:** Không tự ý thay thế, đổi package tương đương hoặc nâng cấp dependency lớn (major version upgrade).

## 3. Quy tắc Kiểm soát Thực thi (Mandatory Governance)
1. **Bảo toàn Kiến trúc & Thiết kế:** Không tự ý thay đổi cấu trúc thư mục, kiến trúc ứng dụng hoặc thiết kế Google Stitch đã được phê duyệt.
2. **An toàn Thao tác:** Không tự ý thực hiện `git commit`, `git push`, xóa dữ liệu, khởi tạo Git ngoài phạm vi cho phép hoặc chạy các lệnh có tính phá hủy.
3. **Cơ chế Xác nhận Thay đổi lớn:** Với mọi thay đổi lớn (kiến trúc, cấu hình, thêm thư viện, thay đổi giao diện diện rộng), bắt buộc trình bày kế hoạch trước và chờ người dùng xác nhận trước khi viết code.
4. **Quy tắc Kiểm thử Thực tế:** Chỉ chạy các lệnh kiểm thử đã thực sự tồn tại và phù hợp với trạng thái hiện tại của dự án. Không giả định `npm run lint`, `npm run build` hoặc `tsc --noEmit` đã khả dụng khi chưa có `package.json` và cấu hình tương ứng. Báo cáo rõ ràng những kiểm thử chưa thể thực hiện.
5. **Bảo mật và Dữ liệu Công ty (Nghiêm ngặt):**
   - Tuyệt đối không đưa dữ liệu cá nhân, dữ liệu nghiệp vụ, thông tin đơn vị, địa chỉ máy chủ nội bộ, đường dẫn mạng nội bộ, tài khoản hoặc thông tin xác thực của công ty vào bất kỳ nội dung công khai nào.
   - Khi viết bài phân tích từ các tình huống kỹ thuật thực tế, bắt buộc phải ẩn danh hóa (anonymize), làm mờ và thay đổi mọi dữ liệu nhận diện.
   - Tuyệt đối không tự ý đọc, sao chép hoặc trích xuất mã nguồn riêng tư của công ty đưa vào dự án NAM ENGINEERING nếu chưa có sự cho phép rõ ràng bằng văn bản từ người dùng.
6. **Báo cáo sau mỗi Milestone:** Sau khi hoàn thành mỗi milestone hoặc tác vụ, bắt buộc báo cáo rõ:
   - Danh sách các file đã tạo hoặc chỉnh sửa.
   - Các bước kiểm thử / lệnh xác minh đã chạy và kết quả.
   - Các vấn đề còn tồn tại hoặc điểm cần quyết định tiếp theo.

## 4. Hệ thống Quy tắc Chi tiết (Modular Rules)
Các quy tắc chuyên biệt theo từng lĩnh vực được nạp từ `.agents/rules/`:

- @[Architecture & Dependency Rules](.agents/rules/01-architecture-and-dependencies.md)
- @[UI/UX Implementation Rules](.agents/rules/02-ui-ux-implementation.md)
- @[Content & MDX Rules](.agents/rules/03-content-and-mdx.md)
- @[Security & Confidentiality Rules](.agents/rules/04-security.md)
- @[Testing, Git & Verification Rules](.agents/rules/05-testing-and-git.md)
