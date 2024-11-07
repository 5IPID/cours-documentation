---
sidebar_position: 1
documentationSidebar: exerciceSidebar
title: Enoncé
---

# Interface de Gestion des Utilisateurs

## EPIC : Gestion des utilisateurs

**Description**  
Créer une interface permettant de gérer les utilisateurs, avec les fonctionnalités de consultation, ajout, modification, suppression et recherche. L’interface doit être intuitive et organisée pour un usage rapide.

**Objectif**  
Fournir une interface centralisée et accessible pour permettre aux administrateurs de gérer efficacement les utilisateurs, améliorant ainsi la gestion des accès et des informations.

---

## User Stories

### 1. Consulter les utilisateurs (User Story - Liste des utilisateurs)

- **En tant qu’administrateur, je veux pouvoir voir la liste complète des utilisateurs avec des informations clés, afin de gérer et d’identifier les utilisateurs rapidement.**

  - **Critères d'acceptation :**
    - L'interface affiche une liste d'utilisateurs avec les colonnes suivantes : Nom, Email, Rôle, Actions.
    - Chaque utilisateur a un bouton « Éditer » pour modifier les informations et un bouton « Supprimer » pour retirer l’utilisateur.
    - La liste est paginée pour une meilleure lisibilité et navigation.
    - Les utilisateurs sont listés par ordre alphabétique (ou un autre ordre défini), et l’interface permet de voir le nombre total d’utilisateurs.

---

### 2. Ajouter un utilisateur (User Story - Ajout d'utilisateur)

- **En tant qu’administrateur, je veux pouvoir ajouter de nouveaux utilisateurs en renseignant leurs informations, afin d’élargir la base d’utilisateurs.**

  - **Critères d'acceptation :**
    - Un bouton « Ajouter un utilisateur » est disponible en haut de la liste des utilisateurs.
    - Cliquer sur le bouton ouvre un formulaire avec les champs requis : Nom, Email, Rôle, et autres champs définis par les besoins (par exemple : Département, Téléphone).
    - Les champs obligatoires sont marqués et validés avant l’enregistrement (ex. : format de l’email).
    - Une confirmation s'affiche une fois le nouvel utilisateur ajouté avec succès, et la liste des utilisateurs se met à jour automatiquement.

---

### 3. Modifier un utilisateur (User Story - Édition de profil)

- **En tant qu’administrateur, je veux pouvoir modifier les informations d’un utilisateur existant, afin de garantir l’exactitude des données.**

  - **Critères d'acceptation :**
    - Chaque ligne d'utilisateur contient un bouton « Éditer ».
    - Cliquer sur « Éditer » ouvre un formulaire prérempli avec les informations actuelles de l'utilisateur.
    - Les champs peuvent être modifiés et soumis, avec des validations similaires à celles de l'ajout d'utilisateur.
    - Une notification de succès s'affiche si les modifications sont enregistrées avec succès.
    - En cas d’erreur, des messages d’erreur spécifiques sont affichés sous les champs concernés.

---

### 4. Supprimer un utilisateur (User Story - Suppression d'utilisateur)

- **En tant qu’administrateur, je veux pouvoir supprimer un utilisateur de la liste, afin de maintenir une base d’utilisateurs à jour.**

  - **Critères d'acceptation :**
    - Un bouton « Supprimer » est disponible pour chaque utilisateur dans la liste.
    - Cliquer sur le bouton déclenche une confirmation avant la suppression.
    - Si confirmé, l’utilisateur est supprimé de la liste et une notification de succès s’affiche.
    - La liste des utilisateurs se met à jour automatiquement pour refléter la suppression.

---

### 5. Rechercher un utilisateur (User Story - Recherche d'utilisateur)

- **En tant qu’administrateur, je veux pouvoir rechercher un utilisateur par nom ou par email, afin de trouver facilement un profil spécifique sans parcourir toute la liste.**

  - **Critères d'acceptation :**
    - Un champ de recherche est disponible en haut de la liste des utilisateurs.
    - Le champ permet de rechercher par nom ou email, avec des résultats qui s'affichent en temps réel ou au clic d’un bouton « Rechercher ».
    - La liste des utilisateurs est filtrée pour afficher uniquement les résultats correspondant aux critères de recherche.
    - Un message informatif s'affiche si aucun résultat n'est trouvé pour la recherche.

