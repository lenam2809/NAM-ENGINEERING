# NAM ENGINEERING — DESIGN SYSTEM & UI/UX SPECIFICATION (`DESIGN.md`)

- **Stitch Project ID:** `projects/1272151449057853785`
- **Stitch Design System Asset:** `assets/14536445716971181936`
- **Aesthetic Direction:** Dark Editorial Technical Monograph
- **Status:** Milestone 3 Deliverable (Pending Final Review before Project Scaffolding)

---

## 1. Triết Lý Thiết Kế (Brand & Aesthetic Direction)

**NAM ENGINEERING** được định hình theo phong cách **Dark Editorial Technical Monograph** (Chuyên khảo Kỹ thuật Tối giản & Chuyên sâu), lấy cảm hứng từ các ấn phẩm kỹ thuật kinh điển của **Stripe Press**, **Increment Magazine**, **MIT Press** và tài liệu kiến trúc hệ thống (RFC / Hardware Schematics).

### Các nguyên tắc thị giác cốt lõi:
1. **Chống giao diện SaaS đại trà (Anti-SaaS Bloat):**
   - **Tuyệt đối không dùng:** Gradient tím-xanh neon, các mảng màu phát sáng lơ lửng (glowing blobs), hiệu ứng kính mờ (glassmorphism) lạm dụng, bo góc tròn trịa kiểu ứng dụng tiêu dùng (`rounded-2xl`/`rounded-full`), hay hình minh họa 3D sáo rỗng.
2. **Lưới Kiến Trúc Lộ Viền (Exposed Structural Hairline Grid):**
   - Sử dụng đường kẻ `1px solid` sắc nét (`--border-subtle`) để phân chia các vùng chức năng (Header, Hero Monograph, System Index, Article Ledger, Reading Well, Dossier Rail, TOC Rail) theo kỷ luật lưới báo chí Thụy Sĩ (Swiss Editorial Grid).
3. **Ưu Tiên Công Thái Học Đọc Dài Hạn (Long-Form Reading Ergonomics):**
   - Cột đọc bài viết chi tiết được khóa ở độ rộng tối ưu **`68ch` (`680px–720px`)** với chiều cao dòng thoáng (`1.75`) và độ tương phản chuẩn WCAG 2.1 AA/AAA trên cả hai chế độ **Dark Monograph (Mặc định)** và **Paper & Ink (Sáng)**.
4. **Cá Tính Kỹ Thuật Qua Monospace Telemetry:**
   - Mọi thông số kỹ thuật (số thứ tự bài viết `01`–`28`, ngày chuẩn ISO `YYYY-MM-DD`, thời lượng đọc `12 PHÚT ĐỌC`, chuyên mục, đường dẫn tệp mã nguồn) đều được hiển thị bằng phông chữ `JetBrains Mono`.

---

## 2. Danh Sách Màn Hình Thiết Kế Trên Google Stitch

Dự án đã được khởi tạo và lưu trữ trên Google Stitch (`projects/1272151449057853785`) với Design System (`assets/14536445716971181936`) và các màn hình chuẩn:

| STT | Tên màn hình | Route tương ứng | Stitch Screen ID | Nội dung thiết kế chính |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Monograph Homepage** | `/` | `136cf84b9fdc45f8b6b2efe3444466d5` | Header 64px, Hero 12 cột bất đối xứng (8 cột Bài viết tiêu điểm + 4 cột System Index), Danh mục ấn phẩm mới nhất dạng bảng đánh số (`01`–`04`) và Colophon Footer. |
| 2 | **Technical Archive & Search (Blog Listing)** | `/blog`, `/category/[category]`, `/tags/[tag]` | `b5b4092c10664a76b84d617284eef4e4` | Khung tìm kiếm tức thì hỗ trợ tiếng Việt có dấu/không dấu (`đ/Đ`), bộ lọc chuyên mục kèm bộ đếm số lượng, bộ lọc tag và danh sách bài viết phân nhóm theo năm (`2026`, `2025`). |
| 3 | **Article Detail & MDX Reading View** | `/blog/[slug]` | `2203973d04c6464c9e37a59252934a54` *(và bản đối chứng `ced4f37cff3e47b6ad5842647532eb34`)* | Thanh tiến độ đọc `2px` trên đỉnh, Header bài viết chuyên khảo, lưới đọc 3 cột (Left Dossier Rail + Center `68ch` MDX Reading Well + Right Sticky TOC Scrollspy), Code Block tùy chỉnh, Callout, Bảng so sánh GFM và Bài viết liên quan. |
| 4 | **About, Colophon & Dual-Theme / Mobile Spec** | `/about` | `872b2c353b2b4af382baa9f05f61213d` | Tuyên ngôn kỹ thuật, Chuẩn biên tập 4 bước, Hồ sơ kiến trúc sư, Bảng thông số kỹ thuật hệ thống (Colophon) cùng khung đối chiếu chế độ **Paper & Ink (Light Mode)** và khung **Mobile Viewport (390px)**. |

