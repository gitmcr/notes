# CSS - Cascading Style Sheets

---

## Syntaxe

```css
selecteur {
  propriété: valeur;
}
```

<br>

- `* {}` : Sélection de tous les éléments dans le fichier
- `tag {}` : Sélection d'un élément HTML (div, button, span...)
- `.classe {}` : Sélection d'une classe d'un élément HTML
- `#id {}` : Sélection d'un ID d'un élément HTML
- `tag ~ tag {}` : Sélection de plusieurs éléments siblings HTML
- `tag:not(.classe) {}` : Sélection d'un élement HTML qui n'as pas la classe référencée

<br>

### Il est possible de référencer plusieurs sélecteurs :

- `tag.classe#id {}` : Sélectionne un élément HTML qui a la classe et l'ID référencés
- `.classe-1, .classe-2 {}` : Sélectionne les deux classes référencées

<br>

### Pour inclure des commentaires dans le fichier CSS :

```css
/* Ceci est un commentaire */

/* Commentaire sur
plusieurs lignes */
```
