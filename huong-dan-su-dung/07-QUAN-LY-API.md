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
