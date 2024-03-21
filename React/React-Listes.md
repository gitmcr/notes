# React

---

## Listes

Pour afficher des listes, on utilisera principalement la méthode map().

Si l'on part d'un tableau de produits :

```javascript
const products = [
  { id: 0, name: "Pomme" },
  { id: 1, name: "Orange" },
  { id: 2, name: "Kiwi" },
];
```

Dans un composant, on utilisera la méthode map() pour transformer ce tableau de produits en tableau d'élément :

```jsx
const listItems = products.map((product) => (
  <li key={product.id}>{product.name}</li>
));

return <ul>{listItems}</ul>;
```

Remarquez que li a un attribut key, pour chaque élément d'une liste, vous devez lui passer un identifiant unique qui proviendra généralement de vos données ou de votre base de données.

React utilise cette key pour comprendre la nature de vos changements apportés.

<br>

---

### Filtrage

Pour filtrer des tableaux d'élements, on utilisera la méthode filter() :

```jsx
const people = [
  {
    id: 0,
    name: "Maxime",
    age: 24,
  },
  {
    id: 1,
    name: "Jordan",
    age: 25,
  },
  {
    id: 2,
    name: "Pedro",
    age: 24,
  },
];

const filterAge = people.filter((person) => person.age === 24);
```

Puis utiliser la méthode map() sur cette variable :

```jsx
const listPeople = filterAge.map((person) => (
  <li>
    <p>
      {person.name} est âgé de {person.age}
    </p>
  </li>
));
```
