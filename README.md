# PSAT2425 - Aplikasi CRUD PHP

Aplikasi ini adalah sistem login dan manajemen data sederhana berbasis PHP + MySQL.

## 🚀 Fitur

- Login / Logout
- CRUD data
- Antarmuka mode gelap (dark mode)
- Dapat dideploy otomatis via UserData di AWS

---

## 🛠️ Cara Deploy ke AWS EC2 dengan UserData

### 1. Buat EC2 Instance

- Masuk ke [AWS Console](https://console.aws.amazon.com/)
- Pilih **Launch Instance**
- Pilih Ubuntu : `Ubuntu`
- Pilih Instance Type: `t2.micro/t2.nano` (gratis)
- Buat Key Pair / gunakan yang sudah ada
- Select existing security group
- Pilih SG yang sudah kalian buat sebelumnnya
- Scroll ke bawah sampai menemukan 'Advanced details'

### 2. Tambahkan UserData

Saat setup EC2, buka **Advanced Details > UserData**, dan masukkan script berikut:

#!/bin/bash
sudo apt update -y
sudo apt install -y apache2 php php-mysql libapache2-mod-php mysql-client
sudo rm -rf /var/www/html/{*,.*}
sudo git clone https://github.com/Fayakun1/psat2425.git /var/www/html
sudo chmod -R 777 /var/www/html
echo DB_USER=admin > /var/www/html/.env
echo DB_PASS=P4ssw0rd  >> /var/www/html/.env
echo DB_NAME=psat2425  >> /var/www/html/.env
echo DB_HOST=psat2425.c1ltei3m5gn3.us-east-1.rds.amazonaws.com >> /var/www/html/.env

 ### 3. JALANKAN APLIKASI
🔑 Login menggunakan username dan password default berikut:

Username: admin

Password: 123

📥 Setelah login, masukkan data sesuai kebutuhan dan simpan.

