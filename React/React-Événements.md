# React

---

## Événements

Vous pouvez réagir à des événements en utilisant des gestionnaires d'événements dans vos composants :

```jsx
function Bouton() {
  function handleClick() {
    alert("Vous avez cliqué sur le bouton");
  }

  return <button onClick={handleClick}>Cliquez ici</button>;
}
```

Remarquez qu'il suffit de transmettre la fonction et non de l'appeler, React appellera votre gestionnaire d'événement lors de l'appui sur le bouton.

Par ailleurs, si le gestionnaire d'événement est relativement court, il est possible de le placer en ligne directement après l'événement :

```jsx
<button onClick={() => alert("Vous avez cliqué sur le bouton")} />
```

<br>

---

### Comportements

Nativement, lorsqu'un bouton dans un formulaire est cliqué, la soumission s'effectue et provoque un rafraîchissement complet de la page, il est possible d'empêcher ce comportement en appelant e.preventDefault sur l'objet événement :

```jsx
<form
  onSubmit={(e) => {
    e.preventDefault();
  }}
/>
```
