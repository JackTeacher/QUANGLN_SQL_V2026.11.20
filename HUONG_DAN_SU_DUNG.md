# 📚 SỔ TAY HƯỚNG DẪN SỬ DỤNG - QUANGLN SQL (V2026.11.20)

> **Tác giả:** Lương Ngọc Quảng  
> **Phiên bản:** V2026.11.20  
> **Ngày phát hành:** 20/11/2026  

---

# 🌟 TỔNG HỢP CÁC BẢN CẬP NHẬT MỚI NHẤT (PHIÊN BẢN V2026.11.20)

Bản cập nhật lớn V2026.11.20 mang đến nhiều cải tiến vượt bậc về không gian soạn thảo SQL, trợ lý tra lỗi tài liệu y tế, hiệu năng khởi động và trải nghiệm thị giác:

| Khu vực nâng cấp | Nội dung thay đổi chi tiết |
| :--- | :--- |
| **Tổng quan (Dashboard)** | Tích hợp **Thanh lối tắt truy cập nhanh (Quick Launch Bar)** đến mọi phân hệ; Nút **`📝 SQL`** và **`🔍 Duyệt`** trực tiếp trên từng thẻ Kết nối yêu thích; Nút **`📝 Mở SQL`** trên từng dòng Hoạt động truy vấn gần đây cùng huy hiệu trạng thái **`✔ Thành công` / `✖ Thất bại`** trực quan. |
| **Trình soạn SQL (SQL Editor)** | **Thước đánh số dòng (Line Numbers Gutter)** đồng bộ tuyệt đối với cuộn dọc; **Thực thi thông minh `Ctrl + Enter`** chạy riêng câu lệnh tại vị trí con trỏ hoặc đoạn bôi đen; **Thanh công cụ Tìm kiếm & Thay thế `Ctrl + F / Ctrl + H`** tích hợp đếm kết quả, `F3 / Shift+F3`, phân biệt hoa thường `Aa`; **Thanh trạng thái con trỏ** hiển thị tọa độ Dòng/Cột, số lượng ký tự chọn, tổng số dòng và bộ nút phóng to/thu nhỏ cỡ chữ (`A- / A+ / ↺`); **Quản lý Tab nâng cao** hỗ trợ nhấp đúp đổi tên trực tiếp và menu chuột phải (Nhân đôi, Sao chép SQL, Đóng các tab khác, Đóng tab bên phải, Đóng tất cả); **Bộ phím tắt nhanh** (`Ctrl+/`, `Ctrl+D`, `Ctrl+Shift+K`, `Ctrl+Shift+U/L`). |
| **Kho mẫu SQL phong phú** | Mở rộng lên **8 nhóm mẫu câu lệnh** bao quát toàn diện: Truy vấn SELECT, Kết hợp bảng JOIN, Thống kê & Phân tích Analytics (Window functions), Bảng tạm WITH CTE & Đệ quy, Chuyên ngành Y tế & HIS (`HIS_PATIENT`, `HIS_SERE_SERV`, `HIS_EXP_MEST`, lọc thời gian `yyyyMMddHHmmss`, trạng thái hiệu lực), Thao tác DML, Cấu trúc DDL, và Tiện ích Chuỗi & Ngày giờ. |
| **Thiết kế Truy vấn (Visual Query Builder)** | Kích hoạt trực tiếp trên thanh menu điều hướng (`📐 Thiết kế truy vấn`); Bổ sung nút **`☑ Tất cả`** trên từng bảng, ô nhập điều kiện lọc **`WHERE`**, nút **`🗑️ Xóa sơ đồ`**, **`📋 Sao chép SQL`** và **`📥 Chèn vào SQL Editor`**. |
| **Trợ lý AI · SQL Partner** | Bổ sung chế độ **`⚡ Chuyên gia SQL Nội bộ (Offline - Không cần API Key)`** hoạt động 100% cục bộ cho các kịch bản Y tế HIS, tối ưu hiệu năng DBA, chuyển đổi Subquery sang CTE, kiểm tra SQL Injection và sinh Mock Data; Tự động chuyển sang màn hình Trình soạn SQL khi bấm Chèn hoặc Chạy ngay. |
| **Trợ lý tra lỗi (RAG Skill Assistant)** | Module **Trợ lý tra lỗi cục bộ (Offline RAG)**: Nạp tệp `.docx`, `.pdf`, `.md`, `.txt` trực tiếp từ máy tính; Tự động bóc tách độc lập từng mục câu lệnh thông minh, triệt tiêu hoàn toàn hiện tượng hiển thị danh sách tràn lan gây rối mắt; Tích hợp tab **Lịch sử hỏi**; Giao tiếp thân thiện, tự nhiên. |
| **Khám phá dữ liệu (Data Explorer)** | Mở rộng lên **10 mẫu sinh SQL tự động** (SELECT, COUNT, GROUP BY, Kiểm tra trùng lặp, Top 50 mới nhất, INSERT đơn/hàng loạt, UPDATE, Xóa mềm HIS `IS_DELETE = 1`, DELETE); Bổ sung nút **`➕ Thêm dòng`** trực tiếp trên bảng, **`📋 Copy danh sách tên cột`** và **`📊 Xuất từ điển cột (Data Dictionary) ra Excel`**. |
| **Lịch sử truy vấn (Query History)** | Bổ sung xuất báo cáo **`📊 Xuất Excel (.xlsx)`** bên cạnh CSV; Nút **`🛠️ Tra lỗi`** gửi trực tiếp câu lệnh bị lỗi sang Trợ lý tra lỗi RAG; Hiển thị đầy đủ thông báo lỗi chi tiết trong khung Inspector. |
| **Nhật ký kiểm toán (Audit Log)** | Nâng cấp khung chi tiết thành 3 Tab chuyên sâu: **`📊 Bảng so sánh Trước / Sau (Visual Diff)`** đối chiếu từng cột thay đổi, **`↩️ Lệnh SQL Hoàn tác (Rollback / Undo)`** tự động sinh mã SQL khôi phục dữ liệu về trạng thái cũ, và **`📄 Dữ liệu JSON gốc (DPAPI)`**. |
| **Quản lý API & HTTP Client** | Bổ sung 6 mẫu API Y tế / HIS tiêu chuẩn (Cổng BHYT, Giám định XML 130/4210, Đơn thuốc quốc gia, HL7 FHIR Patient, LIS/PACS Webhook); Nhấp vào dòng lịch sử để nạp lại Request; Lưu Response Body ra tệp `.json / .xml / .txt`. |
| **Hiệu năng & Giao diện** | Tối ưu hóa chu trình khởi động ứng dụng (Fast Startup), loại bỏ giật lag hoạt cảnh; Bảng màu **High-Contrast Design System** sắc nét trong cả chủ đề **Sáng (Light)** và **Tối (Dark)**. |

