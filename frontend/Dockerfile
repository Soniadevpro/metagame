FROM node:18

WORKDIR /app

# Copier uniquement les fichiers package.json et package-lock.json pour optimiser la mise en cache
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste du projet
COPY . .

# Fixer les permissions
RUN chmod -R 755 /app

# Exposer le port
EXPOSE 3000

# Démarrer l'application
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]

