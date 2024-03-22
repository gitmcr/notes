# React

---

## Affichage conditionnel

Tout comme pour le JavaScript, il est possible d'utiliser des instructions `if` mais **pas dans le return** d'un composant :

```jsx
let content;
if (isLoggedIn) {
  content = <Panel />;
} else {
  content = <LoginPage />;
}

return <div>{content}</div>;
```

<br>

---

### Opérateur ternaire conditionnel

Pour un style d'écriture plus compact dans le JSX, on peut utiliser **l'opérateur ternaire conditionnel** `? :` :

```jsx
<div>{isLoggedIn ? <Panel /> : <LoginPage />}</div>
```

Il est possible de ne **rien envoyer** selon une certaine condition si vous en avez besoin avec `null` :

```jsx
<div>{isLoggedIn ? <Panel /> : null</div>
```

<br>

---

### Opérateur logique

Si vous n'avez pas besoin de la condition else de l'opérateur ternaire conditionnel, on peut utiliser **l'opérateur logique** `&&` :

```jsx
<div>{isLoggedIn && <Panel />}</div>
```
