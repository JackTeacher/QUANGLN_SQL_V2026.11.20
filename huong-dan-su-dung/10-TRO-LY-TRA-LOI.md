# 10 - HƯỚNG DẪN: TRỢ LÝ TRA LỖI & CẨM NANG TRI THỨC (RAG SKILL ASSISTANT)

> **Phiên bản:** V2026.11.15  
> **Dành cho:** Kỹ sư CNTT, Quản trị CSDL bệnh viện, Chuyên viên hỗ trợ vận hành HIS.

---

## 📌 1. Mục đích chức năng
Chức năng **Trợ lý tra lỗi (RAG Skill Assistant)** là hệ thống hỗ trợ kỹ thuật và tra cứu sự cố thông minh tích hợp sẵn trong ứng dụng **QUANGLN SQL**. 
Hệ thống cho phép bạn:
- Nạp các tệp tài liệu nội bộ, sổ tay sự cố, file Word (`.docx`), file kịch bản SQL (`.sql`), nhật ký log (`.log`), cẩm nang nghiệp vụ y tế (`.txt`, `.md`, `.json`, `.csv`) trực tiếp từ máy tính cá nhân.
- Tự động lập chỉ mục và **quét sâu toàn bộ kho tài liệu** để tìm ra chính xác nguyên nhân và giải pháp cho mọi sự cố SQL hoặc quy trình nghiệp vụ HIS.
- Tương tác tự nhiên qua giao diện trò chuyện (Chat) thân thiện, dễ hiểu, có hỗ trợ trích xuất câu lệnh SQL để 1-click đưa ngay vào Trình soạn SQL thực thi.

---

## 🧭 2. Giao diện làm việc tổng quan
Màn hình được chia làm 2 khu vực trực quan:

```
┌───────────────────────────────────────────────┬────────────────────────────────────────────────────────┐
│ CỘT TRÁI: QUẢN LÝ KHO TRI THỨC & LỊCH SỬ       │ CỘT PHẢI: KHUNG TRÒ CHUYỆN & TRA CỨU TƯƠNG TÁC         │
│ ┌──────────────────────┬────────────────────┐ │                                                        │
│ │   📚 Tài liệu (3)    │  🕒 Lịch sử hỏi (N)│ │  👤 Bạn: Đổi thu ngân                                   │
│ └──────────────────────┴────────────────────┘ │                                                        │
│ [➕ Nạp tệp...]       [📁 Nạp thư mục...]     │  🛠️ Trợ lý tra lỗi AI:                                  │
│ 🔍 [Tìm kiếm tài liệu...]                     │  Chào bạn! Mình đã quét các tệp tài liệu và tìm thấy   │
│ ───────────────────────────────────────────── │  đúng câu lệnh bạn cần:                                │
│ • 01_So_Tay_Loi_Oracle_HIS.md  [Bật] [Xóa]   │  ### 🎯 102. Đổi phòng thu ngân                        │
│ • 02_Cam_Nang_Nghiep_Vu_HIS.md [Bật] [Xóa]   │  ```sql                                                │
│ • Câu lệnh .docx               [Bật] [Xóa]   │  update his_transaction set cashier_room_id='61'...    │
│                                               │  ```                                                   │
│                                               │  ┌───────────────────────────────────────────────────┐ │
│                                               │  │ [📥 Chèn vào Trình soạn SQL]  [📋 Sao chép SQL]   │ │
│                                               │  └───────────────────────────────────────────────────┘ │
│                                               │                                                        │
│                                               │  🔎 Tự động quét trong 3 tài liệu đang bật             │
│                                               │  ┌─────────────────────────────────────────┬─────────┐ │
│                                               │  │ Nhập câu hỏi, mã lỗi hoặc yêu cầu...    │ [📎][➤] │ │
│                                               │  └─────────────────────────────────────────┴─────────┘ │
└───────────────────────────────────────────────┴────────────────────────────────────────────────────────┘
```

---

## 📚 3. Quản lý kho tài liệu kỹ năng (Tab "Tài liệu")
Tại cột bên trái, chọn tab **`📚 Tài liệu`**:
1. **Nạp tệp từ máy tính (`➕ Nạp tệp...`)**:
   - Hỗ trợ chọn cùng lúc nhiều tệp văn bản từ máy tính: `.docx` (Word), `.sql`, `.txt`, `.md`, `.log`, `.json`, `.csv`.
   - Đặc biệt hỗ trợ đọc sâu tài liệu Word (`.docx`), tự động bảo toàn từng đoạn văn và bảng biểu.
