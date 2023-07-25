# Guide de démarrage rapide

## 1. Câblage

![etape1](/profile/images/etape1.jpg)

Ensemble des branchements du drone.

*Bien suivre les étapes citées afin d'éviter tout risque d'endommagement de l'appareil.*

### 1.1. Branchements des composants sur le Jetson Nano

![etape1_1](/profile/images/etape1_1.jpg)

#### 1.1.1. Ethernet

![etape1_1_1](/profile/images/etape1_1_1.jpg)

Connecter les prises Ethernet du Jetson Nano et du Navio2.

#### 1.1.2. Lidar

![etape1_1_2](/profile/images/etape1_1_2.jpg)

Brancher le Lidar au Jetson Nano et le poser dans son emplacement.

#### 1.1.3. Module de Télémétrie SiK

![etape1_1_3](/profile/images/etape1_1_3.jpg)

Brancher le module de télémétrie SiK au Jetson Nano et le poser dans son emplacement.

#### 1.1.4. Autres capteurs

Brancher le reste des capteurs à disposition et les positionner correctement.

### 1.2. Branchements des composants sur le Navio2

#### 1.2.1. Connecter le récepteur au Navio2

![etape1_2_1](/profile/images/etape1_2_1.jpg)

Relier la sortie SBUS du récepteur à l'entrée PPM/SB du Navio.

*Attention à bien appairer les cables (- vers -, + vers +, signal vers signal)*

#### 1.2.2. ESCs

|  |  |
:--|--:
![etape1_2_2a](/profile/images/etape1_2_2a.jpg) | ![etape1_2_2b](/profile/images/etape1_2_2b.jpg)

- Brancher l'ESC du moteur gauche sur la broche 1 du rail.

- Brancher l'ESC du moteur droit sur la broche 3 du rail.

*Pour alimenter le rail depuis les ESCs, il faudra brancher le cable d'alimentation*

#### 1.2.3. GPS

![etape1_2_3](/profile/images/etape1_2_3.jpg)

Clipser le GPS à la prise antenne du Navio et le mettre dans son emplacement.

### 1.3. Alimentation

Vérifier le branchement de tous les composants, avant de poursuivre.

*Avant d'alimenter le drone, bien observer la charge des batteries. Une tension inférieure à 11V necessite une recharge.*

#### 1.3.1. Jetson Nano

![etape1_3_1](/profile/images/etape1_3_1.jpg)

Brancher l'un des cables du BEC sur les broches 5V et GND du Jetson Nano (cable rouge sur 5V, cable noir sur GND).

#### 1.3.2. Navio2

![etape1_3_2](/profile/images/etape1_3_2.jpg)

Connecter le deuxième cable du BEC à la dernière broche (14) du rail du Navio2 (cable rouge sur +, cable noir sur -).

#### 1.3.3. Cable Y

|  |  |  |
:--|--|--:
![etape1_3_3a](/profile/images/etape1_3_3a.jpg) | ![etape1_3_3b](/profile/images/etape1_3_3b.jpg) | ![etape1_3_3c](/profile/images/etape1_3_3c.jpg)

- Connecter l'entrée XT90 du cable Y à celle du module d'alimentation

- Connecter les deux sorties XT60 aux ESCs, **bien vérifier que ces derniers sont éteints**.

- En dernier lieu, connecter les deux sorties XT60 du cable Y aux batteries.

## 2. Démarrage de la radio

....

### 2.1. Mise à zéro

![etape2_1](/profile/images/etape2_1.jpg)

Replacer tous les switchs vers le haut et bien centrer les joysticks.

### 2.2. Démarrage

![etape2_2](/profile/images/etape2_2.jpg)

Maintenir le bouton d'allumage, suivre les instructions affichées à l'écran.

### 2.3. Commandes

![etape2_3](/profile/images/etape2_3.png)

Initialement, la radio est programmée de la façon suivante:

#### 2.3.1. Canaux de transmission

Huit canaux de transmission ont été programmé. Ils peuvent être étendus par l'ajout ou le remplacement du récepteur.

1. **CH1: T**hrottle - Ce canal est commandé par la course verticale du joystick gauche de la radio. Il contrôle les gaz du drone et permet un déplacement en marche avant et arrière.

2. **CH2: R**uddle - Ce canal est commandé par la course horizontale du joystick gauche de la radio. Il contrôle la rotation du drône et prend le dessus sur le canal 1.

3. **CH3: E**levator - Ce canal est commandé par la course verticale du joystick droit de la radio. Il n'est relié à aucun élément du drone, mais pourrait servir à contrôler un support de caméra, ...

4. **CH4: A**ileron - Ce canal est commandé par la course horizontale du joystick droit de la radio. Il n'est relié à aucun élément du drone.

5. **CH5: Modes** - Ce canal est commandé par le switch A qui possède trois positions. La position **haut** est associée au mode ..., la position **centrale** correspond au mode ... et la position **bas** active le mode ... Ces paramètres sont configurables depuis QGroundControl.

6. **CH6: Return** - Ce canal est commandé par le switch D qui possède trois positions. La position **bas** est active le retour au point de départ.

7. **CH7: Arm** - Ce canal est commandé par le switch F qui possède deux positions. La position **bas** active l'armement des moteurs, et permet l'opération du drone en mode manuel.e retour au point de départ.

8. **CH8: Hold** - Ce canal est commandé par le switch H qui possède deux positions. La position **bas** provoque l'arrêt des moteurs du drone.

#### 2.3.2. Modes de vols

La radiocommande dispose d'un canal de transmission à six positions représentées par six boutons lumineux. La position 1 (position par défaut) active le mode de vol 1 qui limite la course des canaux 1 et 2 à 30%. La position 6 active le mode de vol 2 qui retire la limitation posée par le mode de vol 1. Les autres positions activent le mode de vol 0 qui désactive les canaux 1 et 2 de la radio.

## 3. Démarrage du drone

Dès sa mise en marche, le drone est prêt à être contrôlé en mode manuel, à l'aide de la télécommande. La configuration de ses paramètres et le monitoring des informations de vol s'effectuent à distance, avec une logiciel de contrôle distant, tel que QGroundControl.

## 4. Mise en place de QGroundControl

Les informations données au cours de cette partie sont spécifiques à QGroundControl mais trouvent leur équivalence dans les autres logiciels de contrôle à distance tels que MissionPlanner ou APM Planner. Ces informations sont complémentaires à la [documentation d'ArduPilot](https://ardupilot.org/rover/index.html) et se focalisent sur les principaux paramètres permettant de configuration du drone.

*NB: Certains logiciels ne sont disponibles que sur Windows, ou Linux.*

### 4.1. Installation de QGroundControl

L'installation du logiciel peut s'effectuer en suivant la [documentation officielle](https://docs.qgroundcontrol.com/master/en/getting_started/download_and_install.html).

Une installation dans un [conteneur logiciel en utilisant Docker](https://fr.wikipedia.org/wiki/Docker_(logiciel)) est également possible. Pour plus d'informations suivre le [tutoriel](https://github.com/Projet-CSU-Vecteur-nautique/QGroundControl) suivant
