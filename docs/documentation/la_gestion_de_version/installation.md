---
sidebar_position: 1
displayed_sidebar: documentationSidebar
title: Installation
---

# Installation de Git en ligne de commande sur Windows

## 1. Télécharger Git pour Windows
- Rendez-vous sur le site officiel : [git-scm.com](https://git-scm.com/)
- Cliquez sur **Download for Windows** pour télécharger l'exécutable Git.

## 2. Installer Git
- Une fois le téléchargement terminé, exécutez l'installateur.
- Suivez les instructions de l'assistant d'installation. Voici les options importantes à considérer :
  - **Composants supplémentaires :** Vous pouvez cocher l'option pour ajouter l'intégration à l'explorateur Windows (clic droit pour accéder à Git Bash/Git GUI).
  - **Choix de l'éditeur par défaut :** Sélectionnez l'éditeur de texte que vous souhaitez utiliser pour modifier vos messages de commit (par défaut, c'est Vim, mais vous pouvez choisir un autre éditeur comme Notepad++ ou Visual Studio Code).
  - **Ajustement de la variable PATH :** Choisissez l'option **Git from the command line and also from 3rd-party software** pour utiliser Git en ligne de commande partout.

## 3. Lancer Git Bash
- Une fois l'installation terminée, vous pouvez utiliser **Git Bash**, une interface en ligne de commande qui inclut Git.
- Ouvrez le menu Démarrer, cherchez "Git Bash" et lancez-le.

## 4. Vérifier l'installation
- Ouvrez **Git Bash** ou **l’invite de commande Windows** et tapez :
  ```bash
  git --version

## 5. Configurer Git
```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```
