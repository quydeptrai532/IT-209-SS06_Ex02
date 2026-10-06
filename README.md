# Bài 2: Cấu hình phân quyền Nhóm và sudoers

## Các bước thực hiện

Tạo nhóm:

```bash
sudo groupadd devops-admin

Tạo user:
sudo adduser deployer

Thêm user deployer vào nhóm devops-admin:
sudo usermod -aG devops-admin deployer

Mở sudoers:
sudo EDITOR=nano visudo

Thêm dòng:
%devops-admin ALL=(ALL) NOPASSWD: /usr/bin/systemctl start *, /usr/bin/systemctl stop *, /usr/bin/systemctl restart *, /usr/bin/systemctl status *

Chuyển sang user deployer:
su - deployer

Kiểm tra quyền:
sudo -l

Kết quả
User deployer thuộc nhóm devops-admin và có quyền chạy các lệnh systemctl start, stop, restart, status mà không cần nhập mật khẩu.


![alt text](<Screenshot 2026-10-06 225340-1.png>)
```
