# Rule 04: Quy tắc Bảo mật và Bảo vệ Dữ liệu Công ty (Security & Confidentiality Rules)

Tài liệu quy tắc này áp dụng tuyệt đối cho toàn bộ mã nguồn, nội dung bài viết, cấu hình môi trường và các lệnh gọi công cụ trong **NAM ENGINEERING**.

## 1. Bảo vệ Thông tin Bí mật và Dữ liệu Công ty (Tuyệt đối nghiêm ngặt)
- **Cấm rò rỉ dữ liệu công ty:** Tuyệt đối không đưa dữ liệu cá nhân, dữ liệu nghiệp vụ, thông tin định danh đơn vị/khách hàng, địa chỉ IP máy chủ nội bộ, tên miền nội bộ, đường dẫn mạng nội bộ, tài khoản, mật khẩu hoặc bất kỳ thông tin xác thực nào của công ty vào mã nguồn công khai hoặc nội dung bài viết.
- **Quy tắc Ẩn danh hóa (Anonymization):** Khi viết bài chia sẻ kinh nghiệm kỹ thuật từ các dự án hoặc tình huống thực tế, bắt buộc phải ẩn danh hoàn toàn, đổi tên biến/thực thể, làm mờ dữ liệu và thay đổi toàn bộ thông số nhận diện để không thể truy nguyên nguồn gốc đơn vị thực tế.
- **Bảo vệ Mã nguồn Riêng tư:** Tuyệt đối không đọc, sao chép, trích xuất hoặc dán mã nguồn riêng tư/nội bộ của công ty vào workspace NAM ENGINEERING khi chưa có sự cho phép bằng văn bản rõ ràng từ người dùng.

## 2. Bảo mật Ứng dụng Web
- **Quản lý Secrets & Credentials:** Tuyệt đối không hardcode API keys, tokens, mật khẩu trong mã nguồn. Mọi tệp chứa biến môi trường (`.env`, `.env.local`, `.env.production`) phải được đưa vào danh sách loại trừ `.gitignore` và không bao giờ được commit.
- **Biến môi trường Client-side:** Chỉ sử dụng tiền tố `NEXT_PUBLIC_` cho các biến thực sự an toàn để phơi bày trên trình duyệt của người dùng cuối.
- **Phòng chống XSS:** Không sử dụng `dangerouslySetInnerHTML` tùy tiện; mọi luồng render mã nguồn hoặc văn bản động phải được kiểm soát chặt chẽ để chống injection.
- **Kiểm soát MCP Server:** Không tự ý kết nối hoặc thực hiện truy vấn đến các MCP server quản lý dữ liệu (như `supabase`, `postgresql`) ngoài phạm vi MVP khi chưa có yêu cầu từ người dùng.

## 3. Ranh giới
- Quy tắc bảo mật là hàng rào an toàn cao nhất; không vì sự tiện lợi hoặc đẩy nhanh tiến độ mà bỏ qua bất kỳ quy tắc bảo mật nào.
