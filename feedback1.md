# Feedback Apprenant 1 : Triple Triad Deck Builder

## Fonctionnalités

### Principales

Tout est fonctionnel, rien à signaler.<br>

### Bonus

Idem. L'application marche à merveille<br>

## Analyse du code

Globalement, le code est bien développé, bien pensé néanmoins il y a quelques axes d'amélioration.<br>


### Les commentaires

Éviter au maximum de charger le code d'informations inutiles.
Les commentaires ne doivent être utilisé que pour aider à comprendre le code et non pour désactiver du code.
Au lieu de commenter le code non exécuté, il vaut mieux le supprimer directement<br>

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

Les 3 premiers points sont importants pour garder un code agréable à lire et à analyser afin de faciliter la reprise en main<br>


### La gestion des erreurs

Il serait intéressé d'expliciter la gestion d'une erreur lorsqu'un élément n'a pas été trouvé en base de données.
Pour une question clarté et de maintenabilité du code.
`next()` renvoie l'execution du code au prochain middleware, pour le projet actuel ce n'est pas gênant mais il est possible que sur un autre projet, le middleware suivant qui sera appelé soit totalement autre chose qu'une erreur 404.
De même, qu'il n'est pas évident de savoir du 1er coup d'oeil comment le code fonctionne avec ce type de fonctionnement.<br>


### Injection SQL

Attention, faille de sécurité 😬️. 
Pour faire simple, l'injection SQL est une faille de sécurité qui consiste à détourner l'utilisation d'une requête SQL afin d'obtenir des informations que normalement l'utilisateur de l'application ne devrait pas avoir accès (Données utilisateur, mots de passe, données bancaires, etc...)
Il devient aussi possible de faire tout autre action comme récupérer la structure de la base de données ainsi que supprimer ou modifier des données.<br>

Cette faille est obtenu par le fait que la rêquete est construite à partir d'une entrée utilisateur.<br>

Cette faille est évité par le fait de prédéfinir à l'avance, les requêtes qui seront executé.<br>

En axe d'amélioration, je t'invite à t'informer sur ce sujet et comparer à nouveau ton code ainsi que celui de la correction.<br><br>


## Conclusion

Mes remarques sont plus des axes d'améliorations qu'autre chose.<br>

Non seulement, tout les tâches ont été complété mais aussi globalement tout le projet a été bien dévelopé.<br><br>


C'est très prometteur, je te félicite, bravo ! 👏️