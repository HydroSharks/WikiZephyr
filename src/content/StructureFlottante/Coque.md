---
title: Coques
description: Description de la coque
---

# Coque

## Dimensions
- **Longueur** : 4680 mm  
- **Hauteur** : 581 mm  
- **Largeur** : 692 mm 

## Étape de construction
La construction de la coque repose sur 4 parties principales :  
1. **Squelette** : réalisé en contreplaqué marine de 5 mm.  
2. **Armature** : constituée de chevrons.  
3. **Forme de la coque** : fabriquée en polystyrène.  
4. **Nez démontable** : pièce amovible fixée à l’avant sur l’armature.

## Assemblage
- **Squelette** : assemblage façon puzzle.  
- **Armature** : fixée avec des vis.  
- **Forme de la coque** : collée pour un maintien optimal (colle à bois).  
- **Nez démontable** : se fixe directement sur l’armature avant du bateau (système de fixation développé plus bas).

### Squelette

Le squelette comporte des encoches spécifiques sur chaque couple pour s’assembler correctement :

- Couple 2 : **102.5 mm**  
- Couple 3 : **145 mm**  
- Couple 4 : **155 mm**  
- Couple 5 : **160 mm**  
- Couple 6 : **160 mm**  
- Couple 7 : **150 mm**  
- Couple 8 : **140 mm**  

Le couple 1 ne fait pas partie du puzzle, il est monté avec le nez.
Il ne se fixe pas sur les traverses (les long cotés verticaux) du squelette contrairement aux autres. 
La partie horyzontale (par rapport au sol) haute du CP a été séparé en 2 dans le plan YZ et sera vissé sur l'armature et collé sur le PS. Le CP du bas est coupé en 4 dans la longueur et la largeur. Il fait parti du puzzle et possède des encoches pour pouvoir le placer correctement.

![Squelette du Zéphyr](/images/structure/Squelette.png)

### Armature

L’armature se compose de chevrons de deux tailles distinctes :  
- **Chevron supérieur** : 50x75 mm, traité en classe 2.  
- **Chevron inférieur** : 38x63 mm ou 38x60 mm (dimensions approximatives).  

Ces chevrons traversent toute la longueur du bateau, de l’avant à l’arrière. Sur eux sont fixés :  
- **Hauteurs** : renforts verticaux.  
- **Traverses** : renforts horizontaux.  

