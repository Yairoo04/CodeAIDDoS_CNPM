# Đồ Án Nhập Môn Công Nghệ Phần Mềm
## Giới Thiệu
> - Tên đề tài: Hệ thống phát hiện tấn công DDoS dựa trên AI
> - Mục tiêu: Xây dựng được một hệ thống phát hiện DDoS và có khả năng tự động chặn ip tấn công
> - Hệ thống được triển khai trên hệ điều hành linux

## Xây dựng PfSense
Bạn có thể tham khảo thông qua link này: [Hướng dẫn cài đặt PfSense](https://thegioifirewall.com/pfsense-huong-dan-cai-dat-firewall-pfsense-len-vmware/)
![image](https://github.com/user-attachments/assets/0975afb2-3b52-4a5f-a5b9-656b0360e012)

PfSense cần ít nhất 2 network adapter:
  - Một adapter để giao tiếp với mạng ngoài
  - Một adapter để quản lý mạng nội bộ, cấp phát IP, thực hiện NAT, tường lửa… cho các máy nằm phía sau pfSense
Bạn có thể tùy chỉnh để phù hợp với cấu hình của máy nhưng phải đáp ứng được ít nhất 2 network adapter cho PfSense

Sau khi cài đặt xong PfSense ta cần phải cấu hình phù hợp để quản lý:
  - Đây là ip của PfSense để ra Internet
    
  ![image](https://github.com/user-attachments/assets/5bc6f541-5361-4788-9f66-1138afc34148)

  - Đây là ip của PfSense trong mạng nội bộ, thường là 192.168.1.1
    
  ![image](https://github.com/user-attachments/assets/56f85cc3-9390-4a3c-a162-7fb9d213d2da)

  - Thiết lập rule để hệ thống có thể giao tiếp với máy bên ngoài tường lửa
    
  ![image](https://github.com/user-attachments/assets/6ab8aa07-e18b-4e67-a92e-2ae7ae87d615)

  - Ở đây chỉ cho phép hệ thống (192.168.1.100) giao tiếp với các máy bên ngoài thông qua cổng 5001 và giao thức TCP/UDP
    
  ![image](https://github.com/user-attachments/assets/953e5b2e-61e3-4961-b532-4fbfc5b5a85d)

**Lưu ý:** Sau khi tải mã nguồn về, bạn cần thay đổi `pfsense_host`, `username`, `password` trong `backend/block.py` để phù hợp với hệ thống của bạn

## Tải và sử dụng hệ thống
```
$ git clone https://github.com/Yairoo04/CodeAIDDoS_CNPM.git
$ python3 app/app.py
```
- Hệ thống sẽ chạy trên ip local thông qua port 5000
- Bạn có thể thử mô phỏng tấn công UDP để kiểm thử hệ thống (sử dụng hping3 hoặc cách khác)


  




  
