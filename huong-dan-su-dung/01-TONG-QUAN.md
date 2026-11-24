# 01 - HƯỚNG DẪN: MÀN HÌNH TỔNG QUAN & ĐIỀU HƯỚNG

## 📌 1. Mục đích chức năng
Màn hình **Tổng quan (Dashboard)** là trung tâm điều khiển của hệ thống, cung cấp cái nhìn toàn diện và trực quan về:
- Các hồ sơ kết nối cơ sở dữ liệu hiện có.
- Trạng thái phiên kết nối đang kích hoạt.
- Thống kê lịch sử truy vấn và hoạt động gần đây.
- Lối tắt truy cập nhanh tới các chức năng thường dùng.

---

## 🧭 2. Thanh menu điều hướng co giãn (Collapsible Sidebar)
Hệ thống trang bị thanh menu chức năng bên trái có thể thu gọn hoặc mở rộng linh hoạt:
- **Nút bấm thu gọn/mở rộng**: Nằm ở góc trên cùng của thanh menu (biểu tượng `☰ Menu`).
- **Khi mở rộng (Expanded)**: Hiển thị đầy đủ biểu tượng và tên chức năng bằng tiếng Việt rõ ràng.
- **Khi thu gọn (Collapsed)**: Chỉ hiển thị các biểu tượng chức năng gọn gàng, giúp tối đa hóa không gian màn hình làm việc cho phần viết SQL và bảng dữ liệu.

---

## 🟢 3. Huy hiệu trạng thái kết nối toàn cục
Ở góc trên bên phải thanh tiêu đề luôn có huy hiệu trạng thái:
- **`🔴 Chưa kết nối`**: Chưa có kết nối CSDL nào được kích hoạt. Các chức năng truy vấn và thay đổi dữ liệu sẽ được khóa tự động để bảo đảm an toàn.
- **`🟢 Đã kết nối (<Tên hồ sơ>)`**: Đang có kết nối CSDL hợp lệ sẵn sàng làm việc.

---

## 📊 4. Các khối chỉ số thống kê (KPI Cards)
Trên màn hình Tổng quan có các thẻ chỉ số trực quan:
1. **Tổng số kết nối**: Số lượng hồ sơ CSDL đã lưu trong hệ thống.
2. **Lịch sử truy vấn**: Tổng số câu lệnh SQL đã chạy và số câu lệnh thực thi gần nhất.
3. **Thao tác kiểm toán (Audit)**: Tổng số giao dịch can thiệp dữ liệu (sửa/xóa) đã được ghi vết an toàn.
4. **Trạng thái AI**: Tình trạng sẵn sàng của trợ lý SQL Partner.

---

## 📝 5. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Hoàn thiện mô tả menu co giãn và cơ chế theo dõi trạng thái kết nối toàn cục.