---

## 3. Hệ Thống Design Tokens (Color, Surface, Border & Semantic Tokens)

Hệ thống màu được thiết kế theo cơ chế biến CSS (`CSS Custom Properties`) tích hợp vào `@theme` của **Tailwind CSS v4**, đảm bảo chuyển đổi tức thì giữa **Dark Mode (Mặc định)** và **Light Mode ("Paper & Ink")** mà không gây chớp trang.

### 3.1. Bảng Màu Chế Độ Tối — Dark Monograph (Default)

| Token CSS Variable | Tailwind Class Gợi Ý | Mã Hex | Độ tương phản (trên `#0B0D10`) | Mục đích sử dụng |
| :--- | :--- | :--- | :--- | :--- |
| `--bg-canvas` | `bg-canvas` | `#0B0D10` | — | Nền chính toàn trang (Carbon Obsidian — giảm mỏi mắt hơn màu đen `#000000` tuyệt đối). |
| `--bg-surface` | `bg-surface` | `#111419` | — | Bề mặt thẻ bài viết, khung Dossier, khung TOC, hộp Callout. |
| `--bg-elevated` | `bg-elevated` | `#161B22` | — | Thanh tiêu đề Code Block, trạng thái hover của dòng bài viết, thanh tìm kiếm. |
| `--bg-code` | `bg-code` | `#0D1014` | — | Lòng khối mã nguồn (`<pre><code>`). |
| `--text-primary` | `text-primary` | `#ECEFF4` | **15.6 : 1 (AAA)** | Tiêu đề `H1`–`H4`, văn bản chính của bài viết, chữ nhấn mạnh. |
| `--text-secondary` | `text-secondary` | `#9CA3AF` | **7.2 : 1 (AAA)** | Đoạn tóm tắt (abstract), văn bản phụ, mục lục chưa kích hoạt. |
| `--text-muted` | `text-muted` | `#6B7280` | **4.6 : 1 (AA)** | Số dòng code, nhãn metadata phụ, chú thích hình ảnh. |
| `--border-subtle` | `border-subtle` | `#1F242D` | — | Đường kẻ khung lưới `1px solid` xuyên suốt toàn trang. |
| `--border-strong` | `border-strong` | `#2E3644` | — | Viền khi hover thẻ bài viết hoặc focus ô tìm kiếm. |
| `--accent-primary` | `text-accent` / `bg-accent` | `#E86C3A` | **6.4 : 1 (AA)** | Cam Kỹ Thuật (Signal Engineering Orange) — nút chính, chỉ báo mục lục đang đọc, thanh tiến độ đọc, viền dòng code nổi bật. |
| `--accent-secondary` | `text-cyan` / `border-cyan` | `#38BDF8` | **9.8 : 1 (AAA)** | Xanh Sơ Đồ (Schematic Cyan) — liên kết kỹ thuật trong bài, nhãn ngôn ngữ code, hộp thông tin. |
| `--semantic-info` | — | `#38BDF8` | **9.8 : 1** | Callout `[!NOTE]` / `[!INFO]`. |
| `--semantic-tip` | — | `#34D399` | **10.4 : 1** | Callout `[!TIP]` / Trạng thái hoàn thành (`✓ COPIED`). |
| `--semantic-warning` | — | `#FBBF24` | **11.8 : 1** | Callout `[!WARNING]` / `[!IMPORTANT]`. |
| `--semantic-danger` | — | `#F87171` | **7.1 : 1** | Callout `[!CAUTION]` / Cảnh báo lỗi bảo mật hoặc phá hủy. |

### 3.2. Bảng Màu Chế Độ Sáng — Editorial Paper & Ink (`[data-theme="light"]`)

