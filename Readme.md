# 🔐 VPN Setup using Docker on AWS EC2

This project shows how I deployed a VPN using Docker in AWS.

## 🚀 Steps I followed
- Created EC2 instance
- Installed Docker
- Ran WireGuard container
- Connected using QR code

## 🛠 Tech Stack
- AWS EC2
- Docker
- WireGuard

## ⚙️ Commands

sudo apt update  
sudo apt install docker.io -y  

docker run -d \
--name wg-easy \
-e WG_HOST=YOUR_PUBLIC_IP \
-e PASSWORD=admin \
-v ~/.wg-easy:/etc/wireguard \
-p 51820:51820/udp \
-p 51821:51821/tcp \
--cap-add=NET_ADMIN \
--cap-add=SYS_MODULE \
--restart unless-stopped \
weejewel/wg-easy

## 🌐 Access
http://YOUR_PUBLIC_IP:51821

## 📸 Screenshots
(Add images here)

## 📌 Result
VPN deployed successfully using Docker in AWS
