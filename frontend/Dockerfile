# Étape 1 : Build de l'application Angular
FROM node:20 AS build

WORKDIR /app

# Copie des fichiers nécessaires à l'installation des dépendances
COPY package*.json ./

# Installation des dépendances
RUN npm install

# Copie de tout le code source Angular
COPY . .

# Build de l'application Angular en mode production
RUN npm run build --prod

# Étape 2 : Serveur NGINX pour héberger l'app compilée
FROM nginx:alpine

# Suppression de la configuration par défaut de NGINX
RUN rm -rf /usr/share/nginx/html/*

# Copie du build Angular généré vers le dossier servi par NGINX
COPY --from=build /app/dist/cafe-mangement3-frontend /usr/share/nginx/html

# Ajout de la configuration personnalisée de NGINX
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Exposition du port 80
EXPOSE 80

# Commande de lancement
CMD ["nginx", "-g", "daemon off;"]
