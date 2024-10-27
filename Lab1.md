## 1. Phân tích kiến trúc
a) Đề xuất kiến trúc

  - Kiến trúc đề xuất: Kiến trúc phân tầng (Layer)
  - Lý do lựa chọn: Có những lý do sau đây:
    + Dễ quản lý và bảo trì: việc phân chia các tầng sẽ giúp tách chức năng của từng tầng rõ ràng, từ đó dễ dàng kiểm soát và bảo trì hệ thống.
    + Tính phân hóa cao: Đảm bảo rằng mỗi tầng chỉ thực hiện đúng nhiệm vụ của nó. Điều này giúp phần mềm dễ dàng được cập nhật, mở rộng chức năng mà không ảnh hưởng đến các phần khác.
    + Tính bảo mật: Kiểm soát quyền truy cập hiệu quả, hạn chế việc truy cập chéo giữa các tầng
    + Tính tái sử dụng: Các tầng như Business và Database có thể tái sử dụng cho các phần mềm khác

b) Ý nghĩa từng thành phần trong kiến trúc

  - Tầng Giao diện người dùng (Presentation Layer): Chứa giao diện cho người dùng, hiển thị dữ liệu, cung cấp đầu vào
  - Tầng Logic Nghiệp vụ (Business Logic Layer): Xử lý các quy tắc nghiệp vụ và yêu cầu từ tầng giao diện, tương tác với tầng giao diện để quản lý dữ liệu.
  - Lớp Lưu trữ (Persistence Layer): Quản lý việc truy cập và lưu trữ dữ liệu, ẩn chi tiết lưu trữ cho các lớp trên.
  - Lớp Cơ sở Dữ liệu (Database Layer): Lưu trữ thực tế dữ liệu trong các bảng hoặc tài liệu.

c) sơ đồ package: 
[sơ đổ package](https://www.planttext.com/api/plantuml/png/V9B1IiCm6CVlVOgFdkfXB-11fYjCM1d2vkvP5jfWJKgJ24LszkJ19z0XeeZ3dPV33eM-Hvx0Lp1PTPki4q9ooFVx9Ty_-TAhjf0eb-ewzJA4hr1CmEzHirmna7cvn71kz1t8nEW75iCmDyjdIAj5DMEn3xSUW1qRS6YMh-kgyeCbC2wV2WWkSY88aqXIpY121ScFQX00fqW8w5B4GqfOFrQSXeh5Tc_gDMYDVhFpnEWNkmIdMPPIV5XhbQgNMEybY_-pHZoc6FfnGcsZ6TnOFGHdIb16hANURVRZPAGSHxAHEcYl5ie6QVIdJOBaWWf962QDnbx28wM6-K5Pfvg1CFeHGkTBtOKL126IQ8n4ixF31pnKaSsYbjfvBszejKxsue9ZyBj6poaKvRi2R6-WV4llrTNmRXO_w3s5T9qUsyssTlmfTuPDxmwsI-5Ed6VkjNyxTUIsp47RvjPKWZZ8SeQXCmWZt_EcNfkmYVlPtm000F__0m00)

## 2. Phân tích cơ chế:

Employee (Nhân viên)

Cơ chế phân tích: Persistence, Security
Giải thích: Hệ thống cần lưu trữ thông tin về nhân viên và đảm bảo rằng dữ liệu của mỗi nhân viên chỉ có thể được truy cập và chỉnh sửa bởi chính họ hoặc Payroll Administrator.
Timecard (Thẻ chấm công)

Cơ chế phân tích: Persistence, Security
Giải thích: Dữ liệu về số giờ làm việc hàng ngày của nhân viên cần được lưu trữ và bảo mật, chỉ cho phép nhân viên liên quan và Payroll Administrator truy cập.
PurchaseOrder (Đơn đặt hàng)

Cơ chế phân tích: Persistence, Security
Giải thích: Các đơn đặt hàng ghi lại doanh số của nhân viên cần được lưu trữ và bảo mật, chỉ cho phép nhân viên liên quan và Payroll Administrator truy cập.
Paycheck (Phiếu lương)

Cơ chế phân tích: Persistence, Security
Giải thích: Hệ thống cần lưu giữ thông tin về phiếu lương để truy xuất và đảm bảo bảo mật thông tin lương của mỗi nhân viên.
ProjectManagementDatabase (Cơ sở dữ liệu Quản lý Dự án)

Cơ chế phân tích: Legacy Interface
Giải thích: Vì hệ thống phải truy cập dữ liệu từ cơ sở dữ liệu hiện có (DB2 trên IBM mainframe) mà không cập nhật, nên cần một cơ chế giao tiếp với cơ sở dữ liệu này.
Payment Method (Phương thức thanh toán)

Cơ chế phân tích: Security, External Interface
Giải thích: Cần đảm bảo bảo mật khi lưu thông tin phương thức thanh toán và thực hiện giao dịch, cũng như tích hợp với các hệ thống ngân hàng cho giao dịch gửi tiền trực tiếp.
Payroll Scheduling (Lịch trình trả lương)

Cơ chế phân tích: Scheduling, Automation
Giải thích: Cần có cơ chế tự động hóa để chạy hệ thống trả lương vào các ngày quy định (mỗi thứ Sáu và ngày làm việc cuối cùng của tháng).
Reporting (Báo cáo)

Cơ chế phân tích: Persistence, Security, Query Interface
Giải thích: Cơ chế cần cho phép nhân viên tạo các báo cáo về thời gian làm việc, số giờ ghi nhận cho các dự án, và tổng số lương đã nhận, đồng thời bảo mật thông tin cá nhân.
Payroll Administrator (Quản trị viên Hệ thống Lương)

Cơ chế phân tích: Persistence, Security, Administrative Interface
Giải thích: Cần cơ chế bảo mật và lưu trữ để Payroll Administrator có thể cập nhật và quản lý thông tin nhân viên, cũng như tạo các báo cáo quản trị.
BankSystem (Hệ thống Ngân hàng)

Cơ chế phân tích: External Interface
Giải thích: Cơ chế kết nối với hệ thống ngân hàng để thực hiện giao dịch chuyển khoản cho các nhân viên chọn phương thức thanh toán qua tài khoản ngân hàng.
3. Phân tích ca sử dụng
