

# 🌐🚀 EC2 Linux Web Server

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge\&logo=amazonaws)
![EC2](https://img.shields.io/badge/Amazon-EC2-blue?style=for-the-badge\&logo=amazonec2)
![Linux](https://img.shields.io/badge/Linux-Amazon%20Linux%202023-black?style=for-the-badge\&logo=linux)
![Apache](https://img.shields.io/badge/Web%20Server-Apache-red?style=for-the-badge\&logo=apache)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> 🚀 **Deploying and hosting a web server on AWS EC2 using Amazon Linux 2023 and Apache HTTP Server.**

---

## 📌 Project Overview

This project demonstrates how to launch and configure a **Linux-based web server on Amazon Web Services (AWS)** using **Amazon EC2**.

An EC2 instance running **Amazon Linux 2023** is launched and configured as a web server. Apache HTTP Server is installed on the instance, and a custom HTML webpage is hosted from the Apache web root directory.

The website can then be accessed publicly through the **EC2 Public IP address**.

🎯 This project provides hands-on experience with:

* ☁️ AWS EC2
* 🐧 Linux Server Administration
* 🔐 Security Groups
* 🔑 SSH Remote Connection
* 🌐 Apache Web Server
* 📝 HTML Web Hosting
* 🔥 Firewall & Port Configuration

---

# ☁️ AWS Services & Technologies Used

| Technology            | Purpose                           |
| --------------------- | --------------------------------- |
| ☁️ Amazon EC2         | Hosts the Linux web server        |
| 🐧 Amazon Linux 2023  | Operating system                  |
| 🌐 Apache HTTP Server | Web server                        |
| 🔐 Security Group     | Controls inbound/outbound traffic |
| 🔑 SSH                | Secure remote server access       |
| 📝 HTML               | Website content                   |

---

# 🏗️ Architecture

```text
                    🌍 Internet
                         │
                         ▼
                ┌─────────────────┐
                │   🔐 Security   │
                │      Group      │
                │                 │
                │ SSH  → 22       │
                │ HTTP → 80       │
                │ HTTPS → 443     │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │   ☁️ AWS EC2    │
                │                 │
                │ Amazon Linux    │
                │     2023        │
                │                 │
                │ Apache Server   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ /var/www/html/  │
                │                 │
                │  index.html     │
                └────────┬────────┘
                         │
                         ▼
                  🌐 Web Browser
```

---

# 🛠️ Project Configuration

### 💻 EC2 Configuration

```text
Instance Name : webserver-project
Operating System : Amazon Linux 2023
Instance Type : t3.micro
Web Server : Apache
```

### 🔐 Security Group Configuration

| Type  | Port | Purpose                      |
| ----- | ---: | ---------------------------- |
| SSH   |   22 | Remote server administration |
| HTTP  |   80 | Website access               |
| HTTPS |  443 | Secure web traffic           |

---

# 🚀 Step-by-Step Implementation

## 1️⃣ Launch EC2 Instance

Go to the **AWS Management Console** and open Amazon EC2.

Click:

```text
EC2 → Instances → Launch Instance
```

Configure the instance:

```text
Name: webserver-project
AMI: Amazon Linux 2023
Instance Type: t3.micro
```

Create/select a key pair for SSH access.

---

## 2️⃣ Configure Security Group 🔐

Create a Security Group with the required inbound rules:

```text
SSH   → TCP → 22
HTTP  → TCP → 80
HTTPS → TCP → 443
```

The Security Group acts as a virtual firewall for the EC2 instance.

---

## 3️⃣ Connect to EC2 Using SSH 🔑

After launching the instance, connect to it using SSH.

Example:

```bash
ssh -i "your-key.pem" ec2-user@EC2-PUBLIC-IP
```
---

# 4️⃣ Update the Linux Server 🔄

Run:

```bash
sudo yum update -y
```

This updates the installed packages on the Amazon Linux server.

---

# 5️⃣ Install Apache 🌐

Install Apache HTTP Server:

```bash
sudo yum install httpd -y
```

---

# 6️⃣ Start Apache ▶️

Start the Apache service:

```bash
sudo systemctl start httpd
```

Check its status:

```bash
sudo systemctl status httpd
```

If Apache is running successfully, you should see:

```text
Active: active (running)
```

---

# 7️⃣ Enable Apache at Boot 🔄

To automatically start Apache whenever the EC2 server starts:

```bash
sudo systemctl enable httpd
```

---

# 8️⃣ Create the Website 📝

Apache's default web directory is:

```text
/var/www/html/
```

Move into the directory:

```bash
cd /var/www/html/
```

Create the HTML file:

```bash
sudo yum index.html
```

Add your webpage content:

```html
<!DOCTYPE html>
<html>
<head>
    <title>My AWS EC2 Web Server</title>
</head>

<body>

    <h1>🚀 Welcome to My AWS EC2 Web Server</h1>

    <h2>☁️ Hosted on Amazon EC2</h2>

    <p>
        This website is running on Amazon Linux 2023
        with Apache Web Server.
    </p>

    <p>
        💻 Project: EC2 Linux Web Server
    </p>

</body>
</html>
```

Save the file.

---

# 9️⃣ Access Website From Browser 🌍

Copy the **Public IPv4 Address** of your EC2 instance.

Open:

```text
http://EC2-PUBLIC-IP
```

🎉 Your website should now be publicly accessible!

---

# 📷 Screenshots

![](./Screenshot%202026-10-01%20151401.png)

![](./Screenshot%202026-10-01%20151508.png)

![](./Screenshot%202026-10-01%20151805.png)

![](./Screenshot%202026-10-01%20152011.png)

