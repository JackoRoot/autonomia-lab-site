---
title: "Calculateur autonomie blackout résidentiel"
description: "Combien d'heures votre installation batterie + solaire tient-elle en cas de coupure réseau ? Calculez selon vos équipements réels, votre saison et votre puissance PV."
date: 2026-05-03
draft: false
keywords: ["blackout", "coupure réseau", "autonomie", "batterie", "solaire", "îlotage", "calculateur"]
icon: "zap"
---

← [Tous les outils](/outils/)

# Combien de temps tiendrez-vous en blackout ?

Une coupure réseau survient. Votre installation batterie + panneaux solaires prend le relais — mais pour combien de temps ? Ce calculateur répond en tenant compte de vos équipements réels, de la production PV de la saison et de la capacité utilisable de votre batterie.

{{< calc-blackout >}}

## Comment utiliser ce calculateur

Cochez les équipements que vous voulez maintenir en fonctionnement pendant la coupure. Ajustez la puissance PV installée et la capacité batterie selon votre installation. Sélectionnez la saison pour adapter la production photovoltaïque journalière. Le calculateur affiche en parallèle l'autonomie **batterie seule** (nuit, ciel couvert) et **batterie + solaire** (journée ensoleillée).

## Les deux scénarios expliqués

**Batterie seule** — c'est le cas le plus défavorable : nuit complète, ciel couvert, pas de production solaire. Ce chiffre représente votre autonomie garantie quelles que soient les conditions météo. C'est le minimum que vous pouvez promettre à votre famille.

**Batterie + solaire** — la production PV vient réduire la consommation nette que la batterie doit couvrir. En été, une installation correctement dimensionnée peut afficher "autonomie illimitée" : la batterie sert uniquement de tampon nuit/nuageux. En hiver, le gain est plus limité (1,7 kWh/kWc/jour à Lyon en décembre).

## Ce qui compte vraiment

**Le chauffe-eau électrique est le poste critique.** Avec 2 000 W, il peut vider une batterie de 5 kWh en 2h30. En mode blackout, programmez un cycle court en milieu de journée (production PV maximale) et descendez la consigne à 50°C.

**La pompe de forage démarre à 2-3× sa puissance nominale.** Votre onduleur doit être dimensionné pour absorber ce pic. Victron Multiplus II et Deye hybride gèrent nativement ce courant de démarrage.

**Pas tous les onduleurs ne fonctionnent en îlotage.** Un onduleur réseau simple s'éteint à la coupure — il ne peut pas alimenter votre maison. Vérifiez que votre onduleur supporte explicitement le mode "off-grid" ou "îlotage" avant de compter dessus.

## FAQ rapide

**Pourquoi la PAC air-eau n'est-elle pas dans la liste ?**
La puissance d'une PAC varie fortement avec la température extérieure (COP variable) et elle peut refuser de démarrer sous certains onduleurs (instabilité de fréquence). Un coefficient de performance de 3 en automne peut chuter à 1,5 en plein hiver. Ce cas requiert une analyse spécifique — consultez votre installateur.

**L'autonomie infinie, c'est vraiment possible ?**
En été avec suffisamment de panneaux, oui : si la production journalière dépasse la consommation journalière, la batterie se recharge la journée et couvre la nuit. Mais un jour nuageux en hiver peut descendre à 0,5 kWh/kWc — l'autonomie réelle revient alors au scénario batterie seule.

**5 kWh suffisent-ils pour une coupure typique en France ?**
Oui, dans la grande majorité des cas. La durée médiane de coupure réseau en France est de 52 minutes (RTE 2024). Avec les équipements essentiels (frigo, éclairage, box), une batterie de 5 kWh couvre statistiquement 99% des incidents réseau. [Voir la méthodologie complète](/outils/calculateur-blackout-residentiel/methodologie/) pour les données RTE.

**DoD 80% : pourquoi pas 100% ?**
Décharger une batterie LFP en dessous de 20% du SOC restant accélère significativement la dégradation des cellules. Les constructeurs (Pylontech, BYD) recommandent une DoD maximale de 80% pour maintenir la durée de vie garantie. En mode urgence, vous pouvez aller jusqu'à 95% — mais de manière exceptionnelle.

[Méthodologie complète : sources, formules, données PVGIS et RTE](/outils/calculateur-blackout-residentiel/methodologie/)
