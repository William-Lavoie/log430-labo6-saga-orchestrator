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

### Question 2
####  Lequel de ces fichiers Python déclenche la création ou suppression des commandes? Est-ce qu'il accède à une base de données directement pour le faire? Illustrez votre réponse avec des extraits de code.

C'est le fichier `src/handlers/create_order_handler.py` qui est response de la création ou supression des commandes. Celui-ci n'accède pas à une base de données, il envoie plutôt une requête HTTP vers `store_manager` qui est responsable de la persistence des données des commandes. Selon le patron saga, l'orchestreur ne fait que coordoner les différents services en leur envoyant des requêtes, c'est le concept d'une transaction distribuée.

![Question 2 image 1](./images/2.1.png)

### Question 3
#### Quelle requête dans la collection Postman du Labo 05 correspond à l'endpoint appelé dans create_order_handler.py? Illustrez votre réponse avec des captures d'écran ou extraits de code.

L'endpoint appelé par la requête dans `create_order_handler.py` est `/order` avec la méthode POST, qui dans la collection Postman correspond à `{{baseURL}}/orders` comme on peut le voir dans l'image ci-dessous.

![Question 3 image 1](./images/3.1.png)


## Observations additionnelles
