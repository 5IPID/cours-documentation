---
sidebar_position: 3
displayed_sidebar: documentationSidebar
title: Exercices
---

# Exercice de Programmation Orientée Objet 

## Énoncé 

**Objectif** : Comprendre et appliquer les concepts de la programmation orientée objet en JavaScript. 

1. Création des Classes : 
    * Crée une classe Animal. 
    * Crée deux sous-classes Chat et Chien qui héritent de la classe Animal. 
2. Méthodes Spécifiques : 
    * Ajoute une méthode parler à la classe Animal qui affiche un message générique. 
    * Redéfinit la méthode parler dans les sous-classes Chat et Chien pour afficher un message spécifique à chaque type d'animal. 
3. Polymorphisme : 
    * Crée des objets pour chaque sous-classe. 
    * Utilise un tableau pour stocker ces objets. 
    * Itère à travers le tableau et appelle la méthode parler pour chaque objet, montrant ainsi le polymorphisme en action. 

## Solution en JavaScript 

```javascript
// Définition de la classe Animal 
class Animal { 
  constructor(name) { 
    this.name = name; 
  } 
 
  // Méthode générale pour tous les animaux 
  parler() { 
    console.log(`${this.name} fait un bruit.`); 
  } 
} 
 
// Sous-classe Chat héritant de Animal 
class Chat extends Animal { 
  constructor(name) { 
    super(name); // Appelle le constructeur de la classe parente 
  } 
 
  // Méthode spécifique au Chat 
  parler() { 
    console.log(`${this.name} dit : Miaou !`); 
  } 
} 
 
// Sous-classe Chien héritant de Animal 
class Chien extends Animal { 
  constructor(name) { 
    super(name); // Appelle le constructeur de la classe parente 
  } 
 
  // Méthode spécifique au Chien 
  parler() { 
    console.log(`${this.name} dit : Ouaf !`); 
  } 
} 
 
// Création d'objets 
const monChat = new Chat('Whiskers'); 
const monChien = new Chien('Rex'); 
 
// Utilisation du polymorphisme 
const animaux = [monChat, monChien]; 
 
animaux.forEach(animal => { 
  animal.parler(); // Appelle la méthode appropriée en fonction du type d'objet 
}); 
 
```