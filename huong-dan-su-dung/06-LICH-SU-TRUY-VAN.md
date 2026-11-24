# 06 - HƯỚNG DẪN: LỊCH SỬ TRUY VẤN (QUERY HISTORY)

## 📌 1. Mục đích chức năng
Chức năng **Lịch sử truy vấn** là trung tâm theo dõi, kiểm toán và tái sử dụng toàn bộ các câu lệnh SQL đã được thực thi trên phần mềm, giúp bạn:
- Dễ dàng tra cứu, lọc và tái sử dụng các câu truy vấn phức tạp đã từng viết.
- Theo dõi thời gian thực thi (duration ms) và số lượng bản ghi ảnh hưởng để đánh giá hiệu năng database.
- Bắt lỗi và xem chi tiết nguyên nhân lỗi (mã lỗi ORA-, SQL Server error...) khi truy vấn thất bại.
- Phục hồi lại câu lệnh khi lỡ đóng tab hoặc tắt phần mềm đột ngột.

---

## 📊 2. Thẻ thống kê tổng quan (Metrics Cards)
Ngay trên đầu giao diện Lịch sử truy vấn là 4 thẻ chỉ số trực quan:
- **TỔNG TRUY VẤN**: Tổng số câu lệnh SQL đã thực thi theo điều kiện lọc hiện tại.
- **THÀNH CÔNG (%)**: Tỷ lệ truy vấn thực thi thành công (hiển thị màu xanh lá).
- **TRUY VẤN LỖI**: Số câu lệnh bị lỗi cú pháp hoặc bị database từ chối (hiển thị màu đỏ).
- **THỜI GIAN TB**: Thời gian xử lý trung bình tính bằng mili-giây (ms).

---

## 🔍 3. Bộ lọc & Tìm kiếm đa năng (Filter Toolbar)
Hệ thống cung cấp thanh công cụ lọc mạnh mẽ:
1. **Ô tìm kiếm từ khóa (Search Box)**: Nhập bất kỳ từ khóa nào xuất hiện trong câu lệnh SQL (ví dụ tên bảng `HIS_TREATMENT`, `JOIN`, `WHERE`), tên kết nối, địa chỉ IP hoặc tên tài khoản Windows.
2. **Lọc theo trạng thái**:
   - `Tất cả`: Xem toàn bộ câu lệnh.
   - `Thành công`: Chỉ xem các câu lệnh chạy thành công.
   - `Thất bại`: Chỉ xem các câu lệnh gặp lỗi hoặc bị ngắt.
3. **Lọc theo hồ sơ kết nối**: Chọn xem lịch sử riêng của từng CSDL (ví dụ `HIS_RS`, `LIS_RS`, `SQLServer_HIS`...).
4. **Lọc theo khoảng thời gian**: `Tất cả thời gian`, `Hôm nay`, `7 ngày qua`, `30 ngày qua`.
5. **Nút `✕ Bỏ lọc`**: Đưa toàn bộ các điều kiện lọc về mặc định chỉ với 1 click.

---

## 📄 4. Bảng chi tiết câu truy vấn (Inspector Panel)
Khi nhấp chọn một dòng bất kỳ trong danh sách lịch sử, bảng chi tiết bên phải sẽ hiển thị:
- **Trạng thái & Thời điểm**: Hiển thị badge màu sắc trực quan (Xanh lá `Thành công`, Đỏ `Thất bại`) cùng ngày giờ chính xác theo giờ máy tính địa phương.
- **Chi tiết lỗi**: Nếu câu lệnh thất bại, khung thông báo đỏ sẽ hiển thị chi tiết mã lỗi từ hệ quản trị CSDL.
- **Khung mã SQL toàn văn**: Hiển thị câu lệnh SQL đầy đủ với font chữ code Cascadia Code, hỗ trợ cuộn và chọn văn bản.
- **Nút `📝 Mở trong SQL`**: Nạp ngay câu lệnh này vào tab mới trong **Trình soạn SQL** và tự động chuyển sang trang soạn thảo để bạn chạy lại hoặc hiệu chỉnh.
- **Nút `📋 Sao chép`**: Copy toàn bộ nội dung SQL vào Clipboard.
- **Thông tin hạ tầng**: Hiển thị Tên kết nối, Hệ quản trị, Thời gian chạy, Dòng ảnh hưởng, Tài khoản Windows và Địa chỉ IP máy trạm.

---

## 🛠️ 5. Thao tác dữ liệu (Xuất file & Dọn dẹp)
- **Nút `↻ Làm mới`**: Nạp lại dữ liệu mới nhất từ bộ nhớ cục bộ.
- **Nút `📥 Xuất CSV`**: Xuất toàn bộ danh sách lịch sử đang được lọc ra file `.csv` để phục vụ báo cáo hoặc kiểm toán.
- **Nút `🗑️ Xóa lịch sử`**: Cho phép dọn dẹp sạch toàn bộ lịch sử truy vấn trên máy (có hộp thoại cảnh báo xác nhận an toàn trước khi xóa).

---

## 🔒 6. Nguyên tắc bảo mật dữ liệu y tế nhạy cảm
- Khi bạn sử dụng chức năng **Tham số SQL (Bind Parameters)**:
  - Hệ thống chỉ lưu **cấu trúc câu lệnh** vào lịch sử (ví dụ: `WHERE id = :p_id`).
  - Toàn bộ giá trị tham số thực tế (như số CCCD, tên bệnh nhân, chẩn đoán, số điện thoại) **không bao giờ bị ghi vào lịch sử**, bảo đảm tuân thủ nghiêm ngặt quy định bảo mật hồ sơ bệnh án.
- Tệp lịch sử được mã hóa bảo vệ an toàn bằng công nghệ Windows DPAPI tại thư mục `%LOCALAPPDATA%\DBStudio`.

---

## 📝 7. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Nâng cấp toàn diện giao diện Lịch sử truy vấn với bộ lọc thông minh, thẻ chỉ số thống kê, bảng Inspector chi tiết, tính năng Xuất CSV và Xóa lịch sử.
