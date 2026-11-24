# 03 - HƯỚNG DẪN: TRÌNH SOẠN SQL (SQL WORKSPACE)

## 📌 1. Mục đích chức năng
**Trình soạn SQL (SQL Workspace)** là môi trường làm việc chính của người dùng, cung cấp trình soạn thảo mã SQL đa tab chuyên nghiệp, hỗ trợ thực thi nhanh, quản lý giao dịch an toàn, sinh mã DML đa năng (hàng loạt) và tích hợp AI tự động sửa lỗi.

---

## ⚡ 2. Quy tắc an toàn: Chặn truy vấn khi chưa kết nối
- **Nguyên tắc**: Nếu bạn chưa bấm nút **`Kết nối`** tới một CSDL cụ thể, hệ thống sẽ **khóa hoàn toàn nút `▶ Chạy SQL (F5)`** và phím tắt F5.
- Khi rê chuột vào nút chạy sẽ có thông báo: *"Chưa kết nối database: Bạn phải bấm 'Kết nối' trước khi chạy truy vấn"*.
- **Cách kết nối**: Chọn tên kết nối ở dropdown trên thanh công cụ và bấm nút **`Kết nối`** ngay bên cạnh. Khi nút chuyển sang `Ngắt kết nối` và có biểu tượng xanh lá, bạn mới có thể thực thi SQL.

---

## 📂 3. Cây đối tượng & Khớp nối Schema tương ứng
- Ở khung **DATABASE EXPLORER** bên trái:
  - Dropdown chọn Schema (ví dụ `HIS_RS`, `LIS_RS`, `QCS_RS`...).
  - **Cơ chế lọc thông minh**: Cây đối tượng chỉ hiển thị các bảng/view thuộc đúng Schema đang được chọn, không làm rối mắt người dùng bởi hàng nghìn bảng của các schema hệ thống khác.
  - Danh sách bảng hiển thị số lượng cụ thể (ví dụ: `Bảng (592)`).
  - Có ô tìm kiếm nhanh bảng ở đầu danh sách.

---

## 📑 4. Giao diện đa Tab (Multi-tab Editor)
- Bấm nút **`＋ Tab SQL mới`** để mở thêm tab làm việc độc lập.
- Mỗi tab lưu trữ nội dung SQL riêng, có nút `✕` để đóng tab khi hoàn thành.
- Hỗ trợ đổi tab linh hoạt mà không bị mất nội dung câu lệnh đang soạn thảo dở dang.

---

## 🛠️ 5. Bộ nút DML Đa Năng (Nhiều dòng cùng một lúc)
Hệ thống cung cấp bộ 3 nút thao tác dữ liệu đa năng với menu lựa chọn (`▾`):

### 5.1. Nút `＋ INSERT ▾` (Thêm dữ liệu đa năng)
Bấm vào nút để chọn 1 trong 4 hình thức sinh câu lệnh:
1. **`➕ Thêm 1 dòng (Bind tham số)`**: Sinh lệnh thêm 1 dòng mẫu dùng tham số `:param`.
2. **`📑 Thêm nhiều dòng cùng lúc (Batch INSERT)`**:
   - Tự động sinh cú pháp `INSERT ALL` (Oracle) hoặc `INSERT INTO ... VALUES (...), (...)` (PostgreSQL/MySQL/SQL Server).
   - Tự động điền dữ liệu mẫu hợp lý: Khóa chính dạng số tự tăng, ngày giờ dạng `TO_CHAR(SYSDATE, 'YYYYMMDDHH24MISS')`, cờ `IS_ACTIVE = 1`, `IS_DELETE = 0`.
3. **`📥 Thêm từ câu lệnh SELECT khác (INSERT INTO ... SELECT)`**:
   - Sinh mẫu nạp dữ liệu hàng loạt từ điều kiện lọc hoặc từ bảng khác.
4. **`🔄 Thêm mới hoặc Cập nhật (MERGE / UPSERT)`**:
   - Sinh mẫu `MERGE INTO` (Oracle) hoặc `ON CONFLICT` (PostgreSQL) chống trùng lặp dữ liệu.

### 5.2. Nút `✎ UPDATE ▾` (Cập nhật dữ liệu đa năng)
1. **`✏️ Cập nhật 1 dòng (Theo khóa chính)`**: Sửa thông tin 1 bản ghi qua khóa chính.
2. **`📋 Cập nhật hàng loạt nhiều dòng (WHERE IN list)`**:
   - Sinh mẫu cập nhật cùng một trạng thái cho hàng loạt ID bệnh nhân/hồ sơ cùng lúc:
     ```sql
     UPDATE HIS_RS.HIS_ADR
     SET IS_ACTIVE = 1, MODIFY_TIME = TO_CHAR(SYSDATE, 'YYYYMMDDHH24MISS')
     WHERE ID IN (1001, 1002, 1003, 1004, 1005);
     ```
3. **`🔀 Cập nhật đa giá trị từng dòng (CASE WHEN)`**:
   - Cập nhật các giá trị khác nhau cho từng dòng riêng biệt trong 1 câu SQL duy nhất bằng biểu thức `CASE [PK] WHEN ... THEN ... END`.
