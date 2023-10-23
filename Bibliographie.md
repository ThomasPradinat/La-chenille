![entete](https://github.com/ThomasPradinat/La-chenille/assets/147373681/b6b9b057-a7ea-477c-bf7a-08bf505c6b44)

# Rapport de projet – ROB3

 Année scolaire 2023-2024

## "Absolem, le robot chenille" 

<img width="419" alt="vrai chenille" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/4d29b74c-35a0-47ee-a780-b57e2a60f4d7">

![montage représentation robot](https://github.com/ThomasPradinat/La-chenille/assets/147373681/2bf0546f-9cf5-4cda-9b87-6021e26f016c)

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

![Image liaisons bras](https://github.com/ThomasPradinat/La-chenille/assets/147373681/6237ae9a-0cef-4754-b212-ff22cce14020)

Figure III. 1. 3. 1. – Schéma des liaisons du bras 

Les articulations du bras seraient des servomoteurs. En effet, seule une position précise est requise pour chaque moteur ; aussi, un moteur pas à pas serait trop volumineux et trop lourd pour qu’il en soit placé 5 sur notre robot.

Les servomoteurs devront être attachés de manière à ne pas fonctionner par arrachement (comme pour le bras d’Arduino). Pour les servomoteurs qui font une rotation directement dans leur axe, il ne faut pas que ce soit le servomoteur qui tienne le reste du bras, donc il faut que la partie mobile soit déjà liée au reste comme ceci : 

![servomoteur tout droit](https://github.com/ThomasPradinat/La-chenille/assets/147373681/1146cc45-ded6-4e6f-bab8-739a320a96a2)

Figure III. 1. 3. 2. – Schéma de liaison du servomoteur 

Une estimation des servomoteurs qui nous semble raisonnable serait des servomoteurs de 35 kg/cm ; cela permettrait de soulever la tête et le bras (pensant donc au maximum 1 kg) à une distance maximale de 30 cm. Ceci semble être en accord avec les dimensions de notre robot. Par exemple nous avons trouvé les servomoteurs ‘’35kg servo numérique sans noyau” qui est capable de faire une rotation supérieure à 180°et qui fonctionne entre 5 et 7.4V (cf. annexe 1).

Un des risques par rapport à la montée à l’arbre, avec le bras mécanique, est que lorsque la tête est détachée, elle risque de créer un moment trop important sur le corps, qui risque de s’arracher du tronc. Pour pallier cela, il y aurait deux solutions : premièrement, un second corps pourrait être ajouté, ainsi la chenille aurait toujours deux parties accrochées au tronc pendant que la troisième se détacherait pour avancer. Cette solution apporterait deux avantages supplémentaires mais aussi des inconvénients. Cela permettrait peut-être de porter plus de charge, en plus de rendre la chenille plus stable. Cependant, elle consommerait beaucoup plus d’énergie pour se déplacer et serait plus lente pour monter, étant donné que le mouvement serait en trois temps au lieu de deux.

La seconde solution serait de rajouter une “queue” à notre chenille pour plaquer le corps contre le tronc (comme cela a été ajouté sur le robot Rise de Boston Dynamics [19]).

Nous pensons que le choix de la solution la plus adaptée dépendra de l’efficacité de la pince que nous arriverons à faire.

### III.	1. 4. Résumé

Le bras reliant la tête au corps est un bras à 5 axes dont les rotations sont effectuées par des servomoteurs de 25kg/cm pour supporter le poids de la tête. Ils devront être assemblés entre eux de manière à ne pas fonctionner par arrachement.
Le poids de la partie avant du robot va impliquer de sûrement ajouter un composant supplémentaire à notre robot, soit une queue, soit un second corps.



### III. 2. Le treuil

### III. 2. 1. Cahier des charges

Le treuil doit être capable de tracter le poids du corps ainsi que la charge supplémentaire que ce dernier pourrait porter.

### III. 2. 1. Etat de l’art et solution envisagée

Durant la phase de poussée, le treuil sera libre et se déroulera (ou bien il tournera pour libérer du câble) lorsque le bras fait avancer la tête ; cependant au retour, le treuil s’active et c’est lui qui tire l’ensemble du poids du corps vers la tête.
Pour ce qui est du choix du treuil à utiliser, en acheter un serait inutile, premièrement par ce que nous n’aurons pas besoin de trois mètres de câble mais aussi que cela est facile à construire soit même avec un servomoteur à 360°, comme on peut le voir sur cette image : 

![treuille](https://github.com/ThomasPradinat/La-chenille/assets/147373681/4384940a-17a0-49e4-8528-4a5b9c27372a)

Figure III. 2. 1. 1. – Treuil Servo Intégré à Tambour GRC 25T, Accessoires de Mise à Niveau

La pièce dorée peut être fabriquée à l’imprimante 3D, tandis que le câble et la bobine peuvent être achetés en ligne (cf. annexe1).

Le servomoteur est utilisé directement autour de son axe, donc la charge qu’il pourrait tirer est celle indiquée par le fabricant (comme 25kg/cm signifie pour nous que l’on peut tracter 25kg avec). Le moteur doit être capable de porter le corps ainsi que sa charge, mais aussi une partie du poids du bras ; donc il ne peut pas s’agir d’un petit servomoteur de 3kg/cm. Un servomoteur de 10kg/cm pourrait suffire mais un de 25 a été trouvé, un peu moins cher que le précédent (cf. annexe1).




## Chapitre IV : Les capteurs

### IV. 1. Cahier des charges

Les capteurs devront permettre à Absolem de détecter un obstacle se situant devant lui, mais aussi de comprendre la courbure du tronc pour permettre aux pinces de s’accrocher correctement à l’arbre. 

### IV.  2. Etat de l’art

<img width="880" alt="tableau capteurs" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/037e98a9-b03a-4a83-a541-78f9e8e26a0c">

 
### IV. 3. Solution retenue

Le capteur que nous utiliserons pour détecter les obstacles situés en face du robot sera un pointeur laser : l’utilisation d’un radar serait optimale sur matériau métallique (ce qui n’est pas ce que nous voulons observer) et le sonar ne fonctionne qu’immergé sous l’eau (l’onde s’évanouit rapidement dans l’air, sans compter le fait qu’émettre des ultrasons dans une zone naturelle peut perturber la faune environnante). Un système de balayage pourra être ajouté afin de permettre au robot d’avoir une vision 3D de ce qui se situe en face de lui. 

Pour les capteurs qui serviront à lire la courbure du tronc, ici encore, des pointeurs laser seront utilisés, pour les mêmes raisons citées précédemment. L’idée est de placer 3 pointeurs lasers sur différents endroits de la pince pour pouvoir voir si les capteurs observent différentes distances entre la pince et le tronc (c’est-à-dire une inclinaison de la pince par rapport au tronc).

## Chapitre V : Alimentation et matériaux

### V. 1. Caractéristiques générales de l’alimentation

Voici un récapitulatif de tout ce qui a besoin d’alimentation dans notre robot : 

- 2 moteurs linéaires = 12V.
  
- 5 servomoteurs du bras = 5-7.4V
  
- servomoteur du treuil = 4.8-7V
  
- carte Arduino = + de 5V
  
- L293 = 5V
  
- capteurs
  
On peut simplifier tout ceci avec uniquement deux tensions différentes : 

12V → 2 moteurs linéaires

6V → Carte Arduino + L293 + servomoteur du treuil + 5 servomoteurs du bras + capteurs

Ensuite, nous utiliserons un régulateur de tension de 12 vers 6V pour n’avoir qu’une seule batterie de 12V (cf. annexe 1).
La batterie doit être assez petite est légère pour pouvoir être transportée par la chenille (cf. annexe1). 


### V.	2. Matériaux

Le robot ne doit pas être trop lourd pour ne pas se décrocher de l’arbre mais assez solide pour pouvoir avoir une accroche efficace sur l’arbre. Surtout, la plus grosse contrainte que nous allons avoir en termes de matériaux est celle de la fabrication. En effet, la plupart des pièces vont être construites sur mesures à l’imprimante 3D, donc les principales parties du robot seront en plastique. Quelques parties qui auraient besoin d’être plus solides pourraient aussi être en métal léger. 
La chenille doit être capable de résister aux intempéries : vent, pluie… Il sera donc pertinent dans un second temps de perméabiliser les fils et les compartiments de la batterie et de la carte.

## Conclusion

Le robot sera constitué de deux parties (les fixations) reliées par un bras mécanique ainsi que par un treuil. Les fixations seront constituées de 4 doigts animés par un moteur linéaire et un système de ressorts. Le bras mécanique possèdera quant à lui 5 axes dont les articulations seront assurées par des servomoteurs. L’ajout d’un second corps ou d’une queue pour le robot est en discussion. Les différentes fixations seront également reliées par un treuil pour ne pas trop mettre d’effort sur le bras mécanique. Des capteurs laser assureront au robot la visualisation de son environnement ainsi que la bonne lecture des reliefs du tronc. 


## Annexes

### Annexe 1 : Liste des pièces à commander

Moteur linéaire   Quantité : 2   Lien moteur linéaire : 
https://www.amazon.fr/Poweka-automatique-Domotique-escamotables-Ascenseur/dp/B0B4MWRFX9/ref=sr_1_6?keywords=Linear+Actuator+12&qid=1696067441&sr=8-6 

Servomoteur bras   Quantité : 5   Lien servomoteur bras : 
https://fr.aliexpress.com/item/1005004347055116.html?spm=a2g0o.productlist.main.119.704c6442SpzyuF&algo_pvid=c4f3b939-388c-4c17-85ac-7a311dc71bd6&algo_exp_id=c4f3b939-388c-4c17-85ac-7a311dc71bd6-59&pdp_npi=4%40dis%21EUR%2123.28%2114.9%21%21%2124.04%21%21%40211b5e2b16979636636915308e1899%2112000030010275368%21sea%21FR%211698746122%21&curPageLogUid=kr6TotET2Pq0 

Treuil   Quantité : 1   Lien treuil : 
https://fr.aliexpress.com/item/4000932042855.html?src=google&src=google&albch=shopping&acnt=248-630-5778&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&isSmbAutoCall=false&needSmbHouyi=false&src=google&albch=shopping&acnt=248-630-5778&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=fr4000932042855&ds_e_product_merchant_id=109164712&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=20180143332&albag=&isSmbAutoCall=false&needSmbHouyi=false&gclid=CjwKCAjw-KipBhBtEiwAWjgwrGMbjXMAoKySz195NetisjnpKh6SXa2wjud1a5qi8O21ZrP0MjvlphoCPm4QAvD_BwE&aff_fcid=0768b7cb076a4a35994d90e072dee117-1697309197398-07037-UneMJZVf&aff_fsk=UneMJZVf&aff_platform=aaf&sk=UneMJZVf&aff_trace_key=0768b7cb076a4a35994d90e072dee117-1697309197398-07037-UneMJZVf&terminal_id=1065899e4d1a410e821ded913fef0ef5&afSmartRedirect=y 

Servomoteur treuil   Quantité : 1   Lien servomoteur treuil : 
https://fr.aliexpress.com/item/4000114287971.html?src=google&src=google&albch=shopping&acnt=248-630-5778&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&isSmbAutoCall=false&needSmbHouyi=false&src=google&albch=shopping&acnt=248-630-5778&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=fr4000114287971&ds_e_product_merchant_id=109256086&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=20180143332&albag=&isSmbAutoCall=false&needSmbHouyi=false&gclid=CjwKCAjwkNOpBhBEEiwAb3MvvWpa0tSuRSOGOBsLRq8m4lYeY8cllPAk0LQIW7yV610MUueB5kWNPBoCccEQAvD_BwE&aff_fcid=b2d802dd0a8344b8a4324f2f2cb2fe9a-1697980295995-05945-UneMJZVf&aff_fsk=UneMJZVf&aff_platform=aaf&sk=UneMJZVf&aff_trace_key=b2d802dd0a8344b8a4324f2f2cb2fe9a-1697980295995-05945-UneMJZVf&terminal_id=1065899e4d1a410e821ded913fef0ef5&afSmartRedirect=y 

Capteurs   Quantité : 7   /

Régulateur de tension   Quantité : 1   Lien régulateur de tension : 
https://fr.aliexpress.com/item/4000091864476.html?src=google&src=google&albch=shopping&acnt=248-630-5778&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&isSmbAutoCall=false&needSmbHouyi=false&src=google&albch=shopping&acnt=248-630-5778&slnk=&plac=&mtctp=&albbt=Google_7_shopping&gclsrc=aw.ds&albagn=888888&ds_e_adid=&ds_e_matchtype=&ds_e_device=c&ds_e_network=x&ds_e_product_group_id=&ds_e_product_id=fr4000091864476&ds_e_product_merchant_id=107733623&ds_e_product_country=FR&ds_e_product_language=fr&ds_e_product_channel=online&ds_e_product_store_id=&ds_url_v=2&albcp=20180143335&albag=&isSmbAutoCall=false&needSmbHouyi=false&gclid=CjwKCAjwkNOpBhBEEiwAb3MvvfiKAU0IvT4mpxK7RanSuN_RsDsOJToHZo3NSkQdEptxKA_KTgkEThoCTh8QAvD_BwE&aff_fcid=0abd50a94eb04cd38a9775afba3303f4-1697992406176-01159-UneMJZVf&aff_fsk=UneMJZVf&aff_platform=aaf&sk=UneMJZVf&aff_trace_key=0abd50a94eb04cd38a9775afba3303f4-1697992406176-01159-UneMJZVf&terminal_id=1065899e4d1a410e821ded913fef0ef5&afSmartRedirect=y

Batterie   Quantité : 1   Lien batterie : 
https://fr.grandado.com/products/original-12v-6-8-ah-6800mah-18650-batteries-rechargeables-12v-avec-bms-batterie-au-lithium-carte-de-protection-chargeur-12-6v?variant=UHJvZHVjdFZhcmlhbnQ6MjM2NTc1OTE0&gclid=CjwKCAjwkNOpBhBEEiwAb3MvvbuRh8Ids2Y29pXX_rKz-rfYT0E51n6E6kvAsRBGaC-MrQd_PXtcFBoCMk0QAvD_BwE

### Annexe 2 : Planning

PLanning Thomas : 

<img width="455" alt="planing Thomas" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/572fd744-109f-4677-a836-8c07cfeb003e">

PLanning Aurélien : 

<img width="470" alt="planing Aurelien" src="https://github.com/ThomasPradinat/La-chenille/assets/147373681/54160d55-e8be-4af6-af04-c0d8bfbd10da">


Pert : 

![Edt](https://github.com/ThomasPradinat/La-chenille/assets/147373681/2cc9c3e4-c297-4cd4-9981-76ee9e80cae8)




## Bibliographie

[1] Rouet, Sébastien. « Au Chili, des capteurs dans les arbres utilisent l’IA pour mieux détecter les feux de forêt ». Geo.fr, 26 février 2020. https://www.geo.fr/environnement/au-chili-des-capteurs-dans-les-arbres-utilisent-lia-pour-anticiper-les-feux-de-foret-200078.

[2] « Quand les capteurs IoT contribuent à la survie des arbres en milieu urbain », 29 novembre 2022. https://www.ictjournal.ch/articles/2022-11-29/quand-les-capteurs-iot-contribuent-a-la-survie-des-arbres-en-milieu-urbain.

[3] « Nos outils ». Consulté le 16 octobre 2023. https://dendro-expo.wsl.ch/fr/un-arbre-se-lit-a-livre-ouvert/nos-outils/.

[4] ONF Vegetis. « Maitrisez l’état de santé de vos arbres et planifiez les travaux », 6 décembre 2022. https://www.onf-vegetis.fr/onf-vegetis/arbre-conseil/+/18::maitrisez-letat-de-sante-de-vos-arbres-et-planifiez-les-travaux-necessaires.html.

[5] Digitale, Usine. « Un robot qui s’inspire du gecko pour adhérer à toutes les surfaces », 3 janvier 2014. https://www.usine-digitale.fr/article/un-robot-qui-s-inspire-du-gecko-pour-adherer-a-toutes-les-surfaces.N229451.

[6] « For Climbing Robots, the Sky’s the Limit - NASA », 10 juillet 2019. https://www.nasa.gov/technology/robotics/for-climbing-robots-the-skys-the-limit/.

[7] « Amaran the Tree-Climbing Robot Can Safely Harvest Coconuts - IEEE Spectrum ». Consulté le 16 octobre 2023. https://spectrum.ieee.org/amaran-tree-climbing-robot-can-safely-harvest-coconuts.

[8] ben_k. « Tree Climbing Robot ». Instructables. Consulté le 16 octobre 2023. https://www.instructables.com/Tree-Climbing-Robot/.

[9] Wevolver. « Treebot ». Consulté le 16 octobre 2023. https://www.wevolver.com/specs/treebot.

[10] Pack, Robert, Joe Christopher, et Kazuhiko Kawamura. « A Rubbertuator-Based Structure-Climbing Inspection Robot », 6 novembre 1997. https://doi.org/10.1109/ROBOT.1997.619060.

[11] Zhang, Houxiang, Jianwei Zhang, et Guanghua Zong. « Effective Pneumatic Scheme and Control Strategy of a Climbing Robot for Class Wall Cleaning on High-rise Buildings ». International Journal of Advanced Robotic Systems 3 (1 juin 2006). https://doi.org/10.5772/5738.

[12] Shen, Weimin, Jason Gu, et Yanjun Shen. « Permanent Magnetic System Design for the Wall-Climbing Robot », s. d.

[13] Kotay, Keith, et Daniela Rus. « The Inchworm Robot: A MultiFunctional System ». Autonomous Robots - AROBOTS 8 (1 janvier 2000): 53‑69. https://doi.org/10.1023/A:1008940918825.

[14] Liu, Rong, Rui Chen, Hua Shen, et Rong Zhang. « Wall Climbing Robot Using Electrostatic Adhesion Force Generated by Flexible Interdigital Electrodes ». International Journal of Advanced Robotic Systems 10 (14 janvier 2013): 1. https://doi.org/10.5772/54634.

[15] Fabulateur84. « Bras robot hydraulique ». fabularium.ch (blog). Consulté le 22 octobre 2023. https://fabularium.ch/portfolio-items/bras-robot-hydraulique/.

[16] Arduino Official Store. « Tinkerkit Braccio Robot ». Consulté le 22 octobre 2023. https://store.arduino.cc/products/tinkerkit-braccio-robot.

[17] « Ned2 Overview - Niryo ». Consulté le 22 octobre 2023. https://niryo.com/products-cobots/robot-ned-2/.


[18] « (PDF) Climbot: A modular bio-inspired biped climbing robot ». Consulté le 22 octobre 2023. https://www.researchgate.net/publication/329388990_Climbot_A_modular_bio-inspired_biped_climbing_robot.

[19] « The RiSE Climbing Robot – Kod*lab ». Consulté le 16 octobre 2023. https://kodlab.seas.upenn.edu/past-work/rise/.
