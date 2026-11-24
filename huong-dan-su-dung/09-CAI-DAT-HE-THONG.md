# 09 - HƯỚNG DẪN: CÀI ĐẶT HỆ THỐNG & PHÍM TẮT

## 📌 1. Mục đích chức năng
Màn hình **Cài đặt hệ thống (Settings)** cung cấp bảng điều khiển trung tâm để bạn tùy biến toàn diện trải nghiệm người dùng, cấu hình trình soạn thảo SQL, thiết lập giới hạn dữ liệu an toàn và quản lý vị trí lưu trữ file báo cáo.

---

## 🎨 2. Giao diện & Trình soạn thảo (Appearance & Editor)
- **Chủ đề giao diện (Theme)**:
  - **Tối (Dark Theme)**: Màu nền tối hiện đại, dịu mắt khi làm việc ban đêm hoặc trong phòng máy chủ kỹ thuật.
  - **Sáng (Light Theme)**: Giao diện sáng rõ ràng, chuyên nghiệp cho văn phòng ban ngày.
  - *Thay đổi có hiệu lực ngay lập tức trên toàn bộ ứng dụng.*
- **Phông chữ trình soạn thảo (Editor Font Family)**: Lựa chọn các font chữ lập trình chuyên dụng như `Cascadia Code`, `Consolas`, `Courier New`, `Segoe UI Mono`.
- **Cỡ chữ (Font Size)**: Tùy chỉnh kích thước chữ trong SQL Workspace từ `11px` đến `20px` (mặc định: `13px`).
- **Gợi ý mã thông minh (Auto-complete Ctrl + Space)**: Tùy chọn Bật/Tắt tính năng tự động gợi ý bảng, cột, hàm và từ khóa SQL khi soạn thảo.

---

## ⚡ 3. Truy vấn & Giới hạn dữ liệu (Execution & Limits)
- **Số dòng hiển thị mặc định**: Thiết lập số dòng tối đa nạp lên bảng kết quả truy vấn (`50`, `100`, `200`, `500`, `1.000`, `2.000`, `5.000 dòng`) giúp kiểm soát dung lượng RAM và tối ưu băng thông mạng nội bộ.
- **Thời gian chờ truy vấn (Timeout - Giây)**: Ngắt truy vấn an toàn nếu câu lệnh chạy vượt quá thời gian thiết lập (`15s`, `30s`, `60s`, `120s`, hoặc `0 - Không giới hạn`), ngăn chặn các câu truy vấn treo vô hạn làm nghẽn CSDL bệnh viện.

---

## 📁 4. Lưu trữ & Xuất file (Storage & Export)
- **Thư mục xuất file mặc định**:
  - Hộp nhập đường dẫn thư mục lưu mặc định cho các file xuất CSV và Excel.
  - Nút **`📁 Duyệt thư mục...`**: Mở hộp thoại chọn thư mục Windows trực quan.
- **Nút `📂 Mở thư mục AppData`**:
  - Mở trực tiếp thư mục `%LOCALAPPDATA%\DBStudio` trong Windows Explorer để người dùng dễ dàng sao lưu, kiểm tra file cấu hình kết nối (`connections.json`) và nhật ký audit (`data-audit.jsonl`).

---

## ℹ️ 5. Thông tin phần mềm & Bản quyền
- **Ứng dụng**: `QUANGLN SQL`
- **Phiên bản**: `v1.0.0`
- **Bản quyền**: `Copyright Ⓒ by Lương Ngọc Quảng`
- **Nền tảng**: `.NET 10.0 · Windows Desktop x64`
- **Kiến trúc**: `Clean Architecture + WPF Modern UI`

---

## ⌨️ 6. Bảng tổng hợp phím tắt nhanh (Shortcut Keys)

| Phím tắt | Chức năng | Vị trí áp dụng |
| :---: | :--- | :--- |
| **`Ctrl + Space`** | **Gợi ý bảng, cột, hàm và từ khóa SQL** (IntelliSense) | Trình soạn SQL |
| **`F5`** | **Thực thi SQL** (Chạy câu lệnh hoặc đoạn bôi đen) | Trình soạn SQL |
| **`Ctrl + N`** | **Mở Tab SQL mới** | Trình soạn SQL |
| **`Ctrl + S`** | **Lưu nội dung SQL** ra tệp `.sql` | Trình soạn SQL |
| **`Ctrl + O`** | **Mở tệp SQL** từ đĩa cứng | Trình soạn SQL |
| **`F8`** | **Định dạng chuẩn SQL** (Format SQL) | Trình soạn SQL |
| **`Double-Click`** | **Mở nhanh bảng dữ liệu** | Cây đối tượng (Khám phá dữ liệu) |
| **`Esc`** | **Hủy truy vấn / Đóng popup gợi ý** | Trình soạn SQL |

---

## 📝 7. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Cập nhật giao diện Cài đặt mở rộng với tùy biến font chữ, cỡ chữ, timeout, duyệt thư mục xuất và mở nhanh AppData.
