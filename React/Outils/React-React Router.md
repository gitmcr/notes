# Outils React

---

## React Router

---

**React Router permet de créer des routes entre vos composants et faire devenir de votre page web en site web.**

<br>

### 1. Installer le module de React Router avec `npm i react-router-dom`

<br>

### 2. Créer un fichier dans votre projet React avec le nom que vous souhaitez, ici je l'appelle `Router.jsx` et importer React Router :

```jsx
import { createBrowserRouter } from "react-router";
```

<br>

### 3. Créer la variable qui contiendra toutes vos routes dans ce même fichier :

```jsx
const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
  },
  {
    path: "/page2",
    element: <Page2 />,
  },
]);
```

<br>

### 4. Une étape importante pour l'accessibilité est de créer une page d'erreur si un utilisateur se retrouve sur un lien non-existant, on crée donc un nouveau fichier, ici je l'appelle `PageErreur.jsx` et je lui indique son comportement comme pour un composant normal :

```jsx
import { Link } from "react-router-dom";

export default function PageErreur() {
  return (
    <>
      <h1>Erreur 404</h1>
      <Link to="/">Retourner à l'accueil</Link>
    </>
  );
}
```

_- Vous remarquez qu'on importe et utilise `Link`, contrairement aux balises HTML `<a>`, `Link` permet d'accéder à une page précise sans recharger entièrement le navigateur car tel est son comportement par défaut._

<br>

### 5. Importer le nouveau fichier vers notre page d'erreur dans `Router.jsx` :

```jsx
const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    // Juste ici
    errorElement: <PageErreur />,
  },
  {
    path: "/page2",
    element: <Page2 />,
  },
]);
```

<br>

### 6. La dernière étape est d'importer `Router.jsx` dans notre main.jsx et de remplacer la page de rendu initiale par la variable créée :

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";

// Ici, on importe nos dépendances et notre variable 'router'
import { RouterProvider } from "react-router-dom";
import { router } from "./router";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    {/* Et ici, on initialise le nouveau rendu initial */}
    <RouterProvider router={router} />
  </React.StrictMode>
);
```
