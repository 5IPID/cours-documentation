---
sidebar_position: 3
displayed_sidebar: documentationSidebar
title: Exercices
---

# Exercice Pratique avec Git

## Objectif

L'objectif de cet exercice est de comprendre et d'appliquer le Semantic Versioning tout en utilisant Git pour gérer les versions de votre projet.

## Étapes de l'Exercice

1. Initialisation du Projet :
    * Créez un nouveau répertoire pour votre projet et initialisez un dépôt Git :
      ```javascript
        mkdir mon-projet
        cd mon-projet
        git init
      ```
2. Création du Premier Commit :
    * Ajoutez un fichier README.md avec la version initiale 1.0.0 :
      ```javascript
        echo "# Mon Projet" > README.md
        git add README.md
        git commit -m "Initial commit avec version 1.0.0"
      ```
3. Ajout de Fonctionnalités (Version Mineure) :
    * Créez une nouvelle branche pour ajouter des fonctionnalités :
      ```javascript
        git checkout -b ajout-fonctionnalites
      ```
    * Modifiez le fichier `README.md` pour ajouter une nouvelle fonctionnalité :
      ```javascript
        echo "Ajout de nouvelles fonctionnalités" >> README.md
        git add README.md
        git commit -m "Ajout de nouvelles fonctionnalités pour version 1.1.0"
      ```
    * Fusionnez cette branche dans la branche principale et taguez la version :
      ```javascript
        git checkout main
        git merge ajout-fonctionnalites
        git tag -a v1.1.0 -m "Version 1.1.0 avec nouvelles fonctionnalités"
      ```
4. Correction de Bogues (Version de Patch) :
    * Créez une nouvelle branche pour corriger les bogues :
      ```javascript
        git checkout -b correction-bogue
      ```
    * Modifiez le fichier `README.md` pour corriger un bogue fictif :
      ```javascript
        echo "Correction d'un bogue" >> README.md
        git add README.md
        git commit -m "Correction de bogue pour version 1.1.1"
      ```
    * Fusionnez cette branche dans la branche principale et taguez la version :
      ```javascript
        git checkout main
        git merge correction-bogue
        git tag -a v1.1.1 -m "Version 1.1.1 avec correction de bogue"
      ```
5. Modification Majeure (Version Principale) :
    * Créez une nouvelle branche pour une modification majeure :
      ```javascript
        git checkout -b modification-majeure
      ```
    * Modifiez le fichier `README.md` pour refléter une modification majeure :
      ```javascript
        echo "Réécriture majeure du projet" >> README.md
        git add README.md
        git commit -m "Modification majeure pour version 2.0.0"
      ```
    * Fusionnez cette branche dans la branche principale et taguez la version :
      ```javascript
          git checkout main
          git merge modification-majeure
          git tag -a v2.0.0 -m "Version 2.0.0 avec modification majeure"
      ```

## Vérification

* Listez les tags pour vérifier les versions :

  ```bash
    git tag
  ```

* Affichez les détails des tags :

  ```bash
  git show v1.0.0
  git show v1.1.0
  git show v1.1.1
  git show v2.0.0
  ```

Cet exercice vous aidera à comprendre comment utiliser le Semantic Versioning en pratique avec Git, en vous familiarisant avec le processus de gestion des versions et des changements dans un projet.