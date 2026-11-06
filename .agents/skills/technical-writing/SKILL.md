---
name: technical-writing
description: Kỹ năng hướng dẫn biên soạn, lập dàn ý và chuẩn hóa bài viết kỹ thuật chuyên sâu cho NAM ENGINEERING. Sử dụng khi lập dàn ý, viết mới hoặc hiệu đính các bài viết kỹ thuật, bài chia sẻ kiến trúc và hướng dẫn thực hành.
---

# Technical Writing Skill

Kỹ năng này hướng dẫn Agent các tiêu chuẩn và phương pháp biên soạn bài viết kỹ thuật chuyên sâu chất lượng cao cho blog **NAM ENGINEERING**.

## 1. Trách nhiệm & Phạm vi
- Hướng dẫn lập dàn ý, viết mới, biên tập và cấu trúc hóa các bài viết kỹ thuật, bài phân tích kiến trúc phần mềm và hướng dẫn chuyên sâu.
- Đảm bảo tính sư phạm, độ chính xác kỹ thuật, khả năng tái lập của các ví dụ mã nguồn và sự mạch lạc trong văn phong.
- **Ranh giới nghiêm ngặt:** Tuân thủ tuyệt đối quy tắc bảo mật dữ liệu công ty (Rule 04). Không đưa bất kỳ thông tin nội bộ thực tế nào vào bài viết. Không tự ý chỉnh sửa cấu hình hệ thống hay source code ứng dụng khi đang thực hiện nhiệm vụ biên soạn nội dung.

## 2. Cấu trúc Chuẩn của Bài viết Kỹ thuật
Mỗi bài viết chuyên sâu trên NAM ENGINEERING nên tuân thủ khung cấu trúc 5 phần logic:

1. **Đặt vấn đề & Bối cảnh (Problem & Context):**
   - Nêu rõ bài toán thực tế cần giải quyết là gì và tại sao các giải pháp thông thường chưa tối ưu.
   - Định hướng đối tượng độc giả mục tiêu và mục tiêu đầu ra sau khi đọc xong bài viết.
2. **Nguyên lý & Phân tích Kiến trúc (Architecture & Deep Dive):**
   - Giải thích bản chất hoạt động bên dưới (under-the-hood), mô hình luồng dữ liệu hoặc cơ chế cốt lõi.
   - Sử dụng sơ đồ logic hoặc bảng so sánh để làm rõ bản chất vấn đề.
3. **Giải pháp & Triển khai Mã nguồn (Implementation & Code):**
   - Trình bày mã nguồn minh họa từng bước, có ngữ cảnh đầy đủ, dễ hiểu.
   - Mọi khối code đều phải có chú thích rõ ràng ở các dòng cốt lõi và giải thích lý do lựa chọn cách viết đó.
4. **Đánh đổi Kỹ thuật & Bài học Thực tế (Trade-offs & Considerations):**
   - Phân tích khách quan các mặt hạn chế, chi phí vận hành, ảnh hưởng hiệu năng hoặc những trường hợp không nên áp dụng giải pháp này.
5. **Tổng kết & Tài liệu Tham khảo (Summary & Next Steps):**
   - Tóm tắt 2–3 điểm then chốt độc giả cần ghi nhớ.
   - Dẫn chiếu các tài liệu chính thức hoặc tiêu chuẩn kỹ thuật liên quan.

## 3. Tiêu chuẩn Văn phong Kỹ thuật (Engineering Tone)
- **Rõ ràng và Trực diện:** Đi thẳng vào trọng tâm kỹ thuật, tránh dùng từ ngữ hoa mỹ hoặc văn phong tiếp thị sáo rỗng.
- **Tính Chính xác và Nhất quán:** Sử dụng thuật ngữ chuyên môn chính xác và đồng nhất xuyên suốt bài viết.
- **Bảo mật và Ẩn danh tuyệt đối:** Nếu sử dụng bài học từ tình huống thực tế, phải ẩn danh hóa toàn bộ thông số, thay đổi tên dịch vụ, giả lập dữ liệu mẫu và tuyệt đối không để lộ thông tin của tổ chức hay khách hàng.

## 4. Phối hợp
- Phối hợp với `mdx-content-engineering` để đảm bảo bài viết tuân thủ đúng định dạng frontmatter và cấu trúc MDX.
