# Feedback Apprenant 2 : Triple Triad Deck Builder

## Fonctionnalités

### Principales

La session avec l'initialisation du deck est fonctionnel
Au niveau de l'affichage du détails de la carte, la structure est bien là, c'est fonctionnel.
Néanmoins, il manque des détails.
Il faudrait afficher les labels correspondant aux valeurs affichés ainsi que de mettre un maximum d'information concernant la carte.<br>

Pour éviter cette erreur à l'avenir, mets toi à la place d'un utilisateur qui vient sur ton application web sans connaître le projet.<br>

Fais en sorte qu'il ne lui manque aucune information à l'écran et qu'elle soit bien détaillé<br>

Mais c'est quelque chose qui se corrige très rapidement, la tâche quand même bien bien exécuté<br>

Concernenant la gestion du deck, il est possible de voir, ajouter une carte mais pas d'en supprimer du deck.<br>

Pour la recherche par élément, c'est fonctionnel mais l'implémentation n'est pas ce qui est recherché.<br>

PostegreSQL est un outil très puissant pour gérer, afficher et filtrer les données stockés en base de données.<br>

Au maximum, il faut privilégier d'utiliser les capacités du langages SQL notamment pour des besoins simples comme récupérer des données en fonction d'une valeur de recherche.<br>

Ainsi que d'éviter au maximum ces traitements dans le code Javascript directement<br>

### Bonus

Rien de fait de ce côté là, dommage :/<br>

## Analyse du code

### Les logs

Éviter au maximum de charger l'espace de log d'informations inutiles.
Les logs ne doivent être utilisé que pour aider à comprendre différents événements liés à l'execution du code.
(Une requête, une erreur, etc...)
Pour inspecter, le code et les valeurs des différents variables, il faudrait plutôt privilégier un outil de débuggage.
En fonction de le IDE que tu utilise pour développer, je pourrais te donner plus d'informations, n'hésite pas à revenir vers moi<br>


### Formatage du code

Prendre le soin de bien formater le code, de bien indenter les lignes et de mettre des espaces entre les différents symboles et mot-clés.
(parenthèse, accalodaes, etc...)<br>

N'hésite d'utiliser des outils prévus à cette effet comme [prettier](https://prettier.io/), [eslint](https://eslint.org/), etc...<br>

Dans le monde du déveleppement, on est très souvent amené à ce que d'autres personnes reprennent notre projet ou on peut soi-même être amené à reprendre un projet après une longue période de délaissement<br>

Les 2 premiers points sont importants pour garder un code agréable à lire et à analyser afin de faciliter la reprise en main<br>


### Codes secrets

Éviter de mettre des données sensible en clair dans le ocde.
Utiliser plutôt des variables d'environnement.
Et ne pas les générer à la main mais utiliser plutôt un outil qui permet de générer une chaîne de caractère complexe aléatoirement
Pour la génération ce site est très bien par exemple :
https://generate.plus/en/base64

Je te conseille de faire un tour sur le code qui initial express dans ton serveur node JS

### La gestion des erreurs

Il serait intéressé d'expliciter la gestion d'une erreur lorsqu'un élément n'a pas été trouvé en base de données notamment.
Pour une question clarté et de maintenabilité du code.
`next()` renvoie l'execution du code au prochain middleware, pour le projet actuel ce n'est pas gênant mais il est possible que sur un autre projet, le middleware suivant qui sera appelé soit totalement autre chose qu'une erreur 404.
De même, qu'il n'est pas évident de savoir du 1er coup d'oeil comment le code fonctionne avec ce type de fonctionnement.<br>

## Conclusion

Globalement il y a du bon travail et une bonne logique mais il reste encore des choses à retravailler.<br>

Tu as un beau potentiel, continue tes efforts ! 👍️