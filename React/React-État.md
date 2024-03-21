# React

---

## État

Si vous souhaitez que votre composant se souvienne de certaines informations et les affiche, il faudra **l'équiper d'un état**.

1. Importer le hook `useState` :

```jsx
import { useState } from "react";
```

2. Servez vous en pour **déclarer une variable d'état** :

```jsx
function Compteur() {
  const [count, setCount] = useState(0);
}
```

`useState` renvoie deux choses :

- L'état courant `count`.
- Sa fonction de mise à jour `setCount`.

A son premier affichage, count sera initialisé à `0` grâce à l'argument passé à droite du hook `useState`.

Lorsque vous souhaiterez modifier cet état, il faudra appeler `setCount` et lui passer une nouvelle valeur en argument :

```jsx
function Compteur() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }

  return <button onClick={handleClick}>Vous avez cliqué {count} fois</button>;
}
```

Ici, le bouton incrémente `count` de 1 à chaque clic.

<br>

---

### Indépendance

Si vous affichez ce même composant plusieurs fois, **chacun aura son propre état** et n'aura aucun impact sur l'état de l'autre composant :

```jsx
<>
  <Compteur />
  <Compteur />
</>
```

Chaque composant se souviendra de son propre état et **n'affectera pas les autres**.

<br>

---

### Cumuler les mises à jour d'un même état

Modifier une variable d'état va planifier un nouveau rendu, vous souhaiterez parfois effectuer **plusieurs opérations** sur la valeur avant de passer au rendu suivant.

React ne se précipite pas au rendu à chaque fois que vous lui soumettez une requête, il vous laisse plutôt terminer vos requêtes avant de procéder.

```jsx
setCount(count + 1); // setCount (0 + 1)
setCount(count + 1); // setCount (0 + 1)
setCount(count + 1); // setCount (0 + 1)
```

Le rendu sera donc `count = 1` et non `count = 3`

<br>

Pour mettre à jour plusieurs fois un même état avant le prochain rendu, vous passerez **une fonction qui va calculer le prochain état** sur base du précédent dans la fil des mises à jour.

```jsx
setCount((c) => c + 1); // setCount(0 + 1)
setCount((c) => c + 1); // setCount(1 + 1)
setCount((c) => c + 1); // setCount(2 + 1)
```

React stocke `3` comme résultat final et le renvoie depuis l'état.
