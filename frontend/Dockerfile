FROM node:18

# Définir le répertoire de travail
WORKDIR /app

# Copier package.json et package-lock.json
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste du projet
COPY . .

# Construire l'application
RUN npm run build

# Exposer le port
EXPOSE 3000

# Commande par défaut
CMD ["npm", "start"]
