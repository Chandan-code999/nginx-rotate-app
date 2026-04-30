# 🚀 Nginx Rotate App

![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![NGINX](https://img.shields.io/badge/NGINX-WebServer-green?logo=nginx)
![Shell Script](https://img.shields.io/badge/Bash-Automation-black?logo=gnubash)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Active-success)

A lightweight DevOps project demonstrating **dynamic content rotation using NGINX, Docker, and shell scripting**.

---

## 📌 Project Overview

This application simulates **dynamic web content rotation** using static HTML files served by NGINX.

💡 Instead of deploying multiple apps, this project:
- Rotates pages automatically
- Uses symbolic links
- Requires zero server restart

---

## 🧠 Architecture

    +----------------------+
    |      User Browser    |
    +----------+-----------+
               |
               v
    +----------------------+
    |        NGINX         |
    |  (serves index.html) |
    +----------+-----------+
               |
               v
    +----------------------+
    |   Symbolic Link      |
    |    index.html        |
    +----------+-----------+
               |
    --------------------------
    |     |       |          |
    v     v       v          v
 page1  page2   page3    (rotating)

---

## 🧱 Project Structure


nginx-rotate-app/
│── docker-compose.yml
│── Dockerfile
│── rotate_pages.sh
│── webpages/
│ ├── page1.html
│ ├── page2.html
│ └── page3.html


---

## ⚙️ How It Works

1. Multiple HTML pages are stored in `/webpages`
2. `rotate_pages.sh` runs in loop
3. Updates symbolic link (`index.html`)
4. NGINX serves updated page

👉 Users see different pages dynamically

---

## 🐳 Setup & Run

### 🔽 Clone Repo
```bash
git clone https://github.com/Chandan-code999/nginx-rotate-app.git
cd nginx-rotate-app
▶️ Run with Docker
docker compose up --build
🌐 Access App
http://localhost:8080
🔄 Rotation Logic
ln -sf page1.html index.html
Uses ln -sf for fast switching
No downtime
No reload required
🛠️ Tech Stack
Tool	Purpose
NGINX	Web server
Docker	Containerization
Bash	Automation scripting
Linux FS	Symlink-based switching
📸 Demo Idea

👉 Refresh browser → Page changes automatically
👉 Simulates load balancing behavior

⚠️ Troubleshooting
❌ Port not working
docker ps
❌ Script not executing
chmod +x rotate_pages.sh
❌ Logs check
docker logs <container_id>
📈 Future Enhancements
🔹 Add CI/CD pipeline (GitHub Actions)
🔹 Kubernetes deployment
🔹 Dynamic API-based content
🔹 UI dashboard for control
🤝 Contributing

Pull requests are welcome! Feel free to improve this project.

📜 License

MIT License

👨‍💻 Author

Chandan M S *
