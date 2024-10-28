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

  - Employee (Nhân viên) : Hệ thống cần lưu trữ thông tin về nhân viên và đảm bảo rằng dữ liệu của mỗi nhân viên chỉ có thể được truy cập và chỉnh sửa bởi chính họ hoặc Payroll Administrator.
  Phân tích cơ chế: Persistence, Security
  
  - Timecard (Thẻ chấm công): Dữ liệu về số giờ làm việc hàng ngày của nhân viên cần được lưu trữ và bảo mật, chỉ cho phép nhân viên liên quan và Payroll Administrator truy cập.
  Phân tích cơ chế: Persistence, Security
  
  - PurchaseOrder (Đơn đặt hàng): Các đơn đặt hàng ghi lại doanh số của nhân viên cần được lưu trữ và bảo mật, chỉ cho phép nhân viên liên quan và Payroll Administrator truy cập.
  Phân tích cơ chế: Persistence, Security
  
  - Paycheck (Phiếu lương): Hệ thống cần lưu giữ thông tin về phiếu lương để truy xuất và đảm bảo bảo mật thông tin lương của mỗi nhân viên.
  Phân tích cơ chế: Persistence, Security
  
  - ProjectManagementDatabase (Cơ sở dữ liệu Quản lý Dự án): Vì hệ thống phải truy cập dữ liệu từ cơ sở dữ liệu hiện có (DB2 trên IBM mainframe) mà không cập nhật, nên cần một cơ chế giao tiếp với cơ sở dữ liệu này.
  Phân tích cơ chế: Legacy Interface
  
  - Payment Method (Phương thức thanh toán): Cần đảm bảo bảo mật khi lưu thông tin phương thức thanh toán và thực hiện giao dịch, cũng như tích hợp với các hệ thống ngân hàng cho giao dịch gửi tiền trực tiếp.
  Phân tích cơ chế: Security, External Interface
  
  - Payroll Scheduling (Lịch trình trả lương): Cần có cơ chế tự động hóa để chạy hệ thống trả lương vào các ngày quy định (mỗi thứ Sáu và ngày làm việc cuối cùng của tháng).
  Phân tích cơ chế: Scheduling, Automation
  
  - Reporting (Báo cáo): Cơ chế cần cho phép nhân viên tạo các báo cáo về thời gian làm việc, số giờ ghi nhận cho các dự án, và tổng số lương đã nhận, đồng thời bảo mật thông tin cá nhân.
  Phân tích cơ chế: Persistence, Security, Query Interface
  
  - Payroll Administrator (Quản trị viên Hệ thống Lương): Cần cơ chế bảo mật và lưu trữ để Payroll Administrator có thể cập nhật và quản lý thông tin nhân viên, cũng như tạo các báo cáo quản trị.
  Phân tích cơ chế: Persistence, Security, Administrative Interface
  
  - BankSystem (Hệ thống Ngân hàng): Cơ chế kết nối với hệ thống ngân hàng để thực hiện giao dịch chuyển khoản cho các nhân viên chọn phương thức thanh toán qua tài khoản ngân hàng.
  Phân tích cơ chế: External Interface

## 3. Phân tích ca sử dụng Payment
a) Các lớp chính:
  - Employee (Nhân viên): Chứa các thuộc tính như EmployeeID, Name, và PaymentMethod. Lớp này chịu trách nhiệm lưu trữ thông tin của nhân viên và các phương thức cần thiết để cập nhật phương thức thanh toán.

  - PaymentMethod (Phương thức thanh toán): Lớp này sẽ lưu trữ các thuộc tính như MethodType (pick up, mail, direct deposit) và các thông tin liên quan nếu chọn "mail" (địa chỉ) hoặc "direct deposit" (tên ngân hàng, số tài khoản).

  - PaymentService (Dịch vụ): Có nhiệm vụ yêu cầu, xác nhận, và cập nhật phương thức thanh toán của nhân viên. Các thuộc tính bao gồm MethodType và các phương thức tương tác với lớp Employee và PaymentMethod để cập nhật thông tin.

b) Quan hệ:
  - Employee và PaymentMethod có quan hệ 1-1 vì mỗi nhân viên chỉ chọn một phương thức thanh toán.
  - PaymentService tương tác với Employee và PaymentMethod để yêu cầu lựa chọn phương thức, kiểm tra thông tin và cập nhật dữ liệu.

c) Thuộc tính:
  - Employee:
    + EmployeeID: Mã nhân viên
    + Name: Tên nhân viên
    + PaymentMethod: Phương thức thanh toán
  - PaymentMethod:
    + MethodType: Kiểu phương thức thanh toán ("pick up", "mail", "direct deposit")
    + MailAddress: Địa chỉ nhận phiếu lương (nếu chọn "mail")
    + BankName: Tên ngân hàng (nếu chọn "direct deposit")
    + AccountNumber: Số tài khoản ngân hàng (nếu chọn "direct deposit")
  - PaymentService:
    + selectPaymentMethod(): Phương thức lựa chọn và cập nhật phương thức thanh toán
    + validateEmployeeInfo(): Kiểm tra tính hợp lệ của thông tin nhân viên
    + updatePaymentInfo(): Cập nhật thông tin phương thức thanh toán

