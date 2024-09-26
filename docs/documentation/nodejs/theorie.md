---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# Introduction à Node.js

## Qu'est-ce que Node.js ?

**Node.js** est un environnement d'exécution JavaScript conçu pour exécuter du code JavaScript en dehors du navigateur. Il a été créé par Ryan Dahl en 2009, et il a révolutionné le développement backend en permettant aux développeurs d'utiliser JavaScript pour construire des applications serveur. Avant Node.js, JavaScript était principalement utilisé pour la programmation côté client, c'est-à-dire dans les navigateurs web. Node.js permet aux développeurs d'utiliser un seul langage (JavaScript) pour le frontend et le backend, ce qui simplifie le développement.

## Comment fonctionne Node.js ?

Node.js est basé sur le moteur V8 de Google, le même moteur utilisé par Google Chrome pour exécuter JavaScript. Ce moteur compile le code JavaScript en code machine natif, permettant une exécution très rapide.

### Modèle d'E/S non bloquant (Non-blocking I/O)

L'une des caractéristiques principales de Node.js est son modèle d'entrée/sortie non bloquant (non-blocking I/O). Contrairement à d'autres environnements, où les opérations d'E/S (comme la lecture de fichiers, les requêtes réseau, etc.) peuvent bloquer l'exécution du programme jusqu'à leur achèvement, Node.js utilise un modèle asynchrone. Cela signifie que les opérations d'E/S sont effectuées en arrière-plan, permettant au programme de continuer à s'exécuter sans attendre que ces opérations soient terminées.

### Boucle d'événements (Event Loop)

Le cœur de l'architecture de Node.js est la **boucle d'événements** (event loop). C'est un mécanisme qui permet à Node.js de gérer de manière efficace des opérations asynchrones. Lorsqu'une opération asynchrone est lancée (comme une requête de fichier), Node.js la délègue au système d'exploitation, et continue d'exécuter d'autres parties du programme. Lorsque l'opération est terminée, un événement est déclenché et la fonction de rappel (callback) associée est exécutée.

### Architecture basée sur les modules

Node.js suit l'architecture des modules CommonJS. Chaque fichier JavaScript dans un projet Node.js est considéré comme un module indépendant. Ces modules peuvent exporter des fonctions, des objets ou des valeurs qui peuvent être réutilisés dans d'autres parties de l'application. Le système de modules permet de structurer le code de manière modulaire, rendant les applications plus faciles à gérer et à maintenir.

## npm (Node Package Manager)

**npm** est le gestionnaire de paquets par défaut de Node.js. Il permet d'installer et de gérer des bibliothèques JavaScript tierces, appelées packages, qui peuvent être intégrées dans vos projets Node.js. npm offre un écosystème riche de milliers de modules open-source que vous pouvez utiliser pour ajouter des fonctionnalités à vos applications.

### Installation et utilisation de npm

Pour installer un module avec npm, vous pouvez utiliser la commande suivante dans votre terminal :

```bash
npm install nom_du_module
```

Par exemple, pour installer Express, un framework web populaire pour Node.js, vous pouvez exécuter :

```bash
npm install express
```

Une fois installé, vous pouvez inclure le module dans votre application en utilisant require :

```javascript
const express = require('express');
```

### Exemple de création de serveur HTTP avec Node.js

Voici un exemple simple de création d’un serveur HTTP avec Node.js sans utiliser de framework comme Express :

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, Node.js!');
});

server.listen(3000, () => {
  console.log('Serveur démarré sur http://localhost:3000');
});
```

#### Explication du code

* http.createServer() : Cette méthode crée un nouveau serveur HTTP.
* req : Représente la requête envoyée par le client (navigateur).
* res : Représente la réponse que le serveur renvoie au client.
* res.statusCode = 200 : Définit le code de statut HTTP de la réponse (200 signifie “OK”).
* res.setHeader(‘Content-Type’, ‘text/plain’) : Définit le type de contenu de la réponse (ici, du texte brut).
* res.end(‘Hello, Node.js!’) : Envoie la réponse au client et termine la requête.
* server.listen(3000) : Le serveur écoute sur le port 3000 pour des requêtes entrantes.

### Avantages de Node.js

* Haute performance pour les applications I/O intensives : Node.js excelle dans les applications qui nécessitent un traitement rapide des E/S, comme les serveurs web ou les applications temps réel (ex : chat, jeux en ligne).
* Unification du développement frontend et backend : Node.js permet aux développeurs d’utiliser un seul langage (JavaScript) pour le frontend et le backend, simplifiant ainsi le processus de développement.
* Grande communauté et écosystème riche : Grâce à npm, vous avez accès à des milliers de bibliothèques et d’outils pour étendre les fonctionnalités de Node.js.

## Conclusion

Node.js est un environnement d’exécution puissant et flexible pour le développement backend en JavaScript. Grâce à son modèle asynchrone et à la boucle d’événements, Node.js est particulièrement adapté aux applications nécessitant une gestion efficace des E/S. En combinant cela avec npm et l’architecture modulaire de Node.js, vous avez tout ce dont vous avez besoin pour développer des applications serveur modernes et performantes.
