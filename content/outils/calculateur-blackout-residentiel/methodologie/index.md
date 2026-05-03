---
title: "Méthodologie : Calculateur autonomie blackout résidentiel"
description: "Sources, consommations réelles des équipements, production PV en îlotage et formules du calculateur blackout."
date: 2026-05-03
draft: false
---

← [Calculateur blackout](/outils/calculateur-blackout-residentiel/) · [Tous les outils](/outils/)

# Méthodologie du calculateur autonomie blackout résidentiel

> Cette page détaille l'origine de chaque chiffre utilisé par notre calculateur. L'objectif : transparence totale pour vous permettre de vérifier, contester ou ajuster selon votre situation réelle.

## Approche du calculateur

Le calculateur propose **2 scénarios en parallèle** :

**Batterie seule** : autonomie calculée uniquement sur la capacité de stockage. C'est le pire cas — nuit complète, ciel couvert, pas de production solaire.

**Batterie + solaire** : autonomie calculée en tenant compte de la production photovoltaïque journalière selon la saison. Si la production dépasse la consommation, l'autonomie devient théoriquement illimitée — la batterie sert alors de tampon nuit/nuageux.

---

## Données de référence — consommations équipements

### Réfrigérateur

- **Puissance absorbée** : 150 W (puissance moyenne de fonctionnement — cycle compresseur inclus)
- **Consommation annuelle classe A+** : ~200 kWh/an soit ~23 W en moyenne continue
- **Note** : La valeur de 150 W intègre les cycles de démarrage du compresseur. En mode économie d'énergie blackout, réduire les ouvertures divise la consommation par 2.

