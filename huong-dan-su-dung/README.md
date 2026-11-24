# 📚 SỔ TAY HƯỚNG DẪN SỬ DỤNG - TOOL SQL CHO HIS
> **Phiên bản tài liệu:** v1.0.0  
> **Dành cho:** Kỹ sư CNTT Bệnh viện, Quản trị viên CSDL y tế (DBA), Chuyên viên triển khai hệ thống HIS.

---

## 🎯 Giới thiệu phần mềm
**Tool SQL CHO HIS** là giải pháp phần mềm chuyên dụng hỗ trợ kết nối, truy vấn, khám phá dữ liệu, can thiệp dữ liệu có kiểm soát an toàn và tích hợp trợ lý AI thông minh dành riêng cho các hệ thống thông tin bệnh viện (HIS/LIS/RIS-PACS).

Hệ thống được thiết kế với tiêu chuẩn khắt khe về **an toàn dữ liệu y tế**, chống thao tác nhầm, phân quyền truy cập chặt chẽ và ghi nhật ký kiểm toán (Audit Log) đầy đủ.

---

## 🗂️ Danh mục hướng dẫn từng chức năng

| STT | Tài liệu hướng dẫn | Chức năng chi tiết |
| :---: | :--- | :--- |
| **01** | [01-TONG-QUAN.md](./01-TONG-QUAN.md) | Màn hình Tổng quan, menu co giãn (Collapsible Sidebar), trạng thái kết nối toàn cục |
| **02** | [02-KET-NOI-CSDL.md](./02-KET-NOI-CSDL.md) | Quản lý kết nối (Oracle, PostgreSQL, MySQL, SQL Server, SQLite), kiểm tra kết nối, phân quyền 3 cấp |
| **03** | [03-TRINH-SOAN-SQL.md](./03-TRINH-SOAN-SQL.md) | Trình soạn SQL đa tab, F5, chặn truy vấn chưa kết nối, DML đa năng (nhiều dòng), Transaction, Tham số |
| **04** | [04-KHAM-PHA-DU-LIEU.md](./04-KHAM-PHA-DU-LIEU.md) | Khám phá dữ liệu bảng/view, 4 tab nghiệp vụ, sửa ô trực tiếp, phân trang 50–1000 dòng, xuất Excel |
| **05** | [05-TRO-LY-AI-SQL-PARTNER.md](./05-TRO-LY-AI-SQL-PARTNER.md) | Trợ lý AI: cấu hình API (Gemini/OpenAI), sinh SQL từ tiếng Việt, giải thích & tối ưu câu lệnh |
| **06** | [06-LICH-SU-TRUY-VAN.md](./06-LICH-SU-TRUY-VAN.md) | Tra cứu lịch sử chạy SQL, thời gian thực thi, tìm kiếm lại câu lệnh cũ |
| **07** | [07-QUAN-LY-API.md](./07-QUAN-LY-API.md) | Kiểm thử kết nối RESTful API, gửi Header/Payload, phân tích phản hồi JSON |
| **08** | [08-NHAT-KY-KIEM-TOAN.md](./08-NHAT-KY-KIEM-TOAN.md) | Audit Log: truy vết can thiệp CSDL (INSERT/UPDATE/DELETE), ghi nhận IP máy trạm trạm, người thực hiện |
| **09** | [09-CAI-DAT-HE-THONG.md](./09-CAI-DAT-HE-THONG.md) | Cài đặt giao diện Sáng/Tối, cấu hình phân trang mặc định, dọn dẹp bộ nhớ đệm |
| **10** | [10-TRO-LY-TRA-LOI.md](./10-TRO-LY-TRA-LOI.md) | Trợ lý tra lỗi & Cẩm nang Tri thức (RAG Skill): nạp file Word (.docx), SQL, txt từ máy, quét tìm câu lệnh chính xác, lưu lịch sử hỏi |

---

## 🔄 Quy trình cập nhật tài liệu khi có thay đổi trong App
Để tài liệu luôn phản ánh chính xác 100% tính năng của phần mềm:
1. **Khi thêm mới hoặc cải tiến chức năng**: Mở tệp markdown tương ứng trong thư mục này và cập nhật thêm mục mới.
2. **Khi thay đổi giao diện hoặc thao tác**: Chụp ảnh hoặc mô tả lại các bước bấm nút, phím tắt hoặc cấu trúc menu mới.
3. **Ghi nhật ký thay đổi (Changelog)**: Cập nhật mục *Nhật ký thay đổi tài liệu* ở cuối tệp tương ứng kèm ngày giờ và phiên bản.
