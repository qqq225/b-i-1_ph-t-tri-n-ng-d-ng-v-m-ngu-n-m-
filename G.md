# G. Triển khai ứng dụng đến End-user
Trong Cloudflare: Tạo tunnel (đường hầm), chọn loại triển khai cho docker
<img width="1486" height="777" alt="image" src="https://github.com/user-attachments/assets/3f337978-a394-45b1-877d-de178f8b75ed" />
Convert lệnh docker run ... sang dạng docker compose
Khai báo kết quả convert vào trong file docker-compose.yml
<img width="1477" height="757" alt="image" src="https://github.com/user-attachments/assets/2fb3d77a-f4fa-49ec-ac17-1b6bb9ecd6f5" />
Chạy lại docker compose
<img width="1457" height="245" alt="image" src="https://github.com/user-attachments/assets/19eadf63-d93c-4dd9-a1dc-7e8da0458e8d" />
Public ứng dụng bằng cách thêm 1 router trỏ tới container đang chạy trong docker, dữ liệu sẽ đi qua tunnel, url dạng sub-domain
Kiểm tra url sub-domain đã hoạt động public cho mọi end-user
<img width="1450" height="928" alt="image" src="https://github.com/user-attachments/assets/f7a4c847-457f-4102-9fd7-99e01f68ca97" />
<img width="1125" height="2436" alt="image" src="https://github.com/user-attachments/assets/d00911af-6b0a-4249-a3b7-ef76917be5d0" />
