# CSS - Cascading Style Sheets

---

## Polices

<br>

---

### Style de police

- `font-weight: 0 à 900` : Défini une largeur de police
- `font-style: normal | italic | underline | oblique` : Défini un style de police

<br>

---

### En ligne

https://fonts.google.com/

```css
@import le lien que vous donne le site sur lequel vous avez pris votre police;

* {
  font-family: Police;
}
```

<br>

---

### En local

```css
@font-face {
  src: url("/chemin/police.format") format("format");
}

* {
  font-family: Police;
}
```
