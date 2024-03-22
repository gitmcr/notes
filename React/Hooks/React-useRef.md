# Hook React

---

## useRef

---

### Référencer une valeur avec une ref

Appelez `useRef` au niveau racine de votre composant pour déclarer une ou plusieurs `refs` :

```jsx
import { useRef } from "react";

function Chrono() {
  const intervalRef = useRef(0);
}
```

useRef renvoie un objet ref `intervalRef` avec une unique propriété current initialement définie à la valeur initiale `0` que vous avez fourni.

Lors des rendus ultérieurs, useRef renverra le même objet. Vous pouvez en modifier la propriété current pour stocker une information que vous relirez plus tard.

Modifier un ref NE DECLENCHE PAS DE RENDU. Les refs sont idéales pour stocker des informations qui n'affectent pas le résultat visuel de votre composant.

Pour mettre à jour la valeur d'une ref, vous devez modifier manuellement sa propriété current `intervalRef.current` :

```jsx
function handleStartClick() {
  const intervalId = setInterval(() => {
    // ...
  }, 1000);
  intervalRef.current = intervalId;
}
```

Par la suite, vous pouvez lire l'identifiant du timer depuis la ref :

```jsx
function handleStopClick() {
  const intervalId = intervalRef.current;
  clearInterval(intervalId);
}
```

En utilisant une ref, vous garantissez :

- Vous pouvez stocker de l'information d'un rendu à l'autre.
- Modifier cette information ne déclenche pas de rendu
- L'information reste locale à chaque instance de votre composant.

<br>

---

### TLDR

`useRef` est un hook qui **permet de créer une variable mutable qui ne sera pas réinitialisée** lors des re-renders du composant.

```jsx
const MyComponent = () => {
  const ref = useRef(0);

  useEffect(() => {
    // Cet effet s'exécute une fois lors du montage du composant
    // et à chaque fois que la valeur de 'ref.current' change
    console.log("useEffect s'est exécuté !");
  }, [ref.current]);

  return (
    <div>
      <h1>Valeur de ref : {ref.current}</h1>
      <button onClick={() => ref.current++}>Incrémenter</button>
    </div>
  );
};
```

- `useRef` renvoie un **objet avec une propriété `current`**.
- La propriété `current` est **mutable** et peut être utilisée pour stocker n'importe quelle valeur.
- La valeur de `ref.current` **n'est pas réinitialisée** lors des re-renders du composant.