---

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


---

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


---

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

## 📑 4. Giao diện đa Tab & Không gian soạn thảo chuyên nghiệp (IDE-Grade Editor)
- **Quản lý đa tab thông minh**:
  - Bấm nút **`＋ Tab SQL mới`** để mở thêm tab làm việc độc lập.
  - **Đổi tên tab trực tiếp**: Nhấp đúp chuột vào tiêu đề tab để chỉnh sửa tên gợi nhớ (ví dụ: `BC_NhapXuatTon`, `Check_HoSo_123`...). Nhấn `Enter` để lưu tên hoặc `Esc` để hủy.
  - **Menu chuột phải phong phú**: Nhấp chuột phải vào tab để chọn:
    - *✏️ Đổi tên tab (Double-click)*
    - *📑 Nhân đôi tab này* (Duplicate tab)
    - *📋 Sao chép toàn bộ SQL* (Copy script)
    - *💾 Lưu tab này...*
    - *✕ Đóng tab này*
    - *✕ Đóng các tab khác* (Close Others)
    - *✕ Đóng các tab bên phải* (Close Tabs to the Right)
    - *✕ Đóng tất cả tab* (Close All)
  - Biểu tượng chấm cam `●` tự động cảnh báo khi script trong tab chưa được lưu.

- **Thước đánh số dòng (Line Numbers Gutter)**:
  - Cột số dòng chuyên dụng hiển thị bên trái cửa sổ code, tách biệt hoàn toàn với vùng văn bản.
  - Đồng bộ 100% với thao tác cuộn chuột lên/xuống.
  - Tự động co giãn bề rộng linh hoạt theo số chữ số của văn bản (hàng chục, hàng trăm, hàng nghìn dòng).
  - **Nhấp vào số dòng**: Con trỏ soạn thảo sẽ lập tức nhảy đến đầu dòng tương ứng.

- **Thực thi câu lệnh thông minh (Smart Execution)**:
  - **`F5`**: Thực thi toàn bộ script trong tab hiện tại.
  - **`Ctrl + Enter` (hoặc nút `▶ Chạy câu hiện tại`)**: Hệ thống tự động phân tích và chỉ thực thi riêng câu lệnh mà con trỏ chuột đang đứng (hoặc đoạn văn bản đang bôi đen), không làm ảnh hưởng đến các câu truy vấn khác trong cùng tab.

- **Thanh công cụ Tìm kiếm & Thay thế (Inline Find & Replace - Ctrl+F / Ctrl+H)**:
  - Bấm **`Ctrl + F`** để mở thanh tìm kiếm; bấm **`Ctrl + H`** để mở thanh thay thế.
  - Hỗ trợ **`F3`** (tìm kế tiếp), **`Shift + F3`** (tìm lùi trước đó).
  - Nút **`Aa`**: Bật/tắt phân biệt chữ hoa và chữ thường.
  - Hiển thị trực tiếp số lượng vị trí trùng khớp (`Tìm thấy (Tổng X vị trí)`).
  - Hỗ trợ **`Thay thế`** (từng vị trí) và **`Thay tất cả`** (toàn bộ tab).
  - Bấm **`Esc`** hoặc nút `✕` để đóng thanh công cụ.

- **Thanh trạng thái con trỏ & Phóng to thu nhỏ (Editor Status Bar)**:
  - Hiển thị chính xác tọa độ con trỏ: `Dòng X, Cột Y`.
  - Hiển thị tổng số dòng: `Tổng cộng: N dòng`.
  - Hiển thị số lượng ký tự được chọn: `Đã chọn: Z ký tự`.
  - Bộ công cụ điều chỉnh cỡ chữ: Nút `A-` (thu nhỏ), `A+` (phóng to), `↺` (đặt lại mặc định 13pt), hoặc giữ `Ctrl + Lăn chuột giữa`.
  - Nút bấm nhanh: `▶ Chạy câu hiện tại (Ctrl+Enter)`.

