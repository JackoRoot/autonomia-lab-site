---
title: "Calculateur durée de vie batterie LFP"
description: "Combien d'années va vraiment durer votre batterie LiFePO4 ? Calculez selon vos conditions, comparez chiffres constructeur et terrain."
date: 2026-05-03
draft: false
keywords: ["batterie LFP", "LiFePO4", "durée de vie", "cycles", "DoD", "calculateur"]
icon: "battery"
---

← [Tous les outils](/outils/)

# Combien va durer votre batterie LFP ?

Les constructeurs annoncent 6000 cycles, 15 ans, voire plus. Mais en conditions réelles
résidentielles, la dégradation est plus rapide. Cet outil affiche en parallèle les chiffres
**constructeur** (datasheet idéale) et **réalistes terrain** (études et retours utilisateurs).

{{< calc-lfp >}}

## Comment utiliser ce calculateur

Entrez la capacité de votre batterie, la profondeur de décharge habituelle, le nombre de cycles par an et le prix payé. Le calculateur affiche en parallèle ce que promet le constructeur et ce que montrent les études terrain. Pour un premier calcul, les valeurs par défaut correspondent à une installation résidentielle typique.

## Les paramètres qui comptent vraiment

**Profondeur de décharge (DoD)** : c'est le facteur le plus impactant après la température. Passer de 80% à 95% de DoD peut réduire la durée de vie de 25 à 30%. La zone 70-80% est le meilleur compromis durée de vie / énergie utilisable.

**Cycles par an** : une installation de stockage solaire quotidien fait environ 365 cycles. Un backup d'urgence, 50 à 100. Un usage intensif (van, bateau), 500 à 700.

**Prix payé** : le coût final au kWh stocké est l'indicateur clé pour comparer des installations de capacités différentes ou arbitrer entre tailles de batterie.

## FAQ rapide

**Pourquoi deux scénarios ?**
Les chiffres constructeurs sont mesurés en laboratoire (25°C, charge lente). La réalité résidentielle produit un écart systématique de 25 à 40%. [Voir la méthodologie complète](/outils/calculateur-batterie-lfp/methodologie/) pour les sources détaillées.

**Comment savoir lequel s'applique à mon cas ?**
Si votre batterie est dans un local frais, chargée doucement par du solaire, avec une marque tier 1 (Pylontech, BYD, Victron) — tirez vers le scénario constructeur. Local chaud, charge réseau intensive, ou marque inconnue — le scénario réaliste est plus fiable.

**Mes batteries actuelles correspondent-elles à ces estimations ?**
Comparez la capacité mesurée aujourd'hui avec la capacité initiale. En dessous de 80% de la capacité d'origine, la fin de vie IEC 62619 approche.

[Méthodologie complète : sources, formules, hypothèses](/outils/calculateur-batterie-lfp/methodologie/)
