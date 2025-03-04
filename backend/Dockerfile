FROM python:3.10

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers de dépendances
COPY requirements.txt .

# Installer les dépendances
RUN pip install --no-cache-dir -r requirements.txt

# Copier le reste du projet
COPY . .

# Créer un utilisateur django
RUN adduser --disabled-password --gecos '' django

# Changer de propriétaire
RUN chown -R django:django /app

# Basculer sur l'utilisateur django
USER django

# Exposer le port
EXPOSE 8000

# Commande par défaut
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
