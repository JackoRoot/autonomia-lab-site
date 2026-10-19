---
title: "DoD LFP vs Plomb Gel : Le vrai calcul de rentabilité sur 10 ans."
linkTitle: "DoD LFP vs Plomb-Gel"
slug: "lab_silo1_dod-lfp-vs-plomb-gel"
title_tag: "Batterie Gel vs LiFePO4 DoD : Calcul de rentabilité 10 ans"
meta_description: "Analyse de la décharge profonde (DoD) Gel vs LiFePO4. Calcul de ROI basé sur les cycles et l'énergie utile."
date: "2026-10-19"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "decharge profonde batterie gel vs lifepo4 dod"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Une décharge profonde (DoD) à 80% sur une batterie Gel vs LiFePO4 n'est pas comparable. La chimie LFP supporte 4000 à 6000 cycles dans ces conditions (Standard industriel, 2026). Une batterie Plomb-Gel soumise au même régime voit sa durée de vie s'effondrer. Le DoD opérationnel recommandé pour le Gel ne dépasse pas 50% pour préserver une durée de vie acceptable. L'énergie utile totale sur 10 ans est le seul calcul pertinent.

## Profondeur de Décharge (DoD) : 50% pour le Plomb-Gel vs 90% pour la LFP

La profondeur de décharge (Depth of Discharge - DoD) est le pourcentage de la capacité nominale qui est retiré de la batterie. Une batterie de 100 Ah qui fournit 80 Ah a atteint un DoD de 80%. Cette valeur n'est pas une simple mesure, elle conditionne directement la dégradation chimique de l'accumulateur.

Pour une batterie à électrolyte gélifié (Plomb-Gel), une décharge profonde et répétée au-delà de 50% de sa capacité nominale engendre une sulfatation irréversible des plaques de plomb. Ce phénomène cristallise le sulfate de plomb, réduisant la surface active et augmentant la résistance interne. Le résultat est une chute de capacité et de puissance disponible. Maintenir une batterie Gel dans une plage de DoD de 30% à 50% est une contrainte opérationnelle pour atteindre une durée de vie de 750 à 1 800 cycles selon la profondeur (Victron/Trojan, 2024).

La chimie Lithium-Fer-Phosphate (LFP) repose sur une structure cristalline de type olivine. Cette structure polyanionique supporte des cycles de décharge profonds sans dégradation structurelle majeure. Une décharge à 90%, voire 100% gérée par le BMS (Battery Management System), est une condition d'usage nominale.

| Paramètre | Plomb-Gel | LFP (Lithium-Fer-Phosphate) | Source | Date de validité |
|---|---|---|---|---|
| DoD Opérationnel Recommandé | 50% | 90% | Standard industriel | 2026 |
| Cycles de vie (à 80% DoD) | 400 à 500 cycles | 3000-6000 | Standard industriel | 2026 |
| Mécanisme de dégradation | Sulfatation des plaques | Croissance SEI (lente) | Standard industriel | 2026 |

## Énergie Utile vs Capacité Nominale : 1 kWh LFP ≠ 1 kWh Gel

La capacité nominale affichée sur une fiche technique est une valeur brute. L'énergie réellement disponible pour l'utilisateur, ou énergie utile, dépend directement du DoD maximal applicable sans endommager la batterie. Un calcul de dimensionnement qui ne prendrait en compte que la capacité nominale est une erreur technique conduisant au sous-dimensionnement et à la défaillance prématurée du parc de stockage, en particulier pour la technologie Plomb.

Une installation de 10 kWh nominaux en Plomb-Gel ne met à disposition que 5 kWh par cycle si l'on respecte la contrainte de 50% de DoD. La même installation en LFP met à disposition 9 kWh par cycle. Pour obtenir 9 kWh utiles avec du Plomb-Gel, il faudrait surdimensionner le parc à 18 kWh nominaux, ce qui double le coût, l'encombrement et le poids.

## Calcul de l'Énergie Totale Cyclée sur 10 ans (kWh)

La rentabilité d'un système de stockage ne se mesure pas à son coût d'achat, mais à la quantité totale d'énergie qu'il pourra stocker et restituer durant sa vie opérationnelle. Cette métrique, l'énergie totale cyclée, s'obtient en multipliant l'énergie utile par cycle par le nombre total de cycles garantis par le constructeur ou mesurés sur le terrain.

