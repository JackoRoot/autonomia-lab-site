---
title: "Méthodologie : Calculateur ROI installation solaire résidentielle"
description: "Sources, formules et hypothèses du calculateur ROI solaire. Prime CRE T14, PVGIS-SARAH3, TRVE 2026 et TVA 5,5% vs 20%."
date: 2026-05-03
draft: false
---

← [Calculateur ROI solaire](/outils/calculateur-roi-solaire/) · ← [Tous les outils](/outils/)

# Méthodologie du calculateur ROI installation solaire résidentielle

> Cette page détaille l'origine de chaque chiffre utilisé par notre calculateur. L'objectif : transparence totale pour vous permettre de vérifier, contester ou ajuster selon votre situation réelle.

## Approche du calculateur

### Deux modes de calcul

**Mode estimation rapide** : saisissez la puissance, la région, le prix global et le taux d'autoconsommation. Résultat en 30 secondes. Idéal pour un ordre de grandeur avant de solliciter des devis.

**Mode "Configurer mon projet"** : décomposez votre devis réel (matériel HT + pose RGE + batterie optionnelle), renseignez les aides réellement obtenues (prime CRE + aides locales), votre consommation annuelle réelle et votre tarif HP/HC. Le calculateur projette sur 20 ans avec dégradation des panneaux et évolution du prix de l'électricité. C'est le mode recommandé avant tout engagement financier.

**Le mode manuel calcule également la TVA automatiquement** selon le type de panneaux choisi (5,5% certifiés PPE2-V2 ou 20% standard) et affiche un récapitulatif du coût net ligne par ligne.

### Deux scénarios en parallèle

Le calculateur propose **2 scénarios en parallèle** :

**Scénario autoconsommation seule** : le ROI repose uniquement sur les économies réalisées en substituant du kWh réseau par du kWh solaire autoproduit. C'est le scénario pessimiste mais le plus proche de la réalité pour une installation sans optimisation.

**Scénario autoconsommation + revente** : le ROI intègre à la fois les économies sur facture ET les revenus issus de la vente du surplus à EDF OA sur 20 ans. C'est le scénario recommandé pour dimensionner un projet sérieux.

**Pourquoi 2 scénarios ?** Le tarif de rachat du surplus a chuté de **−68% depuis 2020** (de 0,126 €/kWh à 0,04 €/kWh en 2026). La rentabilité d'une installation solaire résidentielle repose désormais quasi-exclusivement sur l'autoconsommation, pas sur la revente. Ce calculateur le matérialise.

---

## Données de référence

### Prime à l'autoconsommation — CRE T14 2026

- **Montant** : 80 €/kWc pour les installations ≤9 kWc
- **Trimestre de référence** : T14 (depuis le 01/04/2025, stable)
- **Versement** : en une seule fois, à la première facturation EDF OA (environ 1 an après mise en service)
- **Condition** : installation raccordée au réseau, artisan RGE, conformité Consuel

