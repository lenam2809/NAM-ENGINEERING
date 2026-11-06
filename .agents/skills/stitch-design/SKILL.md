---
name: stitch-design
description: Kỹ năng quản lý và làm việc với Google Stitch MCP để xem xét, tạo và chuyển đổi thiết kế giao diện sang thông số kỹ thuật cho NAM ENGINEERING. Sử dụng khi cần làm việc với Stitch UI, tra cứu màn hình hoặc trích xuất thông số thiết kế.
---

# Stitch Design Skill

Kỹ năng này hướng dẫn Agent cách tương tác an toàn và hiệu quả với hệ thống thiết kế **Google Stitch** thông qua máy chủ công cụ `StitchMCP` cho dự án **NAM ENGINEERING**.

## 1. Trách nhiệm & Phạm vi
- Tương tác với Google Stitch qua các công cụ lazy-loaded của `StitchMCP`.
- Tra cứu danh sách dự án, danh sách màn hình, lấy chi tiết màn hình thiết kế hoặc tạo màn hình từ mô tả theo yêu cầu của người dùng.
- Trích xuất bảng màu, kích thước font chữ, khoảng cách, bo góc và bố cục từ màn hình Stitch đã được phê duyệt để làm thông số triển khai cho Tailwind CSS.
- **Ranh giới nghiêm ngặt:** Không tự ý thay đổi thiết kế Stitch đã được người dùng chốt. Không tự ý viết mã nguồn ứng dụng vượt ra ngoài thông số thiết kế đã duyệt.

## 2. Quy trình Thực thi Chuẩn với StitchMCP
Vì `StitchMCP` là máy chủ công cụ nạp lười (lazy-loaded), Agent phải luôn tuân thủ quy trình 2 bước:

### Bước 1: Đọc tệp Schema của công cụ
Trước khi gọi một công cụ của `StitchMCP`, Agent bắt buộc phải dùng `read_file` đọc tệp định nghĩa schema tương ứng trong thư mục:
`C:\Users\Admin\.gemini\antigravity\mcp\StitchMCP\<toolName>.json`

Các công cụ chính thường dùng:
- `list_projects.json`: Xem danh sách các dự án Stitch hiện có.
- `get_project.json`: Lấy chi tiết thông tin của một dự án cụ thể.
- `list_screens.json`: Lấy danh sách các màn hình giao diện trong một dự án.
- `get_screen.json`: Đọc chi tiết mã nguồn HTML/CSS và thông số của một màn hình.
- `generate_screen_from_text.json`: Sinh màn hình giao diện mới từ mô tả văn bản (chỉ thực hiện khi có yêu cầu).
- `list_design_systems.json`: Tra cứu các hệ thống thiết kế đã lưu.

### Bước 2: Gọi công cụ qua `call_mcp_tool`
Sau khi xác định đúng tham số từ schema, Agent sử dụng `call_mcp_tool` với:
- `ServerName`: `"StitchMCP"`
- `ToolName`: `"<tên_công_cụ>"`
- `Arguments`: Đối tượng JSON chứa các tham số bắt buộc.

## 3. Chuyển đổi Thiết kế sang Thông số Kỹ thuật
Khi một màn hình Stitch được người dùng phê duyệt:
1. Trích xuất mã màu chủ đạo (Primary, Background, Surface, Border, Text Primary, Text Muted).
2. Trích xuất tỷ lệ khoảng cách (padding, margin, gap).
3. Đề xuất cách cấu hình tương ứng vào tệp Tailwind CSS của dự án.
4. Trình bày bảng thông số rõ ràng cho người dùng trước khi tiến hành viết mã component.
