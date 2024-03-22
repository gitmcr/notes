# Hook React

---

## useRef

---

### TLDR

Un `custom hook` est une fonction qui utilise d'autres hooks pour **encapsuler une logique réutilisable**.

```jsx
const useCounter = () => {
  const [count, setCount] = useState(0);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  // Retourne un objet regroupant les états et fonctions utiles
  return { count, increment, decrement };
};

const MyComponent = () => {
  const { count, increment, decrement } = useCounter();

  return (
    <div>
      <h1>Compteur : {count}</h1>
      <button onClick={increment}>Incrémenter</button>
      <button onClick={decrement}>Décrémenter</button>
    </div>
  );
};
```

- Les `custom hooks` acceptent des arguments _si nécessaire_ pour **personnaliser leur comportement**.
- Ils **retournent un tableau contenant les valeurs d'état et les fonctions de mise à jour** que vous souhaitez exposer au composant qui l'utilise.
- Ils permettent de **séparer la logique de la présentation du composant**, _améliorant la lisibilité et la maintenabilité du code_.
- Vous pouvez créer des `custom hooks` pour gérer n'importe quelle logique réutilisable, y compris _la gestion des formulaires_, _l'appel d'API_, _l'abonnement aux événements_ etc.
