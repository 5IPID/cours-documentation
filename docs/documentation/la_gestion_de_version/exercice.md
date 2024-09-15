---
sidebar_position: 3
displayed_sidebar: documentationSidebar
title: Exercices
---

# Exercices Pratiques sur la Gestion de Version avec Git

## Exercice 1 : Initialisation d’un dépôt Git et premier commit
Cet exercice te permettra de comprendre comment initialiser un projet avec Git et faire ton premier commit.

### Étapes :
1. **Créer un dossier projet** :
   - Ouvre un terminal et crée un nouveau dossier pour ton projet.
     ```bash
     mkdir projet_gestion_version
     cd projet_gestion_version
     ```

2. **Initialiser Git dans le projet** :
   - Dans le dossier que tu viens de créer, initialise un dépôt Git.
     ```bash
     git init
     ```
   - Ceci crée un dépôt Git vide dans ton projet.

3. **Créer un fichier** :
   - Crée un fichier simple dans ce projet, par exemple un fichier texte.
     ```bash
     echo "Ceci est mon premier fichier" > fichier.txt
     ```

4. **Ajouter le fichier à l'index** :
   - Pour que Git suive ce fichier, tu dois l'ajouter à l'index (staging area).
     ```bash
     git add fichier.txt
     ```

5. **Faire le premier commit** :
   - Enregistre officiellement ce fichier dans l’historique du projet en faisant un commit.
     ```bash
     git commit -m "Ajout du premier fichier"
     ```

### Objectif :
Tu as créé un projet avec Git, ajouté un fichier, et enregistré ce fichier avec un commit. Cela constitue les bases de la gestion de version.

---

## Exercice 2 : Travailler avec des branches
Cet exercice t’apprend à travailler sur différentes branches dans Git. Les branches permettent de développer des fonctionnalités de manière isolée.

### Étapes :
1. **Vérifier la branche actuelle** :
   - Par défaut, tu es sur la branche principale, souvent appelée `main` ou `master`.
     ```bash
     git branch
     ```

2. **Créer une nouvelle branche** :
   - Crée une nouvelle branche pour ajouter une fonctionnalité.
     ```bash
     git checkout -b nouvelle_fonctionnalite
     ```

3. **Faire des modifications sur cette branche** :
   - Modifie le fichier existant ou crée un nouveau fichier.
     ```bash
     echo "Ajout d'une nouvelle fonctionnalité" >> fichier.txt
     ```

4. **Ajouter les modifications et faire un commit** :
   - Ajoute le fichier modifié et fais un commit.
     ```bash
     git add fichier.txt
     git commit -m "Ajout d'une nouvelle fonctionnalité"
     ```

5. **Revenir à la branche principale** :
   - Reviens à la branche principale.
     ```bash
     git checkout main
     ```

6. **Fusionner les modifications dans la branche principale** :
   - Une fois que tu as testé ta nouvelle fonctionnalité et que tout fonctionne, fusionne la branche avec la branche principale.
     ```bash
     git merge nouvelle_fonctionnalite
     ```

7. **Supprimer la branche** :
   - Si la branche n’est plus nécessaire, tu peux la supprimer.
     ```bash
     git branch -d nouvelle_fonctionnalite
     ```

### Objectif :
Tu as appris à créer une branche pour travailler sur des fonctionnalités isolées, puis à fusionner cette branche avec la branche principale. Cela t’aide à organiser le développement en évitant d’introduire des erreurs dans le projet principal.

---

## Exercice 3 : Collaboration avec GitHub (ou GitLab)
Cet exercice te permet de comprendre comment collaborer avec d'autres développeurs en utilisant une plateforme comme GitHub.

### Pré-requis :
- Avoir un compte sur GitHub et avoir GitHub installé/configuré.

### Étapes :
1. **Créer un dépôt sur GitHub** :
   - Va sur GitHub et crée un nouveau dépôt pour ce projet.

2. **Lier ton dépôt local avec GitHub** :
   - Sur ton terminal, lie ton dépôt local à celui sur GitHub en utilisant la commande suivante (remplace `<url>` par l'URL de ton dépôt GitHub) :
     ```bash
     git remote add origin <url>
     ```

3. **Envoyer le projet sur GitHub** :
   - Envoie ton projet local vers GitHub avec la commande suivante :
     ```bash
     git push -u origin main
     ```

4. **Collaborer** :
   - Un autre développeur peut cloner ce projet, travailler dessus, puis proposer des modifications avec une pull request. Tu peux accepter ou discuter des changements directement sur GitHub.

### Objectif :
Comprendre comment travailler en équipe avec GitHub, partager un projet, et collaborer efficacement.

---

## Exercice 4 : Revenir à une version antérieure
Cet exercice t'apprend comment revenir à une version précédente en cas de problème avec une modification.

### Étapes :
1. **Lister l’historique des commits** :
   - Utilise la commande suivante pour voir l’historique des commits :
     ```bash
     git log
     ```

2. **Revenir à un commit précédent** :
   - Utilise le hash (identifiant unique) d’un commit pour revenir à cet état spécifique :
     ```bash
     git checkout <hash_du_commit>
     ```

3. **Créer une nouvelle branche à partir de cet ancien commit (optionnel)** :
   - Si tu veux continuer à travailler à partir de ce commit, crée une nouvelle branche :
     ```bash
     git checkout -b ancienne_version
     ```

4. **Revenir à la branche principale** :
   - Pour revenir à l’état actuel, retourne à la branche principale :
     ```bash
     git checkout main
     ```

### Objectif :
Tu apprends à revenir à une version antérieure du projet si un problème survient et à travailler à partir d'un point précis de l'historique.