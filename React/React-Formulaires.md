# React

---

## Formulaires

Il y a **plusieurs types** d'éléments dans un formulaire classique :

- `<input>` : Le **type est à spécifier** selon vos souhaits, il peut s'agir d'une checkbox, de boutons radio, d'un mot de passe...
- `<textarea>` : Une **zone de texte** qui s'accroît selon la taille du texte qui y est inscrit.
- `<select>` : Une **liste déroulante** à argumenter avec des `<select value="...">`

<br>

Ces éléments peuvent être considérés comme **"contrôlés"** ou **"non-contrôlés"** selon ce que vous voulez en faire :

```html
<textarea defaultValue="Non-contrôlé" />

<textarea value="Contrôlé" onChange={ fonction de mise à jour de l'état } />
```

En spécifiant `defaultValue` vous donnez une valeur par défaut à votre `<textarea>`, avec `value` on défini une valeur actuelle de l'élément de formulaire.

<br>

---

### Gestionnaire d'événement

Un formulaire sera placé dans des balises `<form>` qui a par défaut, un comportement propre au navigateur que l'on peut empêcher avec `e.preventDefault` pour préserver nos données :

```jsx
function handleSubmit(e) {
  e.preventDefault();
}

<form onSubmit={handleSubmit}>
  <textarea value={content} />
  <button type="submit" />
</form>;
```

Remarquez qu'il n'y a même pas besoin d'ajouter un gestionnaire d'événement sur le bouton car le comportement d'un `<form>` est construit en sorte que l'utilisateur puisse envoyer son formulaire en appuyant sur sa touche "Entrée" ou en cliquant sur le bouton.

<br>

---

### Mettre à jour l'état dans un formulaire

Pour mettre à jour un état avec un formulaire, il faut ajouter dans le gestionnaire d'événement, la fonction de mise à jour de l'état :

```jsx
import { useState } from "react";

export default function App() {
  const [content, setContent] = useState("test");

  return (
    <div className="App">
      <form onSubmit={(e) => e.preventDefault()}>
        <textarea
          value={content}
          onChange={(e) => setContent(e.target.value)}
        />
        <button type="submit" />
      </form>
      {content}
    </div>
  );
}
```
