# RobotSearchAndDestroy (Projet AsCyloom)

----------
![Image Sujet](https://raw.githubusercontent.com/cepes/robotSearchAndDestroy/b4e18d105783127b522bd345816336ddef0f7b48/t%C3%A9l%C3%A9chargement.png)

L'objectif de ce projet est de répondre à un appel d'offre fictif au sujet de robots de nettoyage urbain.
Le projet se présente sous la forme d'un proof of concept.



## Sujet du projet ##
Il s'agit d'un robot qui sera capable de ramasser des cylindres métalliques (canettes).
Les critères initiaux du projet sont les suivants:

- Les déchets à ramasser seront des cylindres métalliques.
- Le robot sera testé dans une zone de 20m² (4x5m)
- Le robot sera utilisé de jour
- Le robot ne sera pas piloté, il sera autonome
- La zone pourra comporter des obstacles qui peuvent être esquivés
- La zone de dépôt sera un carré rouge de 40cmx40cm

Schéma représentant le robot et son envirronnement:
![Image Sujet](https://raw.githubusercontent.com/cepes/robotSearchAndDestroy/master/schema_analyse.png)

Le résumé complet du projet est disponible au lien suivant : 
[https://github.com/cepes/robotSearchAndDestroy/blob/master/sujet.pdf](https://github.com/cepes/robotSearchAndDestroy/blob/master/sujet.pdf "Lien Sujet")

## Projet SearchAndDestroy ##

### Analyse fonctionnelle ###

Dans le Schéma suivant:
- FP correspond à fonction principale.
- FS correspond à fonction secondaire.
- FC correspond à fonction contrainte.
![Image_Analyse_Fonctionnelle](https://raw.githubusercontent.com/cepes/robotSearchAndDestroy/master/analyse%20fonctionnelle.PNG)

| Fonction  | Rôle | Critères | Flexibilité |
| ------------- | ------------- | ------------- | ------------- |
| FP1 (fonction principale 1) | Doit permettre de ramasser des objets cylindrique | Nombre d'essai et erreur par prise | ------------- |
| FP2 (fonction principale 2) | Doit pouvoir se déplacer | Avancer / Reculer / Gauche / Droite | Angle de Rotation |
| FP3 (fonction principale 3) | Doit pouvoir identifier des objets | Taux de reconnaissance des canettes / Accident contre un obstacle | ------------- |
| ------------- | ------------- | ------------- | ------------- |
| FS1 (fonction secondaire 1) | Doit pouvoir se déplacer en faisant de la lumière ou un son | lumière dégagé et son entendu en db | ------------- |
| FS2 (fonction secondaire 2) | Doit pouvoir être paramétrable par l’opérateur | ------------- | ------------- |
| FS3 (fonction secondaire 3) | Doit pouvoir se situer pour retourner au dépôt en évitant les obstacles | ------------- | ------------- |
| FS4 (fonction secondaire 4) | Doit pouvoir se situer pour rester dans la zone en évitant les obstacles | ------------- | ------------- |
| FS5 (fonction secondaire 5) | Doit savoir quand il est chargé | témoin de charge / Décharge | ------------- |
| ------------- | ------------- | ------------- | ------------- |
| FC1 (contrainte 1) | Doit évoluer dans une zone de 20cm² (4 x 5m) | test sur la durée dans une surface supérieur | ------------- |
| FC2 (contrainte 2) | Doit être utilisé de jour | Taux de luminosité de la zone de test | ------------- |
| FC3 (contrainte 3) | Doit être autonome | nombre de raccordement physique en cas d'intervention | ------------- |
| FC4 (contrainte 4) | Doit esquiver des obstacles | parcour de test | ------------- |
| FC5 (contrainte 5) | Doit avoir une zone de dépôt (40 x 40 cm) | ------------- | ------------- |
| FC6 (contrainte 6) | Ne doit pas mettre en danger l’utilisateur | action non prévu interrompt le schéma initial | ------------- |
| FC7 (contrainte 7) | Resistance aux chocs | crashtest/écrassement | ------------- |
| FC8 (contrainte 8) | Conforme aux normes CE | habilitation | ------------- |
| FC9 (contrainte 9) | Resistance a l'eau | test avec de l'eau | Resistance aux eclaboussure |
| FC10 (contrainte 10) | ------------- | ------------- | ------------- |
| FC11 (contrainte 11) | ------------- | ------------- | ------------- |
| FC12 (contrainte 12) | ------------- | ------------- | ------------- |
| FC13 (contrainte 13) | ------------- | ------------- | ------------- |
| FC14 (contrainte 14) | ------------- | ------------- | ------------- |
| FC15 (contrainte 15) | ------------- | ------------- | ------------- |

Au vue des contraintes, il a fallu analyser les différents éléments nécessaire à notre robot. Notre robot nécessite donc un système de

### Schéma Electronique ###

Le schéma éléctrique est le suivant. La R3 électro-aimant de 12,5 Ohm correspond à la resistance interne de l'electroaimant en fonctionnement.
![Circuit_Schéma_dévellopé](https://github.com/cepes/robotSearchAndDestroy/blob/master/Circuit%20schema.PNG)

### FAQ ###

#### Liste des composants ####

Ci-dessous voici les différents éléments composants votre robot.
Certaines partie plastique du proof of concept étant spécifique à notre entreprise veuillez vous rapprochez de nous pour obtenir une pièce de remplacement.

| Matériel  | Nombre | Lien  | Prix en Euros à l'unité |
| ------------- | ------------- | ------------- |------------- |
| Raspberry pi 3 | 1 | http://fr.farnell.com/raspberry-pi/rpi3-modb-16gb-noobs/sbc-raspberry-pi3-mod-b-carte/dp/2525227 | 43,59 |
| Pi camera board  | 1 | http://fr.farnell.com/raspberry-pi/rpi-noir-camera-board/raspberry-pi-noir-camera-board/dp/2510729 | 22,04 |
| Carte micro SD  | 1 | http://fr.farnell.com/transcend/tsraspi10-16g/16gb-microsd-card-preloaded-with/dp/2521753  | 11,70 |
| Chassis  | 1 | http://www.gotronic.fr/art-chassis-eco-dg008-17741.htm | 24,50 |
| Electro aimant | 1 | https://www.gotronic.fr/art-electroaimant-grove-101020073-21548.htm  | 10,20 |
| Servo moteur  | 2 | http://www.gotronic.fr/art-servomoteur-sg90-19377.htm | 4,95 |
| Batterie  | 1 | https://www.amazon.fr/gp/product/B01422TC14/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1 | 32,99 |
| Interrupteur TI3 | 1 | http://www.gotronic.fr/art-interrupteur-ti3-4167.htm | 0,60 |
| Pochette 250 condensateur ceramique | 1 | http://www.gotronic.fr/art-pochette-de-250-condensateurs-ceramiques-19398.htm | 4,95 |
| Assortiment diodes Zener | 1 | http://www.gotronic.fr/art-assortiment-de-diodes-zeners-0-5-w-dz050-2044.htm | 7.90 |
| Assortiment resistance | 1 | http://www.gotronic.fr/art-assortiment-de-610-resistances-1-4-w-2623.htm |  11,50 |
| Pack de cables de connexions | 1 | http://www.gotronic.fr/art-pack-de-cables-de-connexion-12411.htm | 9,90 |
| Arduino Uno | 1 | https://www.amazon.fr/dp/B01N91PVIS/ref=sr_1_3?ie=UTF8&qid=1495631066&sr=8-3&keywords=arduino+uno | 9,90 |
| Cable Alimentation Micro USB | 1 | https://www.amazon.fr/Anker-anti-emm%C3%AAlement-connecteurs-smartphones-Android/dp/B00SUX2IPE/ref=sr_1_9?ie=UTF8&qid=1495631198&sr=8-9&keywords=cable+micro+usb | 5,99 |
| Cable Alimentation Circuit | 1 | Fournisseur | 5,99 |


#### Default d'un composant ? ####

En cas de défault d'un composant, il suffit d'identifier le composant défectueux à l'aide d'un multimètre et d'opérér un remplacement de celui-ci. Une liste des composants présent dans le robot est disponible dans ce FAQ à la partie liste des composants.

Ci-joint un schéma électrique modélisé, un schéma électrique dévellopé est disponible dans le chapitre Projet SearchAndDestroy partie Schéma électronique:
![Circuit_Schéma](https://github.com/cepes/robotSearchAndDestroy/blob/master/Circuit%20modele.PNG)

## Annexes ##

### Matériel fournit ###

Le matériel de base fournit dans le cas de ce projet est le suivant :
Nota: Tout le matériel n’est pas obligatoire, et en cas de difficultés vous pouvez toujours le remplacer par
d’autres matériels que vous pourriez vous procurer.


| Matériel  | Nombre | Lien  |
| ------------- | ------------- | ------------- |
| Raspberry pi 3 | 1 | http://fr.farnell.com/raspberry-pi/rpi3-modb-16gb-noobs/sbc-raspberry-pi3-mod-b-carte/dp/2525227 |
| Pi camera board  | 1 | http://fr.farnell.com/raspberry-pi/rpi-noir-camera-board/raspberry-pi-noir-camera-board/dp/2510729 |
| Carte micro SD  | 1 | http://fr.farnell.com/transcend/tsraspi10-16g/16gb-microsd-card-preloaded-with/dp/2521753  |
| Chassis  | 1 | http://www.gotronic.fr/art-chassis-eco-dg008-17741.htm |
| Electro aimant | 1 | http://www.gotronic.fr/art-cable-de-telechargement-usb-axe027-11921.htm  |
| Circuit picaxe 28x2 AXE401K | 1 | http://www.gotronic.fr/art-circuit-d-essais-pour-picaxe-18m2-chi030-11934.htm#complte_desc |
| Cable Picaxe  | 1 | http://www.gotronic.fr/art-cable-de-telechargement-usb-axe027-11921.htm |
| Servo moteur  | 3 | http://www.gotronic.fr/art-servomoteur-sg90-19377.htm |
| Batterie  | 1 | https://www.amazon.fr/Batterie-15600mAh-Coolreall-Chargeur-Smartphone/dp/B01KFJEEES/ref=sr_1_1?ie=UTF8&qid=1489416295&sr=8-1&keywords=coolreall+15600mah  |
| ULN2803A | 3 | http://www.gotronic.fr/art-uln2803a-10727.htm |
| L7805CV  | 2 | http://www.gotronic.fr/art-l7805cv-1578.htm |
| Interrupteur TI3 | 1 | http://www.gotronic.fr/art-interrupteur-ti3-4167.htm |
| Accu modelisme | 1 | http://www.gotronic.fr/art-accu-modelisme-nimh-9-6v-2ah-5772.htm |
| Kit d'isolement pour TO220  | 2 | http://www.gotronic.fr/art-kit-d-isolement-pour-to220-6029.htm|
| Refroidisseur ML7 | 2 | http://www.gotronic.fr/art-refroidisseur-ml7-6000.htm |
| Pochette 250 condensateur ceramique | 1 | http://www.gotronic.fr/art-pochette-de-250-condensateurs-ceramiques-19398.htm |
| Assortiment resistance | 1 | http://www.gotronic.fr/art-assortiment-de-610-resistances-1-4-w-2623.htm |
| Assortiment diodes Zener | 1 | http://www.gotronic.fr/art-assortiment-de-diodes-zeners-0-5-w-dz050-2044.htm |
| Pack de cables de connexions | 1 | http://www.gotronic.fr/art-pack-de-cables-de-connexion-12411.htm |
| Chargeur | 1 | http://www.gotronic.fr/art-chargeur-minilader-3-vl6424-5720.htm |
| L293D | 1 | http://www.gotronic.fr/art-l293d-14072.htm |
