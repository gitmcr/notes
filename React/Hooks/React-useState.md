# Hook React

---

## useState

---

### Ajouter un état à un composant

Appelez `useState` à la racine de votre composant pour déclarer une ou plusieurs **variables d'état** :

```jsx
import { useState } from "react";

function App() {
  const [age, setAge] = useState(24);
  const [name, setName] = useState("Maxime");
}
```

`useState` renvoie un tableau avec **deux valeurs** :

- **L'état courant** `age` et `name` avec comme valeur l'état initial `24` et `"Maxime"`.
- **La fonction de mise à jour** qui permet de modifier la valeur de l'état `setAge` et `setName`.

<br>

Pour **mettre à jour l'état**, appelez la fonction de mise à jour avec le prochain état :

```jsx
function handleClick() {
  setAge(25);
  setName("Max");
}
```

<br>

---

### Mettre à jour l'état sur base de l'état précédent

Dans l'exemple, `age` vaut `24`. Avec un gestionnaire d'événement on essaye d'appeler `setAge(age + 1)` trois fois pour renvoyer `age = 27` :

```jsx
function handleClick() {
  setAge(age + 1);
  setAge(age + 1);
  setAge(age + 1);
}
```

Cependant, après un clic, `age` vaudra `25` et non `27` comme prévu car appeler **la fonction de mise à jour ne met pas à jour la variable d'état** `age`, donc à chaque appel à setAge(age + 1) devient `setAge(25)`.

<br>

Pour résoudre ce problème, il faut passer une **fonction de mise à jour** à `setAge` au lieu du prochain état :

```jsx
function handleClick() {
  setAge((a) => a + 1);
  setAge((a) => a + 1);
  setAge((a) => a + 1);
}
```

Ici, `(a) => a + 1` est la fonction de mise à jour. Elle prend l'état en attente `a` et **calcule à partir de celui-ci le prochain état** `a + 1`.

<br>

React met ces fonctions de mise à jour dans une **file d'attente** et pendant le prochain rendu, il va les appeler dans le même ordre :

1. `(a) => a + 1` recevra un état d'attente à `24` et renverra `25` comme prochain état.
2. `(a) => a + 1` recevra un état d'attente à `25` et renverra `26` comme prochain état.
3. `(a) => a + 1` recevra un état d'attente à `26` et renverra `27` comme prochain état.

<br>

---

### TLDR

`useState` est un hook qui permet d'ajouter une **variable d'état** à votre composant.

```jsx
const MyComponent = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>Compteur : {count}</h1>
      <button onClick={() => setCount(count + 1)}>Incrémenter</button>
    </div>
  );
};
```

- `useState` renvoie un tableau avec deux valeurs, **l'état actuel** qui correspond à la **valeur initiale** passée lors du premier rendu et sa **fonction de mise à jour** qui permet de modifier l'état et déclencher un nouveau rendu.
- Vous pouvez utiliser plusieurs appels à useState dans un même composant.