- **Phím tắt biên tập mã nhanh**:
  - `Ctrl + /`: Bật/tắt chú thích `--` (Comment/Uncomment).
  - `Ctrl + D`: Nhân bản dòng hiện tại xuống dưới (Duplicate Line).
  - `Ctrl + Shift + K`: Xóa dòng hiện tại (Delete Line).
  - `Ctrl + Shift + U`: Chuyển đoạn bôi đen thành CHỮ IN HOA.
  - `Ctrl + Shift + L`: Chuyển đoạn bôi đen thành chữ in thường.
  - `Ctrl + Space`: Bật bảng gợi ý từ khóa, hàm và tên bảng/cột (IntelliSense).

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

## 🏷️ 7. Nút "Tham số SQL" & Xử lý biến Bind Variable (:PARAM)
- Cho phép truyền các tham số bind dạng JSON hoặc biến đặt tên (ví dụ `:TIME_FROM`, `:TIME_TO`, `:MEDI_STOCK_IDs`, `:id`...).
- **Ưu điểm**:
  - Hỗ trợ chạy các câu lệnh báo cáo phức tạp (như báo cáo nhập xuất tồn `TKB00006`, luân chuyển kho dược) không bị lỗi `ORA-01008: not all variables bound`.
  - Không lưu các thông tin nhạy cảm vào lịch sử truy vấn.
  - Tối ưu bộ nhớ đệm thực thi của Oracle/PostgreSQL (tránh hard-parse).

---

## ⚡ 8. Kho mẫu câu lệnh phong phú (Nút "Mẫu SQL ▾" với 8 nhóm chuyên biệt)
Trên thanh công cụ tích hợp nút **`⚡ Mẫu SQL ▾`** được cấu trúc thành **8 nhóm mẫu câu lệnh** đa dạng, bao quát từ cơ bản, nâng cao đến các mẫu nghiệp vụ y tế & HIS:

1. **🔍 Nhóm 1: Truy vấn dữ liệu (SELECT)**:
   - *Phân trang TOP / LIMIT / FETCH FIRST*: Tối ưu tốc độ tải dữ liệu lớn.
   - *Lọc bản ghi duy nhất DISTINCT + Sắp xếp*: Khử trùng dữ liệu và sắp xếp thứ tự.
   - *Biểu thức điều kiện CASE WHEN ... THEN ... END*: Phân loại trạng thái dữ liệu linh hoạt.
   - *Xử lý giá trị NULL (NVL / COALESCE)*: Thay thế giá trị rỗng an toàn.
   - *Truy vấn con EXISTS / NOT EXISTS*: Lọc quan hệ bảng tốc độ cao.
2. **🔗 Nhóm 2: Kết hợp bảng (JOIN)**:
   - *INNER JOIN*: Kết hợp bảng chính và bảng phụ có cùng khóa liên kết.
   - *LEFT JOIN*: Giữ nguyên toàn bộ dữ liệu bảng chính, ghép thêm thông tin bảng phụ.
   - *FULL OUTER JOIN*: Hợp nhất toàn bộ dữ liệu 2 bảng.
   - *SELF JOIN*: Duyệt danh mục phân cấp cha - con trong cùng một bảng.
   - *CROSS JOIN*: Tích đề-các / sinh tổ hợp kiểm thử.
3. **📊 Nhóm 3: Thống kê & Phân tích (Analytics & Window Functions)**:
   - *Gom nhóm GROUP BY & HAVING*: Tính `COUNT`, `SUM`, `AVG`, `MAX`, `MIN`.
   - *Đánh số dòng ROW_NUMBER() OVER (PARTITION BY ...)*: Đánh số thứ tự từng nhóm dữ liệu.
   - *Xếp hạng dữ liệu RANK() & DENSE_RANK()*: Xếp hạng doanh thu, tần suất khám.
   - *So sánh dòng trước / sau LAG() & LEAD()*: So sánh chỉ số giữa các kỳ khám bệnh.
   - *Tính tổng lũy kế (Running Total) SUM() OVER (...)*: Tính tổng doanh thu tích lũy theo thời gian.
4. **🌳 Nhóm 4: Bảng tạm & Đệ quy (WITH CTE)**:
   - *Bảng tạm đơn giản WITH CTE AS (...)*: Gom câu lệnh dài thành các khối logic dễ đọc.
   - *Nhiều bảng tạm liên hoàn WITH CTE1, CTE2*: Nối tiếp chuỗi xử lý nghiệp vụ phức tạp.
   - *CTE Đệ quy duyệt cây đa cấp (Hierarchy / Tree)*: Duyệt cây khoa phòng, sơ đồ tổ chức bệnh viện.
5. **🏥 Nhóm 5: Chuyên ngành Y tế & HIS (Bệnh viện)**:
   - *Hồ sơ điều trị (`HIS_PATIENT` + `HIS_TREATMENT`)*: Truy vấn thông tin hành chính, mã bệnh nhân, mã điều trị, ngày vào/ra viện.
   - *Y lệnh & Dịch vụ cận lâm sàng (`HIS_SERE_SERV` + `HIS_SERVICE_REQ`)*: Tra cứu chi tiết dịch vụ khám, xét nghiệm, chẩn đoán hình ảnh.
   - *Báo cáo xuất nhập kho Dược / Vật tư (`HIS_EXP_MEST` / `HIS_IMP_MEST`)*: Mẫu kiểm tra chứng từ nhập/xuất kho tủ trực, tồn kho thuốc.
   - *Điều kiện lọc khoảng thời gian `yyyyMMddHHmmss` chuẩn HIS*: Mẫu lọc thời gian định dạng 14 ký tự đặc thù của HIS.
   - *Điều kiện lọc bản ghi hiệu lực*: Tự động áp dụng `IS_ACTIVE = 1` và `IS_DELETE = 0`.
