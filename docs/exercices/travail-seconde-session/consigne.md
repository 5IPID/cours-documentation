---
sidebar_position: 1
documentationSidebar: exerciceSidebar
title: Consignes
---

# Seconde session

## Consignes

Le travail pour la seconde session est un travail individuel !

Il y a trois parties pour l’évaluation, une partie analyse, une partie développement et une partie présentation.

- La partie analyse devra être remise pour le **lundi 18 Août 2025** au plus tard.
- Le code devra être remis pour le **mercredi 20 Août 2025** au plus tard.
- La présentation se fera le **vendredi 22 Août 2025**.

---

## Pour la partie analyse, voici ce qui est attendu :

- La liste des stories business, une story business est un élément fonctionnel. Par exemple :

  - En tant que gestionnaire je dois pouvoir m'authentifier sur la plateforme  
  - En tant que gestionnaire je dois pouvoir réinitialiser mon mot de passe

- Pour chacune des stories, je désire avoir :  
  - Un mockup  
  - Une analyse fonctionnelle
  - Une analyse technique :
    - Schéma DB
    - Modèle Objet lié à la story
    - Update de la DB actuel
    - Problématique technique possible avec la solution

> Attention, on n'est pas en waterfall, il ne faut pas faire de schéma de base de données complets. La base de données évolue avec le temps. On fait de l'Agile.

---

## Pour la partie développement, voici ce qui est attendu :

- On utilise GIT :
  - Une branche master
  - Une branche develop
  - Une branche par feature / story
  - Une branche finale 'release’ avec le code que vous allez présenter

- Le projet doit se faire soit avec un backend et frontend séparé.

- Le projet doit être **mobile first**, l’utilisation de framework comme Mantine ou autre est fortement recommandée.

## 6. **La présentation**

La présentation devra contenir les éléments suivants : 

- Quels sont les besoins de votre client ?
- Quel est la solution fonctionnelle ?
- Quel est la solution technique ?
- Quels sont les problèmes et problématiques rencontrés et comment y avez-vous répondu ?
- Quels sont les défis que vous avez relevé ?
- Quels sont les apprentissages ? 
- Votre conclusion 
- Questions 

### Les technologies autorisées :

- Nodejs pour le backend  
- Mongo Db pour le service DB  
- React pour le frontend

- Je dois pouvoir déployer votre application facilement sur ma machine

> Pas d’utilisation de services externes pour la gestion des utilisateurs, les services externes autorisés ne doit être utilisé que pour des fonctionnalités annexes et non principale.

- Il faut une gestion de compte propre avec un rappel de mot de passe (sécurisé) par email
- Il faut gérer correctement les contraintes de typages pour les différents champs utilisé tant au niveau backend que frontend (adresse email, numéro de téléphone, mot de passe,)

---

## Sujet

Le sujet sera le même pour tout le monde, attention je vérifierai pour être certain qu’il n’y a rien de commun entre le projet.

### Le sujet : Application permettant l’attribution de marché pour le service public

---

## Le besoin de votre client

### L’administrateur de la plateforme d’attribution de marché doit pouvoir :

- Créer / mettre à jour / voir / supprimer des comptes avec plusieurs rôles  
  Exemple de rôle : Administrateur, gestionnaire des entreprises, validation des marchés, ...

- Créer / mettre à jour / voir / supprimer les marchés

- Confier un marché à une personne intéressée

- Visualiser l’offre faite et l’accepter

Un marché est défini par :

- Une période où les personnes / entreprises peuvent postuler
- La date ou période de l’évènement
- Un nom, une description, un lieu, ...

---

### Les personnes intéressées par les marchés doivent pouvoir :

- S’inscrire sur la plateforme
- Mettre à jour leur données
- Supprimer leur compte
- Voir les différents marchés pour lesquels ils ont postulés avec les statuts (accepté / refusé)
- Choisir un marché et déposer leur candidature
- Retirer leur candidature

## Tips :

- L'utilisation de l'AI est authorisée et conseillée, mais vous devez pouvoir comprendre ce qu'elle a fait pour vous.

## Questions / Contact

J'aurai un accès fortement limité à mes e-mails du 20 juillet au 3 aoüt, n'hésitez pas à me conctacter si vous avez des questions.