# 📋 BIÊN BẢN BÀN GIAO & TÀI LIỆU TRẠNG THÁI DỰ ÁN (PROJECT HANDOVER)
> **Dự án:** QUANGLN SQL (Tool SQL cho HIS)  
> **Tác giả:** Lương Ngọc Quảng  
> **Phiên bản hiện tại:** `V2026.11.20`  
> **Thời điểm cập nhật:** 20/11/2026  
> **Mục đích:** Lưu trữ toàn bộ hiện trạng, kiến trúc, quy trình vận hành và thông tin dự án để bất kỳ kỹ sư hoặc tài khoản AI Antigravity nào khi tiếp nhận dự án đều có thể tiếp tục phát triển ngay lập tức mà không bị gián đoạn.

---

## 🏛️ 1. Tổng quan dự án & Ngăn xếp công nghệ (Tech Stack)
- **Tên thương hiệu ứng dụng:** `QUANGLN SQL` (Tệp thực thi: `ToolSQL.exe`)
- **Nền tảng:** `.NET 10.0` (C# 13, Windows Desktop x64, WPF)
- **Kiến trúc phần mềm:** Clean Architecture kết hợp mô hình MVVM (Model-View-ViewModel) hiện đại.
- **Thư viện chính:**
  - `CommunityToolkit.Mvvm`: Điều hướng, ViewModel, RelayCommand và ObservableProperty.
  - `Microsoft.Extensions.Hosting` & `Microsoft.Extensions.DependencyInjection`: Dependency Injection (DI) xuyên suốt các tầng.
  - `Serilog` & `Serilog.Sinks.File`: Ghi nhật ký lỗi, vận hành xoay vòng tự động (rolling logs).
  - `System.Security.Cryptography.ProtectedData`: Mã hóa an toàn mật khẩu và dữ liệu kiểm toán bằng **Windows DPAPI (CurrentUser)**.
  - `DocumentFormat.OpenXml`: Phân tích và đọc sâu dữ liệu cấu trúc bảng và văn bản từ tệp Word `.docx` cho Trợ lý tra lỗi RAG.
  - **Bộ Driver CSDL ADO.NET Native:**
    - `Oracle.ManagedDataAccess.Core` (Hỗ trợ Oracle 11g, 12c, 19c, 21c, 23ai dùng trong HIS_RS).
    - `Npgsql` (PostgreSQL / EMR / PACS).
    - `Microsoft.Data.SqlClient` (Microsoft SQL Server).
    - `MySqlConnector` (MySQL / MariaDB).
    - `Microsoft.Data.Sqlite` (SQLite cục bộ).

---

## 📂 2. Cấu trúc thư mục giải pháp (Solution Structure)
```text
TOOL SQL CHO HIS/
├── DBStudio.sln                           # Solution chính của dự án (.NET 10)
├── Directory.Build.props                  # Cấu hình compiler & metadata toàn cục
├── Directory.Packages.props               # Quản lý phiên bản NuGet tập trung (CPVM)
├── HUONG_DAN_SU_DUNG.md                   # Sổ tay hướng dẫn sử dụng chi tiết (tiếng Việt)
├── HUONG_DAN_SU_DUNG.html                 # Sổ tay giao diện web HTML tương tác
├── PROJECT_STATUS.md                      # Lịch sử và trạng thái chi tiết của dự án
├── HANDOVER.md                            # Tài liệu bàn giao này
│
├── src/
│   ├── DBStudio.Domain/                   # Lớp nghiệp vụ thuần túy: Thực thể, Enums, Value Objects
│   │   ├── Entities/                      # ConnectionProfile, KnowledgeDocument, AuditEvent...
│   │   └── Enums/                         # DatabaseProvider, ConnectionAccessMode...
│   │
│   ├── DBStudio.Application/              # Lớp ứng dụng & Điều phối:
│   │   ├── Connections/                   # Quản lý hồ sơ kết nối, kiểm tra tính hợp lệ
│   │   ├── Database/                      # Interface IDatabaseDriver, ISqlDialect, Metadata
│   │   ├── Knowledge/                     # Bộ bóc tách tài liệu Word .docx, PDF, Text cho RAG
│   │   └── Reports/                       # Dịch vụ xuất CSV, XLSX và cấu hình AI
│   │
│   ├── DBStudio.Infrastructure/           # Lớp hạ tầng kỹ thuật:
│   │   ├── Database/                      # Triển khai Driver Native cho Oracle, Postgres, MSSQL, MySQL, SQLite
│   │   ├── Storage/                       # Lưu trữ hồ sơ JSON, Query History và Audit Log mã hóa DPAPI
│   │   └── Reports/                       # Xuất báo cáo Excel/CSV
│   │
│   ├── DBStudio.Shared/                   # Thư viện tiện ích dùng chung
│   │
│   └── DBStudio.App/                      # Ứng dụng Desktop WPF (Giao diện chính):
│       ├── Controls/                      # SqlSyntaxTextBox (Trình soạn thảo SQL chuyên nghiệp)
│       ├── Services/                      # WpfThemeService, SqlCompletionProvider, SqlFormatter
│       ├── Themes/                        # DesignSystem.xaml (Bảng màu High-Contrast Sáng/Tối)
│       ├── ViewModels/                    # Các ViewModel MVVM chuẩn (SqlEditorTab, SqlEditorViewModel, ...)
│       ├── Views/                         # Các màn hình chức năng XAML
│       └── Resources/                     # Icon ToolSQL.ico, ToolSQL-transparent.png
│
├── tests/
│   ├── DBStudio.UnitTests/                # 34 bài kiểm thử đơn vị (100% Passed)
│   └── DBStudio.IntegrationTests/         # Kiểm thử tích hợp driver & DPAPI
│
└── publish/
    ├── QUANGLN_SQL/                       # Thư mục phát hành ứng dụng độc lập (ToolSQL.exe)
    └── QUANGLN_SQL_V2026.11.20.zip       # Gói nén cài đặt hoàn chỉnh (~93 MB)
```

---

## ⚡ 3. Các tính năng cốt lõi đã hoàn thiện & đi vào sản xuất

### 3.1. Trình soạn SQL chuyên sâu (SQL Editor Workspace - Nâng cấp V2026.11.20)
- **Thước đánh số dòng chuyên dụng (Line Numbers Gutter):** Tự động co giãn theo số chữ số, đồng bộ 100% với cuộn chuột, nhấp vào số dòng để nhảy con trỏ tới dòng đó.
- **Thực thi câu lệnh thông minh (`Ctrl + Enter` & Nút `▶ Chạy câu hiện tại`):** Tự động bóc tách và chỉ thực thi riêng câu lệnh mà con trỏ chuột đang đứng (hoặc đoạn bôi đen) mà không ảnh hưởng tới các câu lệnh khác trong cùng tab.
- **Thanh công cụ Tìm kiếm & Thay thế nổi (`Ctrl + F` / `Ctrl + H`):** Hỗ trợ `F3` (kế tiếp), `Shift + F3` (lùi trước đó), phân biệt hoa thường `Aa`, đếm tổng số vị trí trùng khớp, thay thế từng từ hoặc thay thế toàn bộ.
- **Thanh trạng thái con trỏ (Status Bar):** Báo cáo thời gian thực `Dòng X, Cột Y`, `Tổng cộng: N dòng`, `Đã chọn: Z ký tự`, và cụm nút phóng to/thu nhỏ cỡ chữ (`A- / A+ / ↺` hoặc `Ctrl + Cuộn chuột`).
- **Quản lý Tab nâng cao:** Hỗ trợ nhấp đúp vào tiêu đề tab để đổi tên trực tiếp tại chỗ; Menu chuột phải đầy đủ thao tác: Nhân đôi tab, Sao chép toàn bộ SQL, Lưu tab, Đóng các tab khác, Đóng các tab bên phải, Đóng tất cả tab.
- **Bộ phím tắt chuẩn IDE:** `Ctrl + /` (chú thích `--`), `Ctrl + D` (nhân đôi dòng), `Ctrl + Shift + K` (xóa dòng), `Ctrl + Shift + U` (chữ HOA), `Ctrl + Shift + L` (chữ thường), `Ctrl + Space` (gợi ý IntelliSense).
- **Kho mẫu SQL 8 nhóm:** Tích hợp hơn 40 mẫu câu lệnh chuẩn hóa từ cơ bản đến chuyên ngành Y tế & HIS (`HIS_PATIENT`, `HIS_SERE_SERV`, `HIS_EXP_MEST`, định dạng ngày giờ `yyyyMMddHHmmss`, cờ hiệu lực `IS_ACTIVE = 1 / IS_DELETE = 0`).
- **Quản lý giao dịch an toàn:** Menu Giao dịch với 3 chế độ `Bắt đầu Transaction`, `COMMIT` và `ROLLBACK`.

### 3.2. Trợ lý tra lỗi & Cẩm nang Tri thức (RAG Skill Assistant)
- **Nạp tài liệu Offline an toàn:** Hỗ trợ nạp các tệp `.docx`, `.pdf`, `.md`, `.txt`, `.sql`, `.log` trực tiếp từ máy trạm, hoạt động độc lập không cần kết nối Internet.
- **Bộ bóc tách tệp Word `.docx` chuyên sâu:** Đọc bảo toàn từng đoạn văn và bảng biểu.
- **Chống nhiễu & Bóc tách câu lệnh thông minh:** Tự động phát hiện các danh mục đánh số thứ tự (`1. `, `2. `, `102. `), tách biệt độc lập từng giải pháp, tránh tình trạng hiển thị danh sách tràn lan gây rối mắt.
- **Lịch sử hỏi:** Tab ghi nhớ câu hỏi tự động, hỗ trợ chạy lại nhanh chỉ với 1 click.
- **Chuyển mã SQL nhanh:** Nút `📥 Chèn vào Trình soạn SQL` đưa thẳng giải pháp sang Workspace để chạy.
- **Giao tiếp thân thiện:** Giọng điệu ấm áp, xưng hô *"mình - bạn"*, nhận diện chào hỏi hàng ngày.

### 3.3. Quản lý Kết nối & Bảo mật 3 cấp độ
- **Phân quyền 3 cấp (Access Modes):** *Chỉ đọc (Read-Only)*, *Đọc và ghi (Read-Write)*, *Quản trị (Administrative)*.
- **Bảo mật Windows DPAPI:** Mọi mật khẩu CSDL đều được mã hóa bằng DPAPI theo tài khoản Windows, tuyệt đối không lưu plain-text.
- **Hỗ trợ 5 hệ quản trị:** Oracle, PostgreSQL, SQL Server, MySQL/MariaDB, SQLite.

### 3.4. Khám phá Dữ liệu, Lịch sử truy vấn & Kiểm toán
- **Khám phá dữ liệu:** Duyệt cây schema, xem định nghĩa cột, duyệt phân trang, chỉnh sửa dữ liệu có kiểm soát khóa chính.
- **Lịch sử truy vấn:** Lưu vết toàn bộ câu lệnh, thời lượng, số dòng và mã hóa an toàn.
- **Nhật ký kiểm toán (Audit Log):** Ghi nhận snapshot trước/sau của các thao tác can thiệp dữ liệu.

---

## 🛠️ 4. Hướng dẫn Lệnh Biên dịch, Kiểm thử & Đóng gói

Tất cả các lệnh sau được thực thi từ thư mục gốc của giải pháp (`c:\Users\user\Documents\ChatGPT\TOOL SQL CHO HIS`):

### 4.1. Chạy toàn bộ Unit Tests (Đảm bảo 100% Passed)
```powershell
dotnet test .\tests\DBStudio.UnitTests\DBStudio.UnitTests.csproj
```
*(Hiện tại: **34/34** unit tests đều vượt qua thành công).*

### 4.2. Biên dịch bản phát hành Release (Độc lập Self-Contained - Không cần cài .NET 10)
```powershell
dotnet publish .\src\DBStudio.App\DBStudio.App.csproj -c Release -r win-x64 --self-contained true -o .\publish\QUANGLN_SQL /p:PublishReadyToRun=false
```

### 4.3. Đóng gói tệp ZIP hoàn chỉnh
```powershell
Copy-Item -Path HUONG_DAN_SU_DUNG.md, HUONG_DAN_SU_DUNG.html, README.md -Destination publish\QUANGLN_SQL -Force
Compress-Archive -Path publish\QUANGLN_SQL\* -DestinationPath publish\QUANGLN_SQL_V2026.11.20.zip -Force
```

### 4.4. Kiểm tra khởi động nhanh (Smoke Test)
```powershell
$proc = Start-Process -FilePath "publish\QUANGLN_SQL\ToolSQL.exe" -PassThru
Start-Sleep -Seconds 2
Stop-Process -Id $proc.Id -Force
```

---

## 📍 5. Vị trí lưu trữ dữ liệu người dùng (AppData)
Khi ứng dụng vận hành, toàn bộ dữ liệu cấu hình và kho tri thức được lưu trữ an toàn tại:
```text
%LOCALAPPDATA%\DBStudio\
├── connections.json         # Danh sách hồ sơ CSDL (mật khẩu đã mã hóa DPAPI)
├── settings.json            # Cấu hình giao diện (Sáng/Tối, Cỡ chữ, Thư mục xuất)
├── query-history.jsonl      # Lịch sử thực thi SQL (nội dung SQL mã hóa DPAPI)
├── data-audit.jsonl         # Nhật ký kiểm toán thao tác DML (mã hóa DPAPI)
└── knowledge/               # Thư mục lưu tài liệu kỹ năng & sổ tay nghiệp vụ HIS
```
*Ghi chú:* Để mở nhanh thư mục này từ ứng dụng, vào menu **Cài đặt** -> bấm nút **`📂 Mở thư mục AppData`**.

---

## 🔒 6. Cam kết quy tắc thiết kế & Lưu ý cho Agent tiếp theo
1. **Ngôn ngữ giao diện & Tài liệu:** Toàn bộ văn bản hiển thị cho người dùng, nhãn nút, tooltip, hộp thoại và tài liệu phải sử dụng **tiếng Việt có dấu** rõ ràng, chỉn chu.
2. **Quy tắc an toàn CSDL y tế:** Tuyệt đối không bao giờ cho phép thực thi lệnh DML (`UPDATE`, `DELETE`) ở chế độ Chỉ đọc (Read-Only). Mọi thao tác DML phải được khuyến khích chạy trong Transaction an toàn.
3. **Quy chuẩn phiên bản:** Tuân thủ quy tắc đánh số phiên bản theo ngày: `V[Năm].[Tháng].[Ngày]` (Ví dụ: `V2026.11.20`).
4. **Kiểm thử trước khi đóng gói:** Luôn chạy `dotnet test` đạt 100% trước khi thực hiện `dotnet publish` và nén tệp zip.
