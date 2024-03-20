# CSS - Cascading Style Sheets

---

## Media query

```css
@media all and (max-width: 768px) {
  .classe {
    margin: 10vh;
  }
}
```

Changement d'un élément en dépendance de la largeur de la fenêtre du `viewport`, dans ce cas là `768px`

<br>

```css
@media (min-width: 768px) and (max-width: 1024px) {
  #id {
    padding: 1vh;
  }
}
```

Changement d'un élément en dépendance de la largeur de la fenêtre du `viewport`, dans ce cas là, entre `768px` et `1024px`
