# F. Gỡ lỗi:
nếu có lỗi xẩy ra trong quá trình triển khai docker compose up -d
Kiểm tra nhanh: docker compose ps giúp biết container nào đang chạy xem log, ví dụ: docker logs mynginx docker logs myapi
<img width="1454" height="209" alt="image" src="https://github.com/user-attachments/assets/1ac5ed48-f84f-479d-b36c-5da3caf08904" />

Thêm healthcheck cho myapi trong file docker-compose.yml
healthcheck:
  test: ["CMD", "curl", "-f", "http://localhost:9630"]
  <img width="1462" height="759" alt="image" src="https://github.com/user-attachments/assets/4f956781-2ffa-496a-91f8-9fa3b4510d6a" />
<img width="1460" height="188" alt="image" src="https://github.com/user-attachments/assets/0eeb6800-20a8-410e-b470-88e58d6041de" />

giới hạn resource cho một service: (tránh việc 1 service chiếm quá nhiều ram)
deploy:
  resources:
    limits:
      memory: 512M
<img width="1474" height="759" alt="image" src="https://github.com/user-attachments/assets/94d51f3c-db78-40d9-a585-abdbcfeef8b1" />

sử dụng lệnh: docker compose stats để quan sát lượng ram sử dụng bởi mỗi service
<img width="1364" height="197" alt="image" src="https://github.com/user-attachments/assets/bc872dca-6cd6-4322-86e2-22ca8cb33251" />
