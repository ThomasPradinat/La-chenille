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



### Introduction 

Nous sommes arrivés en début d’année avec le défi de réaliser un robot capable de grimper aux arbres. Puis nous nous sommes aperçus que les robots grimpeurs possédaient différents cas d’application. Dans l’écologie par exemple, où l’installation de capteurs sur les robots grimpeurs pourrait se révéler intéressante pour prévoir les feux de forêts qui se font de plus en plus récurrents et violents d’une année à l’autre [1]. Plus simplement, le robot serait utile pour observer la faune, effectuer des relevés d’analyse sur le temps long ou surveiller la santé de l’arbre en question avec des capteurs [2][3][4]. De même, on retrouve certaines applications de robots grimpeurs dans l’exploration spatiale, où la NASA envisage de mouvoir un rover sur un plan vertical afin de permettre l’analyse de plusieurs cratères martiens avec un seul robot d’exploration (l’escalade pourrait permettre de passer d’un cratère à un autre) [5][6].

Notre robot aura pour mission de s'agripper aux arbres sans les abîmer et de s’y mouvoir tout en étant économe en énergie. 



### Chapitre I : Présentation générale du robot 

La plupart des robots montant aux arbres se distinguent en deux catégories : ceux qui enlacent le tronc et ceux qui n’en agrippent qu’une partie.

L’inconvénient des robots enlaçant l’arbre est qu’ils ne peuvent monter que certains arbres bien droits, tels que les cocotiers (c’est par exemple le cas du robot Amaran [7]). Nous souhaitons un robot plus polyvalent donc nous préférons utiliser un robot qui agrippe le tronc.

Une grande partie des robots qui agrippent les arbres ont un mouvement linéaire, sur la base d’un mouvement périodique de tirer-pousser, tel une chenille (par exemple en utilisant une tige filetée [8]). Mais là encore, le robot ne serait pas vraiment polyvalent.

Une de nos plus grandes inspirations est le Treebot [9]. C’est un robot capable de monter sur un arbre, en étant capable de faire des mouvements en trois dimensions, pour éviter des branches lors de l'ascension, ou bien d’avancer dessus. Il utilise trois câbles semi-rigides pour pousser en avant la partie avant de son robot ; le fait de jouer sur la différence de poussée des trois câbles permet de déplacer l’avant du robot dans les trois dimensions de l’espace. Il fait aussi un mouvement périodique de tirer-pousser mais peut aussi contourner des obstacles sur le tronc : 


