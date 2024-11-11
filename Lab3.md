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
