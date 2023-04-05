# Netmiko

![image](https://user-images.githubusercontent.com/129259654/229759773-2c669390-c33f-4b29-aa1a-19830ab21448.png)
 ## Tổng quan
 
 Netmiko là thư viện mã nguồn mở của Python giúp đơn giản hóa việc quản lý SSH cho các thiết bị mạng. Đây là một thư viện phổ biến và dễ sử dụng vì Netmiko hỗ trợ nhiều thiết bị của nhà cung cấp. Sau đây là một số thiết bị của nhà cung cấp được hỗ trợ bởi Netmiko: Arista vEOS, Cisco ASA, Cisco IOS, Cisco IOS-XR, Cisco NX-OS, Cisco SG300, HP Comware7, Cisco IOS-XE, HP ProCurve, Juniper Junos, Linux,..
  - Mục đích của thư viện Netmiko
    
    Thiết lập thành công kết nối SSH với thiết bị.
    
    Đơn giản hóa việc thực thi, truy xuất và định dạng các lệnh hiển thị.
    
    Đơn giản hóa việc thực hiện các lệnh cấu hình.
    
    Tóm tắt phần lớn cơ chế tương tác với thiết bị ở mức độ thấp.
    
    Cung cấp một API thống nhất (tương đối) để tương tác với các thiết bị.
    
    Thực hiện những điều trên trên một loạt các nhà cung cấp và nền tảng mạng.
  - Nền tảng hỗ trợ
  
   Netmiko hiện hỗ trợ khoảng 80 nền tảng khác nhau. Để biết danh sách gần như đầy đủ các nền tảng được hỗ trợ, có thể truy cập  tại địa chỉ dưới đây để xem thêm: https://github.com/ktbyers/netmiko/blob/develop/PLATFORMS.md
  
   Ngoài hỗ trợ SSH, Netmiko cũng hỗ trợ sao chép an toàn, kết nối telnet và kết nối nối tiếp. Hỗ trợ nền tảng cho mỗi cái này hạn chế hơn SSH. Một lần nữa, hãy xem tại tệp  https://github.com/ktbyers/netmiko/blob/develop/PLATFORMS.md để biết thêm chi tiết về các nền tảng được hỗ trợ cho các trường hợp sử dụng này.

## Bắt đầu với Netmiko
- Cài đặt thư viện Netmiko cho Python

   Thư viện Netmiko mặc định sẽ không được cài đặt sẳn trong Python. Do đó chúng ta có thể cài đặt chúng. Để cài cặt máy tính chúng ta cần có kết nối Internet. Sau đó chúng ta nhấn tổ hợp Windows + R sao đó nhập cmd để vào cửa sổ Terminal:
![image](https://user-images.githubusercontent.com/129259654/229761052-d86385e0-373f-4a11-af19-8e3db78141b3.png)

Sau đó nhập lệnh sau để cài đặt Netmiko: pip install netmiko để cài đặt:

![image](https://user-images.githubusercontent.com/129259654/229761129-e6336567-45c0-4b61-b7b9-7f570832486f.png)

-> Như vậy chúng ta đã cài đặt thư viện Netmiko thành công. 
- Bắt đầu chương trình

  Đầu tiên chúng ta import ConnectHandler() từ thư viện Netmiko sử dụng để thiết lập kết nối SSH:
![image](https://user-images.githubusercontent.com/129259654/229761318-7ec9b324-4569-4fe7-82db-2adf7b636f32.png)
  Tiếp theo chúng ta tạo một biến theo kiểu Dictionary để chứa thông tin thiết bị:
 ![image](https://user-images.githubusercontent.com/129259654/229761395-90bbaf25-e417-4690-9d9c-8a9875a6049f.png)
(Lưu ý: Ở đây danh sách sẽ bao gồm các cặp giá trị Key : Value. Trong đó:
     device_type: Tên thiết bị.
     ip: Địa chỉ của thiết bị.
     username: Là tên truy cập SSH vào thiết bị.
     password: Là mật khẩu truy cập SSH vào thiết bị.
     secret: Là password enable trên thiết bị ).
- Tiếp theo thiết lập kết nối SSH đến thiết bị và vào mode enable bằng lệnh sau:
![image](https://user-images.githubusercontent.com/129259654/229761473-e7014646-778e-4dd0-a1cf-5e0c9ec319ff.png)
Từ đó chúng ta có thể xem thông tin cũng như cấu hình cho các thiết bị thông qua các dòng lệnh sau:
![image](https://user-images.githubusercontent.com/129259654/229761543-09b6affc-e009-4d2d-bd39-17c50e915a64.png)
->Hàm send_command() chỉ cho phép thực hiện một dòng lệnh vì thế chúng ta có thể sử dụng lệnh sau để cấu hình cho thiết bị:
![image](https://user-images.githubusercontent.com/129259654/229761617-e838e9a0-7927-4ee1-9b42-af7cd3866131.png)
-> Dùng để tạo địa chỉ DHCP cho cổng E0/0

