# B. Cài đặt Ubuntu + Docker
1. Cài đặt hệ điều hành Ubuntu 24.04.4 LTS
Sử dụng một trong các công cụ để giả lập: VM_Ware (bản quyền)
Download file iso để cài đặt.
Cấu hình mạng trong Ubuntu (và công cụ giả lập) để cho phép truy cập SSH vào Ubuntu từ cmd của windows
2. Tìm hiểu các lệnh cơ bản của ubuntu
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
3. Cài đặt docker cho Ubuntu
Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose
Cấu hình để docker chạy mà không cần tiền tố sudo
Tìm hiểu tập lệnh của docker và docker compose
Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)
