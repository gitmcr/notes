# React

---

## Rendu et Commit

React effectue le rendu du composant avant de l'afficher sur l'écran de l'utilisateur, ce processus compte **3 étapes** :

<br>

1. Le déclenchement du rendu

- Il y a plusieurs déclencheurs possibles, le **rendu initial** du composant et lorsque **l'état local à été mis à jour** dans le composant ou un de ces ancêtres.

<br>

2. React appelle vos composants pour déterminer ce qu'il doit afficher à l'écran

- Lors de son **rendu initial**, React appelle le composant racine et lors des **rendus suivants**, il appellera les fonctions composants dont une mise à jour de l'état local à déclenché le rendu.

<br>

3. React met à jour le DOM

- Lors du **rendu initial** et des **rendus ultérieurs**, React s'attachera à effectuer le strict minimum d'opération nécessaire pour mettre le DOM à jour en correspondance avec le résultat du dernier rendu en date.