**Source** : [ADEME — Consommation des appareils électroménagers](https://agirpourlatransition.ademe.fr/particuliers/maison/economiser-energie/appareils-electromenagers/consommation-energie-appareils-electromenagers)

### Congélateur coffre

- **Puissance absorbée** : 120 W (puissance moyenne de fonctionnement)
- **Consommation annuelle classe A+** : ~180 kWh/an

**Source** : ADEME 2024 — données appareils électroménagers

### Box internet / routeur

- **Puissance absorbée** : 20 W (fibres et ADSL confondus)
- **Données constructeurs** : Orange Livebox 6 = 12-18 W, SFR Box 8 = 15-20 W, Freebox Pop = 18-22 W

**Source** : Fiches techniques constructeurs Orange, SFR, Free 2024

### Éclairage LED (×4 ampoules)

- **Puissance unitaire** : 9 W par ampoule LED équivalent 60W incandescent
- **Total ×4** : 36 W
- **Économie vs incandescent** : −85% de consommation

**Source** : [ADEME — Guide éclairage](https://agirpourlatransition.ademe.fr/particuliers/maison/economiser-energie/eclairage)

### Télévision 55 pouces LED

- **Puissance absorbée** : 100 W (LCD/LED 55 pouces standard)
- **OLED 55 pouces** : 130-170 W en usage typique
- **Mode veille** : <0,5 W (non intégré au calcul)

**Source** : ADEME 2024 — mesures appareils audiovisuels

### Ordinateur portable

- **Puissance absorbée** : 65 W (chargeur 65W — usage intensif)
- **Usage bureautique léger** : 30-45 W
- **Valeur retenue** : 65 W (pire cas)

**Source** : Fiches techniques constructeurs (Dell, HP, Lenovo 2024)

### Chauffe-eau électrique 200L

- **Puissance de la résistance** : 2 000 W
- **Durée de chauffe** : 2-4 heures pour remonter de 15°C à 60°C (200L)
- **Énergie totale** : ~4-8 kWh par cycle complet

> **Note blackout** : Le chauffe-eau représente souvent le poste le plus gourmand. En mode blackout, programmer un cycle court en milieu de journée solaire (production PV maximale) et réduire la consigne à 50°C réduit significativement l'impact sur la batterie.

**Source** : ADEME 2024 — eau chaude sanitaire

### Micro-ondes

- **Puissance absorbée** : 900 W (puissance nominale micro-ondes 900W standard)
- **Usage typique** : 3-5 minutes par utilisation soit 45-75 Wh par usage

**Source** : Fiches techniques marché (Samsung, Whirlpool, LG 2024)

### Pompe immergée forage (0,75 kW)

- **Puissance absorbée** : 750 W
- **Courant de démarrage** : 2-3× la puissance nominale pendant 1-3 secondes
- **Compatibilité onduleur** : vérifier que l'onduleur supporte le courant de démarrage (Victron Multiplus II : compatible ; vérifier pour les autres marques)

**Source** : Fiches techniques Grundfos, DAB, Wilo 2024

### Chargeurs smartphones/laptops (×2)

- **Puissance totale** : 30 W (2 × 15 W en charge active)
- **Charge complète smartphone** : ~10 Wh (batterie 3 000 mAh)

**Source** : Mesures terrain (chargeurs USB-C standard 2024)

---

## Production PV en mode îlotage — PVGIS-SARAH3

### Compatibilité onduleur hybride en îlotage

> **Point critique** : tous les onduleurs ne fonctionnent pas en mode îlotage (hors réseau). Vérifiez la compatibilité de votre modèle :
> - **Victron Multiplus II** : îlotage natif ✅
> - **Deye hybride** : îlotage natif ✅
> - **Huawei SUN2000** : îlotage sur modèles récents ✅
> - **SMA Sunny Boy** : nécessite module Secure Power Supply ⚠️
> - **Onduleurs réseau simples** : incompatibles — s'éteignent à la coupure réseau ❌

### Productible journalier par saison

Les valeurs sont issues des simulations PVGIS-SARAH3 pour Lyon (zone H2 — représentative du Centre-France), paramètres : c-Si, 35° inclinaison, plein Sud, pertes 14%.

| Saison | Productible journalier | Détail |
|--------|----------------------|--------|
| Hiver (décembre-février) | 1,7 kWh/kWc/jour | PVGIS Lyon décembre réel (1,68 kWh/kWc/j) |
| Printemps/Automne (mars-mai, sept-nov) | 4,1 kWh/kWc/jour | Moyenne mars-avril PVGIS Lyon |
| Été (juin-août) | 4,7 kWh/kWc/jour | Moyenne juin-juillet PVGIS Lyon |

> **Variabilité** : Ces valeurs sont des moyennes. Un jour nuageux en hiver peut descendre à 0,5 kWh/kWc/jour. L'autonomie en cas de blackout hiver nuageux est donc comparable au scénario "batterie seule".

**Source** : [PVGIS-SARAH3 — JRC, Commission Européenne](https://re.jrc.ec.europa.eu/pvg_tools/fr/)

### Rendement onduleur en îlotage

| Modèle / Type | Rendement | Source |
|---------------|-----------|--------|
| Onduleur standard | 85% | Moyenne marché |
| Onduleur hybride récent | 92% | Fiche technique Deye, Huawei 2024 |
| Victron Multiplus II | 97% | Datasheet Victron Energy |

---

## Capacité batterie — valeurs réelles

| Modèle | Capacité nominale | Capacité utilisable (DoD 80%) |
|--------|-------------------|-------------------------------|
| Pylontech US5000 (×1) | 4,8 kWh | 3,84 kWh |
| Pylontech US5000 (×2) | 9,6 kWh | 7,68 kWh |
| BYD Battery-Box HVS 10.2 | 10,2 kWh | 8,16 kWh |
| BYD Battery-Box HVS 20.4 | 20,4 kWh | 16,32 kWh |

> Le calculateur utilise une DoD de 80% — conforme aux recommandations constructeurs pour préserver la durée de vie des cellules LFP. Voir notre [calculateur durée de vie batterie LFP](/outils/calculateur-batterie-lfp/) pour le détail.

**Sources** : [Pylontech — US5000 datasheet](https://en.pylontech.com.cn/products/us5000) · [BYD Battery-Box — warranty letter](https://www.bydbatterybox.com)

---

## Formules appliquées

```
Consommation_totale_W = Σ(Watts_équipements_actifs)

Consommation_24h_kWh = Consommation_totale_W × 24 / 1000

Production_PV_24h_kWh = kWc_installés
                        × Productible_journalier_saison
                        × Rendement_onduleur

Conso_nette_24h = MAX(0, Consommation_24h_kWh - Production_PV_24h_kWh)

Capacité_utilisable = Capacité_batterie_kWh × 0,80

Autonomie_sans_solaire (h) = Capacité_utilisable / (Consommation_totale_W / 1000)

Si Conso_nette_24h > 0 :
  Autonomie_avec_solaire (h) = Capacité_utilisable / (Conso_nette_24h / 24)
Sinon :
  Autonomie_avec_solaire = ∞ (production ≥ consommation)
```

---

## Contexte : durée réelle des coupures en France

Pour relativiser les résultats :

| Indicateur | Valeur | Source |
|-----------|--------|--------|
| Durée médiane de coupure | 52 minutes | RTE — bilan électrique 2024 |
| Durée moyenne de coupure | 1h45 | RTE — bilan électrique 2024 |
| Coupures > 3h | <5% des incidents | RTE 2024 |
| Coupures > 24h (hors tempête) | Exceptionnelles | RTE 2024 |

> La grande majorité des coupures réseau en France durent moins de 2 heures. Une batterie de 5 kWh avec les équipements essentiels (frigo, éclairage, box) couvre statistiquement 99% des incidents réseau.

---

## Ce que le calculateur ne couvre pas

### Courant de démarrage des moteurs
Les équipements à moteur (pompe, compresseur frigo, PAC) consomment 2 à 5× leur puissance nominale pendant 1-3 secondes au démarrage. L'onduleur doit être dimensionné pour absorber ces pics. Le calculateur utilise les puissances nominales (usage continu).

### PAC air-eau
La puissance absorbée d'une PAC air-eau varie fortement avec la température extérieure (COP variable). À −5°C, une PAC de 10 kW thermique peut absorber 4-5 kW électrique. La PAC peut également refuser de démarrer sous certains onduleurs (fréquence instable). **Consultez votre installateur avant de compter sur la PAC en blackout.**

### Stockage thermique
Un chauffe-eau bien isolé maintient la température 24-48h sans chauffe. Un congélateur plein tient 48h sans électricité. Ces "réservoirs thermiques" ne sont pas modélisés dans le calculateur.

### Consommation vampire (veille)
Les box TV, consoles, chargeurs en veille consomment 0,5 à 5 W chacun en permanence. Non intégrés au calcul par défaut — à ajouter via le curseur "appareil custom".

---

## Interpréter les résultats

### Autonomie < 6 heures
Configuration insuffisante pour une coupure sérieuse. Identifier les équipements les plus consommateurs (chauffe-eau, micro-ondes) et les couper en blackout.

### Autonomie 6-24 heures
Couvre la quasi-totalité des incidents réseau en France. Suffisant pour la majorité des situations résidentielles.

### Autonomie > 3 jours
Excellente configuration. Couvre les incidents graves (tempête, panne de grande ampleur). La production solaire en été peut assurer une autonomie illimitée.

### Autonomie infinie (∞)
La production solaire journalière dépasse la consommation. La batterie couvre les périodes nocturnes et les jours nuageux. Configuration autonome complète en été.

---

## Évolutions prévues

- Module courant de démarrage moteurs (pic vs nominal)
- Simulation PAC air-eau avec COP variable selon température extérieure
- Module stockage thermique (inertie frigo/congélateur)
- Carte régionale France (productible PVGIS par département)
- Scénario tempête (3 jours nuageux consécutifs en hiver)

Si vous avez des suggestions, contactez-nous via [le formulaire du Lab](/contact/).

---

**Dernière mise à jour** : Mai 2026
**Sources principales** : ADEME (consommation appareils électroménagers 2024), PVGIS-SARAH3 JRC (production PV saisonnière), Pylontech US5000 datasheet, BYD Battery-Box warranty, Victron Multiplus II datasheet, RTE bilan électrique 2024
