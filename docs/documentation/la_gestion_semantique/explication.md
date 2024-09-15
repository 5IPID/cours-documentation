---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# Introduction au Semantic Versioning (SemVer)

## Qu'est-ce que le Semantic Versioning ?

Le Semantic Versioning, ou SemVer, est un système de versionnage utilisé pour indiquer clairement les changements apportés à un logiciel. Il est utile pour les développeurs afin de comprendre l'impact des mises à jour. La version se compose de trois parties : MAJOR.MINOR.PATCH.

## Structure de la Version
1. MAJOR (Principal) : Change lorsque des modifications incompatibles avec les versions précédentes sont apportées.
2. MINOR (Mineur) : Change lorsque de nouvelles fonctionnalités rétro-compatibles sont ajoutées.
3. PATCH (Correction) : Change pour des corrections de bogues ou des améliorations mineures rétro-compatibles.

## Exemple de Versionnage

Prenons un exemple avec une version 2.3.4 :

* Version 2.3.4 :
  * 2 : Numéro majeur
  * 3 : Numéro mineur
  * 4 : Numéro de patch

### Changements Typiques
1. Modification Majeure : Si vous passez de 2.3.4 à 3.0.0, cela signifie que des changements incompatibles ont été apportés avec la version précédente.
2. Ajout de Fonctionnalités : Si vous passez de 2.3.4 à 2.4.0, cela indique que de nouvelles fonctionnalités ont été ajoutées, mais les fonctionnalités existantes restent compatibles.
3. Correction de Bogues : Si vous passez de 2.3.4 à 2.3.5, cela signifie que des corrections de bogues ont été apportées sans modifier les fonctionnalités existantes.

## Pourquoi Utiliser le SemVer ?
* Clarté : Permet aux utilisateurs de savoir exactement à quoi s'attendre en termes de compatibilité et de changements avec chaque version.
* Gestion des Dépendances : Aide à éviter les conflits et à garantir que les mises à jour ne cassent pas le code existant.
* Communication : Facilite la communication précise des modifications apportées au logiciel.

## Exemple Pratique
Supposons que vous développez une bibliothèque de calcul mathématique :

* Version Initiale : 1.0.0
  * Vous publiez une bibliothèque avec les fonctions de base.
* Ajout de Fonctionnalités : 1.1.0
  * Vous ajoutez de nouvelles fonctions de calcul, mais toutes les fonctions existantes continuent de fonctionner comme avant.
* Correction de Bogues : 1.1.1
  * Vous corrigez un bug dans une des fonctions, sans ajouter de nouvelles fonctionnalités.
* Modification Majeure : 2.0.0
  * Vous réécrivez certaines fonctions pour améliorer la performance, mais cela nécessite des modifications dans le code des utilisateurs.
  
En suivant le SemVer, vous aidez les utilisateurs à comprendre les changements et à mettre à jour leurs projets en conséquence.