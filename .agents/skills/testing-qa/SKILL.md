---
name: testing-qa
description: Kỹ năng điều phối và thực thi kiểm thử chất lượng, kiểm tra cú pháp và nghiệm thu giao diện cho NAM ENGINEERING. Sử dụng khi cần kiểm tra tính hợp lệ của mã nguồn, rà soát tính toàn vẹn nội dung MDX, kiểm thử trên trình duyệt hoặc tổng hợp báo cáo milestone.
---

# Testing & QA Skill

Kỹ năng này hướng dẫn Agent các tiêu chuẩn và quy trình kiểm thử, đảm bảo chất lượng kỹ thuật và nghiệm thu cho dự án **NAM ENGINEERING**.

## 1. Trách nhiệm & Phạm vi
- Thực hiện kiểm tra tính hợp lệ của cấu trúc, tệp quy tắc và cú pháp mã nguồn.
- Rà soát tính toàn vẹn của các bài viết MDX (cấu trúc frontmatter, liên kết nội bộ, tính hợp lệ của thẻ).
- Điều phối kiểm thử giao diện thực tế trên trình duyệt bằng cách phối hợp với các plugin skills sẵn có của hệ thống (`chrome-devtools`, `a11y-debugging`, `debug-optimize-lcp`).
- Tổng hợp và xuất báo cáo nghiệm thu milestone chuẩn mực.
- **Ranh giới nghiêm ngặt:** Tuân thủ nguyên tắc kiểm thử thực tế (Rule 05) — chỉ chạy những lệnh đã thực sự tồn tại trong dự án, không giả định các script `npm run ...` hay `tsc` đã sẵn sàng khi chưa có cấu hình. Không tự ý sửa đổi mã nguồn trong lúc kiểm thử mà chỉ phát hiện và báo cáo vấn đề.

## 2. Quy trình Kiểm thử Theo Từng Giai đoạn

### Giai đoạn Hiện tại (Cấu hình Môi trường & Quy tắc)
Khi dự án chưa có `package.json` hoặc mã nguồn ứng dụng:
1. **Kiểm tra Cấu hình:** Xác minh sự tồn tại của các tệp quy tắc và kỹ năng theo đúng đường dẫn được phê duyệt.
2. **Kiểm tra Cú pháp Markdown & YAML:** Đảm bảo tất cả các tệp `.md` không có lỗi cú pháp và các tệp `SKILL.md` đều có khối YAML frontmatter hợp lệ (`name`, `description`).
3. **Báo cáo Minh bạch:** Nêu rõ các kiểm thử mức ứng dụng (linter, build, typecheck) chưa thể thực hiện do dự án chưa khởi tạo mã nguồn.

### Giai đoạn Phát triển Ứng dụng (Sau khi Khởi tạo Stack)
Khi dự án đã có `package.json` và cấu hình build:
1. **Kiểm tra Kiểu (Static Type Check):** Chạy `npx tsc --noEmit` (hoặc lệnh tương ứng) để phát hiện lỗi kiểu dữ liệu.
2. **Kiểm tra Quy chuẩn Mã nguồn:** Chạy linter (`npm run lint` nếu đã được cấu hình).
3. **Kiểm tra Biên dịch:** Chạy `npm run build` để kiểm tra toàn bộ luồng tạo trang tĩnh SSG có thành công hay không.
4. **Kiểm tra Trình duyệt (Browser QA):**
   - Khi dev server hoạt động, phối hợp sử dụng `chrome-devtools` để kiểm tra console log và network request.
   - Sử dụng `a11y-debugging` để rà soát các vấn đề về khả năng tiếp cận (độ tương phản, nhãn ARIA, phím Tab).
   - Sử dụng `debug-optimize-lcp` để đánh giá thời gian render nội dung chính.

## 3. Mẫu Báo cáo Nghiệm thu Milestone (Milestone QA Report)
Sau mỗi milestone, Agent sử dụng mẫu báo cáo dưới đây để phản hồi cho người dùng:

```markdown
## Milestone QA & Verification Report

### 1. Danh sách Tệp đã Tạo / Chỉnh sửa
| STT | Đường dẫn Tệp | Thao tác | Mô tả tóm tắt |
| :--- | :--- | :--- | :--- |
| 1 | `path/to/file` | Tạo mới / Sửa | ... |

### 2. Kết quả Kiểm thử Đã thực hiện
| Nhóm kiểm thử | Lệnh / Phương pháp | Kết quả | Ghi chú |
| :--- | :--- | :--- | :--- |
| Kiểm tra Cấu trúc | Đọc tệp & kiểm tra thư mục | Đạt | ... |
| Static Verification | `tsc` / Linter | Chưa thực hiện | Chưa có package.json |

### 3. Vấn đề Tồn tại & Điểm cần Quyết định
- Vấn đề 1: ...
- Điểm cần phê duyệt tiếp theo: ...
```
