---
sidebar_position: 2
documentationSidebar: exerciceSidebar
title: Structure Frontend
---

# Exemple de structure frontend

## Structure de dossier recommandée

```javascript
frontend/
├── public/                         # Fichiers publics accessibles directement
│   ├── index.html                  # Fichier HTML principal
├── src/
│   ├── api/                        # Gestion des appels API
│   │   └── userApi.js              # Fonctions pour interagir avec les endpoints utilisateurs
│   ├── assets/                     # Images, icônes, et styles globaux
│   │   ├── images/
│   │   └── styles.css              # Styles globaux (ou fichier CSS pour Mantine overrides)
│   ├── components/                 # Composants réutilisables et généraux
│   │   ├── Button.js               # Exemple de bouton personnalisé
│   │   ├── Modal.js                # Exemple de modal personnalisée
│   │   └── Table.js                # Exemple de table générique
│   ├── features/                   # Composants spécifiques à chaque fonctionnalité
│   │   └── Users/                  # Module de gestion des utilisateurs
│   │       ├── components/         # Composants internes du module
│   │       │   ├── UserList.js     # Liste des utilisateurs avec options de pagination
│   │       │   ├── UserForm.js     # Formulaire pour créer/éditer un utilisateur
│   │       │   └── UserCard.js     # Carte affichant les détails d'un utilisateur
│   │       ├── UserPage.js         # Page principale pour gérer les utilisateurs
│   │       └── userSlice.js        # Slice Redux (ou état local) pour gérer les données utilisateurs
│   ├── hooks/                      # Hooks personnalisés
│   │   └── useFetch.js             # Hook pour les requêtes API avec état de chargement et d'erreur
│   ├── layouts/                    # Dispositions générales de page
│   │   ├── MainLayout.js           # Mise en page principale
│   │   └── AdminLayout.js          # Mise en page pour l'administration
│   ├── pages/                      # Pages principales de l'application
│   │   ├── Dashboard.js            # Tableau de bord
│   │   ├── Login.js                # Page de connexion
│   │   └── NotFound.js             # Page 404
│   ├── providers/                  # Contexte global et configurations
│   │   └── MantineProvider.js      # Configuration de Mantine (thème, etc.)
│   ├── store/                      # Gestion globale de l'état (ex : Redux)
│   │   └── store.js                # Store Redux et combinateurs de reducers
│   ├── utils/                      # Utilitaires et fonctions d'aide
│   │   └── formatDate.js           # Exemple de fonction de formatage de date
│   ├── App.js                      # Composant racine de l'application
│   ├── main.js                     # Point d'entrée de l'application
└── vite.config.js                  # Configuration de Vite
```

---

## Détail des dossiers et fichiers

1.	api/ :
	* Contient les appels API centralisés, permettant de maintenir le code API séparé des composants.
	* Exemple : userApi.js avec des fonctions comme fetchUsers, createUser.
2.	assets/ :
	* Contient les ressources globales, comme les images, les icônes, et les styles CSS.
	* Les overrides CSS de Mantine peuvent également être placés ici.
3.	components/ :
	* Contient les composants réutilisables, qui peuvent être utilisés dans plusieurs parties de l’application.
	* Exemples : Button.js, Modal.js, Table.js.
4.	features/ :
	* Organisation modulaire par fonctionnalité, idéale pour les projets complexes.
	* Chaque fonctionnalité (par exemple, Users) possède ses composants spécifiques, son slice de gestion d’état (pour Redux), et une page principale.
	* Dans Users, on trouve des composants comme UserList, UserForm, et UserCard pour encapsuler toute la logique relative aux utilisateurs.
5.	hooks/ :
	* Contient les hooks personnalisés pour éviter de dupliquer le code et faciliter la réutilisation de logique.
	* Exemple : useFetch pour gérer les appels API avec état de chargement et gestion des erreurs.
6.	layouts/ :
	* Définit les layouts globaux de l’application, comme MainLayout ou AdminLayout, pour structurer l’apparence et l’ergonomie des pages.
7.	pages/ :
	* Contient les pages principales, généralement liées aux routes.
	* Exemple : Dashboard.js pour le tableau de bord, Login.js pour la connexion, NotFound.js pour une page 404.
8.	providers/ :
	* Contient les providers de contexte et de configuration globale, comme la configuration de thème pour Mantine dans MantineProvider.js.
9.	store/ :
	* Gestion globale de l’état (Redux par exemple).
	* store.js est le store principal qui combine tous les slices d’état (par exemple, userSlice).
10.	utils/ :
	* Fonctions utilitaires, comme formatDate.js pour les manipulations courantes (formatage de dates, manipulation de chaînes).
11.	App.js :
	* Le composant principal qui englobe les routes et les layouts, souvent avec la configuration des routes de React Router.
12.	main.js :
	* Point d’entrée de l’application où on importe App.js et on monte l’application dans le DOM.
