LAB 3: IDENTIFY DESIGN ELEMENTS
1. Subsystem context diagrams

  a) Sơ đồ hệ thống con của [banksystem](//www.plantuml.com/plantuml/png/fL0zJiCm5DvzYhUr2De3L95LmTG1gH8dS1stjfey1zkfY82PWGLkK0Q4G4A8jHdRY_WcE4sZje6D34dy_VZxtXjQnupBquHqOFFaoqUKW3EvUMV0roySd5ml0vH9ltf3MAoN5VAHrgHrmWZjYap0nA--SRQ59LXVVaBiozU0H17X2RCMngmmEaakDBhgAqoWU7sW56u9XEVKvBZJTK_8FI4AGyIKSG6ZSuRpgo94fequ5fcsodLPi70f-7m0pTyP1AUkB0EetYESQfCofpHkx-t0fI-V5Lpd347wyW5cofTVVmrDVXVlzUXHdm74oWZkODV8mhO4B1GZXxhehj-7_Nbiz4rn9AWkRaPe4-qvo7wlTLeK2NJA5PJMJDjmAAWLxIv1OVE9hIEp2g7q_yiU2eppDFa1)
  
  b) Giải thích:
  
  - PayrollController: Được biểu diễn là một lớp control, có phương thức runPayroll().
  - IBankSystem: Được biểu diễn là một interface có phương thức deposit(aPaycheck: Paycheck, intoBank: BankInformation), mô tả chức năng nạp tiền.
  - BankSystemProxy: Biểu diễn một hệ thống con BankSystem dưới dạng subsystem, thể hiện hành động deposit.
  - Paycheck và BankInformation: Được biểu diễn là các thực thể (entity), đóng vai trò là các đối tượng dữ liệu được truyền vào trong quá trình xử lý của BankSystem.
  - Mối quan hệ:
      +  PayrollController liên kết với IBankSystem để thực hiện hành động deposit.
      +  BankSystemProxy thực hiện IBankSystem.
      +  IBankSystem phụ thuộc vào Paycheck và BankInformation trong quá trình hoạt động.
   
3. Design element to owning package map
Phân loại gói [package](https://www.planttext.com/api/plantuml/png/R94nRiCm34LtdOBmRdGF0YDfEsP8wnCmAj4ALII7f0mOHK-M8KVA5IerDUh40JZnlqTyGUVZQIMAh6dlJOVs4zy9gZNR3wTaDJ5wsE10B1Ly6O0yDkwx62XevhhEEulgOgXWkVG5R1f0WKbohJmcSO54e2NkdIMv4STyZA_jPrI4jStxMwyabs1kx53e3bxMboTDsa9TDxCIi80dz1uUu9KEYKIpCsEA-DyYAo-9UCZEbkDVhqayqgL4PbkDJB_tbHtrPCotML5uAz_o0m00__y30000)
giải thích:
  a) gói Middleware::Security::GUI Framework: giao diện bảo mật, có 2 phần tử thiết kế:
    - LoginForm
    - MainApplicationFor
  b) gói Applications::Employee Activities: có 2 phần tử thiết kế:
    - MainEmployeeForm
    - TimecardForm
  c) gói Applications::Payroll: quản lý chức năng bảng lương, có 2 phần tử thiết kế:
    - TimecardController
    - PayrollController
  d) gói Business Services::Payroll Artifacts: quản lý dữ liệu bảng lương, có 1 phần tử thiết kế:
    - Paycheck
  e) gói Applications::System: thời gian hệ thống, có 1 phần tử:
    - SystemClockInterface

4. Architectural layers and their dependencies
[Sơ đồ mô tả hệ thống](https://www.planttext.com/api/plantuml/png/R94nRiCm34LtdOBmRdGF0YDfEsP8wnCmAj4ALII7f0mOHK-M8KVA5IerDUh40JZnlqTyGUVZQIMAh6dlJOVs4zy9gZNR3wTaDJ5wsE10B1Ly6O0yDkwx62XevhhEEulgOgXWkVG5R1f0WKbohJmcSO54e2NkdIMv4STyZA_jPrI4jStxMwyabs1kx53e3bxMboTDsa9TDxCIi80dz1uUu9KEYKIpCsEA-DyYAo-9UCZEbkDVhqayqgL4PbkDJB_tbHtrPCotML5uAz_o0m00__y30000)
