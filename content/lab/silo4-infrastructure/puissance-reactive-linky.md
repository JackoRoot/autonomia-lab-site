---
title: "Puissance réactive (kVAR) : Les pénalités Linky sur les moteurs (Ateliers, Fours, PAC)."
linkTitle: "Puissance réactive Linky"
slug: "lab_silo4_puissance-reactive-linky"
title_tag: "Puissance réactive Linky (kVAR) : Cos phi et pénalités"
meta_description: "Analyse technique cos phi sur Linky. Impact sur l'abonnement kVA pour ateliers et PAC."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 4
mot_cle: "cos phi puissance reactive linky kva"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Pour tout contrat résidentiel Basse Tension inférieur ou égal à 36 kVA, le tarif de la puissance réactive (cos phi dégradé) est de 0 c€/kVAr.h (Source: TURPE 7, 2026). Le compteur Linky mesure cette énergie mais ne la facture pas. La seule pénalité est indirecte : un mauvais cos phi augmente la puissance apparente en kVA et peut provoquer un déclenchement pour dépassement d'abonnement.

## kW, kVA et kVAr : L'anatomie vectorielle de la puissance

La puissance apparente (S), exprimée en kilovoltampères (kVA), est la puissance totale soutirée au réseau. Elle dimensionne l'abonnement et l'infrastructure (câbles, disjoncteur). Elle est la somme vectorielle de deux composantes distinctes.

La puissance active (P), en kilowatts (kW), est la seule qui produit un travail utile : chaleur, lumière, force mécanique. C'est celle qui est facturée au kilowattheure.

La puissance réactive (Q), en kilovoltampères réactifs (kVAr), sert à magnétiser les circuits des moteurs, compresseurs et transformateurs. Elle ne produit pas de travail mais est indispensable à leur fonctionnement. Ce flux réactif circule sur le réseau et génère des pertes par effet Joule dans les lignes.

Le déphasage angulaire entre le courant et la tension est mesuré par le facteur de puissance, ou cosinus phi (cos φ). Un cos φ de 1.0 indique une charge purement résistive (radiateur), où kVA = kW. Un cos φ de 0.7, typique d'un moteur d'atelier, signifie qu'une part importante de la puissance soutirée est réactive.

## Cadre réglementaire TURPE 7 : 0 € de pénalité directe pour les contrats ≤ 36 kVA

Le Tarif d'Utilisation des Réseaux Publics d'Électricité (TURPE 7), défini par la Commission de Régulation de l'Énergie (CRE), est formel. Pour les abonnés raccordés en Basse Tension (BT) avec une puissance souscrite inférieure ou égale à 36 kVA, la composante d'énergie réactive n'est pas facturée.

Le compteur Linky mesure la puissance réactive avec précision, mais l'algorithme de facturation l'ignore pour ce segment de clientèle. La comparaison avec le segment industriel (HTA) met en évidence cette distinction réglementaire.

| Segment de Raccordement | Seuil de Tolérance (tan φ) | Tarif Soutirage Réactif | Date de validité |
|-------------------------|----------------------------|-------------------------|------------------|
| BT ≤ 36 kVA (Résidentiel) | Aucun seuil applicable | 0 c€/kVAr.h | TURPE 7 (2026) |
| HTA (Industriel) | > 0,60 | 2.39 c€/kVAr.h | TURPE 7 (2026) |
> *Source des données : Enedis / CRE, rapport TURPE 7 (2026).*

## La véritable sanction : Le déclenchement de l'organe de coupure du Linky

La seule pénalité pour un particulier est physique, pas financière. Elle provient du dépassement de la puissance apparente (kVA) souscrite dans le contrat. L'organe de coupure du compteur Linky ne surveille pas les kW, mais les kVA.

Un moteur de 3 kW avec un excellent cos φ de 0.95 soutire 3.15 kVA. Le même moteur avec un cos φ dégradé de 0.7 soutire 4.28 kVA. Sur un abonnement de 6 kVA, ce moteur seul consomme plus de 70% de la capacité de la ligne, augmentant le risque de déclenchement si un autre appareil démarre.

La sanction n'est donc pas une ligne sur la facture, mais une coupure de l'alimentation. La solution n'est pas de compenser le cos φ (dispositifs coûteux), mais de dimensionner correctement l'abonnement en kVA en tenant compte des charges inductives (moteurs, PAC). Pour les charges à fort courant d'appel, un [Disjoncteur Courbe D ou C ? Le choix vital pour les gros compresseurs.](/lab_silo4_disjoncteur-courbe-d-vs-c/) est par ailleurs normatif.

## Cas des onduleurs solaires : 0.94 de cos φ imposé mais non facturé

Dans le cadre de la stabilité du réseau, les nouvelles normes de raccordement Enedis (F1ATB, 2024) imposent aux onduleurs photovoltaïques d'opérer avec un facteur de puissance dégradé à 0.94.

Cette contrainte technique force l'onduleur à absorber ou générer de la puissance réactive pour aider à maintenir la tension du réseau local dans sa plage réglementaire (230 V +/- 10%).

Cette production ou absorption de réactif est mesurée par le Linky. Conformément au cadre TURPE 7, elle n'entraîne aucune facturation ni pénalité pour le producteur résidentiel.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées

- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Puissance réactive et Linky

**Est-ce que le compteur Linky facture la puissance réactive ?**
Non. Pour les contrats résidentiels et professionnels en Basse Tension jusqu'à 36 kVA, la facturation de l'énergie réactive (kVAr.h) est de 0 € (Source : TURPE 7, 2026). Le compteur la mesure mais ne la facture pas.

**Pourquoi mon Linky disjoncte avec ma pompe à chaleur ou mon moteur ?**
Cela peut venir de deux phénomènes. Un pic de courant au démarrage (courant d'appel) qui nécessite un disjoncteur adapté (Courbe D). Ou une consommation de puissance apparente (kVA) trop élevée en régime nominal à cause d'un mauvais cosinus phi, dépassant la limite de votre abonnement.

**Comment améliorer le cosinus phi de mon installation ?**
Pour un particulier, l'action la plus simple est de choisir des équipements récents avec un facteur de puissance corrigé d'origine. L'installation de batteries de condensateurs est une solution industrielle, rarement justifiée économiquement pour un contrat résidentiel.

**Un mauvais cos phi augmente-t-il ma consommation en kWh ?**
Non. Le cosinus phi n'a pas d'impact direct sur la consommation de puissance active (kWh) mesurée par le compteur. Il augmente la puissance apparente (kVA) et le courant total circulant dans vos câbles, ce qui peut légèrement augmenter les pertes par effet Joule, mais cet effet est marginal sur la facture.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*