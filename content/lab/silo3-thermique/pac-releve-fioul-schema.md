---
title: "PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange)."
linkTitle: "PAC relève fioul schéma"
slug: "lab_silo3_pac-releve-fioul-schema"
title_tag: "Schéma PAC en relève de fioul : Bouteille de mélange"
meta_description: "Schéma hydraulique PAC + chaudière fioul. Calcul volume bouteille de mélange et impact sur le COP."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 3
mot_cle: "schema hydraulique pac air eau releve chaudiere fioul"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Un volume de bouteille de mélange insuffisant pour une PAC de 12 kW en relève de fioul génère des cycles courts qui réduisent prématurément la durée de vie du compresseur. Le schéma hydraulique correct découple les circuits pour protéger l'investissement et garantir le COP annoncé. Sans ce tampon, l'inadéquation des débits entre la PAC et le réseau de radiateurs existant est inévitable.

## Découplage hydraulique : 517 L/h vs 2068 L/h

Une pompe à chaleur air-eau moderne fonctionne à son régime nominal avec un delta de température (différence entre départ et retour d'eau) faible, typiquement 5°C. Pour une PAC de 12 kW, cela impose un débit d'eau minimal de 2068 L/h (ABC Clim/XPair/DTU 65.16/Cedeo, 2024) dans son circuit primaire.

Un réseau de radiateurs en fonte existant, conçu pour une chaudière fioul, opère sur un delta T de 15 à 20°C. Pour transférer la même puissance, le besoin de débit pour le circuit secondaire est de seulement 517 L/h (Cedeo/XPair/IZI by EDF/ABC Clim, 2021).

Le raccordement direct de la PAC au circuit des radiateurs provoquerait un retour d'eau trop rapide et trop chaud. La régulation Inverter interpréterait un besoin de chauffage faible, coupant le compresseur. Deux minutes plus tard, la température chutant, il redémarrerait. Ces cycles courts (short-cycling) détruisent la mécanique du compresseur et effondrent le COP.

La bouteille de mélange, ou ballon tampon, agit comme une zone de découplage hydraulique. Elle permet à chaque circuit de fonctionner avec son propre débit, sans interférer avec l'autre.

## Le schéma 4 piquages : L'architecture de la bouteille de mélange

L'intégration correcte d'une bouteille de mélange dans un **schema hydraulique de PAC air-eau en relève de chaudière fioul** suit une topologie à 4 piquages. Chaque circuit possède son propre circulateur.

**Circuit primaire (côté PAC) :**
*   Le départ d'eau chaude de la PAC est raccordé au piquage supérieur de la bouteille.
*   Le retour d'eau refroidie vers la PAC est aspiré depuis le piquage inférieur.

**Circuit secondaire (côté émetteurs) :**
*   Le départ vers les radiateurs (ou le plancher chauffant) est raccordé au piquage supérieur.
*   Le retour des radiateurs est raccordé au piquage inférieur.

Cette configuration assure que l'eau la plus chaude est toujours disponible en haut du ballon, tandis que l'eau la plus froide retourne aux générateurs, optimisant la stratification et le rendement.

```
      Départ PAC --> |¯¯¯¯¯¯¯¯¯¯| --> Départ Radiateurs
                     |          |
      (Circulateur)  | Bouteille|  (Circulateur)
                     | de       |
                     | Mélange  |
                     |          |
      Retour PAC <-- |__________| <-- Retour Radiateurs
```

La chaudière fioul est montée en parallèle sur le circuit secondaire, prête à prendre le relais lorsque la PAC atteint sa limite de fonctionnement par grand froid.

## Dimensionnement : 10 à 20 litres par kW de puissance PAC

Le volume de la bouteille de mélange est un paramètre critique.

*   **Sous-dimensionnement (< 10 L/kW) :** Le volume tampon est insuffisant pour absorber l'inertie. Les cycles courts persistent, annulant le bénéfice de l'installation.
*   **Sur-dimensionnement (> 20 L/kW) :** Le volume d'eau à maintenir en température devient excessif. Cela génère des déperditions thermiques statiques via les parois du ballon, ce qui dégrade le COP global sur une saison. Un ballon de 500L pour une PAC de 12kW est une aberration technique.

Pour une installation résidentielle standard, un volume de 10 litres par kilowatt minimum (DTU 65.16, 2017) de puissance de la PAC est un dimensionnement correct. Une PAC de 12 kW requiert donc une bouteille de mélange de 120 litres minimum (DTU 65.16, 2017).

## R290 vs R32 : L'impact du fluide sur la température de départ à -7°C

Le choix de la technologie de PAC a un impact direct sur la viabilité du projet en relève de fioul, surtout sur un réseau de radiateurs haute température. Les machines utilisant le fluide R290 (propane) présentent une température critique plus élevée que celles au R32.

Cette propriété physique leur permet de produire de l'eau à plus haute température sans dégrader le cycle thermodynamique, même par grand froid.

| Paramètre technique | PAC R32 (Standard) | PAC R290 (Haute Temp.) | Source (Date) |
|---------------------|--------------------|------------------------|---------------|
| T° max départ eau | 60.0 °C | 75.0 °C | (Mitsubishi Electric, 2023) |
| Performance à -15°C | Perte de puissance significative, appoint électrique ou relève chaudière requis | Maintien du régime nominal sans appoint électrique | (Mitsubishi Electric, 2023) |
| Pertinence en relève | Adaptée aux radiateurs basse T° ou planchers chauffants | Permet de remplacer une chaudière fioul sur des radiateurs fonte sans modification des émetteurs | Analyse technique |

Une PAC au R290 peut ainsi assurer le chauffage sur 100% de la saison avec des radiateurs existants, là où un modèle R32 nécessitera une activation plus fréquente de la chaudière fioul en appoint. Le retour sur investissement est directement affecté. [PAC grand froid : La vérité sur le givrage et le COP à -10°C.](/lab_silo3_rendement-pac-grand-froid/)

## Point de bivalence : Le seuil de bascule à -5°C (Zone H1)

Le point de bivalence est la température extérieure à laquelle la puissance de la PAC ne suffit plus à couvrir les déperditions du bâtiment. En dessous de ce seuil, la chaudière fioul doit démarrer.

Ce point est défini par le bureau d'études thermiques. Pour une maison moyennement isolée en zone climatique H1 (Nord-Est de la France), il se situe souvent autour de -5°C à -7°C (RE2020/RT2012, Ministère de l'Écologie, 2024).