6. **✏️ Nhóm 6: Thao tác dữ liệu (DML)**:
   - *Thêm mới bản ghi INSERT INTO...*: Thêm dữ liệu có danh sách cột rõ ràng.
   - *Thêm mới từ kết quả SELECT (INSERT INTO ... SELECT)*: Sao chép dữ liệu giữa các bảng.
   - *Cập nhật dữ liệu UPDATE ... WHERE ...*: Cập nhật có điều kiện an toàn.
   - *Ghi đè hoặc thêm mới MERGE INTO (Upsert)*: Chống trùng lặp khóa chính.
   - *Xóa dữ liệu có điều kiện DELETE FROM ... WHERE ...*: Xóa an toàn.
7. **🛠 Nhóm 7: Cấu trúc CSDL (DDL)**:
   - *Tạo bảng mới CREATE TABLE*: Khai báo khóa chính `PK`, khóa ngoại `FK`, ràng buộc `CHECK`, giá trị mặc định `DEFAULT`.
   - *Tạo chỉ mục CREATE INDEX*: Đánh chỉ mục tối ưu hóa tốc độ tìm kiếm.
   - *Tạo khung nhìn CREATE VIEW*: Tạo view tái sử dụng câu lệnh báo cáo.
   - *Thêm cột vào bảng ALTER TABLE ADD...*: Mở rộng cấu trúc bảng.
   - *Xóa trắng bảng TRUNCATE TABLE*: Làm sạch dữ liệu bảng tạm nhanh chóng.
8. **⏱ Nhóm 8: Tiện ích Ngày giờ & Chuỗi**:
   - *Lấy thời gian hiện tại đa hệ (`SYSDATE` / `GETDATE()` / `NOW()`)*: Khớp theo hệ quản trị đang dùng.
   - *Định dạng ngày giờ hiển thị (`TO_CHAR` / `FORMAT`)*: Hiển thị ngày giờ dạng `DD/MM/YYYY HH24:MI:SS`.
   - *Ghép chuỗi danh sách (`LISTAGG` / `STRING_AGG` / `GROUP_CONCAT`)*: Gom danh sách tên dịch vụ/khoa phòng vào một ô duy nhất.

---

## ↔️ 9. Bố cục kéo dãn linh hoạt & Lịch sử truy vấn chuẩn
- **Thanh kéo dãn (GridSplitter)**: Có thể dùng chuột kéo thả thanh phân cách giữa khung soạn thảo SQL và bảng kết quả để tùy ý mở rộng không gian quan sát.
- **Lịch sử truy vấn chuẩn thời gian thực**: Danh sách các câu lệnh vừa chạy hiển thị chuẩn xác từng giây (`dd/MM/yyyy HH:mm:ss`) theo giờ hệ thống. Bấm vào câu lệnh cũ để nạp lại ngay vào tab soạn thảo.

---

## 🔍 10. Bảng kết quả, Tìm kiếm theo cột & Phân trang
- **Lọc theo cột hoặc toàn bộ**: Dropdown chọn cột (`[Tất cả các cột]` hoặc từng cột cụ thể) + ô nhập từ khóa tìm kiếm trực tiếp trong bảng kết quả.
- **Tùy chọn số dòng hiển thị**: Chọn hiển thị `50`, `100`, `200`, `500`, hoặc `1.000 dòng`.
- **Xuất file**: Có 2 nút nhanh **`Xuất CSV`** và **`Excel`** xuất kết quả hiện tại ra máy tính.

---

## 🤖 11. Định dạng chuẩn & AI Sửa lỗi cú pháp
- **Nút `✨ Định dạng chuẩn`**: Tự động căn lề, thụt dòng, viết hoa từ khóa SQL theo chuẩn quốc tế chỉ bằng 1 click.
- **Nút `⚡ AI Sửa lỗi & Cấu trúc`**: Khi câu lệnh gặp lỗi cú pháp (sai dấu, thiếu FROM, sai tên cột, sai cú pháp Oracle...), AI sẽ phân tích lỗi từ database và tự động đề xuất câu SQL đã sửa đúng chuẩn.
- **Nút `⚙ Cấu hình AI`**: Cài đặt API key, model (Gemini, OpenAI, v.v.).

---

## ⚡ 12. Gợi ý bảng & cột thông minh (IntelliSense Auto-complete: Ctrl + Space)
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

