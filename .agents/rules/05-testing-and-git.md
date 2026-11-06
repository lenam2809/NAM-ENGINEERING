# Rule 05: Kiểm thử, Git và Báo cáo Milestone (Testing, Git & Verification Rules)

Tài liệu quy tắc này áp dụng cho toàn bộ quy trình kiểm thử chất lượng, kỷ luật kho mã nguồn Git và báo cáo tiến độ của **NAM ENGINEERING**.

## 1. Kỷ luật Quản lý Kho mã nguồn Git
- **Không tự ý thao tác Git:**
  - Không tự ý chạy `git init` khi chưa được phê duyệt kế hoạch khởi tạo Git.
  - Tuyệt đối không tự ý thực hiện `git commit`, `git push`, chuyển nhánh, xóa nhánh hoặc gộp nhánh khi chưa có lệnh rõ ràng từ người dùng.
  - Cấm thực thi các lệnh nguy hiểm hoặc có tính phá hủy (ví dụ: `git reset --hard`, `git clean -fd`, `git push --force`).
- **Tương thích Hệ điều hành Windows:** Khi khởi tạo kho mã nguồn, phải tạo tệp cấu hình `.gitattributes` để chuẩn hóa ký tự xuống dòng (LF) cho toàn bộ tệp mã nguồn web, tránh lỗi diff định dạng CRLF/LF trên Windows.

## 2. Quy tắc Kiểm thử Thực tế (Realistic Verification)
- **Chỉ chạy kiểm thử khả dụng:** Chỉ chạy các lệnh kiểm thử và xác minh đã thực sự tồn tại và phù hợp với trạng thái hiện tại của dự án.
- **Không giả định trước script:** Tuyệt đối không giả định `npm run lint`, `npm run build` hoặc `tsc --noEmit` đã sẵn sàng hoạt động khi dự án chưa có `package.json` hoặc chưa cài đặt các gói công cụ tương ứng.
- **Minh bạch trạng thái:** Khi báo cáo, phải ghi rõ ràng những loại kiểm thử đã thực hiện và những loại kiểm thử chưa thể thực hiện được do trạng thái hiện tại của dự án.

## 3. Quy chuẩn Báo cáo Milestone (Mandatory Reporting)
Sau khi kết thúc mỗi milestone hoặc tác vụ phát triển, Agent bắt buộc phải tổng hợp và trình bày báo cáo gồm 3 phần:
1. **Danh sách file:** Bảng chi tiết toàn bộ các file đã tạo mới, chỉnh sửa hoặc xóa kèm đường dẫn cụ thể.
2. **Kiểm thử đã chạy:** Danh sách các lệnh kiểm tra đã thực thi, kết quả đạt/không đạt, cùng danh sách các kiểm thử chưa thể thực hiện (kèm lý do kỹ thuật).
3. **Vấn đề tồn tại & Điểm cần quyết định:** Nêu rõ các rủi ro, nợ kỹ thuật (nếu có) và những điểm cần người dùng đưa ra quyết định tiếp theo.

## 4. Ranh giới
- Quy tắc này quản lý quy trình nghiệm thu, an toàn kho mã nguồn và kiểm thử chất lượng; không can thiệp vào logic thuật toán hay chi tiết giao diện.
