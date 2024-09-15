---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# La gestion de version

La gestion de version, ou “version control” en anglais, est une pratique essentielle dans le développement logiciel qui permet de suivre les modifications apportées à un projet au fil du temps. Imagine que tu travailles sur un projet de développement avec plusieurs personnes : la gestion de version va permettre de gérer les contributions de chacun, d’éviter les conflits et de maintenir une trace de chaque modification.

## 1. Qu’est-ce que la gestion de version ?

La gestion de version est un système qui enregistre toutes les modifications apportées à un fichier ou à un ensemble de fichiers au fil du temps. Grâce à ce système, tu peux revenir à une version précédente du fichier, savoir qui a effectué telle modification, et même comparer les différentes versions du fichier.

## 2. Pourquoi utiliser la gestion de version ?

Imaginons que tu développes une application et que tu fasses une modification qui cause un bug. Grâce à la gestion de version, tu peux revenir à une version précédente où tout fonctionnait correctement. De plus, si tu travailles en équipe, cela permet à plusieurs développeurs de travailler sur le même projet sans écraser les modifications des autres.

## 3. Les systèmes de gestion de version (VCS)

Il existe plusieurs systèmes de gestion de version, parmi les plus connus :

- **Git** : très populaire et utilisé dans la majorité des projets open-source.
- **Subversion (SVN)** : un autre système plus ancien.
- **Mercurial** : un autre choix moins répandu que Git.

## 4. Les deux types de gestion de version :

- **Centralisé** : Tout le monde travaille à partir d’un serveur central, où les versions sont stockées (ex : Subversion).
- **Distribué** : Chaque utilisateur possède une copie locale complète du projet et peut travailler de manière indépendante (ex : Git).

## 5. Fonctionnement de Git (exemple d’un VCS distribué)

Dans Git, chaque modification est enregistrée sous forme de “commit”.

- **Commit** : Un commit est une sorte de “photo” de l’état du projet à un instant donné. Il contient un message de description, et chaque commit est lié à celui qui le précède, formant une sorte d’historique.
- **Branches** : Dans Git, tu peux travailler sur des branches différentes. Cela te permet de travailler sur des nouvelles fonctionnalités sans affecter le projet principal (souvent appelé la branche “main” ou “master”).
- **Merge** : Lorsque tu as fini une fonctionnalité sur une branche, tu peux “fusionner” cette branche avec la branche principale, pour que le code soit intégré au projet final.

## 6. Avantages de la gestion de version :

- **Collaboration** : Plusieurs développeurs peuvent travailler simultanément sans conflit.
- **Historique complet** : On peut retrouver chaque modification effectuée et savoir qui l’a faite.
- **Revenir en arrière** : Si une erreur est introduite, on peut facilement revenir à une version antérieure.
- **Suivi des bugs** : On peut comprendre quand et où un bug a été introduit en regardant l’historique des commits.

## 7. Exemple d’utilisation simple de Git :

- **Étape 1** : Initialiser un dépôt Git dans ton projet avec `git init`.
- **Étape 2** : Ajouter des fichiers au suivi avec `git add <nom_fichier>`.
- **Étape 3** : Faire un commit avec `git commit -m "Description du changement"`.
- **Étape 4** : Travailler sur une nouvelle fonctionnalité dans une branche avec `git checkout -b <nom_branche>`.
- **Étape 5** : Fusionner cette branche avec la branche principale avec `git merge`.

## 8. Collaborer via GitHub ou GitLab :

- **GitHub** et **GitLab** sont des plateformes qui permettent de stocker les dépôts Git en ligne et de collaborer avec d’autres développeurs.
- Chaque développeur peut cloner un projet, y apporter des modifications, puis envoyer ses modifications sous forme de “pull request” pour les intégrer au projet principal.

# Conclusion

La gestion de version est un outil puissant qui facilite la collaboration entre les développeurs, garantit la traçabilité des modifications, et permet de gérer efficacement l’évolution d’un projet logiciel. Pour un développeur, maîtriser des outils comme Git est indispensable dans la plupart des environnements professionnels aujourd’hui.

Pour mieux comprendre, vous pouvez aussi faire des exercices pratiques en utilisant Git dans vos projets, en créant des branches, en faisant des commits et en travaillant en équipe.