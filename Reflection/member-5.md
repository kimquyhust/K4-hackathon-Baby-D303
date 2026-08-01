# Reflection Cá nhân - Nguyễn Văn Quân

## 1. Thông tin
- **Họ và tên:** Nguyễn Văn Quân
- **Mã sinh viên:** 2A202601544
- **Vai trò:** Product Presenter & Slide Lead
- **Vai trò khác:** Demo & User Validation

## 2. Phần mình làm

### 2.1. Công việc chính
Với vai trò **Product Presenter & Slide Lead**, tôi đã thực hiện:

| STT | Công việc | Kết quả |
|-----|-----------|---------|
| 1 | Thiết kế bộ Slide thuyết trình 6 trang | Slide đã hoàn chỉnh theo guide |
| 2 | Xây dựng kịch bản Demo tương tác | 2 flows: happy path + escalate |
| 3 | Phụ trách báo cáo nghiệm thu | Đã chuẩn bị script cho từng slide |
| 4 | User Validation (n = 3 willing users) | 3 users đã test và phản hồi |

### 2.2. Chi tiết Slide

**6 trang slide:**
**Slide 1**: User & Job (45")

Job executor: Học viên AI Thực Chiến (1.000 người)

Core JTBD: Tìm câu trả lời logistics nhanh và chính xác

Con số: 71% câu hỏi là logistics

**Slide 2**: Vì sao chọn tính năng này (45")

Bảng impact: Logistics vs Nội dung học vs Kỹ thuật

Lý do chọn: Phủ sóng lớn nhất, tần suất cao

**Slide 3**: Giải pháp & Demo live (2')

Lát cắt: 1 user · 1 việc · 1 quyết định AI · 1 kết quả

Demo: Case chuẩn + Case khó (escalate)

**Slide 4**: Kết quả đo (45")

Quality bar: 85% qua bộ, 0% domain case sai

Kết quả: 91% qua bộ (lượt 3)

**Slide 5**: User thật nói gì (45")

2 quotes nguyên văn từ willing users

Thay đổi đã làm từ feedback

**Slide 6**: Nếu có thêm 1 tuần (30")

3 ưu tiên: mở rộng KB, cải thiện case mơ hồ, tích hợp Discord thật

Bài học lớn nhất: "Đúng còn hơn nhanh"

text

**Kịch bản Demo:**

**Flow 1 - Happy Path:**
1. User hỏi: "Format tên Zoom như thế nào?"
2. Bot tìm trong KB → Confidence 96%
3. Bot trả lời: "Format chuẩn: Nhóm - Tên - MSSV"
4. Hiển thị nguồn: "Admin1 · 26/07/2026"

**Flow 2 - Escalate:**
1. User hỏi: "hiện tại chưa chốt danh sách nhóm thì còn 1 thành viên trong nhóm chưa liên hệ được, có cách liên hệ không"
2. Bot không có trong KB → Confidence 20%
3. Bot trả lời: "Chưa có dữ liệu, đã tag @LabCoach"
4. LabCoach trả lời trong dashboard
5. Bot học và ghi nhớ
3. AI hỗ trợ thế nào

## 3.1. Công cụ AI đã dùng

Công cụ	 | Mục đích sử dụng
Claude	 | Tạo script thuyết trình, Tối ưu cấu trúc slide
Gamma AI | Tạo slide đẹp nhanh

## 3.2. Cụ thể AI đã giúp gì

**Script thuyết trình:**

AI gợi ý cách mở đầu hấp dẫn

AI viết các câu chuyển tiếp giữa các slide

**Kịch bản Demo:**

AI gợi ý các tình huống kịch bản

AI đề xuất cách xử lý khi case xấu xảy ra

**Slide design:**

AI gợi ý bố cục và màu sắc

AI tạo các biểu đồ từ số liệu

## 3.3. Giới hạn khi dùng AI

AI không biết giọng nói của tôi → tôi phải tự điều chỉnh

AI không biết không gian/ thời gian demo → tôi phải ước lượng

AI có thể tạo slide đẹp nhưng thiếu nội dung → tôi phải kiểm tra

## 4. Bài học từ case fail của nhóm
## 4.1. Case fail: Demo bị lỗi live
**Tình huống:**
Khi demo flow escalate, bot không hiển thị tag @LabCoach vì backend chưa kết nối.

**Nguyên nhân:**
Chưa kiểm tra kết nối trước khi demo.

**Cách giải quyết:**

Chuẩn bị script dự phòng (screenshot backup)

Kiểm tra kết nối 5 phút trước demo

Test cả 2 flows ít nhất 3 lần

**Bài học:**

"Dry run ít nhất 2 lần trước demo, và luôn có backup phòng live hỏng"


