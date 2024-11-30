# I. Hệ thống con trong run Payroll
---
  1. System Clock
    Mục đích: Xác định thời gian để khởi động quy trình trả lương vào các ngày cụ thể.
    Thành phần:
    Phương thức start(): Bắt đầu tiến trình trả lương.
    Kết nối với SystemClockInterface.
![Sơ đồ subsystem System Clock](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGd1bSKbghdDEVdAsGZMN0X0avoGM5oEBU-QLf1Qb9IQdGXL00DWa3KsmI2rNBPT3QbuAo6000000__y30000)
  3. Payroll Controller
    Mục đích: Là trung tâm xử lý chính, điều phối các luồng công việc trong quy trình trả lương.
    Thành phần:
    Phương thức runPayroll(): Bắt đầu quy trình trả lương.
    Phương thức isPayday(): Kiểm tra xem ngày hiện tại có phải ngày trả lương hay không.
    Phương thức createPaycheck(amount): Tạo phiếu lương với số tiền tương ứng.
    Tương tác với các hệ thống con khác: Employee, PrintService, và BankSystem.
  4. Employee System
  Mục đích: Cung cấp dữ liệu về nhân viên để tính lương.
    Thành phần:
    Phương thức getTimecardInfo(): Lấy thông tin bảng chấm công.
    Phương thức getPOInfo(): Lấy thông tin đơn đặt hàng (cho nhân viên hưởng lương theo doanh số).
    Phương thức calculatePay(): Tính lương dựa trên thông tin đã lấy được.
  5. Timecard
    Mục đích: Lưu trữ thông tin chấm công của nhân viên.
    Thành phần:
    Cung cấp dữ liệu về số giờ làm việc, số ngày làm việc.
  6. Purchase Order (PO)
    Mục đích: Lưu trữ và cung cấp thông tin đơn đặt hàng của nhân viên hưởng lương theo doanh số.
    Thành phần:
    Dữ liệu đơn hàng và doanh thu.
  7. Paycheck
    Mục đích: Đại diện cho phiếu lương của nhân viên.
    Thành phần:
    Số tiền được trả.
    Thông tin nhân viên.
    Phương thức thanh toán (in phiếu hoặc chuyển khoản ngân hàng).
  8. Print Service
    Mục đích: In phiếu lương cho nhân viên.
    Thành phần:
    Phương thức print(Paycheck): In phiếu lương ra giấy.
    Kết nối với Printer.
  9. Printer
    Mục đích: Đảm bảo việc in phiếu lương từ hệ thống.
    Thành phần:
    Giao tiếp với PrintService.
  10. Bank System
    Mục đích: Xử lý các giao dịch ngân hàng cho việc chuyển khoản lương.
    Thành phần:
    Phương thức deposit(Paycheck, BankInformation): Gửi tiền vào tài khoản ngân hàng của nhân viên.
    Phương thức sendTransaction(): Xử lý giao dịch gửi tiền.