## 📝 13. Nhật ký cập nhật tính năng (Changelog - Trình soạn SQL)
- **V2026.11.20 (Bản nâng cấp IDE Chuyên Sâu - 20/11/2026)**:
  - **Thước đánh số dòng (Line Numbers Gutter)**: Hiển thị số dòng chuẩn xác, tự động co giãn theo số chữ số, đồng bộ tuyệt đối khi cuộn dọc và hỗ trợ nhấp chuột để di chuyển con trỏ.
  - **Thực thi thông minh `Ctrl + Enter`**: Tự động phân tách và chỉ thực thi riêng câu lệnh tại vị trí con trỏ chuột (hoặc đoạn bôi đen) mà không ảnh hưởng tới các câu lệnh khác trong cùng tab.
  - **Thanh công cụ Tìm kiếm & Thay thế (Find & Replace Toolbar)**: Phím tắt `Ctrl + F` (tìm kiếm), `Ctrl + H` (thay thế), `F3 / Shift+F3` (tìm tiếp/lùi), nút `Aa` (phân biệt hoa thường), đếm số vị trí trùng khớp và thay thế toàn bộ.
  - **Thanh trạng thái con trỏ (Status Bar)**: Báo cáo Dòng, Cột, Tổng số dòng, Số ký tự đang chọn và cụm nút phóng to/thu nhỏ cỡ chữ (`A- / A+ / ↺` / `Ctrl + Cuộn chuột`).
  - **Quản lý Tab nâng cao**: Nhấp đúp đổi tên tab trực tiếp tại chỗ; Bổ sung Menu chuột phải đầy đủ chức năng (Nhân đôi tab, Sao chép toàn bộ SQL, Lưu tab, Đóng các tab khác, Đóng các tab bên phải, Đóng tất cả).
  - **Bộ phím tắt soạn thảo**: Hỗ trợ `Ctrl+/` (chú thích `--`), `Ctrl+D` (nhân đôi dòng), `Ctrl+Shift+K` (xóa dòng), `Ctrl+Shift+U/L` (chuyển chữ hoa/thường).
  - **Mở rộng kho mẫu SQL**: Tích hợp 8 nhóm mẫu câu lệnh với hơn 40 mẫu truy vấn chuẩn hóa cho y tế & HIS.
- **v1.0.0 (14/11/2026)**:
  - Bổ sung tính năng gợi ý bảng, cột, hàm và từ khóa SQL thông minh qua phím tắt **`Ctrl + Space`**.
  - Cập nhật bộ nút DML đa năng nhiều dòng, giải thích chi tiết Transaction và tính năng tìm kiếm theo cột.


---

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
- **Thanh tìm kiếm & lọc dòng trong bảng (Tối ưu giao diện)**:
  - Chọn cột cần tìm (hoặc `[Tất cả các cột]`).
  - Ô nhập từ khóa tìm kiếm: Lọc dữ liệu tức thì theo thời gian thực trên bộ nhớ.
  - Bố cục thanh tìm kiếm dạng Wrap tự co giãn: Không bao giờ bị đè giao diện hoặc che khuất trên màn hình độ phân giải thấp.
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


---

# 05 - HƯỚNG DẪN: TRỢ LÝ AI · SQL PARTNER

## 📌 1. Mục đích chức năng
**Trợ lý AI · SQL Partner** là chuyên gia AI ảo am hiểu ngôn ngữ SQL và cấu trúc dữ liệu bệnh viện (HIS/LIS/RIS), đóng vai trò như một người bạn đồng hành hỗ trợ:
- Chuyển đổi yêu cầu nghiệp vụ y tế bằng tiếng Việt thành câu lệnh SQL chuẩn xác.
- Tự động đọc hiểu ngữ cảnh Schema và cấu trúc cột của bảng đang mở.
- Giải thích các câu truy vấn phức tạp (nhiều JOIN, Subquery).
- Gợi ý tối ưu hóa hiệu năng câu lệnh (tận dụng Index, tránh Full Table Scan).
- Hướng dẫn sửa các lỗi cú pháp khi thực thi.

---

## ⚙️ 2. Cấu hình kết nối AI (Các nhà cung cấp hỗ trợ)
Bạn có thể thiết lập AI tại nút **`⚙ Cấu hình AI`** trên thanh công cụ của **Trình soạn SQL**, **Trợ lý tra lỗi**, hoặc trực tiếp tại thanh cấu hình phía trên của **Trợ lý AI · SQL Partner**.

### A. Nhóm KHÔNG CẦN API KEY (Dùng ngay miễn phí)
| Nhà cung cấp | Loại | Endpoint mặc định | Model mặc định | Ghi chú sử dụng |
|---|---|---|---|---|
| **⚡ Chuyên gia SQL Nội bộ** | Offline tích hợp sẵn | `local://offline-sql-expert` | `quangln-sql-expert-v2` | Chạy 100% cục bộ trên máy, bảo mật tuyệt đối dữ liệu HIS, không cần Internet. |
| **🌐 Pollinations AI · GPT-OSS 20B** | Cloud miễn phí | `https://text.pollinations.ai/openai` | `openai` | Gọi AI trên Cloud miễn phí hoàn toàn, không cần đăng ký tài khoản hay API Key (chỉ cần có Internet). |
| **🦙 Ollama** | Local / Offline | `http://localhost:11434/v1/chat/completions` | `qwen2.5-coder:7b` | Cài đặt Ollama trên máy và chạy lệnh `ollama pull qwen2.5-coder:7b` để suy luận SQL cục bộ. |
| **🖥️ LM Studio** | Local / Offline | `http://localhost:1234/v1/chat/completions` | `local-model` | Mở LM Studio, tải model bất kỳ và bật **Local Server** tại cổng `1234`. |
| **⚡ Jan AI** | Local / Offline | `http://localhost:1337/v1/chat/completions` | `llama3.2` | Mở Jan AI và bật **Local API Server** tại cổng `1337`. |
| **🚀 llama.cpp / LocalAI** | Local / Offline | `http://localhost:8080/v1/chat/completions` | `default` | Dành cho máy chủ `llama-server` hoặc LocalAI chạy ở cổng `8080`. |

