---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# Introduction à Express.js

## Qu'est-ce qu'Express.js ?

**Express.js** est un framework web minimaliste pour Node.js. Il est conçu pour simplifier la création de serveurs web et d'API, en fournissant une série d'outils et de fonctionnalités pour gérer les requêtes HTTP, les routes, les middlewares, et plus encore. Express est souvent utilisé pour construire des applications web légères, des API RESTful, et des services backend en général.

## Pourquoi utiliser Express.js ?

### Simplicité et minimalisme
Express.js est souvent décrit comme "minimaliste" parce qu'il se concentre uniquement sur l'essentiel pour construire un serveur web ou une API. Contrairement à d'autres frameworks qui peuvent être plus lourds ou complexes, Express vous permet de démarrer rapidement avec un minimum de configuration, tout en restant flexible pour les projets plus complexes.

### Modulaire et extensible
Bien qu'il soit minimaliste, Express est aussi très extensible. Vous pouvez facilement intégrer des middlewares, des bibliothèques externes, ou des composants personnalisés pour ajouter des fonctionnalités à votre application, sans imposer de structure rigide.

### Large communauté et écosystème
Express bénéficie d'une grande communauté d'utilisateurs et de contributeurs, ce qui signifie que vous avez accès à une abondance de modules, de plugins, et de ressources en ligne pour résoudre pratiquement n'importe quel problème que vous pourriez rencontrer.

## Installation de Express.js

Pour installer Express.js dans un projet Node.js, utilisez npm ou Yarn :

### Installation via npm :
```bash
npm install express
```

### Installation via Yarn :
```bash
yarn add express
```

## Exemple d’utilisation de Express.js

Voici un exemple simple de création d’un serveur web avec Express.js :

```javascript 
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello, Express!');
});

app.listen(3000, () => {
  console.log('Serveur démarré sur http://localhost:3000');
});
```

### Explication du code

* const express = require('express'); : Cette ligne importe le module Express dans votre application.
* const app = express(); : Cette ligne initialise une nouvelle application Express.
* app.get('/', (req, res) => { ... }); : Ceci définit une route GET pour l’URL racine /. Lorsqu’un utilisateur accède à cette URL, la fonction de rappel est exécutée, envoyant la réponse ‘Hello, Express!’ au client.
* app.listen(3000, () => { ... }); : Cette ligne démarre le serveur et le fait écouter les requêtes entrantes sur le port 3000. Le message “Serveur démarré…” est affiché dans la console une fois que le serveur est prêt.

## Les Middlewares dans Express.js

Les middlewares sont une caractéristique clé d’Express. Un middleware est essentiellement une fonction qui a accès à l’objet de requête (req), l’objet de réponse (res), et à la fonction next dans le cycle de requête-réponse de l’application. Ils permettent de modifier la requête ou la réponse, de terminer le cycle de requête-réponse ou de passer le contrôle à la fonction middleware suivante.

### Exemple de middleware
```javascript
app.use((req, res, next) => {
  console.log('Une requête a été reçue.');
  next();
});
```

Dans cet exemple, chaque fois qu’une requête est reçue par le serveur, un message est loggé dans la console. La fonction next() est appelée pour passer au middleware suivant ou à la route correspondante.

## Gestion des routes avec Express.js

Express simplifie la gestion des routes dans une application. Vous pouvez définir des routes pour gérer différentes requêtes HTTP (GET, POST, PUT, DELETE, etc.).

### Exemple de routes multiples

```javascript
app.get('/users', (req, res) => {
  res.send('Liste des utilisateurs');
});

app.post('/users', (req, res) => {
  res.send('Utilisateur ajouté');
});
```

### Explication

* GET /users : Cette route renvoie une liste d’utilisateurs lorsqu’une requête GET est envoyée à /users.
* POST /users : Cette route permet d’ajouter un nouvel utilisateur via une requête POST à /users.

## Avantages d’Express.js

1.	Simplicité : Express offre une approche simple pour configurer un serveur web avec Node.js, sans la complexité d’autres frameworks plus lourds.
2.	Flexibilité : Vous pouvez ajouter exactement les fonctionnalités dont vous avez besoin, grâce à son système de middlewares et à son écosystème modulaire.
3.	Grande communauté : Un support vaste et actif de la communauté, avec une abondance de modules tiers et de documentation.

## Inconvénients d’Express.js

1.	Manque de structure imposée : Express ne vous impose pas de structure particulière pour votre application. Bien que cela puisse être un avantage pour les développeurs expérimentés, cela peut aussi conduire à des applications désorganisées si vous n’êtes pas prudent.
2.	Fonctionnalités limitées hors de la boîte : Express est minimaliste par nature. Pour des fonctionnalités avancées (authentification, validation de schéma, gestion des sessions, etc.), vous devrez souvent compter sur des modules tiers.

## Conclusion

Express.js est un framework léger et puissant pour Node.js, parfait pour construire des applications web et des API de manière rapide et efficace. Sa flexibilité et son écosystème riche en font un excellent choix pour les développeurs qui veulent un contrôle total sur la structure et les fonctionnalités de leur application.