---

## Analyse Technique

### Architecture générale

1. **Front-end (React avec Vite et Mantine)**
   - Utilisation de **React** avec **Vite** pour une compilation rapide et le support du hot-reload.
   - Structure de projet en **composants fonctionnels** organisés par fonctionnalités.
   - **Mantine** est utilisé comme framework UI, offrant des composants préréglés et des hooks pour un design réactif et une expérience utilisateur fluide.
     - Utilisation des composants Mantine pour la mise en page (comme `Grid`, `Container`), pour les formulaires (`TextInput`, `Button`, `Modal` pour les actions d'ajout et d'édition).
     - **Notifications** de Mantine pour les messages de succès ou d’erreur.
   - Gestion de l’état avec un **state management** (par exemple, Context API ou Redux si l’application s’élargit).
   - Appels API asynchrones via **Axios** ou **Fetch API** pour interagir avec le back-end.

2. **Back-end (Node.js avec Express)**
   - **Express.js** pour créer des routes RESTful dédiées à chaque action (consultation, ajout, modification, suppression, recherche d’utilisateurs).
   - Architecture en **MVC** (Modèle-Vue-Contrôleur) :
     - **Modèle** : Gestion des schémas et des opérations CRUD avec **Mongoose**.
     - **Contrôleurs** : Fonctions gérant la logique métier pour chaque route.
     - **Vues** : Non nécessaires ici car l’interface est côté front-end.

3. **Base de données (MongoDB avec Mongoose)**
   - Utiliser **MongoDB** pour stocker les données des utilisateurs sous forme de documents JSON.
   - **Mongoose** pour définir le schéma des utilisateurs et gérer les opérations CRUD de manière simplifiée.
   - Schéma d’utilisateur comprenant les champs requis comme **nom**, **email**, **rôle**, et potentiellement d’autres informations utilisateur.

---

### Détail des fonctionnalités

#### 1. Consultation des utilisateurs
- **Front-end** : Composant `UserList` avec pagination et appels API pour la liste des utilisateurs.
  - Utilisation de `Table` de Mantine pour afficher la liste des utilisateurs avec pagination intégrée.
  - Filtrage de colonnes et options de tri avec les composants de table Mantine.
- **Back-end** : Route **GET /users** pour récupérer la liste paginée des utilisateurs.

#### 2. Ajout d’un utilisateur
- **Front-end** : Composant `UserForm` pour ajouter un utilisateur, avec validation.
  - Formulaire construit avec les composants de formulaire de Mantine (`TextInput`, `Select`, `Button`).
- **Back-end** : Route **POST /users** pour ajouter un nouvel utilisateur.

#### 3. Modification d’un utilisateur
- **Front-end** : Composant `UserForm` en mode édition pour modifier les informations.
  - `Modal` de Mantine pour ouvrir le formulaire en mode édition.
- **Back-end** : Route **PUT /users/:id** pour mettre à jour un utilisateur.

#### 4. Suppression d’un utilisateur
- **Front-end** : Bouton « Supprimer » dans `UserList`, confirmation avant suppression.
  - Utilisation d'une `Modal` de confirmation de Mantine pour vérifier la suppression.
- **Back-end** : Route **DELETE /users/:id** pour supprimer un utilisateur.

#### 5. Recherche d’un utilisateur
- **Front-end** : Champ de recherche dans `UserList`.
  - Utilisation du composant `TextInput` pour la recherche, qui peut filtrer dynamiquement les résultats.
- **Back-end** : Route **GET /users/search** pour rechercher par nom ou email.

---

### Sécurité et validation

- **Validation côté serveur** : Utilisation de **Joi** pour valider les données des requêtes.
- **Gestion des erreurs** : Centraliser les erreurs dans un middleware pour des réponses uniformes.
- **Protection des données** : Appliquer des contrôles d'accès (par exemple avec JWT) pour sécuriser l’application.

---

### Déploiement

- **Front-end** : Build Vite optimisé pour déploiement (ex. : Netlify, Vercel).
- **Back-end** : Hébergement sur **Heroku** ou **Render** avec MongoDB connecté à MongoDB Atlas.