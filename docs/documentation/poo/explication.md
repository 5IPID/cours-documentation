---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---

# Introduction à la Programmation Orientée Objet (POO) en JavaScript

La **Programmation Orientée Objet (POO)** est un paradigme de programmation qui repose sur la notion d'objets, qui sont des instances de classes. Contrairement à la programmation procédurale, où les fonctions et les données sont séparées, la POO combine ces deux aspects pour modéliser des entités du monde réel.

## Pourquoi utiliser la POO ?
- Facilite la réutilisabilité du code.
- Améliore la modularité.
- Permet une meilleure maintenance du code à grande échelle.

---

## Concepts de base de la POO

### 1. Objets et Classes

Une **classe** est un modèle pour créer des objets. Un **objet** est une instance d'une classe.

Exemple en JavaScript :

```javascript
// Définition d'une classe
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Méthode de la classe
  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

// Création d'un objet
const person1 = new Person('Alice', 25);
person1.greet();  // "Hello, my name is Alice and I am 25 years old."
```

### 2. Encapsulation

L’encapsulation consiste à protéger l’état interne d’un objet en utilisant des variables privées et des méthodes publiques.

Exemple en JavaScript avec des variables privées (ES6) :

```javascript
class BankAccount {
  #balance;  // Propriété privée

  constructor(balance) {
    this.#balance = balance;
  }

  deposit(amount) {
    this.#balance += amount;
    console.log(`New balance: $${this.#balance}`);
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount(100);
account.deposit(50); // New balance: $150
console.log(account.getBalance());  // 150
```

### 3. Héritage

L’héritage permet de créer de nouvelles classes à partir de classes existantes, ce qui favorise la réutilisation du code.

Exemple en JavaScript :

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  makeSound() {
    console.log(`${this.name} is making a sound.`);
  }
}

class Dog extends Animal {
  makeSound() {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog('Buddy');
dog.makeSound();  // "Buddy barks."
```

### 4. Polymorphisme

Le polymorphisme permet d’utiliser la même méthode avec des objets de types différents. Il peut être implémenté via l’héritage ou des interfaces.

Exemple en JavaScript :

```javascript
class Shape {
  constructor(name) {
    this.name = name;
  }

  draw() {
    console.log(`Drawing a shape.`);
  }
}

class Circle extends Shape {
  draw() {
    console.log(`Drawing a circle.`);
  }
}

class Square extends Shape {
  draw() {
    console.log(`Drawing a square.`);
  }
}

const shapes = [new Circle('circle'), new Square('square')];

shapes.forEach(shape => shape.draw());
// "Drawing a circle."
// "Drawing a square."
```

## Principes SOLID de la POO

1.	Single Responsibility Principle (SRP) : Une classe doit avoir une seule responsabilité.
2.	Open/Closed Principle (OCP) : Les entités doivent être ouvertes à l’extension mais fermées à la modification.
3.	Liskov Substitution Principle (LSP) : Les sous-classes doivent pouvoir remplacer leurs super-classes sans modifier le comportement du programme.
4.	Interface Segregation Principle (ISP) : Les clients ne doivent pas être forcés de dépendre d’interfaces qu’ils n’utilisent pas.
5.	Dependency Inversion Principle (DIP) : Les modules de haut niveau ne doivent pas dépendre des modules de bas niveau. Les deux doivent dépendre d’abstractions.

Exemple pratique : Système de gestion d’étudiants

Voici un exemple simplifié d’une petite application de gestion d’étudiants avec Node.js :

```javascript
class Student {
  constructor(name, grade) {
    this.name = name;
    this.grade = grade;
  }

  getDetails() {
    return `${this.name} has a grade of ${this.grade}.`;
  }
}

class GraduateStudent extends Student {
  constructor(name, grade, thesis) {
    super(name, grade);
    this.thesis = thesis;
  }

  getDetails() {
    return `${this.name} has a grade of ${this.grade} and a thesis on ${this.thesis}.`;
  }
}

const student1 = new Student('Alice', 'A');
const student2 = new GraduateStudent('Bob', 'A+', 'Artificial Intelligence');

console.log(student1.getDetails());  // "Alice has a grade of A."
console.log(student2.getDetails());  // "Bob has a grade of A+ and a thesis on Artificial Intelligence."
```

## Avantages et inconvénients de la POO

### Avantages :

•	Modularité : Le code est organisé en classes, facilitant la maintenance et l’évolution.
•	Réutilisabilité : L’héritage permet de réutiliser des fonctionnalités existantes.
•	Maintenance : Le code orienté objet est plus facile à maintenir.

### Inconvénients :

•	Complexité : Pour de petits projets, la POO peut ajouter une couche de complexité inutile.
•	Performance : L’abstraction et la modularité peuvent entraîner une légère baisse de performance.

## Conclusion

La POO est un paradigme puissant et largement utilisé dans le développement d’applications complexes. En utilisant des concepts tels que l’encapsulation, l’héritage et le polymorphisme, elle permet de structurer le code de manière plus claire, réutilisable et facile à maintenir.

Les principes SOLID sont des guides essentiels pour renforcer les bonnes pratiques en POO, surtout lorsque les projets deviennent plus grands et plus complexes.