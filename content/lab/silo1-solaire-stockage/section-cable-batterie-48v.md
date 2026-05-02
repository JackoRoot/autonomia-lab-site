---
title: "Section de câble batterie 48V : Ne jouez pas avec l'incendie (Abaques)."
linkTitle: "Section câble 48V"
slug: "lab_silo1_section-cable-batterie-48v"
title_tag: "Section câble batterie 48V 5000W : Abaque & Sécurité"
meta_description: "Calculez la section de câble pour batterie 48V. Abaque pour limiter la chute de tension à 1% (NF)."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "section cable onduleur batterie 48v 5000w"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Un onduleur 5000W sur un parc batterie 48V tire plus de 104 A en régime nominal et jusqu'à 200 A en appel de charge. Une section de câble insuffisante, comme du 35 mm², engendre une chute de tension supérieure au seuil critique de 2% et un échauffement menant à un risque d'incendie. Le dimensionnement minimal sécuritaire impose une section de 50 mm² pour une longueur de 1.5 mètre (Calcul Ingénierie, Avril 2026).

## Le calcul du courant nominal et du courant de crête > 100 A

Le dimensionnement de la liaison DC entre un parc batterie et un onduleur hybride est une opération critique. La puissance de l'onduleur (P, en Watts) et la tension du parc batterie (U, en Volts) déterminent le courant (I, en Ampères) qui transitera par les câbles, selon la formule `I = P / U`.

Pour un onduleur de 5000 W en 48 V, le courant nominal est de :
`5000 W / 48 V = 104.16 A (Calcul Ingénierie, Avril 2026).`

Cependant, le courant d'appel au démarrage de charges inductives (moteur, pompe, compresseur) doit être anticipé. Un onduleur de cette catégorie supporte une puissance de crête variant de 2,00 à 2,39 fois sa puissance nominale pendant plusieurs secondes selon l'architecture (Deye/SMA/Victron, 2021-2022). Le courant maximal peut donc atteindre :
`10000 W / 48 V = 208.33 A (Calcul Ingénierie, Avril 2026).`

Le câble doit être dimensionné pour supporter ce courant de crête sans échauffement excessif et sans provoquer une chute de tension qui mettrait l'onduleur en sécurité.

## Chute de tension : L'ennemi N°1 de votre rendement (<1%)

En très basse tension continue (TBT), chaque dixième de volt perdu en ligne impacte directement le rendement global et la stabilité du système. La chute de tension (ΔU) se calcule avec la formule : `ΔU (V) = (ρ * 2L * I) / S`.

