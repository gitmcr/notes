# CSS - Cascading Style Sheets

---

## Propriétés custom

```css
:root {
  --primary-color: black;
  --margin: 1.2rem;
  --padding: 0.5rem;
}

.classe {
  color: var(--primary-color);
  margin: var(--margin);
  padding: var(--padding);
}
```

- Déclaration de variables de couleur / margin et padding qui peut être utilisée n'importe où dans le fichier lors de son appel
- Appel des variables couleur / margin et padding dans l'élément avec la classe spécifiée