4. **`⏱️ Cập nhật theo điều kiện lọc / thời gian`**:
   - Cập nhật hàng loạt theo khoảng thời gian tạo hoặc trạng thái nghiệp vụ.

### 5.3. Nút `▣ DELETE ▾` (Xóa dữ liệu đa năng)
1. **`🗑️ Xóa 1 dòng (Theo khóa chính)`**: Xóa 1 bản ghi xác định.
2. **`📑 Xóa hàng loạt nhiều dòng (WHERE IN list)`**:
   - Xóa nhiều dòng cùng lúc theo danh sách ID.
3. **`🛡️ Xóa mềm HIS (Cập nhật IS_DELETE = 1)`**:
   - *Tính năng an toàn y tế*: Không xóa vật lý trong database, tự động sinh lệnh set `IS_DELETE = 1`, cập nhật `MODIFY_TIME` và `MODIFIER` để bảo toàn hồ sơ bệnh án.
4. **`⏱️ Xóa theo điều kiện lọc thời gian / rác`**:
   - Xóa các bản ghi rác hoặc bản ghi đã đánh dấu xóa mềm quá hạn.

> [!TIP]
> **Bảo toàn công việc**: Nếu tab hiện tại của bạn đang có nội dung, khi bạn bấm sinh mẫu DML hệ thống sẽ **tự động mở tab mới** để không đè lên câu lệnh cũ.

---

## 🛡️ 6. Menu "Giao dịch ▾" (Transaction Control)
Bao gồm 3 tùy chọn:
1. **`Bắt đầu transaction`**: Mở phiên làm việc tạm thời. Dữ liệu sửa/xóa chưa ảnh hưởng đến hệ thống HIS thật.
2. **`COMMIT`**: Xác nhận lưu vĩnh viễn kết quả vừa chạy vào database.
3. **`ROLLBACK`**: Hủy bỏ ngay lập tức toàn bộ câu lệnh vừa chạy, khôi phục lại dữ liệu nguyên vẹn như trước khi mở transaction.

---

## ⚡ 7. Kho mẫu câu lệnh phong phú (Nút "Mẫu SQL ▾")
Trên thanh công cụ của Trình soạn thảo tích hợp nút **`⚡ Mẫu SQL ▾`** với đa dạng các cấu trúc truy vấn chuẩn được dùng nhiều nhất trong quản trị CSDL y tế:
- **`SELECT TOP / LIMIT 100`**: Mẫu truy vấn giới hạn dòng tối ưu hiệu năng.
- **`SELECT với INNER JOIN`**: Mẫu nối bảng liên kết thông tin (ví dụ: bệnh nhân, điều trị, viện phí).
- **`SELECT với LEFT JOIN`**: Mẫu nối bảng bảo toàn bản ghi phía trái (báo cáo doanh thu, xét nghiệm).
- **`GROUP BY & HAVING (Thống kê)`**: Mẫu thống kê tổng hợp số lượng và doanh thu theo khoa phòng.
- **`Common Table Expression (WITH CTE)`**: Mẫu truy vấn bảng tạm phân cấp, xử lý báo cáo phức tạp (như báo cáo xuất nhập tồn, luân chuyển kho dược).
- **`Thêm mới INSERT INTO...`**: Mẫu thêm bản ghi chuẩn cấu trúc.
- **`Cập nhật UPDATE .. WHERE ..`**: Mẫu cập nhật có điều kiện ràng buộc an toàn.
- **`Xóa DELETE FROM .. WHERE ..`**: Mẫu xóa bản ghi có điều kiện.
- **`Tạo bảng CREATE TABLE ..`**: Mẫu tạo bảng mới với đầy đủ kiểu dữ liệu và khóa chính.
- **`Tạo chỉ mục CREATE INDEX ..`**: Mẫu tạo index tăng tốc độ truy vấn trên các cột mã bệnh nhân, mã điều trị, thời gian tạo.

---

## 🧩 8. Tham số động & Xử lý biến Bind Variable (Nút "Tham số SQL")
- Hệ thống hỗ trợ xử lý đầy đủ các câu lệnh chứa biến tham số dạng hai chấm (như `:TIME_FROM`, `:TIME_TO`, `:MEDI_STOCK_IDs`...).
- Bấm nút **`Tham số SQL`** để mở bảng nhập giá trị cho từng biến.
- Tự động nhận diện và bind biến chuẩn xác vào lệnh thực thi, ngăn chặn triệt để lỗi `ORA-01008: not all variables bound` khi chạy các script báo cáo chuyên sâu (như báo cáo TKB00006).

---

## ↔️ 9. Bố cục kéo dãn linh hoạt (Resizable Layout)
- Giữa khung soạn thảo SQL và bảng kết quả hiển thị dữ liệu được trang bị thanh chia cắt **GridSplitter**.
- Bạn có thể rê chuột vào thanh phân cách và kéo lên/xuống để mở rộng không gian viết code hoặc mở rộng bảng xem dữ liệu tùy theo nhu cầu làm việc.

