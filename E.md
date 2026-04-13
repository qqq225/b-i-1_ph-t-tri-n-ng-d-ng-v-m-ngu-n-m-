# E. Triển khai (level test) ứng dụng
Chuyển vào trong thư mục ~/myapp
Gõ lệnh để docker compose chạy: sẽ run tất cả các service khai báo trong file docker-compose.yml
<img width="1452" height="167" alt="image" src="https://github.com/user-attachments/assets/f51434a4-095e-4122-888c-cc72eedd9e1d" />
Lợi ích: Chỉ cần docker-compose up -d là toàn bộ hệ thống (Web + Node-RED + Tunnel) tự chạy,
Kiểm tra các container đang chạy trong docker, nếu có cái nào bị restart cần tìm lỗi rồi edit lại docker-compose.yml
<img width="1461" height="184" alt="image" src="https://github.com/user-attachments/assets/36e46ba2-003e-467e-8730-31963213ff85" />
Sử dụng nodered: kéo nodered http_in , http_response, function : để tạo api get đơn giản (dùng cho /api proxy_pass của nginx)
<img width="771" height="206" alt="image" src="https://github.com/user-attachments/assets/db097971-979e-47a6-9a0f-fdaeb8816ab0" />
Sửa file ./myweb/index.html : thêm code html+js để sử dụng được api đã khai báo proxy_pass (thực ra là sử dụng nodered http_in hoặc sử dụng service myapi)
<img width="1461" height="762" alt="image" src="https://github.com/user-attachments/assets/56bfd3d7-5f37-4436-93af-18a0bf5ab09d" />
<img width="1158" height="871" alt="image" src="https://github.com/user-attachments/assets/3c5ac64f-1e7e-42cd-886a-5ac5348bad59" />
