### *[HOT] Video 15p* -* Hướng Dẫn Chi Tiết Tạo 400GB VPS Window | Admin SSH 24/7 MIỄN PHÍ Trên GITHUB | Không Thanh Toán*

#### ![🪜](https://static.xx.fbcdn.net/images/emoji.php/v9/t3/1/16/1fa9c.png) Các bước cài đặt chi tiết

#### 1\. Cài đặt thư viện

sudo apt update\
sudo apt install docker.io docker-compose

#### 2\. Cập nhật hệ thống

sudo apt update

#### 3\. Cài đặt Docker & Docker Compose

sudo apt install docker.io docker-compose -y

![✅](https://static.xx.fbcdn.net/images/emoji.php/v9/t33/1/16/2705.png) Kiểm tra sau khi cài:

docker -v\
docker compose version

#### ![📂](https://static.xx.fbcdn.net/images/emoji.php/v9/tfb/1/16/1f4c2.png) Cấu trúc file docker-compose

Tạo file `windows10.yml` với nội dung:

`version: "3.8"`\
`services:`\
`windows:`\
`image: dockurr/windows`\
`container_name: windows`\
`environment:`\
`VERSION: "10"`\
`USERNAME: "MASTER"`\
`PASSWORD: "admin@123"`\
`RAM_SIZE: "8G"`\
`CPU_CORES: "4"`\
`DISK_SIZE: "600G"`\
`DISK2_SIZE: "200G"`\
`devices:`\
`- /dev/kvm`\
`- /dev/net/tun`\
`cap_add:`\
`- NET_ADMIN`\
`ports:`\
`- "8006:8006"`\
`- "3389:3389/tcp"`\
`- "3389:3389/udp"`\
`stop_grace_period: 2m`

#### ![▶️](https://static.xx.fbcdn.net/images/emoji.php/v9/t40/1/16/25b6.png) Chạy Windows trong Docker

sudo docker-compose -f windows10.yml up -d

#### ![🐛](https://static.xx.fbcdn.net/images/emoji.php/v9/t1d/1/16/1f41b.png) Các lỗi thường gặp & cách khắc phục

LỗiCách sửa

`no configuration file provided`

Thêm `-f windows10.yml` vào lệnh

`Cannot access /dev/kvm`

Kiểm tra xem KVM đã bật chưa: `ls -la /dev/kvm`

`permission denied on /dev/kvm`

Thêm user vào nhóm `kvm`: `sudo usermod -aG kvm $USER && newgrp kvm`

`image not found`

Kiểm tra kết nối mạng, thử `docker pull dockurr/windows` trước

Không lưu được dữ liệu ổ đĩa sau khi restart

Mount volume hoặc sử dụng `named volumes`

#### ![🌐](https://static.xx.fbcdn.net/images/emoji.php/v9/taa/1/16/1f310.png) Tốc độ mạng trong VPS

Bạn có thể test tốc độ mạng tại: ![👉](https://static.xx.fbcdn.net/images/emoji.php/v9/t51/1/16/1f449.png) https://fast.com

#### ![📎](https://static.xx.fbcdn.net/images/emoji.php/v9/tae/1/16/1f4ce.png) Tham khảo

-   [](https://github.com/dockur/windows)[](https://github.com/dockur/windows)[](https://github.com/dockur/windows)[](https://github.com/dockur/windows)[](https://github.com/dockur/windows)<https://github.com/dockur/windows>

-   [](https://docs.docker.com/engine/install/)[](https://docs.docker.com/engine/install/)[](https://docs.docker.com/engine/install/)[](https://docs.docker.com/engine/install/)[](https://docs.docker.com/engine/install/)<https://docs.docker.com/engine/install/>

-   [](https://docs.docker.com/compose/)[](https://docs.docker.com/compose/)[](https://docs.docker.com/compose/)[](https://docs.docker.com/compose/)[](https://docs.docker.com/compose/)<https://docs.docker.com/compose/>

#### ![🧼](https://static.xx.fbcdn.net/images/emoji.php/v9/tce/1/16/1f9fc.png) Gỡ cài đặt (nếu cần)

sudo docker-compose -f windows10.yml down\
sudo apt remove docker.io docker-compose

#### *Link video*: [](https://youtu.be/febFLjCSNbU)[](https://youtu.be/febFLjCSNbU)[](https://youtu.be/febFLjCSNbU)<https://youtu.be/febFLjCSNbU>

*Cùng 8 Sync Dev, chinh phục thế giới lập trình!*

Nguồn: 8 Sync Dev