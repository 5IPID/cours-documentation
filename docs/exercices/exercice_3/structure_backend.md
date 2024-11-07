---
sidebar_position: 2
documentationSidebar: exerciceSidebar
title: Structure Backend
---

# Exemple de structure backend

## Structure de dossier recommandée

```javascript
backend/
├── src/
│   ├── config/
│   │   ├── db.js              # Configuration et connexion à la base de données MongoDB
│   │   └── default.js         # Fichier de configuration pour les variables globales
│   ├── controllers/
│   │   └── userController.js   # Contrôleur pour les utilisateurs
│   ├── middleware/
│   │   ├── authMiddleware.js   # Middleware d'authentification
│   │   └── errorHandler.js     # Middleware de gestion des erreurs
│   ├── models/
│   │   └── User.js             # Modèle Mongoose pour l'utilisateur
│   ├── routes/
│   │   ├── userRoutes.js       # Routes liées aux utilisateurs
│   │   └── index.js            # Fichier pour regrouper toutes les routes
│   ├── utils/
│   │   └── helpers.js          # Fonctions utilitaires communes
│   ├── app.js                  # Initialisation de l'application Express
│   └── server.js               # Point d'entrée principal pour lancer le serveur
├── .env                        # Variables d'environnement
├── .gitignore                  # Fichiers à ignorer par Git
└── package.json                # Dépendances et scripts Node.js
```

---

## Détail des dossiers et fichiers

1.	config/ :
	* db.js : Fichier de connexion à MongoDB, utilisant Mongoose pour établir la connexion et gérer les options.
  * default.js : Fichier de configuration pour stocker les variables d’environnement (comme le port, la base de données).
2.	controllers/ : Contient les fonctions de contrôle (logique métier). Par exemple, userController.js gère les requêtes HTTP liées aux utilisateurs (création, mise à jour, suppression, etc.).
3.	middleware/ : Contient les middlewares Express.
	* authMiddleware.js : Middleware d’authentification pour protéger certaines routes.
	* errorHandler.js : Middleware central pour gérer les erreurs, ce qui permet un retour d’erreurs cohérent à l’utilisateur.
4.	models/ : Contient les modèles Mongoose. Chaque modèle correspond à une collection dans MongoDB (par exemple, User.js pour la collection d’utilisateurs).
5.	routes/ : Contient toutes les routes de l’application.
	* userRoutes.js : Définition des routes liées aux utilisateurs (par exemple : GET /users, POST /users).
	* index.js : Fichier qui regroupe toutes les routes pour les importer facilement dans app.js.
6.	utils/ : Contient les fonctions utilitaires et helpers (fonctions réutilisables dans plusieurs parties de l’application).
7.	app.js :
	* Point d’entrée où sont initialisés les middlewares globaux, les routes, et d’autres configurations Express.
	* Utilise dotenv pour charger les variables d’environnement du fichier .env.
8.	server.js : Fichier principal pour lancer l’application (définit le port et le serveur HTTP).
