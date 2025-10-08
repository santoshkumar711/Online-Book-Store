# 📚 BookShop Application  

A full-stack **Django BookShop Application** supporting  
🧑‍💻 Local development, 🐳 Docker Compose, and ☸️ Kubernetes deployment.  

---

## ⚙️ Installation  

```bash
pip install django
pip install setuptools distutils
pip install --upgrade django
pip install django-cors-headers
pip install django-crispy-forms
pip install xhtml2pdf
pip install -r requirements.txt
pip install --upgrade pip
```
🗄️ Database Configurations

This application uses three types of databases (configured in settings.py):

db.sqlite3 — for local testing

Database2 — for Docker Compose

Database3 — for Kubernetes

🧑‍💻 Run Application Locally
# Activate virtual environment
venv\Scripts\activate

# Create superuser
python manage.py createsuperuser

# Run Django server
python manage.py runserver


Open your browser at: http://127.0.0.1:8080/

🐳 Run Application with Docker Compose

The Docker Compose setup uses Database2 (MariaDB).

# Start services
docker-compose up -d

# View running containers
docker ps

# Stop and remove services
docker-compose down

# Rebuild if code changes
docker-compose build
docker-compose up -d

☸️ Run Application with Kubernetes

Kubernetes setup uses Database3 (MariaDB).
Make sure you are in the /bookstore folder before applying YAML files.

# Apply MariaDB and BookShop configurations
kubectl apply -f mariadb-deployment.yml
kubectl apply -f mariadb-initdb.yml
kubectl apply -f mariadb-service.yml
kubectl apply -f bookshop-deployment.yml
kubectl apply -f bookshop-service.yml

# Start services (if required)
kubectl start bookshop-service
kubectl start mariadb-service

# Check pods and services
kubectl get pods
kubectl get svc

🔐 Superuser Access

Access Django admin at: http://127.0.0.1:8080/admin/

Login with the credentials created using:

python manage.py createsuperuser
