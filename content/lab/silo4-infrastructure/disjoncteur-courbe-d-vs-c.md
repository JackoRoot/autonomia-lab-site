---
title: "Disjoncteur Courbe D ou C ? Le choix vital pour les gros compresseurs."
linkTitle: "Disjoncteur D vs C"
slug: "lab_silo4_disjoncteur-courbe-d-vs-c"
title_tag: "Disjoncteur Courbe D vs C : Le choix pour compresseur"
meta_description: "Analyse technique courants d'appel (In) et seuils magnétiques (NF EN 60898-1) compresseur."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 4
mot_cle: "disjoncteur courbe d vs courbe c compresseur"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Un compresseur d'atelier de 4 kW génère un courant d'appel jusqu'à 120 A pendant 150 ms au démarrage. Un disjoncteur Courbe C de 20 A, avec son seuil de déclenchement magnétique fixé à 100 A (5x In), provoquera une coupure intempestive. Le choix d'un disjoncteur Courbe D vs Courbe C est dicté par ce pic : sa plage de déclenchement magnétique de 10 à 20x In (200 A à 400 A pour un 20 A) tolère ce démarrage.

## Le courant d'appel : 8 à 12 fois le régime nominal (In)

Un moteur électrique asynchrone, tel que celui d'un compresseur, absorbe une surintensité transitoire massive au démarrage. Ce pic, ou courant d'appel (Id), est nécessaire pour créer le champ magnétique dans les enroulements et vaincre l'inertie mécanique de l'équipage mobile.

Ce courant d'appel peut atteindre 8 à 12 fois le courant nominal (In) du moteur pendant une durée de 50 à 300 millisecondes. Pour un compresseur de 4 kW en 230V monophasé avec un cosinus phi de 0,8, le calcul du courant nominal est :

`In = P / (U * cos φ) = 4000 W / (230 V * 0,8) = 17,4 A`

Le disjoncteur standard pour ce circuit est un modèle de 20 A. Le courant d'appel (Id) se situe donc entre 139 A (8x In) et 208 A (12x In). La protection doit ignorer ce pic tout en restant effective contre les courts-circuits.

## Seuils magnétiques (NF EN 60898-1) : La différence C vs D

La norme NF EN 60898-1 définit les seuils de déclenchement pour la protection magnétique (protection contre les courts-circuits). C'est ce paramètre qui différencie une courbe C d'une courbe D. La protection thermique (contre les surcharges) reste identique.

| Paramètre | Disjoncteur Courbe C | Disjoncteur Courbe D | Source |
|-----------|----------------------|----------------------|--------|
| Seuil déclenchement magnétique | Entre 5 et 10 fois In | Entre 10 et 20 fois In | NF EN 60898-1 (2026) |
| Usage type | Circuits standards (prises, éclairage) | Charges à fort courant d'appel (moteurs, transformateurs) | NF C 15-100 |
| Seuil pour un calibre 20 A | Déclenchement entre 100 A et 200 A | Déclenchement entre 200 A et 400 A | Calcul |

Le courant d'appel de 174 A du cas terrain se situe dans la zone de déclenchement instantané d'un disjoncteur Courbe C 20 A. Le démarrage sera systématiquement interprété comme un court-circuit. Le disjoncteur Courbe D, avec un seuil minimal de 200 A, laissera passer ce pic sans déclencher.

## Analyse de risque : Le coût d'un mauvais calibrage

Le choix d'une courbe C sur un circuit de compresseur engendre deux risques techniques majeurs. Le premier est le déclenchement intempestif, qui paralyse la production d'un atelier et génère des pertes de temps.

Le second risque est un contournement dangereux de la norme. Face aux coupures, un opérateur non averti pourrait installer un disjoncteur Courbe C de calibre supérieur (ex: 32 A) pour "encaisser" le démarrage. La protection thermique est alors surdimensionnée par rapport à la section du câble (souvent 2,5 mm² pour 20 A). En cas de surcharge prolongée, le câble surchauffera et risquera l'incendie avant que le disjoncteur ne déclenche.

La protection magnéto-thermique doit être dimensionnée pour protéger le câble, pas pour accommoder la charge. La variable d'ajustement pour les courants d'appel est la courbe, non le calibre.

## Le protocole de sélection en 3 points

Le dimensionnement correct de la protection d'un moteur suit une procédure stricte, validée par le Consuel.

1.  **Identifier le courant nominal (In) :** Cette valeur est gravée sur la plaque signalétique du moteur du compresseur.
2.  **Quantifier le courant d'appel (Id) :** Si la fiche technique ne le précise pas, une estimation terrain de 10 x In est une base de travail conservatrice.
3.  **Vérifier la double conformité :** Le seuil magnétique bas du disjoncteur doit être supérieur au courant d'appel (`Seuil magnétique > Id`). Simultanément, le calibre du disjoncteur doit être supérieur au courant nominal du moteur, mais inférieur au courant admissible (`Iz`) du câble d'alimentation.

Pour le cas d'étude (In=17,4A, Id≈174A, câble 2,5mm² avec Iz=20A), seul le disjoncteur 20 A Courbe D remplit ces conditions.


---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées

- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Disjoncteur courbe D ou courbe C

**Puis-je utiliser un disjoncteur courbe D pour une prise de courant standard ?**
Non. La protection magnétique serait trop haute. En cas de court-circuit sur un appareil avec un câble fin, le disjoncteur pourrait ne pas déclencher assez vite, créant un risque d'incendie ou d'électrocution. La courbe C est la norme pour les circuits de prises.

**Mon compresseur fait sauter le différentiel 30mA, pas le disjoncteur. Est-ce un problème de courbe ?**
Non. Un déclenchement de différentiel signale un défaut d'isolement, c'est-à-dire une fuite de courant vers la terre. La cause est souvent une humidité dans le moteur ou un câble d'alimentation endommagé. Ce n'est pas un problème de surintensité.

**À quoi sert un disjoncteur Courbe B ?**
La courbe B a le seuil de déclenchement magnétique le plus bas (3 à 5 fois In). Elle est utilisée pour la protection des personnes en régimes de neutre IT ou TN où l'impédance de boucle de défaut est élevée, ou pour les circuits de très grande longueur (générateurs, etc.).

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*