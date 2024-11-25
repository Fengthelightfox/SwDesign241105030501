I. Đăng Nhập
---
[Biểu đồ UML Đăng Nhập](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aOAIN_gn3GztpyrKI3cyCozT8UdXhgKb2jaFTszMKaWiLWWjJYtYAafDBadCIyz9LL1oodoukxbK8VVXhjMb2aSc7ca6QidBUBXhRO6IGZMNWa9fSMfoOZ5GeHzOKA7ayAeyL7KAPOSNWFIl1Te255XP2h77sH1PTyJXXSaA9HaFTszC9i488sGZF40kpGCRqWqa3sy1UUxmmdo5d8UxfsT2THXprN9nWVoeeAjh1tO444FPHa2s4PHjh62b408neoGp3sWhc0aqUd41oBnsX5AGMIXgaHGvfEQbW48U0000__y30000)
**Tên ca sử dụng**: Đăng nhập
**Tác nhân**:
    - Người dùng bất kỳ
    
## Tiền điều kiện:
    - Người dùng phải có tên đăng nhập và mật khẩu hợp lệ.
    
Luồng cơ bản:
    - Người dùng điều hướng đến biểu mẫu đăng nhập.
    - Người dùng nhập tên đăng nhập và mật khẩu.
    - Hệ thống xác thực tên đăng nhập và mật khẩu.
    - Nếu thông tin xác thực hợp lệ, người dùng được cấp quyền truy cập vào hệ thống.
    - Nếu thông tin xác thực không hợp lệ, hệ thống hiển thị thông báo lỗi.
    
## Hậu điều kiện:
    - Người dùng hoặc là đã đăng nhập vào hệ thống hoặc nhận được thông báo lỗi.
    
## Giải thích thiết kế:
    - Thiết kế này đảm bảo quy trình đăng nhập rõ ràng và hiệu quả.
    - Đảm bảo người dùng phải đăng nhập thành công mới sử dụng được.
    
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
