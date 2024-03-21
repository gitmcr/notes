# React

---

## Props

Lorsqu'on passe une prop, il est possible de lui assigner une valeur par défaut lorsque le composant parent n'en fournit pas :

```jsx
function Avatar({ name, age = 24 }) {}
```

Dorénavant, si Avatar est utilisé sans la prop age, la valeur par défaut sera définie à 24.

Si vous passez {age = 30}, la valeur par défaut ne sera pas utilisée.

<br>

---

### Syntaxe spread

```jsx
function Profile({ person, size, isColor, border }) {
  return (
    <div className="card">
      <Avatar person={person} size={size} isColor={isColor} border={border} />
    </div>
  );
}
```

Il peut arriver que passer des props soit répétitif, dans un tel cas, il est possible d'utiliser la syntaxe spread sous cette forme :

```jsx
function Profile(props) {
  return (
    <div className="card">
      <Avatar {...props} />
    </div>
  );
}
```

<br>

---

### Immuabilité

Les props sont immuables, lorsqu'un composant doit modifier ses props, il demande à son composant parent de lui passer des props différentes.

Il ne faut pas essayer de changer les props. Lorsque vous avez besoin de réagir à une telle interaction, vous devrez mettre à jour l'état.
