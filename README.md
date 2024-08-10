# NETWORK MODEL WITH VRRP AND VLAN

Mô hình này mô phỏng một hệ thống mạng sử dụng công nghệ VRRP (Virtual Router Redundancy Protocol) để đảm bảo tính sẵn sàng cao cho các gateway trong mạng và VLAN (Virtual Local Area Network) để phân đoạn và tăng cường bảo mật cho hệ thống.

## Thành Phần Mạng

### Switch Core:
sw-Core1 và sw-Core2: Đóng vai trò là switch trung tâm, đảm bảo kết nối giữa các router và các switch phân phối (distribution switch).
### Router:
R1 và R2: Sử dụng VRRP để cung cấp địa chỉ IP ảo cho các mạng con khác nhau nhằm đảm bảo tính sẵn sàng cao.
### Switch:
sw_lan1 và sw_lan2: Kết nối các thiết bị đầu cuối (VPC8, VPC9) với hệ thống mạng chính.
### Thiết bị đầu cuối:
VPC8 và VPC9: Các thiết bị đầu cuối được kết nối trong các VLAN khác nhau để kiểm tra kết nối và tính bảo mật.