---

## 🕒 10. Lịch sử truy vấn chuẩn thời gian thực
- Cột bên dưới Database Explorer hiển thị danh sách các câu lệnh bạn vừa thực thi.
- Mốc thời gian được hiển thị chuẩn xác từng giây (ngày/tháng/năm giờ:phút:giây) theo giờ hệ thống thực tế.
- Nhấp đúp hoặc bấm vào câu lệnh cũ để nạp lại ngay vào tab soạn thảo.

## 🏷️ 7. Nút "Tham số SQL" (Bind Parameters)
- Cho phép truyền các tham số bind dạng JSON (ví dụ `:id`, `:from_date`).
- **Ưu điểm**:
  - Không lưu các thông tin nhạy cảm (thông tin cá nhân của bệnh nhân) vào lịch sử truy vấn.
  - Tối ưu bộ nhớ đệm thực thi của Oracle/PostgreSQL (tránh hard-parse).

---

## 🔍 8. Bảng kết quả, Tìm kiếm theo cột & Phân trang
- **Lọc theo cột hoặc toàn bộ**: Dropdown chọn cột (`[Tất cả các cột]` hoặc từng cột cụ thể) + ô nhập từ khóa tìm kiếm trực tiếp trong bảng kết quả.
- **Tùy chọn số dòng hiển thị**: Chọn hiển thị `50`, `100`, `200`, `500`, hoặc `1.000 dòng`.
- **Xuất file**: Có 2 nút nhanh **`Xuất CSV`** và **`Excel`** xuất kết quả hiện tại ra máy tính.

---

## 🤖 9. Định dạng chuẩn & AI Sửa lỗi cú pháp
- **Nút `✨ Định dạng chuẩn`**: Tự động căn lề, thụt dòng, viết hoa từ khóa SQL theo chuẩn quốc tế chỉ bằng 1 click.
- **Nút `⚡ AI Sửa lỗi & Cấu trúc`**: Khi câu lệnh gặp lỗi cú pháp (sai dấu, thiếu FROM, sai tên cột, sai cú pháp Oracle...), AI sẽ phân tích lỗi từ database và tự động đề xuất câu SQL đã sửa đúng chuẩn.
- **Nút `⚙ Cấu hình AI`**: Cài đặt API key, model (Gemini, OpenAI, v.v.).

---

## ⚡ 10. Gợi ý bảng & cột thông minh (IntelliSense Auto-complete: Ctrl + Space)
Khi soạn thảo SQL, bạn có thể nhấn tổ hợp phím **`Ctrl + Space`** bất kỳ lúc nào để mở hộp thoại gợi ý thông minh ngay tại vị trí con trỏ chuột:

1. **Gợi ý Bảng / Khung nhìn (Tables & Views)**:
   - Khi gõ sau mệnh đề `FROM`, `JOIN`, `INTO`, `UPDATE`, hoặc gõ tiền tố (ví dụ `his_` như trong câu lệnh `SELECT * FROM his_`), nhấn **`Ctrl + Space`** sẽ tự động liệt kê tất cả các bảng và view phù hợp thuộc Schema đang kết nối (kèm icon `📋` cho bảng và `👁️` cho view).
   - Danh sách hỗ trợ tìm kiếm theo tiền tố hoặc chứa từ khóa.
2. **Gợi ý Cột theo bảng (Columns Auto-complete)**:
   - Khi gõ tên bảng kèm dấu chấm `.` hoặc alias (ví dụ `his_treatment.` hoặc `t.`), nhấn **`Ctrl + Space`** sẽ tự động hiển thị đầy đủ danh sách các cột của bảng đó kèm kiểu dữ liệu (ví dụ `NUMBER(19,0)`, `VARCHAR2(50)`) và đánh dấu khóa chính `PK`.
   - Trong mệnh đề `SELECT`, `WHERE`, `ORDER BY`, `GROUP BY`, hệ thống ưu tiên gợi ý các cột thuộc các bảng xuất hiện trong câu lệnh.
3. **Gợi ý Hàm & Từ khóa SQL (Functions & Keywords)**:
   - Tự động gợi ý các hàm phổ biến (`COUNT()`, `SUM()`, `AVG()`, `NVL()`, `TO_DATE()`...) và các từ khóa chuẩn. Khi chọn hàm có dấu ngoặc tròn `()`, con trỏ tự động nhảy vào bên trong ngoặc để người dùng nhập tham số.
4. **Thao tác phím tắt linh hoạt**:
   - `Phím mũi tên Lên / Xuống`: Di chuyển trong danh sách gợi ý.
   - `Enter` hoặc `Tab`: Chọn và tự động điền gợi ý vào vị trí con trỏ.
   - `Escape`: Đóng hộp thoại gợi ý.

---

## 📝 11. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**:
  - Bổ sung tính năng gợi ý bảng, cột, hàm và từ khóa SQL thông minh qua phím tắt **`Ctrl + Space`**.
  - Cập nhật bộ nút DML đa năng nhiều dòng, giải thích chi tiết Transaction và tính năng tìm kiếm theo cột.
