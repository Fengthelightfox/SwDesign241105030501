# Lab 6: Thiết kế hệ thống Payroll System
---
## I.Timecard Management System Design

![Timecard Management System](https://www.planttext.com/api/plantuml/png/d5JBJiCm4BpdAwoU0g88hZbLj20g0KAYuhxOssBaHsKxY8BuCWvy4h-07tcuJIiX3etgtV7kxCmcFr_V4-l0k5gAWWgmbbpAjT0RHF9H43B6vdG74Ylou0nNgpm-drLahfmFaHMwoovQ7gNuPz6KNN2950oBPGDseHs8QrqR6x1tjNn2qvPHlW_QAsrA1fkApC2XnxGbGdeJeC3OLgp4yDm17lsTMyIdkPy3iOfS2GrXk37p51AHSABFO5OurIpNX73x28ApKFv2Qu6WXYtyJ399mBXT2zYqYJBoz0EWYQ9qmwVw9wHXb8IAO8O27KuZbt98AM8ilE9s2mbSEV_BeWEMK-sLq4AWwUoQriPuTjsjfJQjebMtCvb9xRL8Av6-uTQLr70_8eUEPKLsCU5glGwA_y5TVpQWB537jHfCx9e__Qrisjs-QLQgeposKJIbCxQjjMd_zgD2qg3KhtWWtolUaq_jyGrfxJ1vLIkcapyyBCOIA9BvlT4lIDqjA5YXzABuhOGdiDXxzK_HkUAE-nL-nzIq-nICpavFZqTaF2QZyr5lSVTExy-dztHhyprYk6F5dhNBW0VIXtKeSb6pGedFmFK1OeAAXU_XBm000F__0m00)

### 1. IProjectManagementDatabase (Interface)

   Chức năng:
    Kết nối với cơ sở dữ liệu quản lý dự án.
    Lấy danh sách các mã công việc (charge numbers) dựa trên tiêu chí.
    Khởi tạo cơ sở dữ liệu.
   
### 2. TimecardForm (Lớp giao diện người dùng)

   Chức năng:
    Hiển thị thẻ chấm công.
    Nhập giờ làm việc cho từng ngày.
    Xóa mã công việc khỏi thẻ chấm công.
    Lưu thông tin chấm công.
    Duy trì (chỉnh sửa) thẻ chấm công.
   
### 3. TimecardController (Lớp điều khiển)

   Chức năng:
    Lấy thẻ chấm công hiện tại của một nhân viên.
    Lấy danh sách mã công việc từ cơ sở dữ liệu.
    Cập nhật một mục (entry) chấm công.
    Lưu thẻ chấm công.
   
### 4. Timecard (Lớp chính cho thẻ chấm công)

   Chức năng:
    Tính tổng số giờ làm việc.
    Lấy các mục chấm công của một ngày cụ thể.
    Thêm một mục chấm công.
    Lấy mã nhân viên.
   
### 5. ChargeNumberList

   Chức năng:
    Quản lý danh sách các mã công việc được sử dụng trong thẻ chấm công.
    Kiểm tra một mã công việc có trong danh sách hay không.
    Thêm hoặc xóa mã công việc.
   
### 6. Transaction

   Chức năng:
    Đại diện cho một giao dịch hoặc tác vụ có thể hoàn tác (undo).
    Thực hiện một giao dịch.
    Hoàn tác giao dịch.
   
### 7. TimecardEntry

   Chức năng:
    Đại diện cho một mục (entry) chấm công trên thẻ, với giờ làm việc trong một ngày cụ thể và một mã công việc.
    Kiểm tra tính hợp lệ của mục chấm công.
   
### 8. Employee

   Chức năng:
    Đại diện cho thông tin nhân viên.
    Truy xuất thông tin mã nhân viên.
    
---
## II. Bank System

![Bank System](https://www.planttext.com/api/plantuml/png/X5HBJiCm4Dtd55ucKdk12bMbH1ML448gOZ-rfyZ2dygU52h4oLXm9Av0dBY93HGsJlpcpSoRJ_Bv_h7m18uQhGgkm7ks1FEqENf2pLuBnjZUMOxUtpim7ZX9QqeQtsSiCLGpjhHM8PZWU00b1H1UScuRGoNqpzj6Rz7Ds8QSD8-vooDIPDT889K_wnHfmQbJiqEtQepmvSvP7Oqd-eIH_G61xkyhPO6gh8nUYK7NYjzGUsWy9t_2kkxLBMd6mZbXQCHuhG8nHYZUYjZYAARhx_JNkC6m1GM6OvGO4Fji0kMgyMGrkjYnPSyhgv7916vbA_bRZGzMYc3b3iKVvd4ArrO9T27oa7CeueJqLV1uMzTf2GOqfdTk3RKzNfkTJU0aeG-vRgIdYmZCnuJ9XFgSoHhcQRF2EkPnd-aGmu12Udn1tb3Nm6GN7HxG-GmTf0mp_MU4YK8VwqggcAUBTbUlkWbAXI5FyXLEfyEsv-YuMQU5Qi5XK0cMxdOU8hKKYtPrmt_W2m00__y30000)

### 1.Mô tả hệ thống giao dịch

   Customer: Đại diện khách hàng, liên kết với các tài khoản ngân hàng.
   Transaction: Giao dịch tài chính, hỗ trợ hành vi reverse() để hoàn giao dịch.
   Statement: Tạo báo cáo giao dịch và hỗ trợ xuất ra file PDF.
   Hệ thống đảm bảo tính chính xác khi liên kết khách hàng, quản lý giao dịch, và xuất báo cáo.
   
---
## III. Print Service

![Print Service](https://www.planttext.com/api/plantuml/png/R5DBJiCm4Dtd55wc4hr0X511tGGX18fWxpX3SULFPOyh2k9aB3WILy1EwiHEkhFVFC-yDpF--_dTMAG6dHG54zHQycIumWRCaJCWNmKXnBfMSkpnUzsMUzrM9DvM5RdJMW1LWSceOY1IPhsjI8CUsENC7GH6WnITNV26Gw0T3DU68_-4HRwh63nLf5QOfnVSugqG_f4jVUJ1Nw-Zh9lYkqYzFZjmWzErBs0NR9-ETjqbvw-QTo5iGEhZKc72y7OVuQDlocfACHFYaL76b2K0dMPEWiAARC-dW6R-0s3xTgRz6qPNNfhI37I7ZYAS1v8dYZv6jL74e3QAooKZHm4fmBJ2ti84KOVlsbJanO8vTwbnKb9pAgSj6Ai6rb3H-LDUJL6vA4OPrkfDBziHvPTU-TJHsLooRx1U9wjI95iJ0-7HE4CFZcCQM-N1tkO6L1S-spy0003__mC0)

### 1. Mô tả hệ thống in tài liệu

   User: Đại diện cho người gửi tài liệu.
   PrintJob: Công việc in, được ưu tiên xử lý dựa trên thuộc tính priority.
   PrintQueue: Quản lý hàng đợi in, xử lý công việc theo thứ tự ưu tiên.

---