*   **ρ (Rhô)** : résistivité du cuivre, soit 0.01786 Ω.mm²/m à 25°C (Données matériaux, standard IEC).
*   **L** : longueur du câble en mètres (un aller-retour, d'où le facteur 2).
*   **I** : intensité du courant en ampères.
*   **S** : section du câble en mm².

Pour la liaison critique batterie-onduleur, une chute de tension de 1% est le seuil à ne pas dépasser. Sur un parc 48V, cela représente 0.48V. Au-delà, l'onduleur peut interpréter cette baisse comme une décharge de la batterie et se couper prématurément.

Le tableau suivant modélise la chute de tension pour une longueur totale de 1.5 mètre (distance fréquente en local technique) et un courant nominal de 105 A.

| Paramètre | Câble 35 mm² | Câble 50 mm² | Câble 70 mm² |
|---|---|---|---|
| Chute de tension (V) | 0.96 V | 0.67 V | 0.48 V |
| Chute de tension (%) | 2.00 % | 1.40 % | **1.00 %** |
| Source | Calcul Ingénierie | Calcul Ingénierie | Calcul Ingénierie |
| Date de validité | Avril 2026 | Avril 2026 | Avril 2026 |

Constat : une section de 35 mm² est hors tolérance. Une section de 50 mm² est une configuration acceptable mais non idéale. La section de 70 mm² garantit une chute de tension conforme aux exigences de stabilité.

## Abaques de section pour une liaison batterie-onduleur 48V

Cet abaque fournit la section de câble en cuivre requise pour maintenir une chute de tension inférieure ou égale à 1% (0.48V) sur un système 48V, en fonction de la longueur de la liaison et du courant nominal (105 A).

| Longueur (aller simple) | Section minimale (mm²) | Chute de tension calculée | Statut |
|---|---|---|---|
| 1.0 m | 50 mm² | 0.45 V (0.93%) | Conforme |
| 1.5 m | 70 mm² | 0.48 V (1.00%) | **Recommandé** |
| 2.0 m | 95 mm² | 0.47 V (0.98%) | Conforme |
| 2.5 m | 95 mm² | 0.59 V (1.23%) | Non-conforme |
| 3.0 m | 120 mm² | 0.53 V (1.10%) | Non-conforme |

*Données basées sur la formule de chute de tension (Avril 2026). Une section de 95mm² reste acceptable sur 2.5m si une tolérance de 1.25% est admise par le cahier des charges.*

Pour toute liaison supérieure à 2 mètres, l'architecture de l'installation doit être revue pour rapprocher le parc batterie de l'onduleur. Augmenter la section au-delà de 95 mm² engendre des coûts et des contraintes de sertissage disproportionnés.

## Cuivre OFC vs CCA : 30% de conductivité en moins, risque maximal

Le marché propose des câbles dits "CCA" (Copper-Clad Aluminum), constitués d'une âme en aluminium plaquée d'une fine couche de cuivre. Ces câbles sont formellement proscrits pour les applications de puissance en courant continu.

La résistivité de l'aluminium est d'environ 2.82x10⁻⁸ Ω.m, contre 1.72x10⁻⁸ Ω.m pour le cuivre (Données matériaux, standard IEC). Un câble CCA présente une résistance sensiblement plus élevée qu'un câble en cuivre pur (OFC - Oxygen-Free Copper) de même section (Calcul Ingénierie, Avril 2026).

Pour obtenir une performance équivalente à un câble cuivre de 50 mm², il faudrait utiliser un câble CCA de 77,5 mm² (commercialement : 95 mm²) (Litong Cable, 2026), ce qui est mécaniquement incompatible avec les cosses et borniers standards. L'utilisation d'un câble CCA sous-dimensionné entraîne un échauffement thermique dangereux pouvant provoquer la fonte de l'isolant et un incendie.

## Le serrage au couple : 15 Nm minimum pour un contact parfait

Le dimensionnement du câble est inutile si la connexion n'est pas mécaniquement parfaite. Une connexion lâche sur une cosse de batterie ou un bornier d'onduleur crée un point de résistance localisé. Sous 100 A, ce point peut atteindre plusieurs centaines de degrés Celsius en quelques minutes.

L'utilisation d'une clé dynamométrique n'est pas une option. Pour des bornes M8, un couple de serrage variant de 10 Nm à 12 Nm selon l'équipement est impératif pour assurer une pression de contact suffisante (Pylontech/Victron, 2022-2023) et éviter la création d'arcs électriques ou d'échauffements. Le sertissage des cosses sur le câble doit être réalisé avec une pince hydraulique pour garantir une connexion électrique et mécanique sans défaut.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Section câble batterie 48V

**Quelle section de câble pour un onduleur 3000w 48v ?**
Un onduleur 3000W 48V tire 62,5 A en nominal (P/U = 3000/48). Pour une liaison de 1.5m, une section de 35 mm² est suffisante, assurant une chute de tension de 0,096 V (soit 0,20 %), ce qui reste acceptable. Pour viser 1%, une section de 50 mm² est recommandée.

**Peut-on utiliser du câble de démarrage pour relier les batteries ?**
Non. Le câble de démarrage est conçu pour des courants très élevés sur de très courtes durées (quelques secondes). Son isolant n'est pas prévu pour un usage permanent et ne respecte pas les normes de tenue au feu requises pour une installation fixe.

**Faut-il un fusible entre la batterie et l'onduleur 5000w ?**
Oui, c'est une obligation normative. Un fusible ou un disjoncteur DC doit être installé sur le pôle positif, au plus près de la batterie. Pour un onduleur 5000W 48V, un fusible calibré entre 150 A et 200 A est requis, mais pour les batteries LiFePO4, les modèles ANL/MEGA-fuse s'avèrent inadaptés et des fusibles Class T ou NH00 sont impératifs (UTE/Littelfuse, 2013-2023).

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*