d) Biểu đồ ca sử dụng: 
[Payment](https://www.planttext.com/api/plantuml/png/X58_IyD05D_pAHwTsi4lq46AucPA8C7zI8xUqUJbI2-5p0uEuYZEKKGi20fEkQ53eD_ZFe5VmRj8QcAZBWVltk_VUxmFjPsj9CbadiGE2MMQmLaYuhIWr17ccuTS49GmyaYHK9G-pTOyf2CWA_3yFgGbDarJ30guLB8q-kAxZjDouEZOw4qXP5hTeCTshxiI5u6fdiE04MH1MfSudZYURw66DeKbr-eo2J8IiFhTW3dEMNsF5xpUM6GNMjIR_5HNJ_aVoWTHSbmOpgFubHEdkYfvlztrRUGwvlkS9rhT-aOUngYhRGwXwUAF16udmG0nqkgDWCpChF1VZgarU15pPbwvr_eUf8s1Tdsmjli38_8W8DRgQd8m4BEBH-jpVQxL7H_YBnkRdioCOcJFx1C00F__0m00)

e) Giải thích:
  - Bắt đầu: Employee gửi yêu cầu chọn phương thức thanh toán đến PaymentService.
  - Kiểm tra thông tin: PaymentService xác thực thông tin nhân viên.
  - Chọn phương thức thanh toán: Nếu hợp lệ, PaymentService yêu cầu nhân viên chọn phương thức thanh toán và nhận lại phương thức đã chọn.
  - Yêu cầu thông tin bổ sung: PaymentService yêu cầu thêm thông tin địa chỉ hoặc ngân hàng, tùy thuộc vào phương thức thanh toán.
  - Cập nhật thông tin thanh toán: PaymentService cập nhật phương thức thanh toán đã chọn vào hồ sơ nhân viên.
  - Xử lý lỗi: Nếu thông tin nhân viên không hợp lệ, PaymentService gửi thông báo lỗi.
Biểu đồ mô tả các bước để chọn và lưu trữ phương thức thanh toán chính xác cho nhân viên sau khi đã xác thực.

## 4. Phân tích ca sử dụng Maintain Timecard:
a) Các lớp chính:
  - Employee: Là nhân viên sử dụng hệ thống. Chứa thuộc tính nhân viên
  - Timecard: Là phiếu chấm công, chứa các thông tin về ngày và số giờ làm việc của nhân viên.
  - ChargeNumber: Là các số mã dự án mà nhân viên có thể ghi nhận giờ làm việc.
  - TimecardSystem: Hệ thống quản lý chấm công, thực hiện các thao tác liên quan đến phiếu chấm công.
  - ProjectManagementDatabase: Đối tượng cung cấp danh sách mã dự án từ hệ thống quản lý dự án.

b) Quan hệ:
  - Employee - Timecard: Mỗi Employee chỉ quản lý một Timecard trong kỳ lương hiện tại.
  - TimecardSystem - ProjectManagementDatabase: TimecardSystem truy cập ProjectManagementDatabase để lấy danh sách ChargeNumber.
  - Timecard - ChargeNumber: Timecard chứa nhiều ChargeNumber mà nhân viên đã ghi lại số giờ làm.

c) Thuộc tính:
  - Employee: Gồm tên, ID và các phương thức yêu cầu và gửi Timecard.
  - Timecard: Gồm các thông tin ngày tháng, trạng thái, số giờ làm việc cho từng ChargeNumber và các phương thức như kiểm tra giới hạn giờ làm, lưu, hoặc khóa   chỉnh sửa khi đã gửi.
  - TimecardSystem: Quản lý luồng chính của ca sử dụng, từ tạo/lấy Timecard, lấy mã dự án, đến xác nhận và lưu trữ.
  - ProjectManagementDatabase: Chỉ chứa danh sách mã dự án.

d) Sơ đồ Sequence: 
[Maintain Timecard](https://www.planttext.com/api/plantuml/png/b5FFIiCm7BxtANxix5wWK1auKR2Ae1UFMHQQQfEMDXLwzk31q_3WILWH4PI1eY0q1myHtoDFu2kORdIpcWqz1PBVz-NxatpAjrucK2fo5Za8YpY5JPP4SK68avZj48S9uW8EGqOmIeS7HIO8Qntjf_4nmM8NSHGGHhZe8u46ABCJE8xdWPzhUSa3m5HDE7LXGrUJ13Wros8IFCzfj41t_OS45uxKVGvOLtVv39b0fkK8Wb3BQuZKc3bjn7SE5tnTtHP0OrszOX2wAcCGpSNKK9ppwMve8Lbgk65bwWQ6MZw1AhcpT1gw5bDzn2bagiIqnT88ZRIyiabgSd9XssW_CzgfbXTM2a7LYub-e8pZ6PqrPHVsVeMAgGb9omS3RrcSDsPpv7yyvlDef-rlQJa9_rppR7fEiAhJrZFYWHeN4DJeDH2fwTB8DkRB43hl8oD_UjHPIRXJXyaC6lqd1kjpgrCuLMCueUePBUpq21_MN-yB003__mC0)