À l’avant, un système spécifique permet de fixer le nez démontable du Zéphyr. (Cf [Page coque](#nez))

![Armature du Zéphyr](/images/structure/StructureChevronCoque.png)

Des renforts dans l'armature sont positionnés pour fixer les supports des mâts. Les supports seront vissés aux renforts grâce à des équerres d'assemblage 30 I type rainure 6. 

Il y a aussi des chevrons (...x...mm) qui sont posés afin de partitionner en 3, la boîte où la dérive est positionnée. (Cf [Page derive](/docs/StructureFlottante/Derive))

### Forme de la coque

La **forme de la coque** est créée grâce à des blocs de polystyrènes façonné par un partenaire (iXblue), qui permet de donner la forme de la coque à la future coque. Effectuer une stratification est plus simple si il y a un support sur lequel s'appuyer.

### Nez

Le **nez** du navire sera fixé à l’aide de vis M6. L’étanchéité sera assurée par l’utilisation d’inserts et de joints, tout en conservant la possibilité de démonter le nez pour faciliter la sortie du navire du local. Des perçages ont été réalisés dans le polystyrène pour y insérer des tubes en PVC, lesquels seront intégrés à la stratification. Afin de garantir l’étanchéité, ces tubes seront obturés à l’aide de bouchons en néoprène.


<img src="/images/structure/Schema_fixation_nez_bateau.JPEG" width=400 alt="Schéma de fixation du nez au bateau">
<img src="/images/structure/Nez3D.png" width=400 alt="Nez 3D du bateau">

<!-- --------------------------------------------------------------------------------------------------------------------------------------------------- -->

## Organisation interne
La coque est divisée en 5 compartiments vides, appelés *boites*, numérotées de **1** à **5**, chacune ayant une fonction spécifique :

<img src="/images/structure/Squelette.png" alt="schéma explicitant différence entre boîtes et sections" width=400/>

| **Boite** | **Section** | **Description** |
|-----------|-------------|------------------|
| 1         | 3           | Matériel informatique et communication (ordinateur de bord)|
| 2         | 4           | Voile N°1 et batteries principales |
| 3         | 5           | Puits de dérive, contrôleur de charge et gestionnaire intelligent de la batterie |
| 4         | 6           | Voile N°2 et éventuellement des batteries (à confirmer) |
| 5         | 8           | Gouvernail et éventuellement des batteries (à confirmer) (aux dernières nouvelles elles sont avec les voiles) |

### Étanchéité et connectiques
- La **boite N°1** est entièrement étanche et isolée des autres. Une boîte d’acquisition devra être conçue sur mesure pour gérer les connectiques et l’alimentation de ses composants.
- Les **boites N°2 à N°5** seront étanches uniquement à leur base. Elles sont reliées par des câbles d’alimentation électrique et d’information pour assurer le fonctionnement coordonné de tous les systèmes.  
  *(Pour plus de détails, voir [Page Électricité](/docs/ArchitectureSysteme/Electricite))*

- Entre les **boîtes N°4 et N°5**, nous aurons la **baie de capteurs**.


#### Étanchéité des boîtes

Pour assurer l’étanchéité des boîtes, nous utilisons un système de compression auto-bloquant rapide.

Deux solutions semblent prometteuses :
- Serrure quart de tour
- Bride à levier vertical

La première solution consiste à faire pivoter une pièce pour comprimer le point des capots, la seconde à actionner un levier. Étant donné que le bateau opère sur l’eau et que les pièces peuvent être mouillées, il me paraît plus simple d’actionner un levier que de pousser et tourner une pièce.

En termes de coût, les leviers sont les moins chers, surtout en inox.

Sinon, il existe de nombreuses solutions intéressantes sur ce site :  
https://www.fixtureworks.com/store/pc/quick-release-clamps-ball-lock-fasteners-c7000.htm



### Description plus précise de l'organisation des boites

#### Boite N°1

Dans cette boîte, vous trouverez tous les équipements listés [ici](/docs/ArchitectureSysteme/Equipement#liste-des-équipements-présents-dans-le-zéphyr) :

- **LattePanda Alpha**
  - Ordinateur de bord du Zéphyr
- **Jetson Nano**
  - Carte graphique du Zéphyr
- **MileSight UR35**
  - Modem WiFi et 4G avec GPS intégré
- **AIS Modem**
  - Permet de détecter l'activité des bateaux aux alentours s'ils en sont équipés. Les grands bateaux sont obligés de diffuser sur l'AIS ([Source](https://www.voileetmoteur.com/voiliers/equipement/lais-en-10-questions/112158))
- **Accéléromètre**
- **Boussole magnétique**

##### Plateforme suspendue
Une station suspendue sur amortisseurs, conçue pour servir de plateforme anti-choc, devra être développée pour maintenir les composants électroniques du bateau dans cette boîte.

```text
*Concevoir une plateforme entièrement suspendue est inutile. Les mouvements de rotation n'ont pas besoin d'être amortis, car cela augmenterait inutilement la complexité du système. Les PC peuvent fonctionner sans problème même inclinés, à condition qu'ils soient correctement ventilés.*  
*Le cahier des charges de la plateforme sera donc centré sur l'absorption des chocs provoqués par les impacts du bateau sur l'eau. Les amortisseurs devront être dimensionnés en fonction des chocs auxquels le Zéphyr pourrait être soumis.*
```

#### Boite N°2
Voici la liste des équipements présents dans la **Boite N°2** :

- **Système de maintien de la voile N°1**
- **Réducteur du mât** (Cf [Page voile](/docs/VoilesMats/Voile#système-de-commande))
- **Moteur du mât** (Cf [Page équipement](/docs/ArchitectureSysteme/Equipement#liste-des-équipements-présents-dans-le-zéphyr))
- **Batterie principale** (Cf [Page équipement](/docs/ArchitectureSysteme/Equipement#liste-des-équipements-présents-dans-le-zéphyr))
- **Passage des câbles d'alimentation** (Cf [Page électricité](/docs/ArchitectureSysteme/Electricite))
- **Passage des câbles d'information** (Cf [Page électricité](/docs/ArchitectureSysteme/Electricite))
- **Capteur de température**
- **Capteur hygrométrique**

#### Boite N°3

- **Puits de dérive** (Cf [Page coque](/docs/StructureFlottante/Coque#Dérive))
- **Système de fixation de la dérive** (Cf [Page coque](/docs/StructureFlottante/Coque#Dérive))
- **Contrôleur de charge des batteries** (Cf [Page équipement](/docs/ArchitectureSysteme/Equipement#liste-des-équipements-présents-dans-le-zéphyr))
- **Passage des câbles d'information** (Cf [Page électricité](/docs/ArchitectureSysteme/Electricite))
- **Capteur de température**
- **Capteur hygrométrique**

Dans cette boîte, les équipements sont montés sur des glissières qui permettent de les relever à l'aide d'une poignée. Ces glissières sont fixées sur les deux lambourdes situées sur les côtés de la boîte. Les câbles des équipements doivent être suffisamment longs pour éviter toute tension lorsqu'ils sont relevés. [Type de glissières envisagé](https://www.leroymerlin.fr/produits/quincaillerie/quincaillerie-du-meuble/compas-verin-coulisseau-coulisse/lot-de-2-coulisses-pour-tiroir-a-billes-hettich-45-kg-l-25-cm-70206941.html)
```text
La distance entre le puits de dérive et le bord de la boîte étant restreinte, il est essentiel de concevoir un système aussi compact que possible.
```

```text
Étudier la fixation des câbles sur le contrôleur de charge. Ils pourraient être orientés vers le puits de dérive. Envisager l'achat de coudes pour garantir des connexions plus fiables.
```


#### Boite N°4

- **Système de maintien de la voile N°2**
- **Réducteur du mât** (Cf [Page voile](/docs/VoilesMats/Voile#système-de-commande))
- **Moteur du mât** (Cf [Page équipement](/docs/ArchitectureSysteme/Equipement#liste-des-équipements-présents-dans-le-zéphyr))
- **Batterie principale** (Cf [Page équipement](/docs/ArchitectureSysteme/Equipement#liste-des-équipements-présents-dans-le-zéphyr))
- **Passage des câbles d'alimentation** (Cf [Page électricité](/docs/ArchitectureSysteme/Electricite))
- **Passage des câbles d'information** (Cf [Page électricité](/docs/ArchitectureSysteme/Electricite))
- **Capteur de température**
- **Capteur hygrométrique**


#### Boite N°5
-
-
- **Capteur de température**
- **Capteur hygrométrique**


## Fixation entre coque et flotteurs

Ces bras fixés aux flotteurs seront également fixés à la coque par des brides de fixation. (Cf [Page flotteur](/docs/StructureFlottante/Flotteur###Fixation-des-Flotteurs-à-la-Coque))

Sur les bras des flotteurs seront placés des panneaux solaires qui permettront d'alimenter les batteries du **Zéphyr**, ce qui permettra d'alimenter tout les systèmes. 
