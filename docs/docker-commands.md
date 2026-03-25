# 🐳 Docker Commands – WireGuard VPN Setup

> This file contains all commands used to deploy a WireGuard VPN using Docker on AWS EC2.

---

🔧 Install Docker
sudo apt update
sudo apt install docker.io -y

▶️ Start Docker Service
sudo systemctl start docker
sudo systemctl enable docker

📦 Install Docker Compose
sudo apt install docker-compose -y

📁 Create Project Folder
mkdir wireguard
cd wireguard

📝 Create docker-compose.yml
nano docker-compose.yml

🚀 Start WireGuard Container
sudo docker-compose up -d

📊 Check Running Containers
sudo docker ps

📜 View Logs (Get QR Code)
sudo docker logs wireguard

⛔ Stop Container
sudo docker-compose down

🔄 Restart Container
sudo docker-compose restart
