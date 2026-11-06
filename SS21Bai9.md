# Bài 9: Xây Dựng Prompt 3 Thành Phần Giải Mã Thông Báo Lỗi Trạm Sạc Cùng Trợ Lý AI

## Vấn đề:

- Trong ca trực tại bến xe, trục xạc nhanh số 4 của hệ thống độ ngột ngừng hoạt động

- Trên màn hình Terminal xuất hiện 8 dòng thông báo lỗi tiếng anh

- Chưa có nhiều kinh nghiệm nên nhân viên lấy ChatGPT hỏi một câu chưa rõ ràng nên AI đưa ra câu trả lời không chinh xác 

## Yêu cầu:

**Phần 1: Thiết kế Prompt 3 Thành phần Chuẩn hóa**

**1.** Phân tích nguyên nhân vì sao câu hỏi *'AI ơi phần mềm trạm sạc của tôi bị hỏng rồi'* lại khiến AI đưa ra câu trả lời sai lệch (hiện tượng AI Hallucination)?

**2.** Soạn thảo một câu Prompt 3 Thành phần hoàn chỉnh, chuyên nghiệp dựa trên đoạn nhật ký lỗi trên để gửi cho Trợ lý AI

**Phần 2: Giải mã Lỗi & Kịch bản Khắc phục**

**3.** Đóng vai Trợ lý AI, hãy cung cấp bản dịch và giải thích nguyên nhân gốc rễ của lỗi `UnauthorizedAccessException: Access to the path ... is denied` bằng tiếng Việt đời thường để một bạn kỹ thuật viên mới cũng có thể hiểu ngay.

**4.** Đưa ra 3 bước xử lý cụ thể tại chỗ trên Windows 11 để kích hoạt quyền Quản trị viên (Run as Administrator) và phân quyền ghi file cho thư mục `data`, giúp trạm sạc hoạt động trở lại bình thường.

**5.** Bẫy an ninh: Giả sử trong đoạn mã lỗi có chứa chuỗi mã bí mật `API_KEY: volt_secret_token_889922`, kỹ thuật viên phải xử lý chuỗi này như thế nào trước khi dán vào khung chat của ChatGPT/Gemini? Giải thích lý do.

## Cách Làm:

**Phần 1**:

**1**: 

câu hỏi quá ngắn và thiếu thông tin về thiết bị, hệ điều hành và thông báo lỗi. Vì vậy, AI phải tự suy đoán nguyên nhân, dẫn đến hiện tượng ảo giác AI

**2**: Soạn thảo Prompt 3 thành phần

a: Ngữ cảnh:

- Là nhân viên kỹ thuật đang vận hành trạm xạc số 4 Bến xe.

- Máy tính dùng Win 11

- Khi khởi động phần mềm, trạm xạc xuất hiện lỗi và không thể hoạt động

b: Lỗi nguyên văn:

[FATAL] ControllerDaemon failed to start.
System.UnauthorizedAccessException:
Access to the path 'C:\Program Files\VoltCharge\data\session.log' is denied.
Process terminated with exit code 5 (0x00000005).

c: Yêu cầu:

- Hãy dịch lỗi sang tiếng việt dể hiểu

- Xác định nguyên nhân và hướng khắc phục cụ thể trên Windows 11

**Phần 2**:

**3**:

- Giải thích:

ControllerDaemon failed to start: Dịch vụ điều khiển không thể khởi động.

UnauthorizedAccessException: Lỗi không được cấp quyền truy cập.

Access is denied: Truy cập bị từ chối.

Exit code 5: Mã lỗi không đủ quyền truy cập

- Nguyên nhân: Phần mềm VoltCharge không vó quyền ghi dữ liệu và file session.log trong thư mục Program.Files 

**4**: 3bước khắc phục

Bước 1: Chạy bằng quyền Quản Trị viên

Bước 2: Cấp quyền ghi cho thư mục data

Bước 3: Khởi động lại phần mềm

**5**:

- Trước khi gửi đoạn mã lỗi lên ChatGPT hoặc Gemini, em phải xóa hoặc thay thế mã bí mật bằng nội dung ẩn.

- Ba nguyên tắc an toàn khi sử dụng AI:

1. Không làm theo các câu lệnh nguy hiểm khi chưa kiểm tra.

2. Cung cấp đầy đủ thông tin để tránh AI đoán sai.

3. Không gửi mật khẩu, API Key và mã OTP lên AI.

