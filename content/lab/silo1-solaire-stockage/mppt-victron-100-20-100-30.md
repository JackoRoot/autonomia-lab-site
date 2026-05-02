---
title: "MPPT Victron 100/20 vs 100/30 : Ne bridez pas vos panneaux."
linkTitle: "MPPT 100/20 vs 100/30"
slug: "lab_silo1_mppt-victron-100-20-100-30"
title_tag: "Victron MPPT 100/20 vs 100/30 : Guide de choix technique"
meta_description: "Différence MPPT Victron 100/20 et 100/30. Courant de charge et puissance PV max sans bridage."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "difference mppt 100/20 et 100/30 victron"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

La principale différence technique entre un MPPT Victron 100/20 et un 100/30 est le courant de charge maximal : 20 A pour le premier, 30 A pour le second. Un mauvais dimensionnement entraîne un écrêtage (clipping) de la production. Pour un parc batterie 12V, le 100/20 est limité à 290 Wc (Documentation Victron, 2026) de panneaux, contre 440 Wc (Documentation Victron, 2026) pour le 100/30.

## Le chiffre "100" : Tension maximale (Voc) de 100 V

Le premier nombre, "100", dans la désignation des deux modèles, correspond à la tension maximale en circuit ouvert (Voc) que le régulateur peut accepter en entrée depuis le champ photovoltaïque. Ce seuil de 100 V est une limite absolue.

Le dépassement, même bref, de cette tension endommage de manière irréversible les composants électroniques internes. La tension Voc d'un panneau solaire augmente par temps froid. Un coefficient de sécurité de 15% doit être appliqué sur la Voc nominale des panneaux pour le dimensionnement en climat tempéré.

Pour un panneau avec une Voc de 42 V (STC, 25°C), la tension à froid peut augmenter significativement selon le coefficient de température Voc du panneau (à vérifier sur la fiche technique constructeur). Deux de ces panneaux en série atteignent 94 V, ce qui est acceptable. Trois panneaux en série dépasseraient 140 V, entraînant la destruction du régulateur.

## Le courant de charge : 20 A vs 30 A, une différence de 50%

La différence fondamentale entre le 100/20 et le 100/30 réside dans leur capacité de sortie. Le second nombre indique le courant de charge maximal que le régulateur peut délivrer au parc de batteries. Le 100/30 offre une capacité de charge supérieure de 50% à celle du 100/20.

Ce courant détermine directement la puissance photovoltaïque maximale que le système peut exploiter. Un courant plus élevé permet de recharger un parc de batteries de plus grande capacité dans un temps plus court ou de supporter des consommations DC plus importantes en journée.

## Puissance PV maximale admise : de 290 Wc à 1160 Wc

La puissance photovoltaïque (exprimée en Watt-crête, Wc) que chaque régulateur peut gérer dépend de la tension nominale du parc de batteries (12V, 24V ou 48V). La puissance est le produit de la tension par le courant (P = U x I).

Le tableau suivant détaille la puissance PV maximale recommandée pour chaque configuration. Le non-respect de ces valeurs conduit à une perte de production.

| Modèle | Tension Système (Nominale) | Courant de charge max. | Puissance PV max. (indicative) | Source |
|---|---|---|---|---|
| SmartSolar MPPT 100/20 | 12 V | 20 A | 290 Wc | (Documentation Victron, SmartSolar MPPT 100/20 & 100/30, 2026) |
| | 24 V | 20 A | 580 Wc | (Documentation Victron, SmartSolar MPPT 100/20 & 100/30, 2026) |
| | 48 V | 20 A | 1160 Wc | (Documentation Victron, SmartSolar MPPT 100/20 & 100/30, 2026) |
| SmartSolar MPPT 100/30 | 12 V | 30 A | 440 Wc | (Documentation Victron, SmartSolar MPPT 100/20 & 100/30, 2026) |
| | 24 V | 30 A | 880 Wc | (Documentation Victron, SmartSolar MPPT 100/20 & 100/30, 2026) |

Le modèle 100/20 présente une polyvalence supérieure en étant compatible avec les systèmes 48V, ce que le 100/30 n'est pas. En 48V, le courant de charge reste à 20 A — seule la sortie de charge (load output) est limitée à 1 A, ce qui n'affecte pas la régulation PV.