### B. Nhóm CLOUD CẦN API KEY (Độ chính xác cao / Tốc độ cao)
| Nhà cung cấp | Endpoint mặc định | Model mặc định | Ghi chú |
|---|---|---|---|
| **Google Gemini (OpenAI compat)** | `https://generativelanguage.googleapis.com/v1beta/openai/chat/completions` | `gemini-1.5-flash` | Có gói miễn phí (lấy Key tại Google AI Studio). |
| **Groq (Tốc độ cực nhanh)** | `https://api.groq.com/openai/v1/chat/completions` | `llama-3.3-70b-versatile` | Có gói miễn phí tốc độ rất nhanh (lấy Key tại Groq Console). |
| **DeepSeek** | `https://api.deepseek.com/v1/chat/completions` | `deepseek-chat` | Chi phí rất thấp, viết và tối ưu SQL tốt. |
| **OpenAI (ChatGPT)** | `https://api.openai.com/v1/chat/completions` | `gpt-4o-mini` | Hỗ trợ các dòng GPT-4o / GPT-4o-mini của OpenAI. |
| **Tùy biến...** | *(Tự nhập)* | *(Tự nhập)* | Hỗ trợ mọi gateway chuẩn OpenAI (OpenRouter, vLLM, Azure OpenAI, server nội bộ bệnh viện). |

> **Bảo mật API Key:** API Key chỉ được lưu tạm trong **bộ nhớ RAM của phiên làm việc hiện tại**, không lưu xuống ổ đĩa và không ghi vào file log hệ thống. Khi chọn các nhà cung cấp nhóm **Không cần Key**, bạn có thể để trống ô API Key và bấm **`Lưu cấu hình`** ngay.

---

## 💬 3. Các tính năng chính của SQL Partner

### 3.1. Tự động đọc ngữ cảnh CSDL (Context-Aware)
- AI không sinh câu lệnh bừa bãi hay bị ảo giác (hallucination):
- Hệ thống tự động trích xuất thông tin Schema hiện tại, danh sách bảng và các cột của bảng đang làm việc để gửi kèm lời nhắc hệ thống (System Prompt) cho AI.
- Do đó, câu lệnh SQL do AI sinh ra luôn sử dụng **đúng tên cột thật** trong CSDL của bạn (ví dụ: `TREATMENT_CODE`, `PATIENT_ID`, `IN_TIME`...).

### 3.2. Sinh câu lệnh từ tiếng Việt tự nhiên
Ví dụ bạn nhập vào khung chat:
> *"Lấy danh sách các bệnh nhân điều trị nội trú trong tháng 11/2026, sắp xếp theo thời gian vào viện mới nhất"*

AI sẽ lập tức phản hồi câu lệnh Oracle/Postgres tối ưu:
```sql
SELECT 
    t.ID,
    t.TREATMENT_CODE,
    t.IN_TIME,
    t.CLINICAL_IN_TIME,
    p.VIR_PATIENT_NAME,
    p.DOB,
    p.GENDER_NAME
FROM HIS_RS.HIS_TREATMENT t
JOIN HIS_RS.HIS_PATIENT p ON t.PATIENT_ID = p.ID
WHERE t.IS_DELETE = 0
  AND t.IN_TIME >= 20261101000000 
  AND t.IN_TIME <= 20261130235959
  AND t.TDL_TREATMENT_TYPE_ID = 3 -- Điều trị nội trú
ORDER BY t.IN_TIME DESC;
```
Kèm theo nút **`📋 Sao chép`** hoặc **`Chuyển sang Trình soạn SQL`**.

### 3.3. Giải thích câu truy vấn phức tạp
- Khi bạn gặp một câu SQL báo cáo viện phí hàng trăm dòng khó hiểu: dán vào khung chat và yêu cầu: *"Hãy giải thích ý nghĩa câu lệnh này và các bảng tham gia"*.
- AI sẽ phân tích từng khối logic, từng mệnh đề JOIN và các điều kiện lọc một cách tường minh, dễ hiểu.

### 3.4. Tối ưu câu lệnh & Đề xuất Index
- Hỏi AI: *"Làm thế nào để câu lệnh này chạy nhanh hơn trên Oracle khi bảng có hàng triệu dòng?"*
- AI sẽ chỉ ra các chỗ gây thắt cổ chai (Bottleneck) như việc dùng hàm trên cột ở mệnh đề WHERE làm mất Index, hoặc gợi ý Index kết hợp (Composite Index).

---

## 📝 4. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Hoàn thiện tài liệu Trợ lý AI và hướng dẫn kết nối API Gemini/OpenAI.


---

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


---

# 07 - HƯỚNG DẪN: QUẢN LÝ API (API MANAGER)

## 📌 1. Mục đích chức năng
Chức năng **Quản lý API** là công cụ kiểm thử và tương tác trực tiếp với các dịch vụ mạng (RESTful Web APIs) trong hệ sinh thái y tế số của bệnh viện:
- Cổng giám định BHYT.
- Cổng đơn thuốc quốc gia.
- API kết nối hệ thống xét nghiệm (LIS) và chẩn đoán hình ảnh (RIS/PACS).
- Cổng thanh toán viện phí trực tuyến (QR Code, POS).
- Các API nội bộ đồng bộ dữ liệu giữa HIS và ứng dụng di động bệnh nhân.

---

## 🛠️ 2. Các bước gửi yêu cầu kiểm thử API
1. Chọn phương thức HTTP (Method): **`GET`**, **`POST`**, **`PUT`**, **`DELETE`**...
2. Nhập đường dẫn **Endpoint URL**: Ví dụ `https://api.benhvien.vn/v1/patients/12345`.
3. Cấu hình **Headers**:
   - Thêm các tiêu đề xác thực như `Authorization: Bearer <token>`, `Content-Type: application/json`...
