![entete](https://github.com/ThomasPradinat/La-chenille/assets/147373681/b6b9b057-a7ea-477c-bf7a-08bf505c6b44)

# Rapport de projet – ROB3

 Année scolaire 2023-2024

## "Absolem, le robot chenille" 

Etudiants : Pradinat Thomas et Dorolle Aurélien 

Encadrants : Pascal Masson 

Ecole Polytechnique Universitaire de Nice Sophia-Antipolis, Département robotique
1645 route des Lucioles, Parc de Sophia Antipolis, 06410 BIOT



### SOMMAIRE

Introduction

Chapitre I : Présentation générale du robot

Chapitre II : L'accroche du robot

- II.1. Cahier des charges	

- II.2. Etat de l'art	

- II.3. Résumé	

Chapitre III : La mobilité

- III.1. Le bras	

  - III.1.1. Cahier des charges	

  - III.1.2. Etat de l'art	

  - III.1.3. Solution envisagée	

  - III.1.4. Résumé	

- III.2. Résumé	

  - III.2.1. Cahier des charges	

  - III.2.2. Etat de l'art et solution envisagée	

Chapitre IV : Les capteurs

- IV.1. Cahier des charges	

- IV.2. Etat de l'art	

- IV.3. Résumé	

Chapitre V : Alimentation et matériaux

- V.1. L'alimentation	

- V.2. Matériaux	

Conclusion

Annexes

Bibliographie



## Introduction 

Nous sommes arrivés en début d’année avec le défi de réaliser un robot capable de grimper aux arbres. Puis nous nous sommes aperçus que les robots grimpeurs possédaient différents cas d’application. Dans l’écologie par exemple, où l’installation de capteurs sur les robots grimpeurs pourrait se révéler intéressante pour prévoir les feux de forêts qui se font de plus en plus récurrents et violents d’une année à l’autre [1]. Plus simplement, le robot serait utile pour observer la faune, effectuer des relevés d’analyse sur le temps long ou surveiller la santé de l’arbre en question avec des capteurs [2][3][4]. De même, on retrouve certaines applications de robots grimpeurs dans l’exploration spatiale, où la NASA envisage de mouvoir un rover sur un plan vertical afin de permettre l’analyse de plusieurs cratères martiens avec un seul robot d’exploration (l’escalade pourrait permettre de passer d’un cratère à un autre) [5][6].

Notre robot aura pour mission de s'agripper aux arbres sans les abîmer et de s’y mouvoir tout en étant économe en énergie. 



## Chapitre I : Présentation générale du robot 

La plupart des robots montant aux arbres se distinguent en deux catégories : ceux qui enlacent le tronc et ceux qui n’en agrippent qu’une partie.

L’inconvénient des robots enlaçant l’arbre est qu’ils ne peuvent monter que certains arbres bien droits, tels que les cocotiers (c’est par exemple le cas du robot Amaran [7]). Nous souhaitons un robot plus polyvalent donc nous préférons utiliser un robot qui agrippe le tronc.

Une grande partie des robots qui agrippent les arbres ont un mouvement linéaire, sur la base d’un mouvement périodique de tirer-pousser, tel une chenille (par exemple en utilisant une tige filetée [8]). Mais là encore, le robot ne serait pas vraiment polyvalent.

Une de nos plus grandes inspirations est le Treebot [9]. C’est un robot capable de monter sur un arbre, en étant capable de faire des mouvements en trois dimensions, pour éviter des branches lors de l'ascension, ou bien d’avancer dessus. Il utilise trois câbles semi-rigides pour pousser en avant la partie avant de son robot ; le fait de jouer sur la différence de poussée des trois câbles permet de déplacer l’avant du robot dans les trois dimensions de l’espace. Il fait aussi un mouvement périodique de tirer-pousser mais peut aussi contourner des obstacles sur le tronc : 

<img width="400" alt="mouvement treebot" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/e80ef61c-fa7c-42c3-9f82-f166d18ee5fe">

Figure I.1.1. – Mouvement complet de tirer-pousser 

<img width="400" alt="mouvement treebot2" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/53dfee83-a5bc-42c3-b91b-2f3a516fc8bd">

Figure I.1.2. – Description de l’évitement d’un obstacle

Le problème du Treebot est qu’il est assez lent pour se déplacer, aussi, le système des câbles nous paraissait moins réalisable avec notre niveau de compétence. 

Ainsi, l’idée serait de lier les deux parties, non pas par des liaisons linéaires extensibles (câbles, pistons…) mais avec un bras robotique avec assez d’articulations pour déplacer chaque partie vers toutes les directions.
Aussi, là où le système de câble était ingénieux pour le Treebot (ou les robots à mouvement linéaire), c’est qu’il permettait de tirer la plus grosse partie du robot vers l’avant sans avoir à la soulever. Ainsi, cette idée va être reprise et, en plus du bras, le corps sera relié à la tête par un treuil. Ainsi le bras n’aura pas à forcer pour ramener le corps vers la tête et ne se contentera que d’accompagner le mouvement pour réaligner les deux parties.




## Chapitre II : L’accroche du robot  

### II. 1. Cahier des charges 

Nous souhaitons posséder une fixation assez puissante pour pouvoir supporter le poids du robot, sans pour autant endommager le tronc de l’arbre. De plus, la fixation doit être assez mobile pour pouvoir permettre au robot d’éviter les obstacles qu’il pourrait rencontrer durant son escalade. La pince doit également être en position « fermée » au repos.

### II. 2. Etat de l’art

Différents types de fixations existent pour les robots grimpeurs : fixation par aspiration sous vide [10][11], par attraction magnétique [12][13] ou encore par adhésion électro-statique [14]. Néanmoins, ces fixations sont adaptées pour adhérer sur des surfaces plates, lisses ou métalliques. Etant donné que nous souhaitons réaliser un robot capable de grimper sur un arbre, c’est-à-dire une surface avec reliefs et non métallique, ces solutions ne nous conviennent pas. 
Nous nous sommes donc inspirés de la pince du Treebot, étant donné que la pince est une fixation qui répondait à nos besoins. La pince en question utilise 4 doigts légèrement courbés pour s’accrocher à l’arbre. Un moteur linéaire pousse la première phalange du doigt pour relever celui-ci (voir ci-dessous). Si le moteur linéaire se retire, des ressorts plaquent le doigt sur le tronc. Le doigt sera capable de tenir au tronc grâce à des aiguilles chirurgicales, servant de griffes.

![pince treebot](https://github.com/ThomasPradinat/La-chenille/assets/147373681/8e695f65-afd8-46b7-8c89-8c2b7dcef8a6)

Figure I.2. – Schéma de la pince utilisé



### II. 3. Solution envisagée

Les principaux éléments d’une telle pince sont le moteur linéaire et les ressorts :  c’est donc sur ces deux éléments que nous allons concentrer notre attention dans le paragraphe qui suit. 

Le moteur linéaire que nous utiliserons devra être assez petit pour pouvoir être placé dans chaque fixation tout en étant assez puissant pour déployer les serres de la pince (cf. annexe 1). De plus, nous avons besoin d’un pont en H pour inverser le courant au niveau des bornes du moteur linéaire pour pouvoir permettre au moteur d’effectuer une translation dans un sens et dans l’autre (cf. annexe1).  	

Au total, pour chaque pince, nous utiliserons 8 ressorts par fixation (2 ressorts pour chaque doigt, sachant qu’une fixation compte 4 doigts). Cependant, lorsqu’il s’agit du ressort situé au joint A sur le schéma ci-dessus, deux solutions s’offrent à nous : choisir un ressort de compression ou choisir un ressort de traction. Nous souhaitons placer un piston dans les ressorts de compression que nous utiliserons pour qu’ils ne puissent pousser que dans une direction unique et ne se déforment pas durant l’effort : utiliser un ressort de traction permettrai de s’affranchir de l’utilisation d’un piston dans le ressort :

![deux configurations ressort](https://github.com/ThomasPradinat/La-chenille/assets/147373681/a10feda2-bf38-4eaa-bd24-7fca4afe7ac3)

Figure I.3. – Schéma du système de ressorts


### II. 4. Résumé

La fixation que nous avons retenue est une pince constituée de quatre doigts, qui pourra s’ouvrir par l’activation d’un moteur linéaire. Lorsque le moteur linéaire n’est pas activé, la pince tient en position « fermée » grâce à un système de ressorts. Même si le choix des ressorts se porte plus vers des ressorts de compression, la question se pose de savoir si on ne placerait pas des ressorts à traction pour faire le lien entre la première phalange et le corps de la pince.



## Chapitre III : La mobilité 

### III. 1. Le bras

### III.	1. 1. Cahier des charges

Le bras doit être capable d’orienter la tête de la chenille dans toutes les directions. Aussi le mouvement de la tête doit être fait dans les trois dimensions car le tronc doit être considéré comme cylindrique et non plat comme le laissait entendre la figure. 


### III.	1. 2. Etat de l’art

Parmi les bras robotiques qui existent dans la littérature, nous en avons sélectionnés quelques-uns pour décrire notre raisonnement : 

<img width="659" alt="brasrobot1" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/f4705780-a804-4d4e-b5c6-5b65f91ae23f">

Figure III. 1. 2. 1. - Bras hydraulique de Fabularium cabinet [15]

Le problème est qu’il ne peut se déplacer que dans un plan orthogonal au sol : il ne tourne pas. Cela reviendrait à faire un robot à mouvement linéaire.

<img width="359" alt="brasrobot2" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/3a7db1df-1cc0-4850-9894-bf4dc5ad7b18">

Figure III. 1. 2. 2. - Tinkerkit Braccio robot de Arduino [16]

En ajoutant une rotation à chaque extrémité, le robot est maintenant capable d’orienter la tête dans toutes les directions. Seulement, cela est vrai sur un plan mais il n’est pas capable de pencher la tête de droite à gauche pour suivre la courbure du tronc.

<img width="425" alt="brasrobot3" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/fac2ec03-d34c-4567-8135-98c20b70c4ea">

Figure III. 1. 2. 3. - NED2 de Niryo[17]

Avec une rotation dans l’axe de l’avant-bras, la tête peut être placée dans toutes les directions de l’espace. Il s’agit d’un axe à 6 degrés de liberté, le plus polyvalent possible. Enfin, nous pensons que la rotation à l’extrémité du bras n’est peut-être pas utile dans notre cas car elle serait faite par la rotation dernièrement ajoutée sur l’avant-bras.

Contrairement à tous les bras robotiques cités précédemment, le bras doit être capable de soulever chacune de ses extrémités en s’appuyant sur l’autre. Il ne faut donc pas que les moteurs à une extrémité soient moins puissants qu’à l’autre. Il faut donc partout les mêmes moteurs, tous assez puissants pour soulever le bras en entier, comme sur le Climbot[18].

![climbot](https://github.com/ThomasPradinat/La-chenille/assets/147373681/26c51d70-8ca3-45a9-a0d5-ab4ca76fa4b1)

Figure III. 1. 2. 4. – Schéma des liaisons du Climbot

### III.	1. 3. Solution envisagée

Le raisonnement précédent nous donne un bras à 5 axes, comme ceci : 

