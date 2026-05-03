---
title: "Méthodologie : Calculateur dimensionnement panneaux solaires"
description: "Sources, productibles PVGIS, pertes système, profils de consommation et formules du calculateur de dimensionnement PV résidentiel."
date: 2026-05-03
draft: false
---

← [Calculateur dimensionnement PV](/outils/calculateur-dimensionnement-pv/) · ← [Tous les outils](/outils/)

# Méthodologie du calculateur dimensionnement panneaux solaires

> Cette page détaille l'origine de chaque chiffre utilisé par notre calculateur. L'objectif : transparence totale pour vous permettre de vérifier, contester ou ajuster selon votre situation réelle.

## Approche du calculateur

Le calculateur répond à une question simple : **combien de kWc installer pour couvrir X% de ma consommation annuelle ?**

**Mode estimation rapide** : choisissez un profil type (studio, foyer moyen, maison T3/T4, maison 100m² tout électrique) ou saisissez votre consommation directement. Résultat en 30 secondes.

**Mode "Configurer mon foyer"** : décomposez votre consommation poste par poste — chauffage, eau chaude sanitaire, 8 postes électroménager, voiture électrique, piscine. Plus précis, indispensable pour un dimensionnement sérieux.

Il prend en compte :
- La consommation annuelle réelle du foyer (relevé Linky ou facture)
- Le productible solaire de la région (PVGIS-SARAH3)
- L'orientation et l'inclinaison de la toiture
- Les pertes système réelles (câblage, onduleur, salissures)
- Le taux d'autoconsommation visé

La puissance recommandée est ensuite traduite en nombre de panneaux (base 400 Wc), surface de toiture nécessaire, et estimation budgétaire indicative.

---

## Données de référence — consommation foyer France

### Consommation moyenne nationale

La consommation électrique moyenne d'un foyer français s'établit à 4 287 kWh/an d'après Enedis (Bilan électrique 2024).

