# 🚀 WireGuard VPN Setup using Docker on AWS EC2

## 📌 Project Overview

This project demonstrates how to set up a secure VPN server using **WireGuard** inside a Docker container on an AWS EC2 instance.

It allows secure communication and private internet access using encrypted tunnels.

---

## 🛠️ Tech Stack

* AWS EC2 (Ubuntu)
* Docker & Docker Compose
* WireGuard VPN

---

## ⚙️ Architecture

User Device → WireGuard Client → AWS EC2 → Docker Container → Internet

---

## 🔧 Setup Steps

### 1️⃣ Launch EC2 Instance

* AMI: Ubuntu 22.04
* Instance Type: t3.micro
* Enable Public IP

---

### 2️⃣ Configure Security Group

Allow:

* SSH (22)
* UDP Port 51820 (WireGuard)

---

### 3️⃣ Connect to EC2

```bash
ssh -i your-key.pem ubuntu@YOUR_PUBLIC_IP
```

---

### 4️⃣ Install Docker

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
```

---

### 5️⃣ Install Docker Compose

```bash
sudo apt install docker-compose -y
```

---

### 6️⃣ Create Project Folder

```bash
mkdir wireguard
cd wireguard
```

---

## ⚙️ Docker Compose Configuration

This project uses Docker Compose to deploy a WireGuard VPN server inside a container.

### 🔧 Key Configuration

* **Image:** linuxserver/wireguard
* **Container Name:** wireguard
* **Port:** 51820/UDP (used for VPN tunnel)
* **Environment Variables:**

  * `SERVERURL` → Public IP of AWS EC2 instance
  * `SERVERPORT` → 51820
  * `PEERS` → Number of VPN clients
  * `PEERDNS` → DNS server (8.8.8.8)

### 📦 Volume Mapping

* `./config:/config` → Stores WireGuard configs
* `/lib/modules:/lib/modules` → Required for kernel modules

### 🚀 Run Command

```bash
sudo docker-compose up -d
```

### 📄 Full Configuration

👉 [View docker-compose.yml](docker-compose.yml)

---

### 8️⃣ Start WireGuard

```bash
sudo docker-compose up -d
```

---

### 9️⃣ Verify Container

```bash
sudo docker ps
```

---

### 🔟 Get QR Code

```bash
sudo docker logs wireguard
```

Scan QR using WireGuard mobile app.

---

## 📱 Client Setup

* Install WireGuard app
* Scan QR code
* Connect VPN

---

## ✅ Output

* VPN tunnel established
* Secure internet access via AWS server

---


## 🐳 Docker Commands

👉 [View Commands](docs/docker-commands.md)
