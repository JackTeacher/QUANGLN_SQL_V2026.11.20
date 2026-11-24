# 02 - HƯỚNG DẪN: QUẢN LÝ KẾT NỐI CƠ SỞ DỮ LIỆU

## 📌 1. Mục đích chức năng
Chức năng **Kết nối cơ sở dữ liệu** cho phép quản lý tập trung danh sách các CSDL bệnh viện, hỗ trợ đa hệ quản trị CSDL phổ biến và thiết lập các lớp bảo vệ phân quyền nghiêm ngặt.

---

## 🗄️ 2. Các hệ quản trị CSDL được hỗ trợ
Phần mềm tích hợp sẵn driver native cho:
- **Oracle Database** (Phổ biến nhất trên các hệ thống HIS lớn: HIS_RS, LIS_RS, QCS_RS...).
- **PostgreSQL** (Hệ thống y tế nguồn mở, PACS, Bệnh án điện tử EMR).
- **Microsoft SQL Server**.
- **MySQL / MariaDB**.
- **SQLite** (Các CSDL cục bộ hoặc kiểm thử).

---

## 🔒 3. Ba cấp độ phân quyền an toàn (Access Modes)
Khi tạo hoặc chỉnh sửa một hồ sơ kết nối, bạn **bắt buộc** phải chọn 1 trong 3 chế độ:

| Chế độ | Ý nghĩa & Quyền hạn | Khuyến nghị sử dụng |
| :--- | :--- | :--- |
| **Chỉ đọc (Read-Only)** | Chỉ cho phép chạy `SELECT`. Mọi thao tác `INSERT`, `UPDATE`, `DELETE`, `DROP`, `ALTER` bị **chặn triệt để** ở cấp độ ứng dụng. | Dành cho máy trạm tra cứu báo cáo, tài chính, thống kê, kiểm tra dữ liệu. |
| **Đọc và ghi (Read-Write)** | Cho phép truy vấn và sửa/xóa có kiểm soát thông qua Transaction và Audit Log. Không cho phép DDL (`DROP`, `ALTER`). | Dành cho Kỹ sư HIS khi xử lý sự cố dữ liệu, hiệu chỉnh thông tin hành chính của bệnh nhân. |
| **Quản trị (Administrative)** | Toàn quyền thao tác trên CSDL theo quyền hạn của tài khoản DB. | Dành riêng cho Quản trị viên CSDL (DBA) triển khai hoặc bảo trì hệ thống. |

---

## 🛠️ 4. Các bước thêm mới một kết nối CSDL
1. Nhấp vào menu **`Kết nối cơ sở dữ liệu`** ở thanh bên trái.
2. Bấm nút **`＋ Thêm kết nối`**.
3. Điền các thông số kết nối:
   - **Tên hồ sơ**: Đặt tên gợi nhớ (ví dụ: `HIS_Chính_Oracle`, `EMR_Postgres`...).
   - **Hệ quản trị**: Chọn loại DB tương ứng.
   - **Máy chủ (Host / IP)** và **Cổng (Port)**: Ví dụ `192.168.1.100` : `1521`.
   - **Database / Service Name**: Ví dụ `ORCL`, `XE`, hoặc `his_db`.
   - **Tài khoản & Mật khẩu**: Thông tin đăng nhập CSDL.
   - **Chế độ truy cập**: Chọn *Chỉ đọc*, *Đọc và ghi* hoặc *Quản trị*.
4. Bấm **`Kiểm tra kết nối`** để phần mềm xác thực đường truyền và tài khoản.
5. Khi nhận thông báo kiểm tra thành công, bấm **`Lưu`**.

---

## 🔐 5. Bảo mật mật khẩu (Windows DPAPI)
- Mọi mật khẩu kết nối đều được mã hóa tự động bằng công nghệ **Windows Data Protection API (DPAPI)** gắn liền với tài khoản đăng nhập Windows của bạn.
- Mật khẩu **không bao giờ được lưu dưới dạng văn bản thô (plain-text)** trong file cấu hình, bảo đảm an toàn khi chia sẻ máy trạm.

---

## 📤 6. Sao lưu & Xuất/Nhập hồ sơ
- Hỗ trợ xuất danh sách kết nối (không kèm mật khẩu) để chia sẻ cho các đồng nghiệp trong đội ngũ IT.
- Hỗ trợ nhập hàng loạt file cấu hình kết nối.

---

## 📝 7. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Hoàn thiện hướng dẫn phân quyền 3 cấp và chuẩn hóa hướng dẫn kết nối Oracle HIS.
