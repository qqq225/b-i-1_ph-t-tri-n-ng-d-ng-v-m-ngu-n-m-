# B. Cài đặt Ubuntu + Docker
# 1. Cài đặt hệ điều hành Ubuntu 24.04.4 LTS
Sử dụng một trong các công cụ để giả lập: VM_Ware (bản quyền)
Download file iso để cài đặt.
<img width="1875" height="858" alt="image" src="https://github.com/user-attachments/assets/201408f9-ba22-4394-b6b2-38dfbcdef05b" />

Cấu hình mạng trong Ubuntu (và công cụ giả lập) để cho phép truy cập SSH vào Ubuntu từ cmd của windows
<img width="1116" height="761" alt="image" src="https://github.com/user-attachments/assets/8a17a856-3505-4d8a-adce-f212227c0b00" />

# 2. Tìm hiểu các lệnh cơ bản của ubuntu
Các lệnh cần tìm hiểu:
 - Liệt kê các file trong thư mục: ls
 - Tạo thư mục: mkdir nameFolder
 - Chuyển thư mục làm việc: cd path
 - Copy file: cp file_nguồn path/file_đích
 - Thay đổi quyền thao tác file: sudo chmod xxx filename
 - Edit file: sudo nano tenfile
 - CTRL+o : lưu nội dung sau khi edit
 - CTRL+x : thoát edit file
 - Xem ip của máy ubuntu: ip -4 addr
# 3. Cài đặt docker cho Ubuntu
# Cập nhật hệ thống
- sudo apt update
- sudo apt install ca-certificates curl gnupg lsb-release -y

# Thêm khóa GPG chính thức của Docker
- sudo mkdir -p /etc/apt/keyrings
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Thiết lập repository
- echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Cài đặt Docker engine
- sudo apt update
- sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
  <img width="1480" height="751" alt="image" src="https://github.com/user-attachments/assets/3241ea6a-b183-42a5-9723-f397e74cad0b" />

Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose
<img width="595" height="120" alt="image" src="https://github.com/user-attachments/assets/d0cc2ee2-32f1-4ae2-beaf-6a03db8aa690" />

Cấu hình để docker chạy mà không cần tiền tố sudo
<img width="865" height="123" alt="image" src="https://github.com/user-attachments/assets/d6db5360-6d18-4283-9f69-cef6e99c1d82" />

Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)
<img width="1471" height="739" alt="image" src="https://github.com/user-attachments/assets/c640f0e8-88b1-4a70-bce7-2d290ff0267e" />