## L'écrêtage (clipping) : quand 34% de la production est perdue

Installer une puissance de panneaux supérieure à la capacité du régulateur provoque un phénomène d'écrêtage, ou "clipping". Le MPPT, pour se protéger, bride la puissance entrante à son maximum admissible. L'excédent de production est purement et simplement perdu.

Exemple concret : un champ PV de 440 Wc est raccordé à un MPPT 100/20 sur un parc batterie 12V. La puissance maximale admissible pour ce régulateur est de 290 Wc.

Calcul de la perte à pleine puissance : (440 Wc - 290 Wc) = 150 Wc perdus.
Le ratio de perte est de 150 / 440 = 34%. L'installation est sous-dimensionnée et ne produit qu'à 66% de sa capacité potentielle lors des pics d'ensoleillement. Le choix correct aurait été le MPPT 100/30.

Un léger surdimensionnement du champ PV (jusqu'à 20%) est acceptable et même recommandé pour améliorer la production par temps couvert. C'est un principe de conception détaillé dans le [Ratio DC/AC onduleur : Pourquoi surdimensionner vos panneaux de 20%.](/lab_silo1_ratio-dc-ac-onduleur/).

## Cas pratique : quel MPPT pour 2 panneaux de 410 Wc ?

Le dimensionnement se fait sur la base des fiches techniques des panneaux solaires.
**Spécifications d'un panneau de 410 Wc (exemple fictif — valeurs illustratives uniquement) :**
*   Puissance (Pmax) : 410 Wc
*   Tension circuit ouvert (Voc) : **49,8 V** (valeur illustrative — relever sur fiche technique constructeur)
*   Courant court-circuit (Isc) : **10,5 A** (valeur illustrative — relever sur fiche technique constructeur)

**Configuration :** 2 panneaux sur un système de batteries 24V. Puissance totale : 820 Wc.

**Option 1 : Câblage en série**
*   Voc totale = 49.8 V x 2 = 99.6 V. C'est critique et ne laisse aucune marge de sécurité pour le froid. Ce montage est techniquement non conforme et dangereux pour le matériel.

**Option 2 : Câblage en parallèle**
*   Voc totale = 49.8 V. Tension d'entrée sécuritaire.
*   Isc total = 10.5 A x 2 = 21 A.
*   Puissance totale : 820 Wc.

**Analyse du choix de régulateur :**
*   **MPPT 100/20 (24V)** : Puissance max. 580 Wc. Le régulateur écrêtera 240 Wc (820 - 580), soit une perte de 29% de la production.
*   **MPPT 100/30 (24V)** : Puissance max. 880 Wc. Ce modèle est parfaitement dimensionné pour exploiter la totalité des 820 Wc du champ solaire.

Le choix du MPPT 100/30 est ici une nécessité technique pour ne pas brider l'installation.


---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : MPPT Victron 100/20 vs 100/30

**Peut-on mettre un MPPT 100/30 sur une petite installation ?**
Oui. Le surdimensionnement du régulateur n'a pas d'impact négatif sur la performance ; il offre une marge pour une future extension du champ PV. Le seul facteur limitant est le coût d'achat, supérieur à celui du 100/20.

**C'est quoi la différence entre MPPT 100/20 et 100/30 Victron ?**
La différence principale est le courant de charge maximal : 20 ampères pour le 100/20 et 30 ampères pour le 100/30. Ce chiffre définit la puissance maximale de panneaux solaires que chaque régulateur peut gérer pour une tension de batterie donnée.

**Le MPPT 100/20 chauffe, est-ce normal ?**
Une élévation de température est normale en fonctionnement, surtout à pleine charge (20 A). Le régulateur est conçu avec un radiateur pour la dissipation thermique. Une surchauffe anormale peut indiquer une mauvaise ventilation ou un surdimensionnement excessif du champ PV.

**Faut-il un fusible entre le MPPT et la batterie ?**
C'est obligatoire. La norme impose une protection contre les surintensités au plus près de la batterie. Son calibre doit être légèrement supérieur au courant de charge max du MPPT, par exemple un fusible de 40A pour le 100/30. Voir [Fusibles DC ou Disjoncteurs sur vos strings ? La norme l'exige.](/lab_silo1_fusibles-dc-ou-disjoncteurs/).

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*