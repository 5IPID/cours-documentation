---
sidebar_position: 1
documentationSidebar: documentationSidebar
title: Enoncé
---

# Exercice : Application de gestion de profils

## Objectif
Développer une application React affichant une fiche de profil à partir d'un tableau de données statiques.

## Contraintes
- Utilisation d'un **framework UI** (par exemple, **Material-UI**, **Bootstrap**, ou **Tailwind CSS**) pour styliser l'interface.
- Vous devez découvrir et structurer les composants et fonctions par vous-même.
- Utilisation de **Git** pour gérer les différentes étapes du développement, avec des branches distinctes pour chaque étape.

---

## Étapes à suivre

### Étape 1 : Affichage d'une fiche de profil
- Créez une branche `step1-profile-display`.
- Implémentez l'affichage d'une fiche de profil avec les informations d'un utilisateur (nom, prénom, email, etc.) provenant d'un tableau de données statique.
- Appliquez un design à l'aide du framework UI choisi.

---

## Instructions Git
- **La branche main** : Créer une première branche main pour recevoir l'initialisation du projet
    - Création du dossier sur votre machine
    - On navigue dans ce dossier en ligne de commande : 
        ```bash
        cd nom-du-projet
        ```
    - Initialisation du projet : 
        ```bash
        npm create vite profile-management --template react-ts
        ```
    - Setup git
        ```bash
        git init
        ```
    - Création du repo dans github
    - Suivi du process dans github pour lié votre projet au repo github
    
- **Branching** : Créez une nouvelle branche pour chaque étape avec la commande suivante :
    ```bash
    git checkout -b step1-profile-display
    ```

- **Commit et Push** : Faites des commits réguliers pour chaque fonctionnalité et poussez vos changements sur la branche associée :
    ```bash
    git add .
    git commit -m "Affichage de la fiche de profil"
    git push origin step1-profile-display
    ```
- **Merge** : Une fois l’étape validée, fusionnez-la dans la branche main :
    ```bash
    git checkout main
    git merge step1-profile-display
    ```

## Livrables

- Un dépôt Git avec les différentes branches correspondant aux étapes du développement.
- La branche main doit contenir le produit final après la fusion.