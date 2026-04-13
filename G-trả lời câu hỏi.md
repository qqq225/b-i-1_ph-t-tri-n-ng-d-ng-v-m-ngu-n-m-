# Giải đáp các câu hỏi kỹ thuật đồ án
1. Tại sao dùng Nginx làm Reverse Proxy mà không trỏ thẳng Tunnel vào Node-RED?
Quản lý tập trung: Nginx đóng vai trò "cửa ngõ", cho phép chạy nhiều dịch vụ (Web tĩnh, Node-RED API, Database UI) trên cùng một tên miền thông qua các đường dẫn khác nhau (/, /api).

Bảo mật & Hiệu suất: Nginx xử lý các tệp tĩnh cực nhanh và giúp ẩn thông tin trực tiếp của backend Node-RED, tăng khả năng chịu tải và bảo mật.

2. Sự khác biệt giữa Mount file và Mount thư mục?
Mount file: Chỉ gắn một tệp cụ thể vào container. Nếu tệp đó bị xóa trên máy host, liên kết có thể bị gãy.

Mount thư mục: Gắn toàn bộ thư mục. Mọi tệp mới tạo hoặc thay đổi bên trong thư mục ở máy host đều được đồng bộ ngay lập tức vào container.

3. Thay đổi file index.html ở máy Ubuntu, nội dung web có đổi ngay không?
Có. Vì chúng ta sử dụng Bind Mount thư mục ./myweb. Nginx đọc trực tiếp file từ thư mục đó, nên khi bạn sửa ở Ubuntu, Nginx sẽ phục vụ nội dung mới ngay khi người dùng F5 trình duyệt.

4. Ý nghĩa của restart: always và unless-stopped?
always: Luôn tự động khởi động lại container nếu nó bị dừng (lỗi hoặc máy chủ khởi động lại).

unless-stopped: Tương tự always, nhưng nếu bạn chủ động dùng lệnh docker stop thì nó sẽ không tự chạy lại khi máy chủ restart.

5. Khai báo Network dùng chung và lợi ích?
Cách làm: Docker Compose mặc định tạo một network chung cho các services trong cùng file. Có thể khai báo tường minh bằng khối networks:.

Lợi ích: Các container có thể gọi nhau bằng Tên Service (như http://nodered:1880) thay vì dùng IP vốn thường xuyên thay đổi. Điều này giúp hệ thống linh hoạt và bảo mật nội bộ.

6. Bảo mật với tệp .env và .gitignore
Cách làm: Lưu token vào file .env dạng CF_TOKEN=..., trong compose dùng ${CF_TOKEN}. Thêm tên .env vào .gitignore.

Tầm quan trọng: Tránh lộ thông tin nhạy cảm (Token, mật khẩu) lên GitHub. Nếu lộ Token, người khác có thể chiếm quyền điều khiển đường truyền (Tunnel) của bạn.

7. Tại sao nên thêm hậu tố :ro khi mount cấu hình Nginx?
:ro (Read-Only): Chỉ cho phép container đọc file, không cho phép sửa đổi ngược lại máy host. Điều này bảo vệ file cấu hình gốc khỏi các lỗi vô ý hoặc mã độc từ bên trong container.

8. Có cần mở cổng (ports) khi dùng Cloudflare Tunnel không?
Không cần thiết. Cloudflare Tunnel tạo kết nối từ trong ra ngoài (outbound). Bạn có thể xóa phần ports trong docker-compose.yml (ngoại trừ lúc cần debug nội bộ), giúp máy chủ an toàn hơn vì không để lộ cổng ra Internet công cộng.
