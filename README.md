# 🐚 Online Kubernetes Shell Platform

This project is a Flask-based web application that allows users to register, log in, and access a personal, isolated Ubuntu shell environment running in a Kubernetes Pod. Each user gets their own container where they can execute Linux commands securely via a web browser.

---

## 🚀 Features

- 🔐 User registration and login with JWT authentication
- 🐳 Per-user isolated Ubuntu Pod (via Kubernetes)
- 🖥 Web-based command interface to run shell commands
- 🧾 MySQL-backed user database
- 📦 Docker & Kubernetes integration
- 🛡 Security features like hashed passwords and input validation

---

## 🛠 Tech Stack

- **Frontend**: HTML + Bootstrap 5
- **Backend**: Flask (Python)
- **Database**: MySQL
- **Containerization**: Docker
- **Orchestration**: Kubernetes (Minikube or Docker Desktop)
- **Auth**: JWT (JSON Web Tokens)

---

## 📁 Folder Structure

```
project-root/
├── main.py              # Flask app entry point
├── kubernetesg.py       # Kubernetes pod management
├── runcmd.py            # Pod command executor
├── mod.py               # Utility (optional)
├── templates/           # HTML frontend files
│   ├── index.html
│   ├── login.html
│   ├── signup.html
│   └── shell.html
├── .env                 # Environment variables
```

---

## ⚙️ Setup Instructions

### ✅ Prerequisites

- Python 3.8+
- pip
- Docker
- Kubernetes (Minikube or Docker Desktop)
- MySQL Server

### 🔧 Step-by-Step

```bash
# 1. Clone this project
git clone <your-repo-url>
cd project-root

# 2. Create a virtual environment and activate it
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Create `.env` file
HOST=localhost
PASSWORD=your_mysql_password
SECRET=your_jwt_secret
SESSION=session_key

# 5. Ensure MySQL is running and set up the users table

# 6. Start Docker & Kubernetes (minikube start or Docker Desktop)

# 7. Run the Flask app
python main.py
```

Visit: `http://127.0.0.1:5000` in your browser.

---

## 🧪 Usage

- **Sign Up** → Create an account
- **Log In** → Authenticate and start a shell pod
- **Shell** → Execute shell commands in your pod
- **Log Out** → Pod is automatically deleted

---

## 🛡 Security Notes

- JWT authentication (tokens stored in cookies)
- SHA1 password hashing (upgrade to bcrypt recommended)
- Input validation using regex
- Kubernetes pods are resource limited and isolated

---

## 📈 Future Improvements

- Use `bcrypt` for password hashing
- Auto-terminate idle pods
- Switch to WebSockets for real-time shell output
- Container activity logging
- Deployment using Helm charts

---

## 📜 License

This project is for educational/demo purposes. Customize as needed for your use case.