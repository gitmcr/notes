# Hook React

---

## useEffect

---

### Utilisation

Appelez `useEffect` au niveau racine de votre composant :

```jsx
import { useEffect } from "react";

function Composant() {
  useEffect(
    () => {
      // code de mise en place
      return () => {
        // code de nettoyage
      };
    },
    [
      /*liste de dépendances*/
    ]
  );
}
```

Vous devez passer **deux arguments** à `useEffect` :

1. Une **fonction de mise en place** qui vous connecte au système.

- Elle devrait renvoyer une **fonction de nettoyage** qui vous déconnecte du système.

2. Une **liste de dépendances** comprenant chaque valeur issue de votre composant que ces fonctions utilisent.

<br>

React appellera vos fonctions de mise en place et de nettoyage **chaque fois que nécessaire** :

1. Quand votre composant est ajouté à la page **(montage)**.
2. Après chaque nouveau **rendu** de votre composant, _si les dépendances ont changé_ :

- D'abord, **le code de nettoyage** est exécuté avec les anciennes props et valeurs d'état.
- Ensuite, **le code de mise en place** est exécuté avec les nouvelles props et valeurs d'état.

3. **Le code de nettoyage** est exécuté une dernière fois lorsque le composant est retiré **(démontage)**.

<br>

---

### TLDR

`useEffect` est un hook qui permet d'**exécuter du code en fonction des changements de props ou de l'état d'un composant**. Il est souvent utilisé pour effectuer des effets secondaires tels que l'appel d'API ou l'abonnement aux événements.

```jsx
const MyComponent = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Cet effet s'exécute une fois lors du montage du composant
    // et à chaque fois que la valeur de 'count' change
    console.log("useEffect s'est exécuté !");
  }, [count]);

  return (
    <div>
      <h1>Compteur : {count}</h1>
      <button onClick={() => setCount(count + 1)}>Incrémenter</button>
    </div>
  );
};
```

- `useEffect` prend deux arguments : **une fonction** et **un** **tableau de dépendances**.
- La fonction est exécutée à chaque fois que l'un des éléments du tableau de dépendances change.
- Si le tableau de dépendances est vide, la fonction est exécutée une fois lors du montage du composant.
- Vous pouvez utiliser plusieurs appels à `useEffect` dans un même composant.
