# Retour sur le MCD

Le MCD est cohérent et bien fait globalement.
Mais il y a une erreur la relation entre les entités User et Product.

## The mistake

La relation est 1-1 <-> 1-1, ce qui veut dire un utilisateur ne peut avoir mis un like sur un seul produit et un produit ne peut avoir qu'un seul utilisateur qui l'a liké.

## Proposition de solution

Soit la relation doit être modifié, par exemple User (0,N) <-> (0,N) Product, un utilisateur peut liker plusieurs produits et un produit peut avoir qui avoir été liké plusieurs utilisateurs

Soit la dépendance entre les entités est trop fort et en réalité, il faudrait que les 2 entités ne soient qu'une seule.
Par exemple, si on a une entité User (utilisateur), et une entité Profile_description (description du profil) à moins qu'on modélise une base de donnée pour des agents secrets 🕵‍♂️️ ou pour des personnes qui ont plusieurs vies.
Normalement un utilisateur a une seule description attaché à son profil et une description concerne un seul utilisateur, on est d'accord ?

Donc, il faudrait rassembler les 2 entités en une seule.

## Bonus

Au passage si tu cherches des outils pour modéliser du MERISE, je peux t'en proposer, il y a [Mocodo](https://github.com/laowantong/mocodo) et [MySQL Workbench](https://www.mysql.com/products/workbench/) qui sont des outils gratuits.

Le meilleur pour moi reste [JMerise](http://www.jfreesoft.com/JMerise/) mais il est payant
