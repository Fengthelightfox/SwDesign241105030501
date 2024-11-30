# I. Hệ thống con trong run Payroll
---
  1. System Clock
     
    Mục đích: Xác định thời gian để khởi động quy trình trả lương vào các ngày cụ thể.
    Thành phần:
    Phương thức start(): Bắt đầu tiến trình trả lương.
    Kết nối với SystemClockInterface.
![Sơ đồ subsystem System Clock](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGd1bSKbghdDEVdAsGZMN0X0avoGM5oEBU-QLf1Qb9IQdGXL00DWa3KsmI2rNBPT3QbuAo6000000__y30000)

  2. Payroll Controller
  
    Mục đích: Là trung tâm xử lý chính, điều phối các luồng công việc trong quy trình trả lương.
    Thành phần:
    Phương thức runPayroll(): Bắt đầu quy trình trả lương.
    Phương thức isPayday(): Kiểm tra xem ngày hiện tại có phải ngày trả lương hay không.
    Phương thức createPaycheck(amount): Tạo phiếu lương với số tiền tương ứng.
    Tương tác với các hệ thống con khác: Employee, PrintService, và BankSystem.
![subsystem Controller](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGa1YPL5-JevpVbu9Y4ujKgZcKW22v9p4ucASiX1GL9e7LQ2XYIISMGmKJKciH15CBafDB4a5IYHdf2PdQoJcvfVcbLWffENa9vP0rDLorN8vfEQbW5m70000__y30000)

  3. Employee System
     
    Mục đích: Cung cấp dữ liệu về nhân viên để tính lương.
    Thành phần:
    Phương thức getTimecardInfo(): Lấy thông tin bảng chấm công.
    Phương thức getPOInfo(): Lấy thông tin đơn đặt hàng (cho nhân viên hưởng lương theo doanh số).
    Phương thức calculatePay(): Tính lương dựa trên thông tin đã lấy được.
![Employee](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGa1YPL5-JevpVbu9Y4ujKgZcKW22v9p4ucASiX1GL9e7LQ2XYIISMGmKJKciH15CBafDB4a5IYHdf2PdQoJcvfVcbLWffENa9vP0rDLorN8vfEQbW5m70000__y30000)
    
  4. Timecard
     
    Mục đích: Lưu trữ thông tin chấm công của nhân viên.
    Thành phần:
    Cung cấp dữ liệu về số giờ làm việc, số ngày làm việc.
![Timecard](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGaXcRcfoOb6AGZMN0X0avoGM5wCBGa1wQWb8t2Mr934pfrX34onLorNBvP2Qbm8o4W000F__0m00)
    
  5. Purchase Order (PO)
     
    Mục đích: Lưu trữ và cung cấp thông tin đơn đặt hàng của nhân viên hưởng lương theo doanh số.
    Thành phần:
    Dữ liệu đơn hàng và doanh thu.
![PurchaseOrder](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGa1fKN96Od6gVr5AQf52DPS242Jd91ONOvM1WFJK4h2WIsf9OcPEiOOcMAwMgvRB8JKl1MGw0000__y30000) 
  6. Paycheck

    Mục đích: Đại diện cho phiếu lương của nhân viên.
    Thành phần:
    Số tiền được trả.
    Thông tin nhân viên.
    Phương thức thanh toán (in phiếu hoặc chuyển khoản ngân hàng).
![Paycheck](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGa1YPN96QdAsGZMN0X0avoGM5wCBGa1YRdvfNecLGbfEVc89adXgRa5EVcLggcTUMhwLGd19KMPUEf9qGM9bRcfUYMzgIKP-2efyBLSjbqDgNWh8EG00003__mC0)
    
  7. Print Service
      
    Mục đích: In phiếu lương cho nhân viên.
    Thành phần:
    Phương thức print(Paycheck): In phiếu lương ra giấy.
    Kết nối với Printer.
![PrintService](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGa1HPbv9S6fHMMPoga8rbm8G9ESa5XTZau200f24Ha1YPN96QdAsbGACfGbMKyjLo-MGcfS2iWC0003__mC0)
    
  8. Printer
      
    Mục đích: Đảm bảo việc in phiếu lương từ hệ thống.
    Thành phần:
    Giao tiếp với PrintService.
![Print](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggGa1HPbv9Qf52DPS242Jd91ONeub1G6f5Qd9fIIfOIaCJB57BLSlba9gN0Z8E0000__y30000)
    
  9. Bank System
      
    Mục đích: Xử lý các giao dịch ngân hàng cho việc chuyển khoản lương.
    Thành phần:
    Phương thức deposit(Paycheck, BankInformation): Gửi tiền vào tài khoản ngân hàng của nhân viên.
    Phương thức sendTransaction(): Xử lý giao dịch gửi tiền.
![Bank](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWbDYNdPmPN59Qgv2DPS242Jd91ONOmf3G4fgGNvnPeb6G69bSaPgShQL0eob0zRYcPUMNvIRM9APdsUb45nIb9cNhecalJWrBoMaA36lE34Pf4G38bVBLSlb09G1EGi0003__mC0)