Le comparatif sur une base de 10 kWh nominaux est sans équivoque. La batterie LFP restituera, sur sa durée de vie, une quantité d'énergie 14 fois supérieure à sa concurrente Plomb-Gel.

| Paramètre | Batterie Plomb-Gel (10 kWh) | Batterie LFP (10 kWh) | Source |
|---|---|---|---|
| Capacité nominale | 10 kWh | 10 kWh | Hypothèse de calcul |
| DoD recommandé | 50% | 90% | Standard industriel |
| Énergie utile / cycle | 5 kWh | 9 kWh | Calcul |
| Cycles de vie (au DoD rec.) | 750 à 1 000 cycles | 4000 cycles (valeur conservatrice) | Standard industriel (2026) |
| **Énergie totale cyclable** | **6 000 kWh** | **36 000 kWh** | Calcul |

## Coût par kWh restitué : La métrique finale de 0.41 € vs 0.025 €

Le coût final pour l'investisseur doit être ramené au kilowattheure réellement utilisé. Ce ratio (Coût d'achat / Énergie totale cyclable) est le seul indicateur de performance financière valide. Il neutralise les biais marketing liés au prix facial de la batterie.

Sur la base des coûts moyens de 2026, l'écart est structurel. Le kWh restitué par une batterie LFP est 16 fois moins cher que celui d'une batterie Plomb-Gel. L'investissement initial plus élevé pour la technologie LFP est amorti par un volume d'énergie disponible sans commune mesure.

| Paramètre | Batterie Plomb-Gel (10 kWh) | Batterie LFP (10 kWh) | Source |
|---|---|---|---|
| Coût pack / kWh nominal | 150 à 290 €/kWh (Enexer, 2024) | 80-100 USD/kWh (MotorWatt, 2026) — soit 73–92 €/kWh | Standard industriel (2026) |
| Coût d'achat total | 2 500 € | 900 € | Calcul |
| Énergie totale cyclable | 6 000 kWh | 36 000 kWh | Calcul précédent |
| **Coût / kWh restitué** | **0.41 €** | **0.025 €** | Calcul |


## Bilan technique chiffré

L'analyse comparative de la décharge profonde entre les chimies Plomb-Gel et LFP aboutit à des conclusions factuelles basées sur des ordres de grandeur physiques. La technologie LFP autorise un DoD nominal de 90% pour 4000 cycles, contre un DoD opérationnel de 50% pour 1200 cycles pour le Plomb-Gel.

Pour une capacité nominale identique de 10 kWh, l'énergie totale restituable sur la durée de vie est de 36 000 kWh pour la LFP contre 6 000 kWh pour le Plomb-Gel. Le coût final par kWh utile s'établit à 0.025 € pour la LFP contre 0.41 € pour le Plomb-Gel, soit un facteur de performance économique de 16 en faveur du Lithium-Fer-Phosphate. La décision d'investissement repose sur ce différentiel.

---

### Expertises Croisées
- **Hydraulique & Eau :** [LIEN INTERNE : Pompe immergée à 50m : Calculer la HMT sans griller le moteur.]
- **Thermique & Habitat :** [LIEN INTERNE : PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).]
- **Infrastructure :** [LIEN INTERNE : Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.]

### FAQ : DoD LFP vs Plomb Gel

**Une batterie LFP peut-elle vraiment être déchargée à 100% ?**
Techniquement, oui. Le BMS est calibré pour laisser une marge de sécurité infime en bas de décharge (typiquement 2-5%) pour éviter la dégradation. Pour l'utilisateur, le 0% affiché correspond à la limite de sécurité basse, ce qui équivaut à un DoD de 100% de la capacité utile.

**Pourquoi ma batterie gel a-t-elle perdu sa capacité en 2 ans ?**
Une défaillance prématurée est quasi systématiquement liée à des cycles de décharge trop profonds (au-delà de 50-60%) ou à un maintien en état de charge faible prolongé. Ces deux conditions accélèrent la sulfatation, qui est la cause principale de la perte de capacité irréversible.

**Le poids est-il un facteur de comparaison entre LFP et Gel ?**
Oui, et il est significatif. La densité énergétique massique du LFP est de 90-160 Wh/kg (MotorWatt, 2026) contre 30 à 40 Wh/kg (LVFU/Leipzig, 2024) pour le Plomb-Gel. Un parc de batteries LFP est 3 à 4 fois plus léger que son équivalent Plomb-Gel à capacité nominale égale, ce qui a un impact sur la structure porteuse et la manutention.

---
> Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*