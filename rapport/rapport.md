<img src="https://upload.wikimedia.org/wikipedia/commons/2/2a/Ets_quebec_logo.png" width="250"> \
William Lavoie \
Rapport de laboratoire \
LOG430 — Architecture logicielle \
4 Novembre 2025
École de technologie supérieure

## Questions
### Question 1
#### Lequel de ces fichiers Python représente la logique de la machine à états décrite dans les diagrammes du document arc42? Est-ce que son implémentation est complète ou y a-t-il des éléments qui manquent? Illustrez votre réponse avec des extraits de code.

C'est le fichier `src/controllers/order_saga_controller.py` qui est responsable d'implémenter la logique de la machine à états. Le contrôleur est responsable de choisir l'action a effectué en fonction de l'état courant, et il appelle les fonctions nécessaires afin d'effectuer les différentes étapes de la saga. L'implémentation n'est toutefois pas complète tel que le suggère le `TODO`, car certains des états ne sont pas considérés, soit `CREATING_PAYMENT`, `INCREASING STOCK` et `CANCELLING ORDER`.

![Question 1 image 1](./images/1.1.png)

## Observations additionnelles
