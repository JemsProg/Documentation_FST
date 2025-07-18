# Django + React Deployment Guide (Manual)

This guide helps you manually deploy a Django (backend) + React (Vite) (frontend) app with Gunicorn and Nginx using different ports per student (e.g., `8002`, `8003`, etc.).

---

## Folder Structure Example
```
/home/dockerlabs/student3/
├── docker-compose.yml
└── rivanit_web/
    ├── backend/
    └── frontend/
```

---

## Step-by-Step Deployment (Student3 Example)

### ✅ 1. Backend Setup (Django)

```bash
cd ~/dockerlabs/student3/rivanit_web/backend
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt  # ensure gunicorn is included
```

Run migrations and collect static files:
```bash
python manage.py migrate
python manage.py collectstatic --noinput
```

### 🐍 2. Run Gunicorn on Custom Port
```bash
pip install gunicorn
python -m gunicorn backend.wsgi:application --bind 0.0.0.0:800/
gunicorn backend.wsgi:application --bind 0.0.0.0:800/ --daemon

```

> ✅ Replace `/` with the port assigned to the student

---

### ⚛ 3. Frontend Setup (React + Vite)

```bash
cd ~/dockerlabs/student3/rivanit_web/frontend
npm install
npm run build
```

Vite will generate static files inside `frontend/dist/`

---

### 🌐 4. Nginx Config (student3.rivanacad.com)

Create:
```bash
sudo nano /etc/nginx/sites-available/student3_rivanit
```

Paste:
```nginx
server {
    listen 80;
    server_name student3.rivanacad.com;

    root /home/dockerlabs/student3/rivanit_web/frontend/dist;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }

    location /api/ {
        proxy_pass http://127.0.0.1:8003;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    location /static/ {
        alias /home/dockerlabs/student3/rivanit_web/backend/staticfiles/;
    }
}
```

Enable the config:
```bash
sudo ln -s /etc/nginx/sites-available/student3_rivanit /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

---

## 🧪 Test It
- Public IP: `http://147.93.107.162:8003` (for backend)
- Domain: `http://student3.rivanacad.com`

Make sure:
- DNS for `student3.rivanacad.com` points to `147.93.107.162`
- Gunicorn is running on correct port
- Frontend is built
- Nginx is restarted

---

## ✅ Done!
You now have a manually deployed Django + React app per student.

Repeat for `student4`, `student5`, etc. by changing the folder paths, ports, and Nginx config accordingly.