| Token CSS Variable | Mã Hex | Độ tương phản (trên `#F7F6F2`) | Mục đích sử dụng |
| :--- | :--- | :--- | :--- |
| `--bg-canvas` | `#F7F6F2` | — | Nền giấy in chuyên khảo ấm (Warm Archival Paper), chống chói mắt ban ngày. |
| `--bg-surface` | `#EFECE6` | — | Bề mặt thẻ phụ, hộp Callout, khung Dossier. |
| `--bg-elevated` | `#FFFFFF` | — | Bề mặt nổi bật khi hover, ô tìm kiếm, thanh công cụ. |
| `--bg-code` | `#14171C` *(hoặc `#EFECE6`)* | — | Khối mã nguồn giữ nền tối tương phản cao (`#14171C`) để bảo toàn bảng màu cú pháp code. |
| `--text-primary` | `#14171C` | **16.1 : 1 (AAA)** | Mực in đậm cho tiêu đề và nội dung bài viết. |
| `--text-secondary` | `#4B5563` | **7.1 : 1 (AAA)** | Mô tả tóm tắt và văn bản phụ. |
| `--text-muted` | `#6B7280` | **4.5 : 1 (AA)** | Chú thích, số thứ tự, ngày tháng phụ. |
| `--border-subtle` | `#DFDDD5` | — | Đường kẻ khung lưới `1px solid` trên nền giấy. |
| `--border-strong` | `#B8B5AA` | — | Viền khi hover hoặc focus. |
| `--accent-primary` | `#C84B18` | **5.4 : 1 (AA)** | Cam đất đậm (Deep International Orange) đảm bảo độ tương phản chuẩn AA trên nền giấy sáng. |
| `--accent-secondary` | `#0284C7` | **4.8 : 1 (AA)** | Xanh bản vẽ kỹ thuật (Blueprint Blue) cho liên kết và chỉ báo phụ. |

### 3.3. Spacing, Border Radius & Elevation Tokens
- **Border Radius:**
  - `--radius-xs`: `2px` (Nhãn inline `code`, badge nhỏ)
  - `--radius-sm`: `4px` (Chuẩn mặc định cho toàn bộ Button, Input, Card, Code Block)
- **Spacing Scale:**
  - `space-1` (`4px`), `space-2` (`8px`), `space-3` (`12px`), `space-4` (`16px`), `space-6` (`24px`), `space-8` (`32px`), `space-12` (`48px`), `space-16` (`64px`).
- **Elevation:**
  - Không dùng bóng đổ mờ (`box-shadow`) cho các thẻ nằm trên mặt phẳng trang; phân tách hoàn toàn bằng màu nền bậc thang (`#0B0D10` -> `#111419` -> `#161B22`) và viền `1px solid var(--border-subtle)`.

---

## 4. Hệ Thống Typography (Typography System)

Tải phông chữ qua `next/font/google` với `subsets: ['latin', 'vietnamese']` và `display: 'swap'` để đảm bảo **CLS = 0** và hiển thị hoàn hảo dấu tiếng Việt:

1. **Font Tiêu Đề (`--font-display`: `Space Grotesk`):**
   - Mang cấu trúc hình học kỹ thuật sắc sảo, tạo điểm nhấn thị giác mạnh cho tiêu đề bài viết và các con số.
2. **Font Văn Bản Đọc (`--font-sans`: `Be Vietnam Pro`):**
   - Được thiết kế chuyên biệt cho cấu trúc dấu tiếng Việt (như `ử`, `ữ`, `ệ`, `ắ`, `đ`), có chiều cao chữ thường (x-height) thoáng, giúp đọc các bài phân tích dài 3.000–5.000 từ không bị mỏi mắt.
3. **Font Mã Nguồn & Thông Số (`--font-mono`: `JetBrains Mono`):**
   - Dùng cho toàn bộ khối code, inline code, nhãn ngày tháng, thời gian đọc và chỉ mục.

### Bảng Thang Cỡ Chữ (Typographic Scale)

