---
name: frontend-development
description: Kỹ năng hướng dẫn xây dựng và phát triển giao diện Next.js, TypeScript và Tailwind CSS cho NAM ENGINEERING theo đúng kiến trúc MVP và thiết kế đã duyệt. Sử dụng khi cần triển khai trang, layout, component hoặc tối ưu giao diện.
---

# Frontend Development Skill

Kỹ năng này hướng dẫn Agent các nguyên tắc và quy trình triển khai tầng giao diện cho **NAM ENGINEERING** sử dụng **Next.js (App Router)**, **TypeScript** và **Tailwind CSS**.

## 1. Trách nhiệm & Phạm vi
- Triển khai cấu trúc layout, trang và component giao diện tái sử dụng.
- Đảm bảo tính toán vẹn giữa thiết kế Stitch đã duyệt và mã nguồn Tailwind CSS.
- Tối ưu hóa hiệu năng tải trang tĩnh (SSG), hỗ trợ hiển thị nội dung đọc dài hạn và đảm bảo khả năng tiếp cận (Accessibility).
- **Ranh giới nghiêm ngặt:** Chỉ sử dụng stack đã duyệt (`Next.js + TypeScript + Tailwind CSS`). Tuyệt đối không tự ý cài thêm package mới (như thư viện icon, UI library bên ngoài) khi chưa được người dùng phê duyệt. Không tự ý thay đổi cấu trúc mã nguồn khi chưa đến milestone Architecture.

## 2. Nguyên tắc Kiến trúc Next.js App Router
1. **Ưu tiên Server Components (RSC):**
   - Mặc định toàn bộ các component layout, danh sách bài viết, trang chi tiết bài viết và phần tử tĩnh đều là Server Components.
   - Giữ mã nguồn phía client tinh gọn nhất có thể để đạt điểm số hiệu năng Core Web Vitals tối đa.
2. **Sử dụng Client Components có chọn lọc (`"use client"`):**
   - Chỉ thêm chỉ thị `"use client"` cho những thành phần bắt buộc phải lắng nghe sự kiện trình duyệt hoặc quản lý state cục bộ (ví dụ: nút bật/tắt giao diện sáng/tối, nút sao chép mã nguồn, thanh điều hướng đóng/mở trên mobile).
   - Tách biệt phần Client Component thành các component con nhỏ nhất, tránh biến cả trang thành Client Component.

## 3. Tiêu chuẩn Mã nguồn TypeScript và Tailwind CSS
- **TypeScript nghiêm ngặt:** Khai báo kiểu rõ ràng cho toàn bộ `props` của component. Không sử dụng kiểu `any` tùy tiện.
- **Tailwind CSS có cấu trúc:**
  - Sử dụng class tiện ích của Tailwind CSS một cách có trật tự (Layout -> Spacing -> Sizing -> Typography -> Colors -> States).
  - Tránh các giá trị tùy biến tùy tiện (`arbitrary values` như `w-[327px]`) khi có thể dùng các lớp token tiêu chuẩn của Tailwind.
- **HTML Ngữ nghĩa:** Đảm bảo sử dụng đúng các thẻ `<header>`, `<main>`, `<article>`, `<nav>`, `<aside>`, `<footer>`.

## 4. Phối hợp với các Kỹ năng Khác
- Tham chiếu thông số từ `stitch-design` để định nghĩa màu sắc và bố cục.
- Phối hợp với `mdx-content-engineering` để đồng bộ kiểu dáng hiển thị cho các phần tử nội dung bài viết.
- Phối hợp với `testing-qa` để chạy kiểm tra giao diện và khả năng tiếp cận khi có môi trường thử nghiệm.
