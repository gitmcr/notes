# React

---

## Composant

Un composant est un bout d'UI, il a son propre comportement et sa propre apparence.

Les composants sont des fonctions JavaScript qui renvoient du balisage JSX.

```jsx
function Bouton() {
  return <button>Bouton</button>;
}
```

Après avoir déclaré ce composant Bouton, vous pouvez l'imbriquer dans un autre composant.

```jsx
function App() {
  return (
    <>
      <h1>Voici mon bouton</h1>
      <Bouton />
    </>
  );
}
```

Remarquez que le composant est nommé avec une majuscule au début pour éviter de les confondre avec les balises HTML, qui commencent par une minuscule.

Au fur et à mesure que votre application grandit, vous serez amenés à déplacer vos composants dans différents fichiers à part pour garder une bonne lisibilité.

<br>

---

### Importer et exporter des composants

1. Créer un nouveau fichier pour y loger un composant.
2. Exporter ce composant à partir de ce même fichier :

```jsx
export function Bouton() {
  return <button>Bouton</button>;
}

// Ou par défaut :

export default function Bouton() {
  return <button>Bouton</button>;
}
```

3. Importer ce composant dans le fichier qui en fera usage :

```jsx
import Bouton from "./chemin-du-bouton.jsx";

// Si le fichier comporte plusieurs composants,
// il faudra importer ce composant manuellement :

import { Bouton } from "./chemin-du-bouton.jsx";
```

<br>

---

## Garder des composants purs

En informatique, une fonction pure a les caractéristiques suivantes :

- Elle s'occupe de ses affaires, elle ne modifie pas les objets, variables... qui existaient avant son appel.
- Pour les mêmes entrées, elle produit les mêmes sorties.

Un rendu peut survenir à tout moment, les composants ne doivent pas dépendre de leurs position dans la séquence de rendu.

Mettez plutôt l'état à jour au lieu de modifier des objets existants pour mettre à jour l'affichage.
