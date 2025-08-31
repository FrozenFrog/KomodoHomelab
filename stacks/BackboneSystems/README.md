# 🦴 Backbone System  

[![Komodo](https://img.shields.io/badge/stack-komodo-orange.svg)](https://komo.do)
![Status](https://img.shields.io/badge/status-core_system-critical.svg)
![Compose](https://img.shields.io/badge/compose-docker--compose-blue.svg)

---

## 📌 Giới thiệu  

**Backbone System** là **xương sống của toàn bộ hệ thống**, bao gồm những **Docker Compose quan trọng** để đảm bảo hệ thống hoạt động ổn định và liền mạch.  

Đây là lớp hạ tầng tối thiểu cần có để các dịch vụ khác trong homelab có thể chạy đúng cách.  

---

## ⚡ Tại sao tách riêng?  

Việc tách **Backbone System** gồm các container riêng ra khỏi một file compose duy nhất khác nhằm:  

- 🛡 **An toàn**: Nếu một container gặp sự cố, các container quan trọng khác trong Backbone System vẫn tiếp tục hoạt động.  
- 🔄 **Dễ bảo trì**: Quản lý độc lập giữa **dịch vụ cốt lõi** và **dịch vụ bổ sung**.  
- 🚀 **Ổn định**: Giảm nguy cơ ảnh hưởng dây chuyền khi một container không liên quan bị lỗi.  

---

## 🌱 Nguyên tắc  

- Backbone System chỉ chứa **các dịch vụ quan trọng nhất**.  
- Các dịch vụ không ảnh hưởng trực tiếp đến hệ thống chính sẽ đặt ở **stack riêng**.  
- Khi cần rollback, Backbone System sẽ là điểm tựa ổn định để khôi phục các phần khác.  
- Trước tiên install Periphery agent - systemd cho komodo
```
curl -sSL https://raw.githubusercontent.com/moghtech/komodo/main/scripts/setup-periphery.py | python3
```
- Copy file core.config.yaml và periphery.config.toml vào /etc/komodo/
- Sau đó chạy periphery theo hướng dẫn tại https://komo.do/docs/setup/connect-servers
- Tiếp theo mới start stack komodo
---

## ❤️ Ghi chú  

Đây là **trái tim của homelab**, vì vậy hãy đảm bảo **luôn kiểm tra kỹ trước khi chỉnh sửa** bất kỳ thành phần nào trong Backbone System.  