4. Cấu hình **Nội dung yêu cầu (Request Body)**:
   - Nhập payload JSON đối với các phương thức POST / PUT.
5. Bấm nút **`Gửi yêu cầu (Send)`**.

---

## 📥 3. Phân tích kết quả phản hồi (Response)
Sau khi máy chủ phản hồi, màn hình sẽ hiển thị:
- **Mã trạng thái HTTP**: `200 OK`, `201 Created`, `400 Bad Request`, `401 Unauthorized`, `500 Server Error`... kèm mã màu trực quan.
- **Thời gian phản hồi (Response Time)**: Giúp đánh giá độ trễ đường truyền API của bệnh viện.
- **Headers phản hồi**: Thông tin định dạng, máy chủ, token phiên.
- **Nội dung phản hồi (Response Body)**: Tự động định dạng JSON rõ ràng (format & highlight cú pháp) giúp dễ dàng kiểm tra các trường dữ liệu kết quả.

---

## 📝 4. Nhật ký thay đổi tài liệu
- **v1.0.0 (14/11/2026)**: Xuất bản tài liệu Quản lý API và kiểm thử kết nối REST y tế.


---

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


---

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
- **Phiên bản**: `V2026.11.20`
- **Bản quyền**: `Copyright Ⓒ by Lương Ngọc Quảng`
- **Nền tảng**: `.NET 10.0 · Windows Desktop x64`
- **Kiến trúc**: `Clean Architecture + WPF Modern UI`

---

## ⌨️ 6. Bảng tổng hợp phím tắt nhanh (Shortcut Keys)

| Phím tắt | Chức năng | Vị trí áp dụng |
| :---: | :--- | :--- |
| **`Ctrl + Enter`** | **Thực thi thông minh câu lệnh tại con trỏ** (hoặc đoạn đang bôi đen) | Trình soạn SQL |
| **`F5`** | **Thực thi toàn bộ script SQL** trong tab hiện tại | Trình soạn SQL |
| **`Ctrl + Space`** | **Gợi ý thông minh (IntelliSense)** bảng theo Schema / chỉ cột của bảng sau `WHERE` | Trình soạn SQL |
| **`Ctrl + F`** / **`Ctrl + H`** | Mở thanh công cụ **Tìm kiếm** / **Tìm kiếm & Thay thế** (`F3` / `Shift+F3` điều hướng) | Trình soạn SQL |
| **`Ctrl + /`** | **Bật / Tắt chú thích dòng** (`--`) | Trình soạn SQL |
| **`Ctrl + D`** / **`Ctrl + Shift + K`** | **Nhân đôi dòng hiện tại** / **Xóa dòng hiện tại** | Trình soạn SQL |
| **`Ctrl + Shift + U`** / **`L`** | Chuyển đoạn chọn thành **CHỮ IN HOA** / **chữ in thường** | Trình soạn SQL |
| **`Ctrl + Cuộn chuột`** | **Phóng to / Thu nhỏ cỡ chữ** trình soạn thảo | Trình soạn SQL |
| **`Ctrl + S`** | **Lưu nội dung SQL** ra tệp `.sql` | Trình soạn SQL |
| **`Double-Click`** | **Đổi tên tab tại chỗ** (trên tab SQL) / **Mở nhanh bảng** (trên cây Explorer) | Toàn hệ thống |
| **`Enter`** / **`Shift + Enter`** | **Gửi câu hỏi tra cứu** / **Xuống dòng trong ô nhập liệu** | Trợ lý tra lỗi |
| **`Esc`** | Đóng thanh tìm kiếm / Đóng popup gợi ý / Hủy đổi tên tab | Toàn hệ thống |

---

## 📝 7. Nhật ký thay đổi tài liệu
- **V2026.11.20 (20/11/2026)**: Đồng bộ toàn bộ tài liệu `.md` và `.html` cho tất cả 11 phân hệ, bổ sung hướng dẫn chi tiết **Thiết kế truy vấn trực quan**, **Chuyên gia SQL Offline**, **Audit Log 3 Tab (Visual Diff & Rollback SQL)**, **IntelliSense lọc cột sau `WHERE`**, và gói chạy độc lập **Self-Contained `win-x64`**.


---

# 10 - HƯỚNG DẪN: TRỢ LÝ TRA LỖI & CẨM NANG TRI THỨC (RAG SKILL ASSISTANT)

## 📌 1. Mục đích chức năng
Chức năng **Trợ lý tra lỗi (RAG Skill Assistant)** là trung tâm hỗ trợ kỹ thuật và tra cứu sự cố thông minh tích hợp sẵn trong ứng dụng **QUANGLN SQL**:
- Cho phép người dùng nạp các tài liệu nghiệp vụ, sổ tay lỗi, tệp Word (`.docx`), tệp SQL (`.sql`), nhật ký log (`.log`), cẩm nang kỹ thuật (`.txt`, `.md`, `.json`, `.csv`) trực tiếp từ máy tính.
- Tự động lập chỉ mục và **quét sâu toàn bộ kho tài liệu** để tìm ra chính xác nguyên nhân và giải pháp cho mọi sự cố SQL hoặc quy trình nghiệp vụ HIS.
- Tương tác tự nhiên qua giao diện Chat thân thiện, thông minh, hỗ trợ trích xuất câu lệnh SQL để 1-click đưa ngay vào Trình soạn SQL thực thi.

