# React

---

## L'UI vue comme un arbre

<br>

<img src="https://i.imgur.com/two2OIy.png" />

<br>

React crée un arbre de l'UI à partir de vos composants.

Avec un rendu conditionnel, l'arbre peut différer entre les composants :

```jsx
function Generateur() {
  return <div>{data ? <Composant A /> : <Composant B />}</div>;
}
```

<br>

```mermaid
graph TD;
Generateur-->?
?-->Composant-A;
?-->Composant-B;
```
