# CSS - Cascading Style Sheets

---

## Placement

---

### Float

- `float: right | left` : Place un élément sur le côté spécifié sur le `viewport`
- `clear: right | left` : Place un élément en dessous d'un élément qui a une propriété `float` sur le côté spécifié

<br>

---

### Flexbox

- `display: flex` : Affiche en ligne tous les éléments enfants selon l'axe

<br>

- `flex-direction: row | column | reverse` : Change l'axe directionnel de l'affichage

<br>

- `justify-content: flex-start` : Démarre du début de la fenêtre sur l'axe principal
- `justify-content: flex-end` : Démarre de la fin de la fenêtre sur l'axe principal
- `justify-content: center` : Aligne au centre de la fenêtre sur l'axe principal
- `justify-content: space-around` : Aligne au centre de la fenêtre sur l'axe principal avec des espaces autour des éléments ( X X X )
- `justify-content: space-between` : Aligne au centre de la fenêtre sur l'axe principal avec des espaces entre des éléments (X X X)

<br>

- `align-items: flex-start | flex-end | center | baseline | stretch` : Aligne les éléments sur l'axe secondaire

<br>

- `align-self: flex-start | flex-end | center | baseline | stretch` : Aligne 1 élément sur l'axe secondaire sans prendre en compte `align-items`

<br>

- `flex-wrap: nowrap | wrap | wrap-reverse` : Force les éléments à être sur la même ligne sur l'axe principal ou sur plusieurs lignes

<br>

- `order: 1 | 2 | ...` : Défini un ordre d'affichage des éléments

<br>

---

### Grid

- `display: grid` : Affiche les éléments sous forme de grille

<br>

- `grid-template-columns: 25% 25% 25% 25%` : Divise la grille en 4 cases de 25% de hauteur chacunes
- `grid-tempalte-rows: 25% 25% 25% 25%` : Divise la grille en 4 cases de 25% de largeur chacunes

<br>

- `grid-column-start: 2` : Déplace un élément sur la 2ème case colonne de la grille
- `grid-row-start: 2` : Déplace un élément sur la 2ème case ligne de la grille

<br>

- `grid-column-end: 4` : Etale l'élément de la case X à la case 4 de la grille en colonne
- `grid-row-end: 4` : Etale l'élément de la case X à la case 4 de la grille en ligne
