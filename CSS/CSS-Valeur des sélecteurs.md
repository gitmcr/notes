# CSS - Cascading Style Sheets

---

## Valeur des sélecteurs

```css
0, 1, 0, 0
#id {}

0, 0, 1, 0
.classe {}

0, 0, 0, 1
tag {}

1, 0, 0, 0
!important
```

<br>

Tout comme les sélecteurs, il est possible de combiner les valeurs pour montrer une importance de style :

```css
1, 1, 1 ,1
#id.class tag !important {}

0, 0, 2, 0
.classe1.classe2
```
