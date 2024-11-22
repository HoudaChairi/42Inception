# 42 Inception 🚀

## Project Overview 📚

Inception is a **System Administration** project at **42 School** that focuses on **Docker containerization**.  
The goal is to set up a small infrastructure composed of different services under specific rules using Docker Compose.

<p align="center">
  <img src="https://github.com/user-attachments/assets/9d6c8ab9-91e2-4a2f-9fb4-57607a6f60e7" alt="Project Overview" style="width:80%; border-radius:10px;"/>
</p>

---

## 🗂 Table of Contents
- [✨ Requirements](#requirements)
- [🛠️ Services](#services)
- [📂 Directory Structure](#directory-structure)
- [⚙️ Configuration](#configuration)
- [🐛 Troubleshooting](#troubleshooting)

---

## ✨ Requirements

Before starting, ensure the following are installed:

- 🐳 **Docker**
- ⚙️ **Docker Compose**
- 📦 **Containers**
- 💾 **Volumes**
- 🌐 **Network**

---

## 🛠️ Services

Here are the main services you will set up:  

- 🌐 **NGINX**: Web server with SSL/TLS support.  
- 📝 **WordPress**: CMS with php-fpm.  
- 💾 **MariaDB**: Database server.  

**Bonus Services**:  

- 🔄 **Redis**: Caching system.  
- 📡 **FTP server**: File transfer protocol server.  
- 🖼️ **Static website**: Simple static HTML site.  
- 📊 **Adminer**: Managing contents of MySQL databases.  

---

## 📂 Directory Structure

```plaintext
42_INCEPTION/
├── srcs/
│   ├── requirements/
│   │   └── bonus/
│   │       ├── adminer/
│   │       │   └── Dockerfile
│   │       ├── simple_page/
│   │       │   └── website/
│   │       │       ├── index.html
│   │       │       └── styles.css
│   │       └── Dockerfile
│   ├── mariadb/
│   │   ├── conf/
│   │   │   └── 50-server.cnf
│   │   ├── tools/
│   │   └── Dockerfile
│   ├── nginx/
│   │   ├── conf/
│   │   │   └── nginx.conf
│   │   └── Dockerfile
│   ├── wordpress/
│   │   ├── tools/
│   │   └── Dockerfile
│   ├── .env
│   ├── docker-compose.yml
└── Makefile
```


## ⚙️ Configuration
Key configuration files:
- `.env`: Environment variables
- `docker-compose.yml`: Service definitions
- `srcs/requirements/*/Dockerfile`: Individual service configurations
- `srcs/requirements/*/conf/*`: Service-specific configuration files

Important environment variables:
- `DOMAIN_NAME`: Your domain name
- `MYSQL_ROOT_PASSWORD`: MariaDB root password
- `MYSQL_USER`: MariaDB user
- `MYSQL_PASSWORD`: MariaDB user password
- `WORDPRESS_DB_NAME`: WordPress database name

## 🐛 Troubleshooting
1. **Containers not starting**: 
   - Check logs: `docker-compose logs`
   - Verify port availability

2. **WordPress not connecting to database**:
   - Ensure MariaDB is fully initialized
   - Check database credentials in WordPress configuration

3. **SSL certificate issues**:
   - Verify SSL certificate generation in NGINX container
   - Check NGINX configuration for proper SSL setup

For more detailed troubleshooting, refer to individual service logs:
  docker-compose logs [service_name]

