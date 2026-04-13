# C. Cấu hình docker compose:
**1. Cấu Hình**
Tạo thư mục: ~/myapp
Chuyển vào trong thư mục ~/myapp
<img width="469" height="94" alt="image" src="https://github.com/user-attachments/assets/4eaa905b-428a-43ca-914f-b4ed76204497" />

Tạo thư mục: ./myweb
Tạo file ./myweb/index.html (với nội dung là thông tin cá nhân của em)
<img width="683" height="56" alt="image" src="https://github.com/user-attachments/assets/830cecfc-6942-4c4f-b390-4be19298a43e" />
<img width="1100" height="528" alt="image" src="https://github.com/user-attachments/assets/4c58284c-f339-4764-814b-567113658619" />
Tạo file docker-compose.yml để nó sẽ có các dịch vụ sau:
Khai báo sử dụng nodered/node-red, cổng 1880, dữ liệu nằm tại thư mục ./nodered
Khai báo sử dụng nginx, cổng 80, cấu hình trong file ./nginx/nginx.conf
<img width="1282" height="592" alt="image" src="https://github.com/user-attachments/assets/a198259a-bdee-46c3-9b58-4808733f2e5b" />

Mount thư mục ./myweb thành thư mục /myweb trong nginx
Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
Edit file ./nginx/nginx.conf để:
Cấu hình web server cổng 80
server_name là sub-domain (sub-domain tuỳ ý của em)
location / trỏ tới root là thư mục /myweb
location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
<img width="1135" height="579" alt="image" src="https://github.com/user-attachments/assets/31b1e45f-57ad-4a56-adb4-8e5f624073d3" />

Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
<img width="1477" height="746" alt="image" src="https://github.com/user-attachments/assets/6b76ed07-f3c6-4b51-b0ba-4d74ad43a618" />

**2. Kiểm tra các dịch vụ:**
- nginx:
  <img width="859" height="397" alt="image" src="https://github.com/user-attachments/assets/1a0e9193-df10-47d1-96cf-a71cc4f261e7" />
- nodered:
  <img width="1763" height="908" alt="image" src="https://github.com/user-attachments/assets/33c68251-1f16-489a-8784-5a3670b224f3" />

