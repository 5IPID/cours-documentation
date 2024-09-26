---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# Introduction à Nodemon

## Qu'est-ce que Nodemon ?

**Nodemon** est un outil qui aide au développement d'applications Node.js en surveillant automatiquement les fichiers du projet et en redémarrant le serveur lorsque des changements sont détectés. Il élimine le besoin de redémarrer manuellement le serveur à chaque fois que vous modifiez un fichier, ce qui améliore l'efficacité du développement.

## Installation de Nodemon

Vous pouvez installer Nodemon globalement sur votre machine pour l'utiliser dans n'importe quel projet Node.js, ou l'installer en tant que dépendance de développement spécifique à un projet.

### Installation globale via npm
```bash
npm install -g nodemon
```

### Installation locale (dépendance de développement)

```bash
npm install --save-dev nodemon
```

### Utilisation de Nodemon

Une fois Nodemon installé, vous pouvez l’utiliser pour exécuter votre application Node.js. Au lieu de lancer votre application avec la commande node, utilisez nodemon :

```bash
nodemon app.js
```

Dans cet exemple, app.js est le fichier principal de votre application. Nodemon surveillera ce fichier et tous les autres fichiers de votre projet, et redémarrera automatiquement l’application si des changements sont détectés.

## Configuration de Nodemon

Nodemon est très flexible et peut être configuré de plusieurs façons. Vous pouvez spécifier des options directement dans la ligne de commande, ou utiliser un fichier de configuration pour personnaliser son comportement.

### Utilisation de la ligne de commande

Vous pouvez passer des options directement via la ligne de commande. Par exemple, pour spécifier un fichier différent comme point d’entrée :

```bash
nodemon server.js
```

Ou pour spécifier un répertoire spécifique à surveiller :

```bash
nodemon --watch src/
```

## Fichier de configuration nodemon.json

Pour une configuration plus avancée, vous pouvez créer un fichier nodemon.json dans le répertoire de votre projet. Voici un exemple de configuration :

```json
{
  "watch": ["src", "config"],
  "ext": "js,json",
  "ignore": ["node_modules"],
  "exec": "node --inspect"
}
```

### Explication de la configuration

* watch : Spécifie les répertoires à surveiller pour les changements.
* ext : Définit les extensions de fichiers à surveiller (par exemple, .js, .json).
* ignore : Liste des répertoires ou des fichiers à ignorer.
* exec : Commande à exécuter pour démarrer l’application (ici avec --inspect pour le mode debug).

## Avantages de Nodemon

1.	Gain de temps : Nodemon supprime la nécessité de redémarrer manuellement le serveur après chaque modification de fichier, ce qui accélère le développement.
2.	Facilité d’utilisation : Nodemon est simple à utiliser avec une configuration minimale, tout en étant suffisamment flexible pour répondre aux besoins plus complexes.
3.	Débogage simplifié : Nodemon peut être utilisé avec des outils de débogage, facilitant ainsi le processus de développement.

## Inconvénients de Nodemon

1.	Ressources système : Nodemon surveille constamment les fichiers du projet, ce qui peut consommer des ressources système, en particulier dans de grands projets.
2.	Compatibilité : Dans certains environnements ou configurations complexes, Nodemon peut rencontrer des problèmes de compatibilité ou de surveillance de fichiers.

## Conclusion

Nodemon est un outil indispensable pour les développeurs Node.js qui cherchent à améliorer leur flux de travail. En automatisant le redémarrage du serveur, Nodemon vous permet de vous concentrer sur le développement sans interruption. Avec une installation facile et une configuration flexible, il est un ajout précieux à tout projet Node.js.