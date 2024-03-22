# Hook React

---

## useContext

---

### Transmettre des données dans l'arbre

Appelez `useContext` au niveau le plus élevé du composant :

```jsx
import { useContext } from "react";

function Bouton() {
  const theme = useContext(ThemeContext);
}
```

`useContext` renvoie la valeur du texte `theme` pour le contexte `ThemeContext` que vous avez passé.

Pour définir la valeur du contexte, React remonte dans l'arbre des composants à la recherche du fournisseur de contexte le plus proche.

Pour passer un contexte à `Bouton`, il faut enrober ce composant ou l'un de ses parents dans le fournisseur de contexte correspondant :

```jsx
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Formulaire />
    </ThemeContext.Provider>
  );
}
```

Le nombre de couches de composants qu'il y a entre le fournisseur et le `Bouton` importe peu. Un `Bouton` situé n'importe où à l'intérieur du composant `Formulaire` recevra la valeur `'dark'` quand il appelle `useContext(ThemeContext)`.

<br>

---

### Mettre à jour les données passées au contexte

Pour mettre à jour le contexte, associez-le à un état :

```jsx
function App() {
  const [theme, setTheme] = useState("dark");

  return (
    <ThemeContext.Provider value={theme}>
      <Formulaire />
      <Bouton
        onClick={() => {
          setTheme("light");
        }}
      >
        Passer le thème en clair
      </Bouton>
    </ThemeContext.Provider>
  );
}
```

Désormais, tout `Bouton` à l'intérieur du fournisseur recevra la valeur actuelle de `theme`.

Si vous appelez `setTheme` pour mettre à jour la valeur de `theme` que vous avez passé au fournisseur, tous les `Boutons` referont leurs rendus avec la nouvelle valeur `'light'`.

<br>

---

### Spécifier une valeur par défaut

Si React ne trouve aucun fournisseur pour ce contexte `ThemeContext` particulier, la valeur de contexte renvoyée par `useContext` sera égale à la valeur par défaut `'light'` que vous avez spécifié lorsque vous avez créé ce contexte :

```jsx
const ThemeContext = createContext("light");
```

La valeur par défaut ne change jamais, si vous voulez mettre à jour le contexte, associez-le à un état comme décrit dans la section précédente.

<br>

---

### Surcharger le contexte pour une partie de l'arbre

Il est possible de surcharger le contexte en l'enrobant avec un fournisseur ayant une valeur différente :

```jsx
<ThemeContext.Provider value="dark">
  ...
  <ThemeContext.Provider value="light">
    <Footer />
  </ThemeContext.Provider>
  ...
</ThemeContext.Provider>
```

<br>

---

### TLDR

`useContext` est un hook qui **permet d'accéder aux valeurs d'un contexte** React depuis un composant.

```jsx
const ThemeContext = createContext({ theme: "light" });

const MyComponent = () => {
  const { theme } = useContext(ThemeContext);

  return (
    <div>
      <h1>Le thème est : {theme}</h1>
    </div>
  );
};
```

- `useContext` prend un seul argument, **le contexte React auquel vous souhaitez accéder**.
- Vous devez utiliser `useContext` à l'intérieur d'un composant descendant du composant qui a fourni le contexte.
- Vous pouvez utiliser plusieurs contextes dans un même composant.