La régulation de l'installation doit être calibrée précisément sur ce seuil. Une sonde de température extérieure est indispensable. Elle donne l'ordre à la vanne trois voies d'isoler la PAC et de faire passer le flux dans la chaudière fioul lorsque le seuil est franchi. Un mauvais réglage peut entraîner un fonctionnement simultané et chaotique des deux générateurs.

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [Thermostat PID et Plancher chauffant : Dompter l'inertie de la dalle.](/lab_silo3_regulation-pid-plancher/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : PAC en relève de fioul

**Faut-il obligatoirement garder la chaudière fioul ?**
Non, si la PAC est un modèle haute température (type R290) correctement dimensionné pour couvrir 100% des besoins, même à la température de base du lieu. Conserver la chaudière fioul offre une redondance de sécurité et peut éviter un surdimensionnement coûteux de la PAC pour les quelques jours les plus froids.

**Quelle est la taille correcte pour une bouteille de mélange ?**
Le minimum normatif est de 10 litres par kilowatt (kW) de puissance nominale de la pompe à chaleur (DTU 65.16, 2017). Pour une PAC de 10 kW, un ballon de 100 litres minimum est requis pour assurer le découplage hydraulique.

**Ma PAC peut-elle chauffer mes vieux radiateurs en fonte ?**
Oui, si c'est une PAC dite "haute température", capable de produire une eau entre 65°C et 75°C par temps froid. Les PAC standards (R32) plafonnent à 55-60°C, ce qui peut être insuffisant pour des radiateurs en fonte dans une maison non rénovée. Une étude thermique est obligatoire pour le valider.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*