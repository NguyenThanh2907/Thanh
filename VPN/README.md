1. Chuẩn bị:
- 1 máy ảo Windows 10.
- 1 máy ảo Ubuntu 20.04.
- 1 máy ảo Windows 7.
2. Mô hình:
 ![image](https://github.com/user-attachments/assets/0a5bef61-8010-4b41-b46f-4018ecbc00e9)
- Thông tin thiết bị:
   + Windows 10: 192.168.20.26
   + Ubuntu – VPN Server: 192.168.20.21
                          172.16.0.5
   + Windows 7: 172.16.0.14
III. Thực hiện:
1. Cài đặt trên máy Ubuntu:
- Cài đặt OpenVPN Server:
 ![image](https://github.com/user-attachments/assets/eb17b868-dbd8-45ec-a384-70d73f522d42)
- Tạo easy-rsa:
 ![image](https://github.com/user-attachments/assets/8ffa4874-71dc-4da5-838b-8dc136228d5f)
- Thay đổi chủ sở hữu của các tập tin:
 ![image](https://github.com/user-attachments/assets/74d9bf6f-4902-4a39-9a21-962a0bc9336e)
- Tạo PKI:

  ![image](https://github.com/user-attachments/assets/7582b6ed-1587-40f9-a498-8824905f5026)
- Tạo các DIR để giữ các tệp:
 ![image](https://github.com/user-attachments/assets/18d4a24f-632e-47c6-9e67-4010094e4aa9)
- Dựng CA:
 ![image](https://github.com/user-attachments/assets/e7e0d55f-0cf5-4be5-8d02-ce5135134530)
- Dựng chứng chỉ và khóa cho Server:
 ![image](https://github.com/user-attachments/assets/b592876e-2ccb-44fe-b587-2bcac38db189)
- Tạo CRL:
 ![image](https://github.com/user-attachments/assets/11f5974e-f483-4992-93af-11c22c97724c)
- Tạo tham số DH:
 ![image](https://github.com/user-attachments/assets/b275f320-85d6-409c-9bca-903594e38832)
- Tạo khóa mật mã TLS:
 ![image](https://github.com/user-attachments/assets/4311cf67-e57b-4b70-8a6e-f8b02f382e6d)
- Sao chép các tệp cần thiết vào thư mục server:
  ![image](https://github.com/user-attachments/assets/2599305a-47d0-4b10-a311-22010a3b06bf)
- Dựng chứng chỉ và khóa cho Windows client:
 ![image](https://github.com/user-attachments/assets/df63a39e-9bc3-430c-9f4a-bd91b9c8938c)
- Sao chép các tệp Windows client:
 ![image](https://github.com/user-attachments/assets/0437253e-a2c5-4c41-bfcf-95304fd7082b)
- Nén thư mục client:
 ![image](https://github.com/user-attachments/assets/163b3909-4c75-416f-a2ff-0cb7497cded5)
- Đưa tệp zip sang máy client:
 ![image](https://github.com/user-attachments/assets/5dbe127b-789b-40f8-bc9d-90b590ecd0ee)
- Sao chép các tệp server sang thư mục server:
 ![image](https://github.com/user-attachments/assets/1765dd9c-0246-4519-92a2-bab96555719b)
- Cấp cho server khả năng chuyển tiếp IP:
 ![image](https://github.com/user-attachments/assets/799d5582-a0eb-4c93-94cc-e825ebeadb94)
- Tạo tệp cấu hình:
  
  ![image](https://github.com/user-attachments/assets/4c68a34b-630e-4ea8-adde-36c47eef5695)
  ![image](https://github.com/user-attachments/assets/02a71053-fe0b-441a-8345-2429d53f364b)
- Bật dịch vụ OpenVPN Server:
 ![image](https://github.com/user-attachments/assets/e36947f9-53d8-451e-9030-a612bd1a0012)
- Thêm luật iptables:
 ![image](https://github.com/user-attachments/assets/01ebee26-3337-44e7-976a-9254f568ea50)
 ![image](https://github.com/user-attachments/assets/02f84e9f-6bca-4a04-8f10-c2febfa3a647)
2. Cài đặt trên máy Windows 10:
- Truy cập vào https://openvpn.net/community-downloads/ , chọn phiên bản 2.5.5 và tải tệp .msi ở mục Windows 64-bit MSI installer:
 ![image](https://github.com/user-attachments/assets/143460be-fabd-4bee-bb6d-a01936775ebb)
- Sau khi tải về và chạy tệp ta được OpenVPN:
 ![image](https://github.com/user-attachments/assets/90fa99d8-ac5e-4894-8370-a1adce817b33)
- Giải nén tệp zip win_client:
 ![image](https://github.com/user-attachments/assets/25736ca1-7a36-4fc5-a751-eb81ee7201cd)
- Sao chép các tệp trong thư mục win_client vào thư mục C:\Program Files\OpenVPN\config:
 ![image](https://github.com/user-attachments/assets/e15e87e3-9769-4bed-b9a6-edae6c881dda)
- Tạo tệp client.ovpn và thêm nội dung vào tệp:
 ![image](https://github.com/user-attachments/assets/104aa825-5491-40b5-a479-b2eb29104209)
 ![image](https://github.com/user-attachments/assets/6f6e1ecb-2a9c-4b25-a613-bb0b7542756f)
- Sao chép tệp client.ovpn sang thư mục C:\Program Files\OpenVPN\config:
 ![image](https://github.com/user-attachments/assets/4bd1991e-dbbe-4ccb-88c2-97c5b5e9f547)
- Nhấp chuột phải vào biểu tượng OpenVPN, chọn Connect và nhập mật khẩu:
 ![image](https://github.com/user-attachments/assets/2787cff6-4302-4414-b000-9e6f68fa54b5)
 ![image](https://github.com/user-attachments/assets/bc0c8595-ae44-4e2b-9454-87d81b0b4418)
3. Kiểm tra kết nối:
- Ping từ máy Windows 10 sang máy Windows 7:
  
  ![image](https://github.com/user-attachments/assets/86cf0c9a-4737-42da-984d-12da4f765bae)
- Thực hiện truy cập vào tệp của máy Windows 7:
 ![image](https://github.com/user-attachments/assets/136e1019-3e52-4d6c-a017-e2e257b59188)
- Thử xóa thư mục test, thư mục biến mất ở máy Windows 7:
 ![image](https://github.com/user-attachments/assets/e83cd72b-dd21-4871-bbf4-141a04183404)
 ![image](https://github.com/user-attachments/assets/c9dd799a-445d-41e0-85b7-b2fda5517efe)


 


