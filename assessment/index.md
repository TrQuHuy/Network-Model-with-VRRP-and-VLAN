# ĐÁNH GIÁ MÔ HÌNH

![Mô hình](/assessment/model.png)

Xây dựng một hệ thống mạng doanh nghiệp có tính sẵn sàng cao, khả năng chịu lỗi và bảo mật mạnh mẽ, đáp ứng nhu cầu của một tổ chức có khoảng 100 người dùng.

#### Thiết bị mạng:
- Router Cisco (2 thiết bị): Cần có hai router để cấu hình VRRP, đảm bảo tính dự phòng cho các gateway.
- Switch Layer 3 (2 thiết bị): Để phân đoạn mạng thành các VLAN và hỗ trợ định tuyến giữa các VLAN.
- Switch Layer 2 (2 thiết bị): Để kết nối các máy tính và thiết bị khác trong từng VLAN.
- Thiết bị cân bằng tải: Để phân phối lưu lượng mạng hiệu quả và đảm bảo tính sẵn sàng của các dịch vụ trực tuyến.
- Máy tính người dùng: Các máy tính đầu cuối trong mạng, được chia vào các VLAN khác nhau.
#### Công nghệ và giao thức:
- VRRP (Virtual Router Redundancy Protocol): Được cấu hình trên các router để cung cấp địa chỉ gateway ảo cho các VLAN, đảm bảo khả năng chịu lỗi.
- VLAN (Virtual Local Area Network): Phân chia mạng thành các VLAN khác nhau để tăng cường bảo mật và quản lý.
- Địa chỉ IP: Phân bổ các dải địa chỉ IP tĩnh cho các VLAN, router, và switch.
- Routing: Định tuyến giữa các VLAN qua các switch Layer 3 và router.

## Phân Tích Điểm Yếu Mô Hình Hiện Tại:
- Phức tạp trong quản lý VRRP: Việc cấu hình và duy trì VRRP trên cả switch core và router có thể gây khó khăn và rủi ro nếu không đúng cách.
- Bảo mật VRRP yếu: Thiếu xác thực VRRP có thể dẫn đến tấn công giả mạo.
- Phân tách VLAN chưa đủ: Nếu thiếu chính sách bảo mật, có nguy cơ bị tấn công VLAN hopping.
- Single Point of Failure: Nếu một switch core hoặc router gặp sự cố, toàn bộ mạng có thể bị gián đoạn.

## Đánh Giá An Toàn:
- VRRP: Cần xác thực VRRP để ngăn chặn tấn công giả mạo.
- Phân đoạn mạng: Đảm bảo bảo mật giữa các VLAN để ngăn chặn truy cập trái phép.
- Dự phòng: Đảm bảo không có đơn điểm thất bại trong hệ thống.
- Chính sách bảo mật: Cần thực thi ACL để bảo vệ luồng dữ liệu giữa các VLAN.

## Thiết Kế An Toàn:
- Bảo mật VRRP: Sử dụng xác thực VRRP như MD5.
- Phân tách VLAN bằng ACL: Kiểm soát truy cập giữa các VLAN.
- STP: Ngăn chặn vòng lặp, đảm bảo kết nối ổn định.
- Đa dạng hóa đường truyền: Tạo dự phòng để duy trì hoạt động mạng khi gặp sự cố.