**Source officielle** : [CRE — Arrêtés tarifaires photovoltaïques en métropole (open data)](https://www.cre.fr/documents/open-data/arretes-tarifaires-photovoltaiques-en-metropole.html)

| Puissance | Prime T14 (€/kWc) | Prime totale exemple |
|-----------|-------------------|----------------------|
| 3 kWc | 80 €/kWc | 240 € |
| 6 kWc | 80 €/kWc | 480 € |
| 9 kWc | 80 €/kWc | 720 € |

> **Note** : La prime CRE est révisée trimestriellement. Le montant de 80 €/kWc est celui du T14. Vérifier le trimestre en cours sur cre.fr avant tout engagement.

### Tarif de rachat du surplus — EDF OA 2026

- **Tarif** : 0,04 €/kWh (≤9 kWc, vente du surplus uniquement)
- **Contrat** : 20 ans, garanti à la date de raccordement
- **Condition** : autoconsommation avec vente du surplus (pas vente totale)

**Source officielle** : [CRE — Arrêtés tarifaires obligation d'achat photovoltaïque](https://www.cre.fr/documents/open-data/arretes-tarifaires-photovoltaiques-en-metropole.html)

### TVA applicable en 2026

Depuis le 1er janvier 2026, le régime de TVA sur le photovoltaïque résidentiel est **binaire** :

| Taux | Conditions | Cas typique |
|------|-----------|-------------|
| **5,5%** | Puissance ≤9 kWc + panneaux certifiés bas carbone (PPE2-V2, empreinte <530 kgCO2eq/kWc) + système gestionnaire d'énergie | Panneaux européens certifiés (DualSun, Voltec, Sunpower) |
| **20%** | Toutes les autres installations | Majorité des installations avec panneaux importés |

> **Important** : Le taux de 10% a été définitivement supprimé au 1er janvier 2026 (BOFiP-ACTU-2025-00165 du 22 octobre 2025). La TVA à 5,5% nécessite l'éligibilité des modules sur [Certisolis](https://www.certisolis.com/certisolis/bilan-carbone/).

**Sources** :
- [Service-Public.fr — Changement de TVA pour les panneaux photovoltaïques](https://www.service-public.fr/particuliers/actualites/A18469)
- Arrêté du 8 septembre 2025 (Journal officiel)
- BOFiP-ACTU-2025-00165 du 22 octobre 2025

### Prix de l'électricité — TRVE 2026

- **Option Base TTC** : 0,1940 €/kWh
- **Heures Pleines** : 0,2065 €/kWh
- **Heures Creuses** : 0,1579 €/kWh
- **Date de référence** : Tarif en vigueur depuis février 2026

**Source officielle** : [CRE — Tarifs réglementés de vente d'électricité](https://www.cre.fr/consommateurs/marche-de-detail/tarifs-reglementes-de-vente-d-electricite/trv-tarifs-reglementes-de-vente-d-electricite)

> Le calculateur utilise le tarif Base (0,1940 €/kWh). Si vous êtes en option HP/HC et que votre production solaire coïncide principalement avec les Heures Pleines, ajustez le curseur vers 0,2065 €/kWh.

### Productible solaire — PVGIS-SARAH3

**Paramètres de simulation** :
- Technologie : c-Si (silicium cristallin)
- Inclinaison : 35° (optimum France)
- Orientation : plein Sud (azimut 0°)
- Pertes système : 14%
- Type de montage : free-standing

| Zone géographique | Productible (kWh/kWc/an) |
|-------------------|--------------------------|
| Nord — Paris, Île-de-France | 950 kWh/kWc/an |
| Centre — Lyon, Auvergne-Rhône-Alpes | 1 200 kWh/kWc/an |
| Sud — Marseille, PACA | 1 580 kWh/kWc/an |

> Ces valeurs sont des moyennes calculées sur la période 2005-2023. Une année défavorable peut être 10-15% en dessous.

**Source officielle** : [PVGIS — JRC, Commission Européenne](https://re.jrc.ec.europa.eu/pvg_tools/fr/)

### Prix du marché — installations clé en main 2026

| Puissance | Fourchette marché 2026 (TTC, pose incluse) |
|-----------|-------------------------------------------|
| 3 kWc | 6 000 – 9 000 € |
| 6 kWc | 10 000 – 15 000 € |
| 9 kWc | 15 000 – 22 000 € |

> Données de marché agrégées (ENERPLAN, SER-SOLER, Hello Watt 2026). **Demandez plusieurs devis RGE** avant tout engagement.

---

## Formules appliquées

```
Production_annuelle (kWh) = Puissance_kWc × Productible_région

kWh_autoconsommés = Production_annuelle × Taux_autoconsommation
kWh_revendus = Production_annuelle × (1 - Taux_autoconsommation)

Économies_annuelles (€) = kWh_autoconsommés × Prix_TRVE
Revenus_revente (€) = kWh_revendus × 0,04 €/kWh

Gain_annuel_auto = Économies_annuelles
Gain_annuel_full = Économies_annuelles + Revenus_revente

Mode rapide :
Prime_CRE = 80 €/kWc × Puissance_kWc
Coût_net = Prix_achat_TTC - Prime_CRE

Mode manuel :
TVA_matériel_pose = (Matériel_HT + Pose_HT) × Taux_TVA (5,5% ou 20%)
TVA_batterie = Batterie_HT × 20% (toujours 20%)
Prix_TTC = Matériel_HT + Pose_HT + TVA_matériel_pose + Batterie + TVA_batterie
Coût_net = Prix_TTC - Prime_CRE - Aides_locales

ROI_simple = Coût_net / Gain_annuel_full

Projection 20 ans (mode manuel) :
Pour chaque année n de 1 à 20 :
  Facteur_dégradation = (1 - Taux_dégradation)^(n-1)
  Facteur_élec = (1 + Hausse_élec)^(n-1)
  Gain_année_n = Gain_annuel_full × Facteur_dégradation × Facteur_élec
  Cumul += Gain_année_n
  Si Cumul ≥ Coût_net → ROI atteint à l'année n

Bénéfice_net_20_ans = Cumul_20_ans - Coût_net
```

---

## Projection 20 ans — mode manuel

### Dégradation des panneaux

Les cellules photovoltaïques perdent du rendement chaque année sous l'effet des cycles thermiques, des UV et du vieillissement des encapsulants.

| Scénario | Taux annuel | Perte cumulée 20 ans |
|----------|-------------|----------------------|
| Calcul simplifié | 0%/an | 0% |
| Réaliste terrain | **0,5%/an** | ~10% |
| Panneaux premium (tier 1) | 0,3%/an | ~6% |

**Source** : Étude Preger et al. 2020 (Journal of The Electrochemical Society) · Clean Energy Reviews · Garanties constructeurs Pylontech, BYD, Victron

### Évolution du prix de l'électricité

Le TRVE a augmenté en moyenne de +3,5%/an sur 2010-2026. En 2026, il se stabilise à 0,194 €/kWh après les hausses de 2022-2024.

| Scénario | Hausse annuelle | Impact ROI |
|----------|----------------|------------|
| Prix constant | 0%/an | ROI conservateur |
| Tendance historique | **+2%/an** | ROI amélioré |
| Scénario haussier | +4%/an | ROI très amélioré |

> La combinaison dégradation 0,5%/an + hausse électricité +2%/an est le scénario le plus réaliste pour une projection 20 ans.

---

## Taux d'autoconsommation — que choisir ?

| Taux | Profil typique |
|------|---------------|
| **50%** | Logement sans optimisation, personnes absentes en journée, pas de batterie |
| **70%** | Usage optimisé : lave-linge et lave-vaisselle programmés en journée, présence partielle |
| **85%** | Avec batterie de stockage ou présence permanente (télétravail, retraite) |

> Un taux d'autoconsommation élevé est toujours plus rentable qu'une augmentation de puissance en 2026, compte tenu de la faiblesse du tarif de rachat (0,04 €/kWh vs 0,194 €/kWh de valeur évitée).

---

## Ce que le calculateur ne couvre pas

### Dégradation des panneaux (mode rapide uniquement)
En mode rapide, le calcul utilise la production constante de l'année 1. Le mode manuel intègre la dégradation réelle — utilisez-le pour une décision d'investissement sérieuse.

### Maintenance et assurance
Non intégrés dans les deux modes :
- Nettoyage annuel (~100 €/an)
- Remplacement onduleur à mi-vie (~800-1 500 € vers 10-12 ans)
- Surprime d'assurance habitation (~50-100 €/an)

Ces coûts peuvent allonger le ROI réel de 1 à 2 ans.

### Batterie de stockage
Le coût de la batterie est intégrable dans le mode manuel. Son ROI propre dépend de votre taux d'autoconsommation actuel et de la capacité choisie — voir notre [calculateur durée de vie batterie LFP](/outils/calculateur-batterie-lfp/).

### Aides locales variables
Les montants des aides régionales, départementales et communales varient fortement selon votre territoire. Le mode manuel vous permet de les saisir manuellement une fois obtenues.

---

## Interpréter les résultats

### ROI < 10 ans
Excellent — dans la fourchette haute du marché. Vérifiez que les hypothèses sont réalistes.

### ROI entre 10 et 15 ans
Standard pour une installation résidentielle en 2026. Rentable sur la durée de vie des panneaux (25-30 ans), mais exige de ne pas déménager avant l'amortissement.

### ROI > 15 ans
À optimiser : réduire le prix d'achat, augmenter l'autoconsommation, vérifier le dimensionnement.

---

## Évolutions prévues

- Module orientation/inclinaison réelle (calcul PVGIS selon azimut et tilt saisis)
- Comparateur régions avec carte interactive France
- Module remplacement onduleur à mi-vie dans la projection 20 ans
- Simulation mois par mois (saisonnalité production vs consommation)

Si vous avez des suggestions, contactez-nous via [le formulaire du Lab](/contact/).

---

**Dernière mise à jour** : Mai 2026
**Sources principales** : CRE (arrêtés tarifaires T14 2026), PVGIS-SARAH3 JRC (simulations 2005-2023), Service-Public.fr (TVA 5,5% arrêté 8 septembre 2025), BOFiP-ACTU-2025-00165, TRVE CRE février 2026