2. **Nạp toàn bộ thư mục (`📁 Nạp thư mục...`)**:
   - Chọn một thư mục trên máy tính, hệ thống sẽ tự động quét và nạp toàn bộ các tài liệu kỹ thuật có trong thư mục đó vào kho tri thức.
3. **Bật / Tắt tài liệu khi quét tra cứu (`Bật / Tắt`)**:
   - Nút huy hiệu hiển thị trạng thái rõ ràng:
     - **`Bật`** (Xanh lá): Tài liệu đang được đưa vào ngữ cảnh quét.
     - **`Tắt`** (Xám): Tạm thời bỏ qua tài liệu này khi tra cứu để thu hẹp phạm vi tìm kiếm.
4. **Xóa tài liệu (`Xóa`)**:
   - Bấm nút **`Xóa`** màu đỏ để gỡ bỏ tài liệu khỏi kho tri thức khi không còn sử dụng.
5. **Tìm kiếm tài liệu**:
   - Ô tìm kiếm nhanh phía trên giúp bạn lọc nhanh tài liệu theo tên tệp trong danh sách.

---

## 🕒 4. Quản lý lịch sử câu hỏi (Tab "Lịch sử hỏi")
1. **Tự động lưu lịch sử**:
   - Mọi câu hỏi bạn gửi đi đều được tự động lưu lại vào hệ thống kèm mốc thời gian chi tiết (giờ, phút, ngày, tháng).
2. **Xem lại và hỏi lại nhanh**:
   - Chuyển sang tab **`🕒 Lịch sử hỏi`** ở cột bên trái (hoặc click nút liên kết nhanh `🕒 Lịch sử hỏi (N)` phía trên ô nhập liệu).
   - Nhấp vào câu hỏi bất kỳ để đưa lại vào ô soạn thảo.
   - Bấm nút **`▶`** để hỏi lại câu lệnh đó ngay lập tức mà không cần gõ lại.
3. **Quản lý danh sách**:
   - Bấm nút **`🗑`** bên cạnh từng câu để xóa câu hỏi đó.
   - Bấm nút **`🗑 Xóa hết`** ở góc trên để dọn sạch toàn bộ lịch sử câu hỏi khi cần.

---

## 🔍 5. Cơ chế quét tệp thông minh & Loại bỏ nhiễu
Hệ thống sử dụng cơ chế tìm kiếm RAG (Retrieval-Augmented Generation) chuyên dụng cho cơ sở dữ liệu y tế:
1. **Phân tách mục độc lập cho tệp tổng hợp / sổ tay**:
   - Đối với các tài liệu tổng hợp nhiều câu lệnh (như file `.docx` chứa các mục `1. `, `2. `, `102. `), hệ thống tự động bóc tách từng mục thành các khối độc lập.
   - Tránh tình trạng đổ dồn một lúc hàng chục câu lệnh không liên quan gây rối mắt.
2. **Khớp chính xác & Chống nhiễu**:
   - Ưu tiên cao nhất cho tiêu đề khớp chính xác cụm từ tìm kiếm (ví dụ: *"đổi thu ngân"* sẽ trả về chính xác mục *"102. Đổi phòng thu ngân"*).
   - Tự động hạ điểm các câu lệnh chỉ chứa từ khóa phụ (như từ *"đổi"* đơn lẻ trong *"đổi người chỉ định"*, *"đổi trạng thái"*).
3. **Phân chia các trường hợp rõ ràng**:
   - Nếu tìm thấy **1 giải pháp đúng nhất**: Trả về trực tiếp tiêu đề, hướng dẫn và khối lệnh SQL chuẩn.
   - Nếu có **nhiều trường hợp cùng liên quan**: Trợ lý sẽ phân tách thành từng mục rõ ràng: `Trường hợp 1`, `Trường hợp 2` kèm tên tài liệu nguồn để bạn lựa chọn đúng trường hợp mình muốn.

---

