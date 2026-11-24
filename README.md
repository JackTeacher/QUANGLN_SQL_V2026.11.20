# Tool SQL v1.0.0

Tool SQL v1.0.0 của Lương Ngọc Quảng là ứng dụng Windows dùng để quản trị cơ sở dữ liệu, được xây dựng bằng .NET 10 và WPF. Hỗ trợ kết nối, metadata, Explorer phân trang và CRUD một bảng theo lô trên Oracle, SQL Server, PostgreSQL, MySQL và SQLite; SQL Workspace có nhiều tab, mở/lưu tệp SQL, script nhiều câu, bind tham số, transaction thủ công, kết quả Excel/CSV và Query History. Có Audit Log CRUD DPAPI, API request playground, Visual Query Builder lưu/mở sơ đồ JSON, trợ lý SQL cấu hình endpoint và cài đặt theme/thư mục xuất. Không có module Báo cáo riêng; kết quả được truy vấn/xuất ngay trong SQL Workspace. Khả năng tương thích máy chủ ngoài cần được xác minh; quản lý người dùng/RBAC, audit tập trung, API collections/OAuth và một số mô-đun quản trị khác đang phát triển.

## Tài liệu hướng dẫn sử dụng

Xem toàn bộ tài liệu hướng dẫn chi tiết từng chức năng tại thư mục [huong-dan-su-dung/](huong-dan-su-dung/README.md).

## Tình trạng hiện tại


Xem [PROJECT_STATUS.md](PROJECT_STATUS.md) để biết tình trạng chi tiết và [docs/architecture.md](docs/architecture.md) để xem các quyết định kiến trúc.

Xem [CHUC_NANG.md](CHUC_NANG.md) để tra cứu danh sách chức năng đã triển khai, đang hỗ trợ một phần và chưa triển khai.

Định hướng thao tác một/nhiều bản ghi và nhật ký truy vấn có IP được mô tả trong [docs/data-management-and-audit.md](docs/data-management-and-audit.md).

## Yêu cầu

- Windows 10/11 x64
- .NET 10 SDK (phiên bản 10.0.100 trở lên, bao gồm các bản cập nhật định kỳ)
- Visual Studio 2022 có bộ công cụ phát triển .NET Desktop, hoặc .NET CLI cùng bộ công cụ đích Windows Desktop

## Biên dịch

```powershell
dotnet restore .\DBStudio.sln
dotnet build .\DBStudio.sln -c Release --no-restore
```

Kho mã cố định phiên bản .NET SDK bằng `global.json`. Chỉ ghi lệnh biên dịch và kiểm thử vào [PROJECT_STATUS.md](PROJECT_STATUS.md) sau khi đã chạy thành công.

## Chạy trên Windows

Sau khi cài .NET 10 SDK, chạy các lệnh sau tại thư mục gốc của kho mã:

```powershell
dotnet restore .\DBStudio.sln
dotnet run --project .\src\DBStudio.App\DBStudio.App.csproj -c Release
```

Xem [docs/installation.md](docs/installation.md) để biết cách chạy trực tiếp tệp ứng dụng và thông tin triển khai.

Hướng dẫn thao tác hiện tại: [docs/user-guide.md](docs/user-guide.md).

## Cấu trúc dự án

```text
src/DBStudio.App/             Giao diện WPF và điểm khởi chạy ứng dụng
src/DBStudio.Application/     Các ca sử dụng và hợp đồng của ứng dụng
src/DBStudio.Domain/          Thực thể và quy tắc nghiệp vụ
src/DBStudio.Infrastructure/  Cơ sở dữ liệu, bảo mật, lưu trữ và tích hợp
src/DBStudio.Shared/          Thành phần dùng chung
tests/                        Các dự án kiểm thử đơn vị và kiểm thử tích hợp
 docs/                        Tài liệu kiến trúc, bảo mật, trình điều khiển và vận hành
```


