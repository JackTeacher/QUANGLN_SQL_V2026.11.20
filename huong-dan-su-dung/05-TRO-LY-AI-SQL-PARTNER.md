# 05 - HƯỚNG DẪN: TRỢ LÝ AI · SQL PARTNER

## 📌 1. Mục đích chức năng
**Trợ lý AI · SQL Partner** là chuyên gia AI ảo am hiểu ngôn ngữ SQL và cấu trúc dữ liệu bệnh viện (HIS/LIS/RIS), đóng vai trò như một người bạn đồng hành hỗ trợ:
- Chuyển đổi yêu cầu nghiệp vụ y tế bằng tiếng Việt thành câu lệnh SQL chuẩn xác.
- Tự động đọc hiểu ngữ cảnh Schema và cấu trúc cột của bảng đang mở.
- Giải thích các câu truy vấn phức tạp (nhiều JOIN, Subquery).
- Gợi ý tối ưu hóa hiệu năng câu lệnh (tận dụng Index, tránh Full Table Scan).
- Hướng dẫn sửa các lỗi cú pháp khi thực thi.

---

## ⚙️ 2. Cấu hình kết nối AI (AI Configuration)
Để sử dụng Trợ lý AI, bạn cần cấu hình API key:
1. Bấm nút **`⚙ Cấu hình AI`** trên thanh công cụ của Trình soạn SQL hoặc trong màn hình Trợ lý AI.
2. Thiết lập các thông số:
   - **Nhà cung cấp (Provider)**: Google Gemini (mặc định khuyến nghị), OpenAI hoặc các dịch vụ tương thích chuẩn OpenAI.
   - **Mã khóa API (API Key)**: Nhập khóa API của bạn (được lưu an toàn).
   - **Model AI**: Ví dụ `gemini-1.5-flash`, `gemini-1.5-pro`, `gpt-4o`...
   - **Endpoint / URL tùy chỉnh** (nếu dùng proxy hoặc AI nội bộ On-Premise của bệnh viện).
3. Bấm **`Kiểm tra & Lưu cấu hình`**.

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