**Source** : [Enedis — Bilan électrique 2024](https://www.enedis.fr)

### Profils par type de logement

| Profil | Consommation typique | Notes |
|--------|---------------------|-------|
| Studio / Appartement | ~2 000 kWh/an | Sans chauffage électrique |
| Foyer moyen | ~4 300 kWh/an | Moyenne nationale Enedis 2024 |
| Maison T3/T4 | ~9 000 kWh/an | Avec quelques usages électriques |
| Maison 100m² tout électrique | ~14 500 kWh/an | Chauffage + ECS électrique |

> **Note** : Ces profils sont des moyennes. Votre consommation réelle dépend du nombre d'occupants, de l'isolation, des équipements et des habitudes. **Utilisez toujours votre relevé Linky ou votre facture annuelle** pour un calcul précis.

**Source** : ADEME — Panel usages électrodomestiques · Enedis bilan 2024 · CRE données résidentielles

---

## Productible solaire — PVGIS-SARAH3

### Productible annuel par région

Le productible (kWh produits par kWc installé et par an) est issu des simulations PVGIS-SARAH3 du Joint Research Centre (JRC) de la Commission Européenne.

**Paramètres de simulation de référence** :
- Technologie : c-Si (silicium cristallin)
- Inclinaison : 35° (optimum France)
- Orientation : plein Sud (azimut 0°)
- Pertes système : 14% (défaut PVGIS on-grid)
- Type de montage : free-standing

| Zone | Productible de référence | Correction orientation |
|------|--------------------------|----------------------|
| Nord — Paris, Île-de-France (H1) | 950 kWh/kWc/an | Plein Sud 100% |
| Centre — Lyon, Auvergne-Rhône-Alpes (H2) | 1 200 kWh/kWc/an | Plein Sud 100% |
| Sud — Marseille, PACA (H3) | 1 580 kWh/kWc/an | Plein Sud 100% |

> **Important** : Ces valeurs sont des moyennes calculées sur la période 2005-2023. La variabilité interannuelle est de ±10 à 15%.

**Source** : [PVGIS-SARAH3 — JRC, Commission Européenne](https://re.jrc.ec.europa.eu/pvg_tools/fr/)

---

## Pertes système — détail par poste

Les pertes système réduisent la production théorique des panneaux. Le calcul utilise la valeur par défaut PVGIS de **14% pour une installation on-grid standard**.

| Poste de pertes | Valeur | Source |
|-----------------|--------|--------|
| **Total on-grid standard** | **14%** | JRC PVGIS 2022 (valeur par défaut) |
| Câblage DC | 2% | ADEME 2019 (PVGIS défaut : 1,5%) |
| Encrassement / salissures | 1% | Obton 2023, NREL 2022 (Europe tempérée) |
| Mismatch électrique (cellules) | 1,5% | NREL 2022 |
| Onduleur + divers | ~9-10% | SMA, Victron datasheets |

### Pertes selon l'orientation

| Orientation | Coefficient | Perte vs plein Sud |
|------------|-------------|-------------------|
| Plein Sud | 1,00 | Référence |
| Sud-Est / Sud-Ouest | 0,95 | −5% |
| Est / Ouest | 0,85 | −15% |
| Nord-Est / Nord-Ouest | 0,70 | −30% |

**Source** : PVGIS Guide utilisateur — JRC 2022

---

## Puissance des panneaux — hypothèse de calcul

Le calculateur utilise une puissance unitaire de **400 Wc** par panneau, standard sur le marché résidentiel 2026.

| Gamme de panneaux | Puissance unitaire typique |
|-------------------|---------------------------|
| Entrée de gamme | 350-380 Wc |
| Standard marché 2026 | **400-420 Wc** |
| Haut de gamme | 440-480 Wc |

Surface par panneau : **2,0 m²** (panneau 1 m × 2 m — standard marché)

---

## Taux d'autoconsommation — hypothèses

| Taux | Profil | Implication sur dimensionnement |
|------|--------|--------------------------------|
| **50%** | Personnes absentes en journée, pas de batterie | Puissance à installer × 2 pour couvrir la conso |
| **70%** | Usage optimisé (lave-linge programmé en journée) | Puissance × 1,43 — scénario par défaut |
| **85%** | Avec batterie de stockage | Puissance × 1,18 — nécessite batterie ~5-10 kWh |

> En 2026, avec un tarif de rachat du surplus à 0,04 €/kWh (vs 0,194 €/kWh évité), il est toujours plus rentable d'autoconsommer que de revendre. **L'objectif est donc de dimensionner pour maximiser l'autoconsommation**, pas pour produire le maximum absolu.

---

## Formules appliquées

```
Productible_réel (kWh/kWc/an) = Productible_région 
                                × Coefficient_orientation 
                                × (1 - Pertes_système)

kWh_à_couvrir = Consommation_annuelle × Taux_autoconsommation

kWc_nécessaire = kWh_à_couvrir / Productible_réel

kWc_recommandé = ARRONDI_SUPERIEUR(kWc_nécessaire, 0.5 kWc)
                 limité à 9 kWc (calcul simplifié)

Nb_panneaux = ARRONDI_SUPERIEUR(kWc_recommandé × 1000 / 400 Wc)

Surface_toiture = Nb_panneaux × 2,0 m²

Production_annuelle = kWc_recommandé × Productible_réel

kWh_autoconsommés = Production_annuelle × Taux_autoconsommation
kWh_surplus = Production_annuelle × (1 - Taux_autoconsommation)

Taux_couverture = kWh_autoconsommés / Consommation_annuelle

Budget_indicatif = kWc_recommandé × 2 000 €/kWc (marché 2026)
Prime_CRE = kWc_recommandé × 80 €/kWc (T14 2026)
Budget_net = Budget_indicatif - Prime_CRE
```

---

## Limite des 9 kWc dans ce calculateur

Le calculateur affiche un maximum de 9 kWc. Au-delà :
- Les démarches administratives changent (permis de construire obligatoire selon les cas)
- Le raccordement Enedis nécessite une convention spécifique
- Les tarifs de rachat EDF OA changent de tranche
- La prime CRE passe à 90 €/kWc pour la tranche 9-36 kWc

**Pour des installations >9 kWc, consultez obligatoirement un installateur RGE.**

---

## Interprétation des résultats

### Couverture < 40%
Votre consommation est élevée ou vous êtes dans une région peu ensoleillée. Pistes : augmenter la puissance installée, réduire la consommation (isolation, PAC en remplacement du chauffage électrique), ou envisager une installation >9 kWc.

### Couverture 40-80%
Dimensionnement standard. Le solaire couvre une part significative de votre facture. Rentable sur 10-15 ans selon la région.

### Couverture > 80%
Excellente configuration. Une batterie vous permettrait d'approcher l'autonomie complète. Voir notre [calculateur ROI installation solaire](/outils/calculateur-roi-solaire/) pour la rentabilité détaillée.

---

## Ce que le calculateur ne couvre pas

**Ombrage** : les arbres, cheminées et bâtiments voisins réduisent significativement la production — jusqu'à −30% selon la configuration. Non modélisé — à évaluer avec un installateur sur site.

**Dégradation annuelle** : les panneaux perdent ~0,5%/an de rendement. Sur 20 ans, la production est ~10% inférieure à la 1ère année. Non intégré.

**Installations >9 kWc** : non couvertes dans ce calculateur simplifié.

---

## Évolutions prévues

- Module ombrage (coefficient de masque)
- Simulation mois par mois (saisonnalité)
- Comparateur avec/sans batterie
- Calcul pour les installations >9 kWc
- Intégration directe avec PVGIS API (coordonnées GPS)

Si vous avez des suggestions, contactez-nous via [le formulaire du Lab](/contact/).

---

**Dernière mise à jour** : Mai 2026
**Sources principales** : PVGIS-SARAH3 JRC (2005-2023), Enedis bilan électrique 2024, ADEME Panel usages électrodomestiques, CRE arrêté tarifaire T14 2026
