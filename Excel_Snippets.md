# Excel

## conseils et raccourcis
$A$1 pour verrouiller les adresses de cellules : que veut dire verrouiller?

Excel Barre d'outil accès rapide : filtrer/ repérer les ascendants/précédants
Nommer les plages de cellules

F4 pour répéter la commande comme fusionner les cellules
F9 pour le recalcul des formules
Le recalcul se fait uniquement par un calcul forcé (Ctrl+Maj+F9) et non par calcul automatique (option ou F9)
Utiliser le insérer une fonction à gauche du = pour éviter de galérer

filtre effacer pour enlever tous les filtres

formule>
 l trace precedant dependencies/arrows pour les débugger  formules excel
 ->mettre dans la barre d'outils accès rapide (mettre des 
raccourcis?)
renvoyer à la ligne automatiquement au dessus de fusionner
Tour de couleur autour des tableaux pour effacer le quadrillage et faire plus propre

## formules 

### Dates
02:50:12 =MINUTE(A1)

### TODO Jauge dans une case Excel 
------------------------
`=A1&" "&C1` pour rassembler en colonne D

`=substitue(a1;" ";"")` pour enlever les espaces d'une case 

`=SI(J103<>""; CONCATENER("S";NO.SEMAINE(J103));"")` mettre S + nb semaine si il y a une date dans la colonne

`=SIERREUR(RECHERCHEV(D396;Feuil1!A:B;2;FAUX);"")`
le SIERREUR protège par rapport au #N/A si la valeur n'est pas trouvée dans le tableau cible

`=RECHERCHEV(A2;'Activite FT'!D:D;1;FAUX)`
il est possible de faire un rechercheV sur une colonne 
un peu l'équivalent de =SI(B2<>"";SI(NB.SI(INDIRECT($F$2);B2)=0;"B non présent dans A!"; "présent dans A");"Rien dans B")

### NB.SI
NB.SI, l’une des fonctions Statistiques,  permet de compter le nombre de cellules qui répondent à un critère ; 
par exemple, pour compter le nombre de fois où le nom d’une ville 
apparaît dans une liste de clients.
`=NB.SI(A:A;"REC_IHM_*")`
`=NB.SI(E2:E18;3)`
`=SOMME.SI`

### NB.SI.ENS 
La fonction NB.SI.ENS applique les critères aux cellules de plusieurs 
plages et compte le nombre de fois où tous les critères sont remplis.
`=SOMME.SI.ENS(O:O;C:C;C45;D:D; "<>" & D25)`

`= SI(ESTNUM` pour protéger les cases
`= NBVAL(A2:A307)` pour ne pas compter les cellules vides

`=DATEDIF(I18;J17;"D")`

How to Compare Two Columns in Excel (for matches & differences)
`=IF(COUNTIF($B:$B, $A2)=0, "No match in B", "")`
`=NB.SI(B:B;A1)`
`COUNTIF` = `NB.SI` en français 

A regarder
`=SI(ESTNA(EQUIV(O99;$'Tableau grades'.A$1:A$24;0));"";INDIRECT("'Tableau
 grades'!B"&EQUIV(O99;$'Tableau grades'.A$1:A$24;0)))`
---------------------------------
Coloration syntaxique OK 
`=$K2="Terminé"` avec tout le tableau en sélection 

case auteur Rouge car pas remplie si case date remplie
`=ET($B1="";$D1<>"")`

on sélectionne tout le tableau pour avoir la ligne qui se colore

recherche de doublons
Sinon mise en forme conditionnelle doublon encore plus rapide
regarder les menus avant de faire une formule personnalisée 

Pas de SXX et filtre fin d'action =Thales à 1 il faut utiliser les numéros 1 sinon la coloration syntaxique aura un décalage
`=ET($Q1="";$P1=1)`

Mise en forme conditionnelle : 
`=SI(SOMME.SI($A:$A;$A2;$I:$I)=5;0;1)`
pour mettre en bleu 
`=MOD(NO.SEMAINE($J2);2)<>0`
mettre les lignes de la semaine en vert 
`=MOD(NO.SEMAINE($J2);2)=0`
Mise en couleur des lignes dont le total ne fait pas 5 Jours 
