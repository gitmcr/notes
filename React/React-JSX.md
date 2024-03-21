# React

---

## JSX

Le JSX est plus exigeant que le HTML, il faut impérativement fermer toutes les balises déclarées, même les auto-fermantes :

```html
<br />

<!-- deviendra : -->

<br />
```

Par ailleurs, un composant ne peut renvoyer qu'une seule balise parente JSX (qui peut en enrober une multitude) :

```jsx
<div>
  <h1>Titre</h1>
  <p>Paragraphe</p>
</div>
```

Ou un Fragment React qui sera invisible dans le code source de la page :

```jsx
<>
  <h1>Titre</h1>
  <p>Paragraphe</p>
</>
```

<br>

---

### Attributs

Le JSX provoque aussi des changements nominatifs d'attributs comme pour "class" dans HTML ou encore le "for" HTML :

```jsx
<div class="classe"></div>

// deviendra :

<div className="classe"></div>
```

```jsx
<label for="label">Label</label>

// deviendra :

<label htmlFor="label">Label</label>
```

On convertis donc en camelCase comme pour du JavaScript.

<br>

---

### Ajouter du JavaScript

Il est possible d'entrer en mode JavaScript dans le balisage en utilisant les accolades { } afin d'injecter une variable ou des expressions :

```jsx
function App() {
  return <h1>{user.name}</h1>;
}
```

Tout comme il est aussi possible d'ajouter du JavaScript au sein d'attributs comme pour le src d'une image :

```jsx
<img className="avatar" src="{user.imageUrl}" />
```

<br>

---

### Ajouter du style

Pour définir du style en ligne dans le JSX, il faut passer en mode JavaScript ainsi qu'un littéral objet donc deux paires d'accolades {{ }} :

```jsx
<img
    className="avatar"
    src={user.imageUrl}
    style={{width: 10px, height: 10px}}
/>
```