| Cấp độ (Token) | Font Family | Kích thước (Desktop) | Kích thước (Mobile) | Line Height | Letter Spacing | Weight | Ứng dụng |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `display-xl` | `Space Grotesk` | `2.5rem` (`40px`) | `1.875rem` (`30px`) | `1.2` | `-0.025em` | `700` | Tiêu đề `H1` của bài viết chi tiết và bài tiêu điểm trên trang chủ. |
| `headline-lg` | `Space Grotesk` | `2.0rem` (`32px`) | `1.5rem` (`24px`) | `1.25` | `-0.02em` | `700` | Tiêu đề trang (`/blog`, `/about`) và tiêu đề cấp `H2` trong bài viết. |
| `headline-md` | `Space Grotesk` | `1.5rem` (`24px`) | `1.25rem` (`20px`) | `1.3` | `-0.015em` | `600` | Tiêu đề cấp `H3` trong bài viết và tiêu đề bài viết trong danh sách. |
| `headline-sm` | `Space Grotesk` | `1.25rem` (`20px`) | `1.125rem` (`18px`) | `1.4` | `-0.01em` | `600` | Tiêu đề cấp `H4`, tiêu đề hộp Callout và thẻ bài viết liên quan. |
| `body-lead` | `Be Vietnam Pro` | `1.125rem` (`18px`) | `1.0625rem` (`17px`) | `1.7` | `0em` | `400` | Đoạn mở đầu (Lead/Abstract) ngay dưới tiêu đề `H1`. |
| `body-prose` | `Be Vietnam Pro` | `1.0625rem` (`17px`) | `1.0rem` (`16px`) | `1.75` | `0.005em` | `400` | Nội dung văn bản chính của bài viết MDX (độ rộng dòng `65–75ch`). |
| `body-sm` | `Be Vietnam Pro` | `0.9375rem` (`15px`) | `0.875rem` (`14px`) | `1.6` | `0em` | `400` | Tóm tắt bài viết ở danh sách, liên kết mục lục TOC. |
| `code-block` | `JetBrains Mono` | `0.875rem` (`14px`) | `0.8125rem` (`13px`) | `1.65` | `0em` | `400` | Nội dung bên trong khối `<pre><code>`. |
| `label-mono` | `JetBrains Mono` | `0.75rem` (`12px`) | `0.75rem` (`12px`) | `1.4` | `0.06em` | `500` | Nhãn chuyên mục, ngày tháng ISO, thời gian đọc, đường dẫn tệp. |

---

## 5. Danh Mục Thành Phần Giao Diện (Component Inventory)

### 5.1. Nhóm Layout & Điều Hướng (`src/components/layout/`)
1. **`Header.tsx` (Server Component + Client Triggers):**
   - Chiều cao cố định `64px`, viền dưới `1px solid var(--border-subtle)`, nền `var(--bg-canvas)` cố định trên đỉnh (`sticky top-0 z-40`).
   - Góc trái: Biểu trưng vuông `6x6px` màu `#E86C3A` + chữ `NAM ENGINEERING // MONOGRAPH`.
   - Giữa: Liên kết điều hướng đánh số `01. BÀI VIẾT`, `02. CHUYÊN MỤC`, `03. KIẾN TRÚC / ABOUT`, `04. RSS`.
   - Góc phải: Nút mở/cuộn tới tìm kiếm và nút `ThemeToggle.tsx` (`[ DARK / PAPER ]`).
2. **`Footer.tsx` (Server Component):**
   - Viền trên `1px solid var(--border-subtle)`, hiển thị thông tin Colophon kỹ thuật, liên kết tới `/sitemap.xml`, `/feed.xml`, `/robots.txt` và cam kết bảo mật nội dung.
3. **`ThemeToggle.tsx` (`"use client"`):**
   - Chuyển đổi thuộc tính `data-theme="dark" | "light"` trên thẻ `<html>` và lưu vào `localStorage`, đồng bộ qua đoạn script nhỏ chống chớp sáng (`no-flash script`) trong `<head>`.

### 5.2. Nhóm Hiển Thị & Tương Tác Blog (`src/components/blog/`)
4. **`FeaturedPostHero.tsx` (Server Component):**
   - Khung 8 cột bên trái trang chủ giới thiệu bài viết chuyên khảo mới nhất kèm nhãn số phát hành, tóm tắt, tags và nút hành động chính màu `#E86C3A`.
5. **`SystemIndexPanel.tsx` (Server Component):**
   - Khung 4 cột bên phải trang chủ liệt kê danh sách chuyên mục (`category`) cùng số lượng bài viết thực tế được tính tự động từ `content/posts/`.
6. **`ArticleLedgerRow.tsx` (Server Component):**
   - Hàng hiển thị bài viết trong bảng danh sách: Cột chỉ mục (`01`, `02`), ngày xuất bản (`YYYY-MM-DD`), badge chuyên mục, tiêu đề `Space Grotesk`, mô tả ngắn, danh sách tags và thời lượng đọc.
