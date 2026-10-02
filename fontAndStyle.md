# Raycast Design System

## 1. Tổng quan thiết kế (Design Overview)

**Chủ đề:** Midnight command center, coral neon (Trung tâm chỉ huy nửa đêm, màu san hô neon).

**Mô tả thiết kế:**
Raycast mang lại cảm giác như một khoang lái công cụ mạnh mẽ (power-tool cockpit) tông màu tối: một khung nền gần như đen tuyền (`#040506`) với các bậc độ cao (elevation) gần như vô hình, một điểm nhấn màu san hô ấm áp duy nhất (`#ff6363`) mang đậm bản sắc thương hiệu, cùng hệ thống chữ màu trắng/xám tĩnh lặng sử dụng font Inter. 

Các thành phần (components) được xác định thông qua các đường viền mỏng (hairline borders) và các nét viền nổi (inset highlight strokes) thay vì sử dụng đổ bóng, cùng với hiệu ứng bóng đổ bên trong dạng 'phím cơ' (keyboard key) đặc trưng giúp các thẻ (cards) mang lại cảm giác có thể ấn được (tactile) thay vì trôi nổi. 

Màu sắc được sử dụng cực kỳ tiết kiệm — trang web có 98% là màu vô sắc (achromatic), và màu san hô chỉ xuất hiện ở logo, artwork chính (hero), huy hiệu AI, và một vài bề mặt được ám màu ấm. Thanh điều hướng trôi nổi với hiệu ứng kính mờ (glass-blur), và hầu hết các bề mặt tương tác là các nút xám nhạt trung tính trên nền tối, không dùng CTA đa sắc. Phần hero thoát khỏi hệ thống chung với các khối hình học lớn chuyển màu đỏ/xanh dương (red/blue gradient), sau đó toàn bộ phần còn lại của trang quay trở về bề mặt tối nghiêm ngặt — tạo độ tương phản thông qua bầu không khí chứ không phải qua trang trí.

---

## 2. Hệ thống kiểu chữ (Typography)

**Type Scale (Tỷ lệ chữ):** Minor Third (1.2) từ kích thước cơ sở 16px.

### Thang đo kích thước (Type Scale)

| Phân loại | Kích thước / Trọng lượng / Chiều cao dòng | Font chữ sử dụng |
| :--- | :--- | :--- |
| **display** | 64px · 600 · 1.1 | Inter |
| **32px** | 32px · 400 · 1.15 | Inter |
| **32px** | 32px · 500 · 1.15 | SF Pro Text |
| **heading-sm** | 24px · 500 · 1.15 | SF Pro Text |
| **subheading** | 20px · 500 · 1.2 | Inter |
| **body-lg** | 18px · 400 · 1.15 | Inter |
| **16px** | 16px · 400 · 1.15 | Inter |
| **16px** | 16px · 500 · 1.15 | SF Pro Text |

---

### Chi tiết các Font chữ (Fonts)

#### 1. Inter (Primary / Font chính)
*   **Weight (Trọng lượng):** 400, 500, 600
*   **Sizes (Kích thước):** 11–64px · 12 values
*   **Line height (Chiều cao dòng):** 0.91–1.71
*   **Letter spacing (Khoảng cách chữ):** 0.004–0.073px · 5 values
*   **Fallback:** `system-ui, -apple-system, 'Helvetica Neue', Arial, sans-serif`
*   **Cách sử dụng:** Là typeface chính của giao diện — văn bản thân bài (body text) ở 16px/400, nhãn thẻ (card labels) và điều hướng (nav) ở 13–14px/500, tiêu đề phụ (subheadings) ở 18–22px/400, tiêu đề mục (section headings) ở 32–56px trong khoảng 400–600, và text hiển thị (display) ở 64px/600. Hình học trung tính của Inter mang lại sự nghiêm túc của một công cụ dành cho lập trình viên. Việc sử dụng weight 400 cho tiêu đề hero 56px là một lựa chọn đi ngược lại lối mòn — hầu hết các thương hiệu đều gây chú ý bằng weight 700, nhưng Raycast thì "thì thầm" bằng trọng lượng chữ thường và để kích thước tự lên tiếng.

#### 2. GeistMono (Code)
*   **Weight (Trọng lượng):** 300, 400, 500
*   **Sizes (Kích thước):** 10px, 12px, 14px
*   **Line height (Chiều cao dòng):** 1.00–1.60
*   **Letter spacing (Khoảng cách chữ):** 0.0170em ở 12px, 0.0500em ở 10px (chữ in hoa)
*   **Fallback:** `'JetBrains Mono', Menlo, Monaco, Courier, monospace`
*   **Cách sử dụng:** Font Monospace dành cho các chuỗi phiên bản (version strings), các nhãn dán kỹ thuật nhỏ, và các văn bản mang phong cách terminal. Xuất hiện trong metadata ở footer (vd: v1.104.21), các gợi ý command-line, và các nhãn eyebrow in hoa 10px. Hình dáng gọn gàng, mang hơi hướng hình học của Geist Mono khiến cho các nhãn dán siêu nhỏ này mang cảm giác được "chế tác kỹ thuật" (engineered) thay vì chỉ để trang trí.

#### 3. SF Pro Text (System Typeface)
*   **Weight (Trọng lượng):** 500, 700
*   **Sizes (Kích thước):** 16px, 24px, 32px
*   **Line height (Chiều cao dòng):** 1.15
*   **Cách sử dụng:** Font hệ thống được sử dụng cho các biểu tượng (icon glyphs) và các phần làm nổi bật số liệu (numeric stat callouts) ở mức 24–32px/500. Sẽ fallback về SF Pro trên macOS để mang lại cảm giác native (bản địa) — nhằm củng cố bản sắc "đây là một ứng dụng dành cho Mac".