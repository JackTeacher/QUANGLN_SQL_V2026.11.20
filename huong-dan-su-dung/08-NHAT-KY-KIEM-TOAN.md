# 08 - HƯỚNG DẪN: NHẬT KÝ KIỂM TOÁN (AUDIT LOG)

## 📌 1. Mục đích chức năng
Chức năng **Nhật ký kiểm toán (Audit Log)** là chốt chặn an ninh quan trọng nhất của phần mềm, được thiết kế đặc thù cho các môi trường dữ liệu y tế đòi hỏi tính minh bạch và trách nhiệm giải trình cao:
- Ghi vết vĩnh viễn mọi hành vi can thiệp dữ liệu (`INSERT`, `UPDATE`, `DELETE`) thực hiện từ máy trạm.
- Phục vụ công tác thanh tra an toàn thông tin, kiểm tra sai sót dữ liệu bệnh viện hoặc đối chiếu trách nhiệm khi có sự cố dữ liệu.

---

## 📋 2. Các thông tin được lưu vết tự động
Mỗi khi có một lệnh thay đổi dữ liệu được thực thi (trong Khám phá dữ liệu hoặc qua Transaction), hệ thống tự động ghi lại bản ghi kiểm toán gồm:
1. **Thời gian chính xác**: Ngày, giờ, phút, giây đến phần nghìn giây.
2. **Địa chỉ IP máy trạm (Client Workstation IP)**: Tự động phát hiện IP máy tính đang thao tác trong mạng LAN bệnh viện.
3. **Tài khoản người dùng Windows**: Danh tính tài khoản đang đăng nhập trên máy tính.
4. **Hồ sơ kết nối & Schema**: Tên CSDL và Schema bị tác động (ví dụ: `HIS_RS`).
5. **Đối tượng / Bảng đích**: Bảng bị sửa đổi (ví dụ: `HIS_TREATMENT`, `HIS_PATIENT`...).
6. **Hành động (Action)**: `INSERT`, `UPDATE`, `DELETE`.
7. **Số lượng dòng tác động**: Số bản ghi đã bị thay đổi thực tế.
8. **Trạng thái giao dịch**: `COMMITTED` (đã lưu thật) hoặc `ROLLED_BACK` (đã hủy).
9. **Mã lệnh SQL thực tế**: Toàn bộ câu lệnh SQL đã chạy trong transaction.

---

## 🔐 3. Tính bất biến & Bảo mật nhật ký (Audit Integrity)
- Tệp nhật ký kiểm toán được bảo vệ bằng cơ chế mã hóa **Windows DPAPI**.
- Người dùng thông thường **không thể sửa đổi hay xóa** các dòng nhật ký này bằng các trình soạn thảo thông thường.
- Đảm bảo tính pháp lý và tính toàn vẹn khi phục vụ công tác thanh tra CNTT bệnh viện.

---

## 🔍 4. Tra cứu & Lọc nhật ký kiểm toán
- Lọc theo khoảng ngày (Từ ngày – Đến ngày).
- Lọc theo loại thao tác (`UPDATE`, `DELETE`, `INSERT`).
- Lọc theo tên bảng hoặc từ khóa câu lệnh.
- Hỗ trợ xuất báo cáo kiểm toán ra tệp **Excel** hoặc **CSV** phục vụ báo cáo lãnh đạo.

---

## 📝 5. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Hoàn thiện tài liệu Nhật ký kiểm toán và quy chuẩn truy vết IP máy trạm.
