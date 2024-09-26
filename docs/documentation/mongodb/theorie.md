---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# Introduction à MongoDB

## Qu'est-ce que MongoDB ?

**MongoDB** est une base de données NoSQL orientée documents, conçue pour stocker des données sous forme de documents JSON (JavaScript Object Notation) plutôt que dans des tables relationnelles comme dans les bases de données SQL traditionnelles. MongoDB est extrêmement flexible et évolutif, ce qui en fait un choix populaire pour les applications modernes qui nécessitent une gestion efficace de grandes quantités de données non structurées ou semi-structurées.

## Caractéristiques principales de MongoDB

1. **Documents JSON** : MongoDB stocke les données sous forme de documents BSON (Binary JSON), qui est un format binaire proche de JSON. Cela permet de représenter les données de manière plus naturelle pour les applications web modernes.

2. **Schéma flexible** : Contrairement aux bases de données SQL, MongoDB n'impose pas de schéma rigide. Vous pouvez ajouter de nouveaux champs à des documents sans avoir à modifier les structures de données existantes, ce qui facilite l'évolution des applications.

3. **Scalabilité horizontale** : MongoDB supporte la scalabilité horizontale via le sharding, ce qui permet de distribuer les données sur plusieurs serveurs ou clusters pour gérer de grandes quantités de données et des charges de travail élevées.

4. **Performances élevées** : Grâce à son modèle de stockage optimisé pour les documents, MongoDB offre des performances élevées, en particulier pour les opérations de lecture et d'écriture sur des ensembles de données volumineux.

## Installation de MongoDB

### Installation locale

Pour installer MongoDB localement sur votre machine, suivez les étapes spécifiques à votre système d'exploitation (Windows, macOS, ou Linux). Voici un exemple pour une installation sous macOS avec Homebrew :

```bash
brew tap mongodb/brew
brew install mongodb-community@6.0
```

## Lancer MongoDB

Une fois MongoDB installé, vous pouvez démarrer le serveur MongoDB avec la commande suivante :

```bash
mongod --config /usr/local/etc/mongod.conf --fork
```

Cette commande démarre le serveur MongoDB en arrière-plan (grâce à l’option --fork).

## Connexion à MongoDB

Pour interagir avec MongoDB, utilisez le client MongoDB en ligne de commande :

```bash
mongo
```

Cela vous connecte au serveur MongoDB en cours d’exécution sur votre machine.

## Utilisation de MongoDB avec Node.js

Pour utiliser MongoDB dans une application Node.js, vous devez installer le package mongodb :

### Installation du package MongoDB

Installez le driver MongoDB avec npm ou Yarn :

```bash
npm install mongodb
```

ou 

```bash
yarn add mongodb
```

### Connexion à MongoDB depuis Node.js

Voici un exemple simple de connexion à une base de données MongoDB et d’insertion d’un document dans une collection :

```javascript 
const { MongoClient } = require('mongodb');

async function main() {
  const uri = 'mongodb://localhost:27017';
  const client = new MongoClient(uri);

  try {
    await client.connect();
    const database = client.db('testdb');
    const collection = database.collection('testcollection');

    const doc = { name: 'John Doe', age: 25, job: 'Developer' };
    const result = await collection.insertOne(doc);

    console.log(`New document inserted with _id: ${result.insertedId}`);
  } finally {
    await client.close();
  }
}

main().catch(console.error);
```

### Explication du code

* MongoClient : C’est la classe utilisée pour se connecter à un serveur MongoDB.
* uri : Contient l’URL de connexion à MongoDB (ici, une connexion locale sur le port 27017).
* client.connect() : Ouvre une connexion avec MongoDB.
* client.db() : Sélectionne une base de données (ici, testdb).
* collection.insertOne() : Insère un document dans la collection spécifiée.
* client.close() : Ferme la connexion à MongoDB après l’exécution.

## Avantages de MongoDB

1.	Flexibilité du schéma : La possibilité de stocker des documents avec des structures différentes dans la même collection permet d’adapter facilement l’application à des besoins changeants.
2.	Scalabilité : MongoDB est conçu pour gérer des charges de données massives et peut être mis à l’échelle horizontalement à l’aide de sharding.
3.	Haute disponibilité : MongoDB offre des fonctionnalités de réplication qui permettent de maintenir plusieurs copies des données, assurant ainsi la disponibilité en cas de défaillance d’un serveur.
4.	Performance : MongoDB est optimisé pour les opérations d’écriture et de lecture rapide, ce qui le rend adapté aux applications nécessitant un traitement de données en temps réel.

## Inconvénients de MongoDB

1.	Consommation de mémoire : MongoDB peut consommer plus de mémoire par rapport à d’autres bases de données, surtout lorsqu’il est utilisé avec des ensembles de données très volumineux.
2.	Transactions complexes : Bien que MongoDB supporte les transactions multi-documents, leur gestion est plus complexe que dans les bases de données relationnelles.
3.	Flexibilité excessive : La liberté de ne pas avoir de schéma strict peut parfois mener à des incohérences si la structure des données n’est pas bien contrôlée.

## Conclusion

MongoDB est une base de données NoSQL puissante et flexible, idéale pour les applications modernes qui nécessitent une gestion de données évolutive et rapide. Sa capacité à manipuler des données non structurées, associée à sa scalabilité, en fait un choix privilégié pour de nombreux développeurs. Cependant, il est important de bien comprendre ses avantages et ses limitations pour l’utiliser de manière optimale dans vos projets.