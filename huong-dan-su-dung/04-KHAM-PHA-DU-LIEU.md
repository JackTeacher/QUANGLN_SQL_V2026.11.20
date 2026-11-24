# 04 - HƯỚNG DẪN: KHÁM PHÁ DỮ LIỆU (DATA EXPLORER)

## 📌 1. Mục đích chức năng
Chức năng **Khám phá dữ liệu (Data Explorer)** giúp người dùng duyệt cấu trúc các bảng và khung nhìn (view) trong CSDL, tra cứu nhanh dữ liệu thực tế, chỉnh sửa ô dữ liệu trực tiếp có kiểm soát an toàn, xem định nghĩa cột và sinh các mẫu truy vấn tự động.

---

## ⚡ 2. Trạng thái kết nối trực tiếp
- Tại thanh tiêu đề có dropdown chọn **Kết nối**, nút **`⚡ Kết nối`** / **`Ngắt kết nối`** và dropdown chọn **Schema**.
- Bạn chỉ có thể duyệt và nạp dữ liệu khi kết nối đã được kích hoạt thành công.

---

## 🌳 3. Cây đối tượng (Database Explorer Tree)
- Cây đối tượng bên trái hiển thị danh sách các bảng và view theo từng schema.
- **Thao tác 1 chạm (Single-Click)**: Bạn chỉ cần **nhấp chuột vào bất kỳ bảng nào** trong danh sách, hệ thống sẽ tự động nạp cấu trúc và dữ liệu của bảng đó ngay lập tức sang khung làm việc bên phải.
- **Hỗ trợ nhấp đúp (Double-Click)**: Cũng mở bảng tương tự.
- **Tìm kiếm đối tượng**: Có ô tìm kiếm nhanh ở đầu cây đối tượng để lọc bảng theo tên (ví dụ: gõ `HIS_ADR` hoặc `TREATMENT`).

---

## 🗂️ 4. Bốn (4) Tab chi tiết chuyên sâu

### 4.1. 📊 Tab 1: Dữ liệu (Data Viewer & Editor)
- **Thanh tìm kiếm & lọc dòng trong bảng (Đã tối ưu giao diện)**:
  - Chọn cột cần tìm (hoặc `[Tất cả các cột]`).
  - Ô nhập từ khóa tìm kiếm: Lọc dữ liệu tức thì theo thời gian thực trên bộ nhớ.
  - Bố cục thanh tìm kiếm được tối ưu dạng Wrap tự co giãn: Không bao giờ bị đè giao diện hoặc che khuất trên màn hình độ phân giải thấp.
  - Nút `✕` để xóa bộ lọc nhanh.
  - Thanh đếm dòng hiển thị kết quả lọc: ví dụ `5 kết quả lọc (1–100 / 529 dòng)`.
- **Tùy chọn số dòng hiển thị**: Dropdown chọn `50`, `100`, `200`, `500` hoặc `1.000 dòng` mỗi trang.
- **Thao tác xuất file**:
  - **`📊 Excel`**: Xuất trang dữ liệu hiện tại ra tệp `.xlsx`.
  - **`📄 CSV`**: Xuất trang dữ liệu ra tệp `.csv` chuẩn UTF-8 có BOM (mở tiếng Việt trên Excel không bị lỗi font).
- **Chỉnh sửa ô dữ liệu có kiểm soát**:
  - Với các bảng có khóa chính (PK) và kết nối ở chế độ *Đọc & Ghi*:
    - Bạn có thể **nhấp đúp vào ô dữ liệu bất kỳ** để sửa giá trị trực tiếp trên bảng.
    - Cột khóa chính được đánh dấu biểu tượng **`🔑 TÊN_CỘT`** và được khóa an toàn (chỉ đọc) để không làm gãy tính toàn vẹn dữ liệu.
    - Sau khi sửa, nút **`💾 Lưu thay đổi`** sẽ sáng lên.
    - Bấm **`Lưu thay đổi`**: Hệ thống sẽ hiển thị hộp thoại xác nhận số lượng dòng cần sửa và thực thi trong **Transaction** an toàn.
- **Xóa dòng đã chọn**:
  - Chọn một hoặc nhiều dòng trên bảng ➔ Bấm **`🗑️ Xóa dòng chọn`**. Hệ thống sẽ yêu cầu xác nhận trước khi thực hiện xóa.

### 4.2. 📋 Tab 2: Cấu trúc cột (Schema Columns)
- Liệt kê toàn bộ các cột của bảng: Số thứ tự (#), Tên cột, Kiểu dữ liệu (VARCHAR2, NUMBER, TIMESTAMP...), Có cho phép NULL không, Cột khóa chính (PK), Giá trị mặc định, Ghi chú / Diễn giải.
- **Ô tìm kiếm nhanh cột**: Tích hợp ô lọc cột ở đầu bảng giúp kỹ sư nhanh chóng tìm cột cần xem trên các bảng HIS lớn có hàng trăm trường dữ liệu.

### 4.3. ℹ️ Tab 3: Thông tin & Thống kê (Table Metrics)
- Cung cấp các thẻ thông tin tổng quan (KPI cards):
  - Tên đối tượng và Schema sở hữu.
  - Loại đối tượng (Table hoặc View).
  - Hệ quản trị CSDL (Oracle, Postgres...).
  - Tổng số dòng dữ liệu thực tế trong bảng.
  - Số lượng cột.
  - Danh sách các cột thuộc khóa chính (PK).
  - Chế độ truy cập hiện tại (*Đọc & Ghi* hoặc *Chỉ đọc*).

### 4.4. 📝 Tab 4: SQL Mẫu (SQL Generator)
- Tự động sinh các câu lệnh SQL mẫu tương ứng chính xác với bảng hiện tại:
  - `SELECT *` có giới hạn dòng.
  - `COUNT (*)` đếm số dòng.
  - `INSERT` có đầy đủ danh sách cột.
  - `UPDATE` có mệnh đề WHERE theo khóa chính.
  - `DELETE` có mệnh đề WHERE theo khóa chính.
- **Nút tiện ích**:
  - **`📋 Sao chép SQL`**: Lưu câu lệnh mẫu vào Clipboard để dán vào công việc khác.
  - **`🚀 Mở trong Trình soạn SQL`**: Chuyển ngay câu lệnh sang tab mới trong Trình soạn SQL để chạy hoặc chỉnh sửa tiếp.

---

## 📝 5. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Cập nhật cơ chế mở bảng 1 chạm (single-click), sửa lỗi nạp trạng thái sạch `AcceptChanges`, hoàn thiện tài liệu 4 tab nghiệp vụ.