7. **`SearchAndFilterBar.tsx` (`"use client"`):**
   - Ô nhập từ khóa tìm kiếm tức thì (hỗ trợ chuẩn hóa tiếng Việt `đ/Đ` và bỏ dấu tổ hợp), các nút lọc theo `category` và `tag`, kèm bộ đếm số lượng kết quả khớp.
8. **`ReadingProgress.tsx` (`"use client"`):**
   - Thanh mảnh `2px` màu `--accent-primary` (`#E86C3A`) nằm sát mép trên cùng của cửa sổ trình duyệt ở trang đọc bài viết, cập nhật bằng `transform: scaleX()` mượt mà.
9. **`TableOfContents.tsx` (`"use client"`):**
   - Ở Desktop (`>= 1024px`): Cột sticky bên phải hiển thị danh sách tiêu đề `H2` và `H3` của bài viết, tự động tô sáng mục đang đọc nhờ `IntersectionObserver`.
   - Ở Mobile/Tablet (`< 1024px`): Chuyển thành thanh ngăn kéo gọn (`Collapsible Drawer` `"MỤC LỤC BÀI VIẾT [▾]"`) nằm ngay đầu bài viết.
10. **`DocumentDossier.tsx` (Server Component + Client Copy Link):**
    - Cột trái ở trang bài viết chi tiết hiển thị thông tin xuất bản, ngày cập nhật, chuyên mục và nút sao chép liên kết bài viết.
11. **`RelatedPosts.tsx` (Server Component):**
    - Lưới 3 cột ở cuối bài viết gợi ý các bài viết cùng chuyên mục hoặc có nhiều tag chung nhất.

### 5.3. Nhóm MDX Components & Code Block (`src/mdx-components.tsx` & `src/components/mdx/`)
12. **`CodeBlock.tsx` + `CopyCodeButton.tsx` (Thiết kế chuẩn cho MDX `<pre>`):**
    - **Khung ngoài:** Viền `1px solid var(--border-subtle)`, bo góc `4px`, `overflow-hidden`, khoảng cách trên/dưới `1.5rem`.
    - **Thanh Header (`36px`):** Nền `var(--bg-elevated)`, viền dưới `1px solid var(--border-subtle)`. Bên trái hiển thị biểu tượng tệp + tên tệp (nếu có) hoặc nhãn ngôn ngữ viết hoa (`TSX`, `BASH`, `JSON`, `SQL`) bằng `JetBrains Mono` màu `#38BDF8`. Bên phải là nút `[ COPY CODE ]` chuyển sang `[ ✓ COPIED ]` màu `#34D399` trong `2000ms` khi nhấp.
    - **Vùng nội dung Code:** Nền `var(--bg-code)`, cuộn ngang mượt (`overflow-x-auto`), font `JetBrains Mono` `14px`, hỗ trợ hiển thị số thứ tự dòng và làm nổi bật dòng quan trọng với viền trái `2px solid #E86C3A`.
    - *(Lưu ý kiến trúc: Trong bước khởi tạo Scaffolding ban đầu sẽ hiển thị `<pre><code>` theo đúng khung thiết kế này; sau đó có thể tích hợp `shiki` / `rehype-pretty-code` vào đúng cấu trúc DOM này mà không phải sửa giao diện)*.
13. **`Callout.tsx` (Custom MDX Component cho các ghi chú kỹ thuật):**
    - Hỗ trợ 4 loại ngữ nghĩa: `info` (`#38BDF8`), `tip` (`#34D399`), `warning` (`#FBBF24`), `danger` (`#F87171`).
    - Thiết kế: Nền `var(--bg-surface)`, viền bao `1px solid var(--border-subtle)`, cạnh trái dày `3px solid` theo màu ngữ nghĩa, tiêu đề in hoa bằng `JetBrains Mono`.
14. **`HeadingAnchor.tsx` (`h2`, `h3`, `h4`):**
    - Tự động gắn thuộc tính `id` chuẩn hóa từ nội dung tiêu đề, đặt `scroll-margin-top: 88px` (để không bị Header `64px` che khuất khi nhấp từ mục lục) và hiển thị ký hiệu `#` màu `#E86C3A` khi di chuột qua.