## 💬 6. Thao tác trò chuyện & Trích xuất câu lệnh SQL
1. **Gửi câu hỏi**:
   - Nhập nội dung vào ô soạn thảo ở góc dưới bên phải.
   - Bấm phím **`Enter`** để gửi câu hỏi.
   - Bấm tổ hợp phím **`Shift + Enter`** nếu muốn xuống dòng khi gõ đoạn văn dài.
2. **Đưa câu lệnh sang Trình soạn SQL (1-Click Execution)**:
   - Khi câu trả lời có chứa mã lệnh SQL, hệ thống tự động tạo khung **"CÂU LỆNH SQL KHẮC PHỤC / KIỂM TRA ĐỀ XUẤT"**.
   - Bấm nút **`📥 Chèn vào Trình soạn SQL`**: Ứng dụng sẽ tự động sao chép câu lệnh này sang tab làm việc trong Trình soạn SQL để bạn thực thi hoặc hiệu chỉnh ngay lập tức.
   - Bấm nút **`📋 Sao chép SQL`**: Sao chép riêng khối SQL vào Clipboard máy tính.
   - Bấm nút **`📋 Sao chép toàn bộ phản hồi`**: Sao chép toàn bộ văn bản giải thích.
3. **Giao tiếp thân thiện hàng ngày**:
   - Bạn có thể thoải mái chào hỏi (*"chào bạn"*, *"chào buổi sáng"*), cảm ơn (*"cảm ơn nhé"*), hoặc hỏi thăm (*"hôm nay thế nào"*, *"bạn là ai"*).
   - Trợ lý sẽ phản hồi ấm áp, vui vẻ như một người đồng nghiệp nhiệt tình thay vì báo lỗi máy móc.

---

## ⚙️ 7. Chế độ hoạt động: Offline cục bộ & Online AI
1. **Chế độ Offline cục bộ (Mặc định)**:
   - Hoạt động 100% trên máy tính của bạn, không gửi dữ liệu ra Internet.
   - Quét trực tiếp và trích xuất câu trả lời từ các tài liệu bạn nạp vào.
   - Tuyệt đối bảo mật dữ liệu nghiệp vụ và bệnh án của bệnh viện.
2. **Chế độ Online AI (Kết nối mô hình ngôn ngữ lớn)**:
   - Bấm nút **`⚙ Cấu hình AI`** ở thanh công cụ phía trên.
   - Điền thông tin Endpoint và API Key của:
     - **Google Gemini API** (Gemini 1.5 Flash / Pro).
     - **OpenAI API** (GPT-4o, GPT-4o-mini).
     - **DeepSeek API** (DeepSeek-V3, DeepSeek-R1).
     - **Ollama / LM Studio cục bộ** (Llama 3, Qwen, Mistral...).
   - Khi bật AI, mô hình sẽ đọc nội dung từ các tệp tài liệu đã nạp kết hợp với năng lực suy luận của AI để phân tích sâu nguyên nhân sự cố và viết lại câu lệnh SQL tối ưu nhất cho bạn.

---

## 💾 8. Xuất báo cáo & Làm mới cuộc trò chuyện
- **`💾 Xuất Markdown`**: Lưu toàn bộ nội dung buổi trao đổi ra tệp `.md` để lưu trữ vào hồ sơ kỹ thuật hoặc gửi cho đồng nghiệp.
- **`🧹 Cuộc trò chuyện mới`**: Xóa trắng màn hình chat hiện tại để bắt đầu phiên xử lý sự cố mới. Toàn bộ câu hỏi trước đó vẫn được lưu an toàn tại tab **`🕒 Lịch sử hỏi`**.

---

## 📝 9. Nhật ký cập nhật tính năng
- **V2026.11.15**:
  - Ra mắt chính thức tính năng **Trợ lý tra lỗi (RAG Skill Assistant)**.
  - Tích hợp nạp tệp Word `.docx` bảo toàn cấu trúc đoạn văn bản.
  - Nâng cấp bộ tách mẹo/câu lệnh đánh số thông minh, loại bỏ hoàn toàn hiện tượng hiển thị một loạt câu lệnh gây rối mắt.
  - Cập nhật huy hiệu trạng thái Bật/Tắt dạng vector sắc nét, khắc phục triệt để lỗi hiển thị ô vuông emoji trên Windows.
  - Tích hợp tab **Lịch sử hỏi** tự động ghi nhớ và chạy lại nhanh các câu hỏi đã tra cứu.
