FROM python:3.10

WORKDIR /app

# Copier seulement les fichiers nécessaires avant d'installer les dépendances
COPY requirements.txt .

# Installer les dépendances
RUN pip install --no-cache-dir -r requirements.txt

# Copier le reste du projet après l'installation des dépendances
COPY . .

# Fixer les permissions
RUN chmod -R 755 /app

# Ajouter le script d'attente pour PostgreSQL
ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.9.0/wait /wait
RUN chmod +x /wait

# Exposer le port
EXPOSE 8000

# Définir l'utilisateur non-root (optionnel mais recommandé)
USER 1000

# Attendre la disponibilité de la base de données avant de démarrer Django
CMD /wait && python manage.py migrate && python manage.py runserver 0.0.0.0:8000
