# Guide de démarrage rapide

## 1. Câblage

Ensemble des branchements du drone.

*Bien suivre les étapes citées afin d'éviter tout risque d'endommagement de l'appareil.*

### 1.1. Branchements des composants sur le Jetson Nano

#### 1.1.1. Ethernet

Connecter les prises Ethernet du Jetson Nano et du Navio2.

#### 1.1.2. Lidar

Brancher le Lidar au Jetson Nano et le poser dans son emplacement.

#### 1.1.3. Module de Télémétrie SiK

Brancher le module de télémétrie SiK au Jetson Nano et le poser dans son emplacement.

#### 1.1.4. Autres capteurs

Brancher le reste des capteurs à disposition et les positionner correctement.

### 1.2. Branchements des composants sur le Navio2

#### 1.2.1. Connecter le récepteur au Navio2

Relier la sortie SBUS du récepteur à l'entrée PPM/SB du Navio.

*Attention à bien appairer les cables (- vers -, + vers +, signal vers signal)*

#### 1.2.2. ESCs

- Brancher l'ESC du moteur gauche sur la broche 1 du rail.

- Brancher l'ESC du moteur droit sur la broche 3 du rail.

*Pour alimenter le rail depuis les ESCs, brancher le cable d'alimentation*

#### 1.2.3. GPS

Clipser le GPS à la prise antenne du Navio et le mettre dans son emplacement.

#### 1.2.4. Module d'alimentation

Connecter le module d'alimentation sur la prise `POWER` du Navio.

### 1.3. Alimentation

Vérifier le branchement de tous les composants, avant de poursuivre.

#### 1.3.1. Jetson Nano

Brancher l'un des cables du BEC sur les broches 5V et GND du Jetson Nano (cable rouge sur 5V, cable noir sur GND).

#### 1.3.2. Navio2

Connecter le deuxième cable du BEC à la dernière broche (14) du rail du Navio2 (cable rouge sur +, cable noir sur -).

#### 1.3.3. Cable Y

- Connecter l'entrée XT90 du cable Y à celle du module d'alimentation

- Connecter les deux sorties XT60 aux ESCs, **bien vérifier que ces derniers sont éteints**.

- En dernier lieu, connecter les deux sorties XT60 du cable Y aux batteries.

## 2. Démarrage de la radio

....

### 2.1. Mise à zéro

Replacer tous les switchs vers le haut et bien centrer les joysticks.

### 2.2. Démarrage

Maintenir le bouton d'allumage, suivre les instructions affichées à l'écran.

### 2.3. Commandes 

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

8. **CH8: Arm** - Ce canal est commandé par le switch H qui possède deux positions. La position **bas** provoque l'arrêt des moteurs du drone.

#### 2.3.2. Modes de vols

La radiocommande dispose d'un switch à six positions représentées par six boutons lumineux. La position 1 (position par défaut) active le mode de vol 1 qui limite la course des canaux 1 et 2 à 30%. La position 6 active le mode de vol 2 qui retire la limitation posée par le mode de vol 1. Les autres positions active le mode de vol 0 qui désactive les canaux 1 et 2 de la radio.

## 3. Démarrage du drone

Le drone est maintenant prêt à opérer en mode manuel.
