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

Voici une **commande unique** à copier-coller dans votre terminal.  
Elle :
- Libère les ports `3306`, `8080` et `4200` si occupés
- Clône le dépôt GitHub
- Construit et lance le projet avec Docker

---

### 🪟 Pour Windows (CMD)

```cmd
(for %P in (3306 8080 4200) do @for /f "tokens=1" %I in ('docker ps --format "{{.ID}} {{.Ports}}" ^| findstr ":%P"') do docker rm -f %I) & git clone https://github.com/BDSDM/Mon-CafeManagement3-Dockerise.git && cd Mon-CafeManagement3-Dockerise && docker-compose build && docker-compose up -d
```

### 🪟 Pour Linux (bash)

```bash
for P in 3306 8080 4200; do docker ps --format '{{.ID}} {{.Ports}}' | grep ":$P" | awk '{print $1}' | xargs -r docker rm -f; done && git clone https://github.com/BDSDM/Mon-CafeManagement3-Dockerise.git && cd Mon-CafeManagement3-Dockerise && docker-compose build && docker-compose up -d
```
