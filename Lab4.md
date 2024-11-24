I. Đăng Nhập
---
  1. Tên UseCase: Login
  2. Actor: User, hệ thống xác thực
  3. Mục tiêu: Cho phép người dùng đăng nhập thông qua tài khoản và mật khẩu
  4. Luồng sự kiện:
      - Người dùng mở form đăng nhập
      - Người dùng nhập tài khoản, mật khẩu vào form và bấm đăng nhập
      - Hệ thống tiến hành kiểm thử: Nếu hợp lệ sẽ chuyển tới trang chính, nếu không hợp lệ thì báo lỗi
      - Luồng phụ: Người dùng không nhập gì cả, hệ thống yêu cầu nhập để xác thực
      - Kết quả: Người dùng đăng nhập thành công hoặc nhận thông báo lỗi
II. Maintain Timecard:
  1. Tên Usecase: Maintain Timecard
  2. Actor: Employee, Project Management
  3. Mục tiêu:
     - Employee có thể tạo Timecard (TC - bảng chấm công)
     - Employee có thể gửi Charges Code (mã thanh toán) tới Project Management
     - Employee có thể thêm giờ, sửa thông tin TC
     - Employee lưu lại TC
  4. Luồng sự kiện:
     - Tạo Timecard:
       + Employee nhập thông tin vào form tạo Timecard
       + Employee
