# ⚙️ DVWA Local Setup Project

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Tool](https://img.shields.io/badge/Tool-DVWA-orange)
![Category](https://img.shields.io/badge/Category-Lab%20Setup-blue)
![Language](https://img.shields.io/badge/Language-PHP%2C%20MySQL%2C%20Linux-yellow)

---

## 📖 Project Overview
**Damn Vulnerable Web Application (DVWA)** is a PHP/MySQL web application that is intentionally vulnerable.  

Its main goal is to help **security professionals** test their skills and tools in a **legal, controlled environment**.  

---

## 🛠️ Setup Environment
- **OS:** Kali Linux  
- **Web Server:** Apache2  
- **Database:** MariaDB / MySQL  
- **Language:** PHP 8.4.5  
- **Tools:** DVWA, Git, PhpMyAdmin (optional)  

---

## 🚀 Steps Taken

1. Installed required packages:  
```bash
sudo apt install apache2 mariadb-server php php-mysqli git -y
```

2. Cloned DVWA from GitHub:  
```bash
git clone https://github.com/digininja/DVWA.git
```

3. Configured **config.inc.php** with database credentials.  

4. Created database and user with privileges:  
```sql
CREATE DATABASE dvwa;
CREATE USER 'dvwauser'@'localhost' IDENTIFIED BY 'p@ssw0rd';
GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwauser'@'localhost';
FLUSH PRIVILEGES;
```

5. Enabled PHP settings & Apache modules.  

6. Restarted Apache2 and accessed DVWA at:  
```
http://localhost/DVWA
```

7. Clicked **"Create / Reset Database"** on DVWA setup page.  

---

## 📝 Configuration Example (`config.inc.php`)
```php
$_DVWA[ 'db_server' ]   = '127.0.0.1';
$_DVWA[ 'db_database' ] = 'dvwa';
$_DVWA[ 'db_user' ]     = 'dvwauser';
$_DVWA[ 'db_password' ] = 'p@ssw0rd';
```

---

## 🐞 Troubleshooting
- Fixed **"mysqli_connect(): Connection refused"** → corrected DB credentials & permissions.  
- Resolved **"Access denied for user"** → granted privileges + flush.  
- Verified **Apache/PHP configs** → enabled `mod_rewrite`, `display_errors`.  
- Ensured MySQL was listening on the correct port.  

---

## 🔮 Next Steps
- 🔗 Integrate **DVWA logs with Splunk** for monitoring.  
- 🛡️ Add **Wazuh agent** for threat detection.  
- 🧪 Explore vulnerabilities in DVWA (SQLi, XSS, File Inclusion, CSRF, etc.).  

---
