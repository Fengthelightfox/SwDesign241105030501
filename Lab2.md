1. Ca sử dụng "Close Registration"
   
a) Lớp phân tích chính
  Registrar: Người thực hiện thao tác đóng đăng ký. 
  System: Hệ thống chịu trách nhiệm đóng đăng ký, xử lý các khóa học và quản lý các hoạt động liên quan.
  Course offering: Đại diện cho mỗi khóa học được mở, có thể bị hủy nếu không đủ sinh viên đăng ký hoặc không có giảng viên dạy.
  Schedule: Lịch trình của từng sinh viên, chứa các khóa học mà họ đăng ký.
  Student: Đại diện cho sinh viên trong hệ thống.
  Billing System: Hệ thống thanh toán, nhận thông báo để lập hóa đơn cho sinh viên đã đăng ký thành công.

b) Sơ đồ tuần tự: [nhấn vào đây](https://www.planttext.com/api/plantuml/png/T5H1Ri8m4Bpd5IjESEYfDzGYIbgfN4f5-83hRC3gnevi1uctzT0dzGjTXpZ48AmeKJ8xdjbPAty_lqldXVLjJPcGtbZOubuvRuND6lwkf6g4zZ29dxqokZWvZ_K4X8DjaPRbfhKEDrM5LkbzLv9lqf927h1i2JkmoD-lKD-MgFqPtANOIX7nhYFvLP5bWs5uMB2VEKWo3iT-fxDiMmpe0UNtkXhZQ_rfpTwYSrmfoCCO1AMXwU4CUFLRHTKvl2hNa3Yb6GLQt7NIyKhaWDLHU0of8JbCTRJnDrfaJ0DlGXuW3RO3BsRoJTyNArRCDVP5btsIJDIU-ugCqDzG1k8e58alGX2w17UcE5Wym-F022lVnFnoKzVAW-pyWBasbBgEiqxWYs-U_Xm8ZqYnS6GqBYwAsWKIIXzQGAivI0Ug0erOOfdGKAVlevJ2sKYpl98ScJ-d4OPoPjpfOiNE74lsntEjApCjThExZhhHVvWmwNuAV0tHFrqbF_8kj4IwQpvAnEVDEKrEMnS4JxoLaZrKBT4f2ymbtyBFu1y00F__0m00)

c) Nhiệm vụ của từng lớp
  Registrar: Khởi tạo yêu cầu đóng đăng ký. Đảm bảo rằng đăng ký không còn đang mở để bắt đầu quy trình.
  RegistrationSystem: Là lớp điều phối chính, thực hiện các bước kiểm tra điều kiện đăng ký, xử lý từng khóa học, và quản lý việc gửi thông tin thanh toán.
  CourseOffering: Kiểm tra số lượng sinh viên và giảng viên, xác định khóa học cần hủy hoặc tiếp tục. Đảm bảo khóa học có ít nhất 3 sinh viên và có giảng viên để tiếp tục.
  Schedule: Chứa lịch trình của sinh viên và quản lý danh sách thay thế các khóa học chính. Đảm bảo số lượng khóa học phù hợp và chọn khóa học thay thế nếu cần.
  Student: Đại diện cho các sinh viên trong hệ thống. Mỗi sinh viên được kết nối với các khóa học mà họ đã đăng ký.
  BillingSystem: Nhận thông tin thanh toán từ hệ thống đăng ký và thực hiện gửi hóa đơn tới sinh viên.
  
d) Thuộc tính và quan hệ
   Các thuộc tính
   
      Registrar
         id: ID của người dùng hệ thống
         name: Tên của người dùng hệ thống
         
      RegistrationSystem
         isRegistrationOpen: Biến trạng thái cho biết đăng ký có đang mở hay không
      CourseOffering
         courseID: ID của khóa học
         students[]: Danh sách sinh viên đăng ký khóa học
         professor: Giảng viên phụ trách khóa học
         minStudentCount: Số lượng sinh viên tối thiểu (3 sinh viên)
      Schedule
         courses[]: Danh sách các khóa học sinh viên đã đăng ký
         alternates[]: Danh sách các khóa học thay thế
      Student
         studentID: ID của sinh viên
         name: Tên sinh viên
         schedule: Lịch trình của sinh viên trong kỳ học hiện tại
      BillingSystem
         transactionID: ID giao dịch
         billingInfo: Thông tin thanh toán của sinh viên
         Quan hệ giữa các lớp
         Registrar — gửi yêu cầu đóng đăng ký → RegistrationSystem
         RegistrationSystem — kiểm tra và xử lý các khóa học → CourseOffering
         CourseOffering — tham gia vào lịch trình → Schedule
         Schedule — chứa thông tin sinh viên → Student
         RegistrationSystem — gửi thông tin thanh toán → BillingSystem
2. Ca sử dụng
3. Ca sử dụng
4. Ca sử dụng
