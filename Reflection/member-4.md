# Reflection cá nhân

**Học viên**: Nguyễn Minh Đạt  
**Mã học viên**: 2A202601810  
**Lớp thực hành**: D303  
**Tên nhóm**: BABY

## Vai trò của tôi trong nhóm

Trong dự án này, tôi chịu trách nhiệm chính cho tính năng **tổng hợp thông báo trên Discord**. Vai trò của tôi không chỉ là viết code, mà còn là chuyển một pain point đã được nhóm xác nhận thành một tính năng có thể sử dụng và kiểm chứng được.

Pain point mà nhóm quan sát được là khi học viên vắng mặt hoặc không theo dõi Discord thường xuyên, họ phải đọc lại nhiều tin nhắn để tìm các thông tin quan trọng như lịch học, deadline, sự kiện, đường dẫn đăng ký hoặc những thay đổi mới nhất. Các thông tin này có thể nằm xen giữa hội thoại thông thường, khiến người dùng dễ bỏ sót hoặc sử dụng một thông báo đã cũ. Từ vấn đề đó, tôi đề xuất và phát triển luồng cho phép người dùng hỏi bot bằng ngôn ngữ tự nhiên, chẳng hạn “Hôm nay có thông báo gì mới?” hoặc “Deadline gần nhất là khi nào?”, sau đó nhận lại câu trả lời ngắn gọn kèm nguồn để tự kiểm tra.

Phần tôi phụ trách bao gồm việc lọc tin nhắn theo server, kênh và role chính thức; nhận diện các dữ kiện cần giữ nguyên như thời gian, ngày tháng, deadline và URL; gửi phần ngữ cảnh phù hợp cho mô hình AI; xác thực các message ID do mô hình lựa chọn; và gắn lại liên kết tới tin nhắn Discord gốc. Tôi cũng xây dựng các trường hợp kiểm thử cho việc lọc nguồn, chọn thông báo mới nhất, xử lý bản cập nhật và tình huống không tìm thấy dữ liệu phù hợp.

## Cách tôi sử dụng AI để phát triển nhanh

Sau khi ý tưởng và pain point đã rõ, tôi sử dụng AI như một công cụ hỗ trợ lập trình để rút ngắn thời gian chuyển từ ý tưởng sang prototype. Tôi mô tả luồng xử lý mong muốn, các điều kiện lọc, định dạng dữ liệu và những trường hợp biên; sau đó dùng AI để gợi ý cấu trúc code, tạo phiên bản đầu, viết test và hỗ trợ refactor. Nhờ vậy, tôi có thể thử nghiệm nhanh nhiều cách tiếp cận thay vì dành phần lớn thời gian cho các đoạn code lặp lại.

Tuy nhiên, tôi không xem kết quả do AI tạo ra là đáp án hoàn chỉnh. Tôi vẫn phải kiểm tra lại logic, chạy test, quan sát đầu ra và điều chỉnh prompt hoặc code. Đặc biệt với thông báo có deadline và đường dẫn, chỉ một chi tiết sai cũng có thể làm người dùng hiểu nhầm. Vì vậy, tôi thiết kế hệ thống theo hướng AI chỉ được chọn message ID và diễn đạt câu trả lời; backend mới là phần xác thực ID, giữ nguyên dữ kiện quan trọng và tạo nguồn. Qua quá trình này, tôi nhận ra AI giúp code nhanh nhất khi con người đã xác định rõ vấn đề, tiêu chí đúng/sai và cách kiểm chứng kết quả.

## Bài học từ một case fail của nhóm

Một case fail quan trọng của nhóm là phiên bản thử nghiệm ban đầu phụ thuộc quá nhiều vào khả năng tự phân loại và ghi nhớ của mô hình. Khi đưa nhiều tin nhắn
Discord trực tiếp cho AI, mô hình có thể xem một đoạn trò chuyện thông thường như thông báo chính thức, ưu tiên nhầm thông báo cũ hoặc tạo một nguồn không tồn tại. Kết quả trông hợp lý về mặt ngôn ngữ nhưng không đủ đáng tin cậy để học viên sử dụng cho lịch và deadline.

Từ thất bại này, tôi học được rằng một sản phẩm có AI không nên giao toàn bộ quyền quyết định cho mô hình. Nhóm cần xác định rõ phần nào nên do code kiểm
soát và phần nào phù hợp để AI xử lý. Trong phiên bản hiện tại, code chịu trách nhiệm kiểm soát quyền truy cập, lọc nguồn chính thức, giới hạn ngữ cảnh, bảo toàn dữ kiện và xác thực nguồn; AI chủ yếu đảm nhiệm việc hiểu câu hỏi, chọn nội dung liên quan và diễn đạt câu trả lời dễ đọc.

Bài học rộng hơn đối với tôi là cần kiểm chứng pain point và failure case càng sớm càng tốt. Một demo trả lời trôi chảy chưa chắc đã giải quyết đúng vấn đề.
Chỉ khi thử với các tình huống như chat xen lẫn thông báo, thông tin bị cập nhật, nguồn không hợp lệ và trường hợp không có dữ liệu, nhóm mới nhìn thấy rủi ro thực sự. Việc biến các case fail thành test giúp chúng tôi vừa phát triển nhanh với AI, vừa giữ được độ tin cậy của sản phẩm.
