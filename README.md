# 🚀 Hosting Static Website on AWS EC2 with Apache

This project demonstrates how to host a static website on an EC2 instance using the Apache web server.

## 🛠️ Steps to Deploy

### 📥 1. Clone the Repository
```bash
git clone https://github.com/JustPritam/AWSDemo.git
cd AWSDemo/
```

### 🧰 2. Install Apache (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install apache2 -y
```
> 🟡 For Amazon Linux:
> ```bash
> sudo yum install httpd -y
> ```

### 📁 3. Copy Website Files to Apache Directory
```bash
sudo cp index.html /var/www/html/
sudo cp -r assets/ /var/www/html/
sudo cp -r error/ /var/www/html/
sudo cp -r images/ /var/www/html/
```

### 🔍 4. Check if Files are Placed
```bash
ls /var/www/html/
```
Expected output:
```
index.html  assets/  error/  images/
```

### ▶️ 5. Start Apache Server
```bash
sudo systemctl start apache2
```
> 🟡 For Amazon Linux:
> ```bash
> sudo systemctl start httpd
> ```

### 🔄 6. Enable Apache on Boot (Optional)
```bash
sudo systemctl enable apache2
```

## 🌐 Access Your Website
Open your browser and go to:
```
http://<your-ec2-public-ip>
```
✅ Make sure **port 80** is allowed in your EC2 Security Group settings.
✅ Make sure that you are using **http** not **https** (sometimes by default it takes https).

## 📌 Notes
- Apache root directory: `/var/www/html/`
- To check Apache status:
  ```bash
  sudo systemctl status apache2
  ```
- Ensure your EC2 instance is running and public IP is reachable.

---

Happy Hosting! 🎉
