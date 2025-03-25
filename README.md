# AWS EC2 Web Application Deployment

This guide walks you through deploying a web application on an AWS EC2 instance using Apache.

## 🚀 Steps to Deploy

### 1️⃣ Launch an EC2 Instance 🖥️
- **Selected Ubuntu 22.04 LTS as the OS**
- **Chose an appropriate instance type (t2.micro, free-tier eligible)**
- **Configured the security group to allow HTTP (port 80) and SSH (port 22) access**

### 2️⃣ Connect to the EC2 Instance 🔑
Use SSH to connect:
```sh
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

### 3️⃣ Install Apache Web Server 🌐
Update packages and install Apache:
```sh
sudo apt update && sudo apt install apache2 -y
```
Start and enable the Apache service:
```sh
sudo systemctl start apache2
sudo systemctl enable apache2
```

### 4️⃣ Deploy Your Web Application 📂
Clone your project from GitHub:
```sh
git clone https://github.com/your-username/your-repo.git
```
Copy files to Apache’s web root:
```sh
sudo cp -r your-repo/* /var/www/html/
```

### 5️⃣ Test the Deployment ✅
Open `http://your-ec2-public-ip` in a browser. If everything is set up correctly, your website should be live! 🎉

## 🎯 Additional Notes
- Ensure your AWS security group settings allow inbound HTTP (port 80) traffic.
- Restart Apache if needed:
  ```sh
  sudo systemctl restart apache2
  ```

Happy hosting! 🚀
