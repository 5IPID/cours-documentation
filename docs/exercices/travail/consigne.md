---
sidebar_position: 1
documentationSidebar: exerciceSidebar
title: Consignes
---

# Résumé et Consignes du Projet

## **Résumé**

### **Structure et organisation du projet**
1. **Branches Git :**
   - **Master** : Branche principale pour les versions stables.
   - **Release** : Préparation des versions à déployer.
   - **Dev** : Branche pour le développement.
     - Sous-branches pour les modules spécifiques :
       - **Biens** : Gestion des biens.
       - **Users** : Gestion des utilisateurs et des rôles.
       - **Auth** : Gestion de l’authentification.
       - **Manage** : Autres fonctionnalités de gestion.

### **Fonctionnalités obligatoires**
1. **Gestion des utilisateurs et rôles :**
   - Créer, modifier, supprimer des utilisateurs.
   - Associer des rôles aux utilisateurs.

2. **Authentification (Auth) :**
   - Authentification avec Google.
   - Connexion via login et mot de passe.
   - Réinitialisation de mot de passe :
     - Génération de lien avec un token.
     - Gestion de la validité du lien.

3. **Gestion des biens :**
   - Ajouter, modifier, supprimer et lister des biens.

### **Structure technique**
- **Frontend (Front)** : Développement de l’interface utilisateur.
  - Intégration des fonctionnalités Auth (Search, Post).
  - Administration (Admin).
- **Backend (B)** : Gestion des données et de la logique métier.

---

## **Consignes**

### 1. **Mise en place des branches Git**
- Créez les branches nécessaires dans Git : `master`, `release`, `dev`, ainsi que les sous-branches spécifiques (`auth`, `users`, `biens`, etc.).
- Effectuez chaque fonctionnalité dans une branche dédiée.

### 2. **Développement des fonctionnalités**
- **Frontend :**
  - Créez une interface utilisateur intuitive avec des frameworks comme **Mantine**.
  - Implémentez les écrans nécessaires pour :
    - Connexion / Inscription.
    - Gestion des biens (exemple : tableau pour lister les biens).
    - Administration (gestion des utilisateurs et rôles).
- **Backend :**
  - Utilisez Node.js avec Express et MongoDB pour gérer les données.
  - Implémentez l’authentification et les rôles d’accès.
  - Créez des APIs REST pour communiquer avec le frontend.

### 3. **Gestion des rôles et autorisations**
- Ajoutez des vérifications pour que certaines actions soient limitées à des rôles spécifiques (ex. : rôle admin pour la gestion des utilisateurs).

### 4. **Authentification**
- Implémentez une connexion sécurisée via Google (OAuth2).
- Ajoutez un système de connexion classique avec email et mot de passe.
- Implémentez la réinitialisation de mot de passe (via email avec un lien valide pendant une période limitée).

### 5. **Livrables**
- Un dépôt Git bien structuré avec des commits clairs.
- Une application fonctionnelle avec :
  - Authentification sécurisée.
  - Gestion des utilisateurs et rôles.
  - Gestion des biens.