---

## 🧭 2. Bố cục làm việc trực quan
Màn hình được chia làm 2 khu vực chính:
1. **Cột trái - Quản lý Kho tài liệu & Lịch sử câu hỏi**:
   - **Tab `📚 Tài liệu`**:
     - Nút **`➕ Nạp tệp...`**: Chọn một hoặc nhiều tệp từ máy tính (.docx, .sql, .txt, .md, .log...).
     - Nút **`📁 Nạp thư mục...`**: Quét và nạp toàn bộ thư mục tài liệu kỹ năng.
     - Nút **`Bật / Tắt`** (Huy hiệu vector xanh/xám): Bật hoặc tắt tài liệu khi quét tìm kiếm.
     - Nút **`Xóa`**: Xóa tài liệu khỏi kho tri thức.
     - Ô tìm kiếm tài liệu nhanh theo tên tệp.
   - **Tab `🕒 Lịch sử hỏi`**:
     - Tự động lưu mọi câu hỏi kèm mốc thời gian chi tiết.
     - Bấm vào câu hỏi để điền lại vào ô nhập, hoặc bấm **`▶`** để hỏi lại ngay lập tức.
     - Nút **`🗑 Xóa hết`** để dọn dẹp lịch sử khi cần.
2. **Cột phải - Khung trò chuyện & Tra cứu giải pháp**:
   - Dòng chỉ báo trạng thái quét: `🔎 Tự động quét trong N tài liệu kỹ năng đang bật` kèm nút truy cập nhanh lịch sử hỏi.
   - Luồng hội thoại bong bóng chat rõ ràng giữa người dùng và trợ lý.
   - Khung chuyên dụng **"CÂU LỆNH SQL KHẮC PHỤC / KIỂM TRA ĐỀ XUẤT"** hiển thị mã SQL sạch.
   - Nút **`📥 Chèn vào Trình soạn SQL`**: 1-click chuyển thẳng mã lệnh sang Workspace để chạy.
   - Nút **`📋 Sao chép SQL`** và **`📋 Sao chép toàn bộ phản hồi`**.
   - Ô nhập đa dòng hỗ trợ **`Enter`** để gửi và **`Shift + Enter`** để xuống dòng.

---

## 🔍 3. Cơ chế quét tệp thông minh & Loại bỏ nhiễu
- **Đọc sâu tệp Word (.docx)**: Tự động bóc tách từng đoạn văn và bảng biểu bảo toàn cấu trúc dòng.
- **Tách độc lập từng mục câu lệnh**: Với các tài liệu chứa danh mục mẹo/câu lệnh đánh số liên tiếp (`1. `, `2. `, `102. `), hệ thống tự động bóc tách từng số mục độc lập, tránh hiện tượng đổ dồn hàng loạt câu lệnh gây rối mắt.
- **Khớp chính xác & Chống nhiễu**: Khi tìm kiếm (ví dụ: *"đổi thu ngân"*), hệ thống tìm chính xác mục số `102. Đổi phòng thu ngân`, tự động loại bỏ các câu lệnh không liên quan.
- **Phân chia các trường hợp rõ ràng**:
  - Nếu có 1 giải pháp chính xác: Trả về trực tiếp câu lệnh và cách khắc phục.
  - Nếu có nhiều trường hợp cùng liên quan: Trợ lý phân tách thành các mục rõ ràng `Trường hợp 1`, `Trường hợp 2` kèm tên tài liệu nguồn.

---

## 💬 4. Giao tiếp thân thiện hàng ngày
- Trợ lý mở đầu và giao tiếp với giọng điệu tự nhiên, gần gũi, xưng hô *"mình - bạn"* như một người đồng nghiệp hỗ trợ kỹ thuật tận tình.
- Tự động nhận diện các câu giao tiếp hàng ngày (*"chào bạn"*, *"chào buổi sáng"*, *"cảm ơn"*, *"bạn là ai"*, *"hôm nay thế nào"*...) để phản hồi vui vẻ, ấm áp thay vì báo lỗi máy móc.

---

## ⚙️ 5. Chế độ Offline cục bộ & Online AI
- **Chế độ Offline cục bộ (Mặc định)**: Hoạt động 100% trên máy tính cá nhân, tuyệt đối an toàn và bảo mật dữ liệu y tế, không cần Internet.
- **Chế độ Online AI**: Bấm nút **`⚙ Cấu hình AI`** để kết nối các mô hình ngôn ngữ lớn (Gemini, OpenAI GPT-4o, DeepSeek, Ollama) giúp suy luận nâng cao và tối ưu câu lệnh.

---

## 📝 6. Nhật ký cập nhật tính năng
- **V2026.11.20**:
  - Ra mắt chính thức tính năng **Trợ lý tra lỗi (RAG Skill Assistant)**.
  - Tích hợp nạp tệp Word `.docx` bảo toàn cấu trúc đoạn văn bản.
  - Nâng cấp bộ tách mẹo/câu lệnh đánh số thông minh, loại bỏ hoàn toàn hiện tượng hiển thị một loạt câu lệnh gây rối mắt.
  - Cập nhật huy hiệu trạng thái Bật/Tắt dạng vector sắc nét, khắc phục triệt để lỗi hiển thị ô vuông emoji trên Windows.
  - Tích hợp tab **Lịch sử hỏi** tự động ghi nhớ và chạy lại nhanh các câu hỏi đã tra cứu.


