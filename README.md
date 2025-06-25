# ☕ Mon Café Management – Application de Gestion de Café / Restaurant

**Mon Café Management** est une application complète de gestion de café/restaurant permettant aux utilisateurs d’acheter des produits en ligne, de recevoir un email de confirmation, et offrant une interface administrateur complète. L’application intègre également des cookies pour personnaliser l’expérience utilisateur.

---

## 🚀 Fonctionnalités principales

- 🔐 Authentification sécurisée (JWT)
- 🛍️ Achat de produits en ligne avec email de confirmation
- 🍪 Intégration des cookies
- 📦 Gestion des produits (CRUD)
- 👥 Gestion des utilisateurs avec rôles (ADMIN / USER)
- 📊 Tableau de bord administrateur
- 🔄 Application fullstack conteneurisée avec Docker

---

## ▶️ Lancement automatique de l'application

> Voici une **commande unique** à copier-coller dans votre terminal (Windows) pour exécuter automatiquement tout le projet, même si les ports 3306, 8080 ou 4200 sont déjà occupés :

```bash
(for %P in (3306 8080 4200) do @for /f "tokens=1" %I in ('docker ps --format "{{.ID}} {{.Ports}}" ^| findstr ":%P"') do docker rm -f %I) & git clone https://github.com/BDSDM/Mon-CafeManagement3-Dockerise.git && cd Mon-CafeManagement3-Dockerise && docker-compose build && docker-compose up -d