15. **`MdxTable.tsx` (`table`, `thead`, `th`, `td` từ `remark-gfm`):**
    - Bọc trong khung `overflow-x-auto` có viền `1px solid var(--border-subtle)`, tiêu đề bảng nền `var(--bg-elevated)` font `JetBrains Mono`, các ô dữ liệu kẻ lưới `1px` rõ ràng.

---

## 6. Thông Số Responsive (Responsive Specifications)

| Breakpoint | Kích thước Viewport | Cấu trúc Lưới & Thích ứng Bố cục |
| :--- | :--- | :--- |
| **Desktop XL / Monograph** | `>= 1280px` | Khung `max-w-[1280px]` căn giữa với 2 đường kẻ dọc `1px` hai bên. Trang bài viết hiển thị đầy đủ **3 cột**: Dossier trái (`2 cols`) + Cột đọc giữa (`7 cols`, khóa `68ch`) + TOC phải (`3 cols`). |
| **Desktop / Laptop** | `1024px – 1279px` | Khung `max-w-7xl` với `px-6`. Trang chủ giữ lưới 8/4; trang bài viết giữ lưới 3 cột (cột Dossier thu gọn còn `2 cols` hẹp). |
| **Tablet** | `768px – 1023px` | Chuyển sang bố cục 1 cột trung tâm (`px-6`). Ở trang bài viết: thông tin Dossier gộp vào ngay dưới tiêu đề `H1`; cột TOC bên phải thu gọn thành hộp `Collapsible TOC` đặt ở đầu bài viết; cột đọc vẫn giữ `max-w-[68ch]` căn giữa. |
| **Mobile** | `< 768px` (`375px – 767px`) | Bố cục 1 cột toàn chiều rộng với lề `px-4` (`16px`). Thanh điều hướng thu gọn thành menu ngăn kéo (`Mobile Nav Drawer`). Bảng so sánh và khối Code Block có thanh cuộn ngang độc lập (`overflow-x-auto`) để không làm vỡ khung trang. |

---

## 7. Thông Số Tương Tác & Trải Nghiệm (Interaction & A11y Specifications)

1. **Điều hướng Bàn phím & Trạng thái Focus (WCAG 2.1 AA):**
   - Mọi phần tử tương tác (`a`, `button`, `input`) đều có trạng thái `:focus-visible` rõ nét: `outline: 2px solid var(--accent-primary); outline-offset: 2px;`.
2. **Hiệu ứng Chuyển trạng thái (Micro-transitions):**
   - Chỉ sử dụng chuyển đổi màu nền và màu viền tinh tế (`transition-colors duration-150 ease-out`). Không dùng hiệu ứng phóng to (`scale`) gây nhức mắt trên các dòng bài viết.
3. **Tương tác Tìm kiếm Tiếng Việt (`/blog`):**
   - Lọc tức thì ngay khi gõ, tự động chuẩn hóa cả chuỗi truy vấn và dữ liệu bài viết qua 4 bước (`normalize('NFD')` -> xóa dấu `\u0300-\u036f` -> đổi `đ/Đ` thành `d/D` -> `toLowerCase()`), hỗ trợ phím `Escape` để xóa nhanh từ khóa.
4. **Cam kết Chống Giật Bố Cục (`CLS = 0`):**
   - Header có chiều cao cố định `64px`; khối Code Block và hình ảnh luôn có khung bao xác định kích thước trước khi tải.

---

## 8. Quy Tắc Triển Khai Giao Diện Cho Antigravity (Implementation Governance)

Khi chuyển sang giai đoạn viết code ở các Milestone tiếp theo, Agent bắt buộc tuân thủ:
1. **Ánh xạ Token 1-1:** Toàn bộ mã màu, phông chữ và khoảng cách trong `src/styles/globals.css` phải lấy chính xác từ Mục 3 và Mục 4 của tài liệu `DESIGN.md` này, không tự ý dùng các màu mặc định lệch tông của Tailwind (như `bg-blue-500` hay `bg-purple-600`).
2. **Semantic HTML5:** Trang chủ và trang danh sách dùng `<header>`, `<main>`, `<section>`, `<footer>`; trang bài viết bắt buộc dùng `<article>` cho nội dung chính và `<aside>` cho cột Dossier / Table of Contents.
3. **Server-First:** Giữ nguyên kiến trúc Server Components cho toàn bộ các thành phần hiển thị tĩnh; chỉ gắn `"use client"` cho `ThemeToggle`, `SearchAndFilterBar`, `ReadingProgress`, `TableOfContents` và `CopyCodeButton`.
