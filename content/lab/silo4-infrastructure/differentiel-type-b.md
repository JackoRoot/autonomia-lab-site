---
title: "Interrupteur Différentiel Type B : Exigé (et cher) en stockage DC."
linkTitle: "Différentiel Type B"
slug: "lab_silo4_differentiel-type-b"
title_tag: "Différentiel Type B vs Type A : Norme Solaire & IRVE"
meta_description: "Pourquoi la norme exige le Type B en stockage DC et IRVE. Risque d'aveuglement du Type A."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 4
mot_cle: "differentiel type b vs type a courant continu"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

La saturation du tore magnétique d'un différentiel type A par un courant de fuite continu supérieur à 6 mA le rend inopérant face à un défaut d'isolement alternatif. Le différentiel type B vs type A pour la gestion du courant continu n'est donc pas un choix mais une exigence normative pour la protection des installations avec stockage DC ou borne de recharge (IRVE).

## Le différentiel 30 mA : un tore magnétique pour la protection des personnes

Un dispositif différentiel à courant résiduel (DDR) assure la protection des personnes contre les contacts indirects. Son fonctionnement repose sur un tore magnétique qui mesure en permanence la somme vectorielle des courants entrants (phase) et sortants (neutre).

En l'absence de défaut, cette somme est nulle. En cas de fuite de courant vers la terre, une asymétrie apparaît. Le tore détecte ce flux magnétique différentiel et commande l'ouverture mécanique du circuit dès que le seuil de 30 mA est atteint (NF C 15-100, 2026).

## Saturation par courant continu : Comment un Type A devient aveugle > 6 mA

L'électronique de puissance (onduleurs, variateurs, chargeurs de batterie) peut générer des courants de fuite à composante continue (DC). Un courant de fuite DC lisse, même de faible valeur, polarise le circuit magnétique du tore d'un différentiel de type AC ou A. Il est saturé, "aveuglé".

L'appareil devient alors incapable de détecter une surintensité alternative, même mortelle. Un défaut d'isolement franc sur un appareil ne provoquera plus le déclenchement. La protection des personnes n'est plus assurée. La norme NF C 15-100 (Source : AFNOR NF C 15-100, 2024) fixe le seuil de tolérance à 6 mA de courant de fuite DC pour un type A.

| Type de Différentiel | Détection Courant Alternatif (AC) | Détection Courant Continu Pulsé | Détection Courant Continu Lisse | Source Normative |
|-----------------------|-----------------------------------|----------------------------------|-----------------------------------|------------------|
| **Type AC** | Oui | Non | Non | NF C 15-100 (obsolète pour circuits spécialisés) |
| **Type A** | Oui | Oui | Non (tolérance < 6 mA) | NF C 15-100 (standard) |
| **Type F** | Oui | Oui (immunité renforcée) | Non (seuil de tolérance identique au Type A) | NF C 15-100 (applications spécifiques) |
| **Type B** | **Oui** | **Oui** | **Oui** | **NF C 15-100-7-722** |

## Architecture du Type B : La double détection AC + DC pur

L'interrupteur différentiel de Type B intègre deux systèmes de détection distincts pour garantir la protection en toutes circonstances. Un premier circuit, basé sur un tore classique, surveille les défauts alternatifs et continus pulsés, comme un Type A.

Un second circuit, souvent basé sur un capteur à effet Hall ou un transformateur de flux, mesure spécifiquement et indépendamment toute composante de courant continu lisse. Cette architecture garantit que le dispositif ne sera jamais saturé et déclenchera quel que soit le type de courant de défaut.

## NF C 15-100-7-722 : Le cadre normatif pour stockage et IRVE

La section NF C 15-100-7-722, dédiée aux Infrastructures de Recharge pour Véhicules Électriques (IRVE), est formelle. Toute borne de recharge triphasée, ou monophasée non équipée d'une détection de courant de fuite DC 6 mA intégrée, impose l'installation d'un interrupteur différentiel de Type B en tête de ligne.

Par extension, cette exigence s'applique à toute installation de stockage d'énergie (batteries solaires) dont l'onduleur hybride est susceptible de générer un courant de défaut à composante continue lisse. Le Consuel est intransigeant sur ce point pour la validation des installations neuves.

## Coût d'investissement : Un facteur 5 à 10 sur le prix du module

La complexité technique de la double détection se répercute directement sur le coût du matériel. Le prix d'un interrupteur différentiel Type B est sans commune mesure avec celui d'un Type A standard. L'investissement est conséquent et doit être provisionné dans le chiffrage d'un tableau électrique pour stockage DC.

| Type de Module | Calibre | Prix public constaté (HT) | Source | Date |
|----------------|---------|---------------------------|--------|------|
| ID Type A | 40A / 30mA | 41,90 à 60,96 € HT | Castorama / Comptoir des Pros, 2026 | 2026 |
| ID Type B | 40A / 30mA | 200 à 350 € HT | Viox / Distributeurs, 2026 | 2026 |

Le rapport de coût, de l'ordre de 1 à 8, ne résulte pas d'une stratégie marketing mais du coût des composants électroniques de détection du courant continu pur et de la complexité de leur intégration dans un module au format DIN.

## Bilan technique : Les 3 cas où le Type B est non-négociable

1.  **IRVE triphasée :** L'installation d'une borne de recharge pour véhicule électrique en triphasé impose sans dérogation un différentiel Type B (NF C 15-100-7-722).
2.  **Onduleur hybride sans transformateur :** Les onduleurs sans transformateur d'isolement galvanique peuvent, en cas de défaut interne, injecter du courant DC sur le réseau AC. Le Type B est une exigence de sécurité.
3.  **Exigence du Consuel :** Pour toute installation neuve ou rénovation lourde impliquant ces technologies, l'absence de différentiel Type B conforme entraîne un refus de l'attestation de conformité.


---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Interrupteur différentiel Type B stockage DC
**Un différentiel Type A suffit-il pour mon installation solaire ?**
Non, si votre onduleur hybride ou votre système de stockage par batterie peut générer une fuite de courant continu lisse supérieure à 6 mA. Le Type A ne détecte pas ce type de défaut et peut être rendu inopérant. Le Type B est alors requis.

**Quel est le risque réel de ne pas installer un différentiel Type B ?**
Le risque est l'électrocution. Un courant de fuite DC peut "aveugler" un différentiel Type A, qui ne déclenchera plus en cas de contact d'une personne avec une masse métallique sous tension, même si la fuite alternative est supérieure à 30 mA.

**Pourquoi un différentiel Type B est-il si cher ?**
Son coût est justifié par une double technologie de détection. Il embarque à la fois le tore magnétique classique pour les courants alternatifs (comme le Type A) et un circuit électronique supplémentaire (capteur à effet Hall) pour mesurer les courants de fuite continus purs.

**Le Type B protège-t-il également contre les défauts gérés par le Type A ?**
Oui. Le Type B est le dispositif le plus complet. Il assure la détection des défauts à composante alternative (Type AC), continue pulsée (Type A) et continue lisse. Il couvre l'ensemble du spectre de défauts potentiels.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*