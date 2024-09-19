---
sidebar_position: 2
displayed_sidebar: documentationSidebar
title: Théorie
---


# Introduction à React

## Introduction

**React** est une bibliothèque JavaScript utilisée pour créer des interfaces utilisateurs dynamiques et interactives. Développée par Facebook, elle permet de créer des composants réutilisables et d'organiser le code de manière modulaire.

### Pourquoi utiliser React ?
- **Composants réutilisables** : Un des principaux avantages de React est de diviser l'interface en plusieurs composants réutilisables.
- **Performance** : React utilise un "Virtual DOM", ce qui rend les mises à jour de l'interface rapides et efficaces.
- **Écosystème riche** : React a une communauté active et un écosystème large de bibliothèques pour des fonctionnalités avancées.

## Concepts de base de React

### 1. Composants
Les composants sont les éléments de base dans React. Ils peuvent être des **composants fonctionnels** ou des **composants de classe**.

- **Composants fonctionnels** : Ils sont définis comme des fonctions JavaScript qui renvoient du JSX.

  ```jsx
  function Bonjour() {
    return <h1>Bonjour, React!</h1>;
  }
  ```

- **Composants de classe** : Ils sont définis comme des classes ES6 avec une méthode render.

    ```jsx
    class Bonjour extends React.Component {
        render() {
            return <h1>Bonjour, React!</h1>;
        }
    }
    ```

### 2. JSX (JavaScript XML)

JSX est une extension de JavaScript qui permet d’écrire du HTML directement dans le code JavaScript. Bien que JSX ressemble à du HTML, il est compilé en JavaScript pur.

```jsx
const element = <h1>Hello, world!</h1>;
```

### 3. Props (Propriétés)

Les props sont des arguments que vous pouvez passer aux composants. Cela permet de rendre les composants dynamiques et réutilisables.

```jsx
function Salut(props) {
  return <h1>Bonjour, {props.nom}!</h1>;
}

<Salut nom="Alice" />
```

### 4. State (État)

L’état est une fonctionnalité qui permet à un composant de suivre les informations qui peuvent changer au cours de l’exécution. Contrairement aux props, l’état est géré à l’intérieur du composant.

- Exemple avec un composant de classe :

    ```jsx
    class Compteur extends React.Component {
    constructor(props) {
        super(props);
        this.state = { compteur: 0 };
    }

    incrementer = () => {
        this.setState({ compteur: this.state.compteur + 1 });
    }

    render() {
        return (
        <div>
            <p>Vous avez cliqué {this.state.compteur} fois</p>
            <button onClick={this.incrementer}>Cliquez ici</button>
        </div>
        );
    }
    }
    ```

### 5. Hooks

Les Hooks sont une fonctionnalité ajoutée dans React pour utiliser l’état et d’autres fonctionnalités React dans les composants fonctionnels.

- **useState** : Permet de gérer l’état dans un composant fonctionnel.

    ```jsx
    import React, { useState } from 'react';

    function Compteur() {
    const [compteur, setCompteur] = useState(0);

    return (
        <div>
        <p>Vous avez cliqué {compteur} fois</p>
        <button onClick={() => setCompteur(compteur + 1)}>Cliquez ici</button>
        </div>
    );
    }
    ```

## Le cycle de vie des composants

Les composants React suivent un cycle de vie avec plusieurs étapes clés, notamment :

* Montage (componentDidMount) : Lorsque le composant est ajouté au DOM.
* Mise à jour (componentDidUpdate) : Lorsque les props ou l’état changent.
* Démontage (componentWillUnmount) : Lorsque le composant est retiré du DOM.

Avec les hooks, vous pouvez gérer ces étapes avec useEffect.

```jsx
import React, { useEffect } from 'react';

function MonComposant() {
  useEffect(() => {
    console.log('Le composant est monté');

    return () => {
      console.log('Le composant est démonté');
    };
  }, []);

  return <div>Mon composant</div>;
}
```

## Comment démarrer avec React

### 1. Installer Node.js et npm

Assurez-vous que Node.js et npm sont installés sur votre machine.

### 2. Créer une application React

Avec Create React App, vous pouvez facilement configurer une nouvelle application React :

```bash
npx create-react-app mon-app
cd mon-app
npm start
```

Cela va démarrer un serveur de développement sur http://localhost:3000.

## Structurer un projet React

Dans une application React, il est important de structurer votre projet de manière logique. Voici une structure de base :

```
mon-app/
├── public/       # Fichiers publics comme index.html
├── src/
│   ├── components/  # Composants réutilisables
│   ├── App.js       # Composant principal
│   ├── index.js     # Point d'entrée de l'application
```

## Conclusion

React est une bibliothèque puissante pour créer des interfaces utilisateurs modernes et dynamiques. Avec sa structure basée sur les composants, l’utilisation du state et des props, et des fonctionnalités comme les Hooks, il offre une approche flexible et efficace pour le développement web. En maîtrisant ces concepts de base, vous serez en mesure de créer des applications web interactives et performantes.

## Documentation

* https://fr.react.dev/learn/thinking-in-react

N’oubliez pas de consulter la documentation officielle de React pour approfondir votre apprentissage : https://reactjs.org/.