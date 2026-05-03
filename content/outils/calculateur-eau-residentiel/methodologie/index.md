---
title: "Méthodologie : Calculateur autonomie eau résidentielle"
description: "Sources, tables détaillées par équipement et hypothèses du calculateur. CIEAU, ADEME, SISPEA et constructeurs."
date: 2026-05-03
draft: false
---

← [Calculateur eau](/outils/calculateur-eau-residentiel/) · [Tous les outils](/outils/)

# Méthodologie du calculateur autonomie eau résidentielle

> Cette page détaille l'origine de chaque chiffre utilisé par notre calculateur. L'objectif : transparence totale pour vous permettre de vérifier, contester ou ajuster selon votre situation réelle.

## Approche du calculateur

Le calculateur propose deux modes complémentaires :

**Mode "Estimation rapide"** : applique la moyenne nationale CIEAU (148 L/personne/jour) avec des paramètres minimaux. Idéal pour un ordre de grandeur en 30 secondes.

**Mode "Configurer mon foyer"** : décompose la consommation par poste réel selon vos équipements. Plus précis, plus long à remplir, mais beaucoup plus utile pour un dimensionnement sérieux d'installation autonome.

Le mode détaillé est celui que nous recommandons pour toute prise de décision (dimensionnement de cuve, projet d'autonomie, calcul d'impact d'un changement d'équipement).

## Données de référence nationales

### Consommation moyenne France

- **148 à 150 litres par personne et par jour** en France
- Stable depuis 2014 (variation 144-150 L)
- Tendance baissière entre 2004 (165 L) et 2014 (143 L) puis stabilisation

**Sources** :
- [CIEAU - Centre d'Information sur l'Eau](https://www.cieau.com/le-metier-de-leau/usages-consommation-conseils/calculateur-consommation-eau-annuelle/) (2024)
- [SISPEA - Rapport 2025 données 2023](https://www.services.eaufrance.fr/) : 145 L/jour/personne
- [notre-environnement.gouv.fr](https://www.notre-environnement.gouv.fr/themes/societe/le-mode-de-vie-des-menages-ressources/article/quelle-est-la-consommation-des-menages-en-eau-potable) (décembre 2025)

### Variations par profil

| Profil | Consommation | Source |
|--------|-------------|--------|
| Adulte moyen | 148-150 L/jour | CIEAU 2024 |
| Enfant | 55 L/jour | SISPEA 2024 |
| Personne âgée (domicile) | 105 L/jour | CIEAU |
| Revenus modestes | 90 L/jour | CIEAU |
| Sportif | 204 L/jour | CIEAU |
| En vacances | 230 L/jour | CIEAU |
| Personne âgée en résidence | 240-310 L/jour | CIEAU |

### Variations géographiques

| Région | Conso moyenne | Source |
|--------|---------------|--------|
| Nord-Pas-de-Calais | 109 L/jour | SISPEA |
| Provence-Alpes-Côte d'Azur | 228 L/jour | SISPEA |
| Île-de-France (133 communes SEDIF) | 100 L/jour | INSEE 2019 |

Le climat est le facteur principal de variation : régions chaudes = jardins, piscines, arrosage, +50 à +100% de consommation par rapport aux régions tempérées.

## Décomposition officielle CIEAU

Selon le [CIEAU](https://www.cieau.com/le-metier-de-leau/ressource-en-eau-eau-potable-eaux-usees/quels-sont-les-usages-domestiques-de-leau/) :

| Usage | % conso | Litres/jour (sur 148L) |
|-------|---------|------------------------|
| Hygiène corporelle (douches, bains, lavabos) | 39 % | 58 L |
| Sanitaires (WC) | 20 % | 30 L |
| Lessive (lave-linge) | 12 % | 18 L |
| Vaisselle | 10 % | 15 L |
| Préparation alimentaire (cuisson) | 6 % | 9 L |
| Entretien logement | 6 % | 9 L |
| Jardin / voiture / divers | 6 % | 9 L |
| Boisson | 1 % | 1,5 L |

**93%** est dédié à l'hygiène et au nettoyage (incluant l'entretien et les usages secondaires), **7%** à l'alimentation (boisson + cuisine).

## Tables détaillées par équipement

### WC / Toilettes

Source : [ADEME](https://agirpourlatransition.ademe.fr/particuliers/economiser/eau/conseils-economie-eau-maison), Geberit, Planetoscope

| Type de WC | Litres par chasse | Économie vs ancien |
|-----------|-------------------|---------------------|
| Anciens WC simple | 9-12 L | référence |
| WC modernes | 6-9 L | -25% |
| Double débit 3/6 L | 4,5 L mix moyen | -55% |
| WC siphonique sans réservoir | 4 L | -60% |
| Ultra-économe (Jacob Delafon, Gustavsberg) | 2,6 / 4 L | -65 à -70% |
| **Toilettes sèches** | **0 L** | **-100%** |

**Fréquence moyenne** : 4-6 passages par jour selon les sources (CIEAU = 4, Aubade = 4, autres études = 5-6).

**Pour 4 chasses/jour avec WC standard 7,5 L** = 30 L/personne/jour, soit 20% de la consommation totale (cohérent avec CIEAU).

**Important** : un WC qui fuit consomme jusqu'à **600 L/jour** (Espace Aubade). Vérifier régulièrement.

### Hygiène corporelle

Sources : [ADEME](https://agirpourlatransition.ademe.fr), [Selectra](https://eau.selectra.info/consommation/douche), Engie

#### Douche

| Type de pommeau | Débit (L/min) | Source |
|-----------------|---------------|--------|
| Pommeau standard | 15-20 L/min | ADEME |
| Pommeau économe | 6-8 L/min | ADEME |
| Pommeau ultra-éco (type Hydrao) | 4-6 L/min | Constructeur |
| Pommeau "ciel de pluie" | jusqu'à 20 L/min | ADEME |

**Économie d'eau avec pommeau économe** : jusqu'à **75%** selon ADEME.

#### Bain

- **Bain complet** : 150-200 litres (ADEME)
- Une douche de 5 minutes avec pommeau standard = 75-100 L = équivalent à un demi-bain
- Une douche de 10 minutes avec pommeau standard = 150-200 L = équivalent à un bain complet

**Conclusion** : la douche n'est plus économe que le bain au-delà de 10 minutes.

#### Calculs du calculateur

- Bain : valeur fixe **175 L/usage** (moyenne 150-200)
- Douche standard : **15 L/min × durée**
- Douche économe : **8 L/min × durée**
- Douche ultra-éco : **6 L/min × durée**
- Seau / minimaliste : **10 L/usage** (estimation pour douche au seau)

### Lave-linge

Sources : [BUT](https://blog.but.fr/article/combien-deau-consomme-une-machine-a-laver/), ADEME, Selectra, Engie

| Génération | Litres par cycle | Source |
|-----------|------------------|--------|
| Très récent (classe A) | 40-50 L | BUT, ADEME |
| Récent (classe A à A+) | 50-70 L | Engie |
| Standard | 70 L | Selectra moyenne |
| Ancien | 100-120 L | BUT |

**Cycles moyens** : 3-4 par semaine pour un foyer de 2-3 personnes, jusqu'à 7-10 pour un foyer avec enfants.

**Note** : depuis fin 2025, les modèles vendus neufs ne peuvent plus être en dessous de la classe A+ (réglementation européenne).

### Lave-vaisselle

Sources : ADEME, Selectra, Hydrao

| Méthode | Litres | Conditions |
|---------|--------|-----------|
| Lave-vaisselle récent (classe A+) | 9-12 L/cycle | Selectra |
| Lave-vaisselle standard | 10-16 L/cycle | ADEME |
| Lave-vaisselle ancien | 16-20 L/cycle | Hydrao |
| À la main, robinet ouvert | 30-60 L/jour | Hydrao (débit robinet 12 L/min) |
| À la main, 2 bacs (éco) | 10-15 L/jour | ADEME |

**Cycles moyens** : 1 cycle/jour pour un foyer de 4 personnes, moins pour un foyer plus petit.

**Comparaison économique** (pour 250 cycles/an, 5 personnes) :
- Lave-vaisselle : 0,09 à 0,28 €/cycle d'énergie
- À la main : 0,47 €/jour d'énergie (eau chaude)
- **Économie possible avec lave-vaisselle : ~95 €/an**

### Cuisine et boisson

Source : CIEAU (7% de la consommation totale)

- **Boisson** : ~1,5 L par personne par jour
- **Cuisson + préparation alimentaire** : ~8,5 L par personne par jour
- **Total** : ~10 L/personne/jour

Variable selon habitudes (cuisine maison vs plats préparés, fréquence des soupes/pâtes/etc.).

### Entretien logement

Source : CIEAU (6% de la consommation totale)

Largement **incompressible** quel que soit le nombre de personnes au foyer, comme le rappelle le CIEAU :

> "Le nettoyage du logement est un poste globalement incompressible, tout comme le volume d'eau nécessaire à une vaisselle ou une lessive en machine reste le même."

| Niveau | Litres/jour (foyer entier) |
|--------|---------------------------|
| Léger | ~5 L |
| Standard | ~9 L |
| Intensif | ~15 L |

### Jardin et arrosage

Sources : [ADEME](https://agirpourlatransition.ademe.fr), Hydrao

L'ADEME indique : **environ 10 L pour arroser 1 m² de jardin**.

Mais cette valeur varie énormément selon :
- La saison (juillet-août : x2 ; mars-octobre : x1 ; hiver : 0)
- Le type de plantation (gazon, potager, fleurs, plantes méditerranéennes)
- Le climat régional
- Le mode d'arrosage (goutte-à-goutte = -50%, arrosage classique au tuyau)

Le calculateur propose 4 niveaux :

| Niveau | Litres/m²/jour | Cas typique |
|--------|---------------|-------------|
| Aucun | 0 L/m²/j | Pas d'arrosage |
| Léger | 3 L/m²/j | Potager occasionnel, plantes adaptées |
| Modéré | 6 L/m²/j | Potager + gazon entretenu |
| Intensif | 10 L/m²/j | Arrosage été plein, recommandation ADEME |

**Le slider "Autres usages extérieur"** couvre : lavage voiture, terrasse, piscine, etc. À ajuster selon votre situation.

## Méthode de répartition potable / technique

Pour le calcul de la cuve, le calculateur sépare :

### Eau potable nécessaire (qualité réseau)

- Hygiène corporelle (39%)
- Cuisine + boisson (7%)
- Entretien logement (6%)

**Total : ~52% de la consommation = environ 84 L/personne/jour**

### Eau technique (peut être eau pluie filtrée)

- WC (20%)
- Lave-linge (12%)
- Vaisselle (10%) — discutable selon usage final
- Jardin / extérieur (6%)

**Total : ~48% de la consommation = environ 64 L/personne/jour**

### Important sur cette répartition

Cette répartition est une **moyenne calculée** à partir des % CIEAU. Votre cas réel dépend :

- De la qualité de votre installation de récupération d'eau de pluie (filtration, traitement UV)
- De votre réglementation locale (certaines communes interdisent l'eau de pluie pour la lessive)
- De votre confort personnel (certains préfèrent rester sur eau réseau pour la vaisselle)

Le calculateur donne un **ordre de grandeur de capacité de cuve** ; l'usage final eau pluie vs eau réseau dépend de votre installation finale.

## Formules appliquées (mode détaillé)

```
WC = Litres_par_chasse × Passages_par_jour × Personnes
Hygiène = (Litres_par_usage × Fréquence_par_semaine ÷ 7) × Personnes
Vaisselle (machine) = (Litres_par_cycle × Cycles_par_semaine) ÷ 7
Vaisselle (main) = Litres_par_jour (constant)
Linge = (Litres_par_cycle × Cycles_par_semaine) ÷ 7
Cuisine = 10 L × Personnes_équivalent  (1 enfant = 0,37 adulte selon SISPEA)
Entretien = Litres_par_jour selon niveau (foyer)
Jardin = (Surface × Ratio_arrosage) + Autres_usages

Conso_totale_jour = WC + Hygiène + Vaisselle + Linge + Cuisine + Entretien + Jardin
Eau_potable = Hygiène + Cuisine + Entretien
Eau_technique = WC + Vaisselle + Linge + Jardin
Cuve_recommandée = Conso_correspondante × Jours_d_autonomie
```

## Comment interpréter les résultats

### Le résultat est plus haut que prévu

**Causes possibles** :
- Vous avez un type de WC ancien encore en place
- Votre lave-linge ou lave-vaisselle est ancien
- Votre durée de douche dépasse 10 minutes
- Votre jardin est plus consommateur que vous pensiez

**Solution** : utilisez le calculateur pour simuler l'impact d'un changement d'équipement avant de décider.

### Le résultat est plus bas que prévu

**Vérifiez** :
- Vous n'avez pas oublié un usage (piscine, animaux, atelier)
- Vous n'oubliez pas les invités occasionnels
- Vous tenez compte des saisons (jardin été)

### Le résultat est cohérent avec la moyenne nationale (148 L/pers/jour)

**Bon signe**. Cela veut dire que vos paramètres reflètent une consommation typique. Le calculateur est utile pour :
- Identifier les postes les plus gourmands
- Simuler des améliorations
- Dimensionner une cuve d'autonomie

## Tableau "Votre cas → Ajustements"

| Votre situation | Ajustement à faire |
|-----------------|-------------------|
| Foyer multigénérationnel (grands-parents) | +20-40% sur le total (les personnes âgées en résidence montent à 240-310 L) |
| Foyer avec adolescents | +10-20% (douches longues fréquentes) |
| Foyer en région PACA / Occitanie | +30-50% (climat, jardin, arrosage) |
| Foyer en région Nord / Hauts-de-France | -20-30% (climat tempéré, moins d'arrosage) |
| Maison passive avec récupération pluie complète | -30-40% sur "eau potable" |
| Famille avec enfants en bas âge | +15% (lavages plus fréquents) |
| Travail à domicile | +10-15% (plus de temps à la maison) |
| Animaux (chiens) | +5-10 L/jour par chien moyen |
| Piscine privée | +30-50 L/jour selon taille (évaporation + nettoyage) |

## Limites de cet outil

### Ce qu'il ne couvre pas précisément

- **Saisonnalité jardin** : le calcul utilise un ratio constant, mais en réalité l'arrosage est concentré sur 5-6 mois
- **Variations hebdomadaires** : weekend vs semaine, présence à domicile
- **Habitudes individuelles** : certains prennent 2 douches par jour, d'autres 3 par semaine
- **Climat régional fin** : les ratios sont nationaux
- **Consommation invisible** : fuites, évaporation, gel
- **Eau virtuelle** : empreinte cachée (alimentation, vêtements, etc.) qui représente ~6 000 L/jour selon ADEME, mais hors scope du calculateur

### Ce qu'il faut compléter

- Mesurer votre consommation réelle au compteur sur quelques mois
- Identifier les fuites éventuelles (relevé du compteur la nuit)
- Adapter les saisons pour le jardin
- Consulter un installateur pour le dimensionnement final d'une cuve

## Évolutions prévues du calculateur

- Module saisonnier (variation conso jardin selon mois)
- Module économies (combien gagner avec WC double débit + douche éco)
- Module récupération eau pluie (combien votre toit peut récupérer)
- Comparateur d'équipements (impact ROI d'un changement)
- Module climat régional fin

Si vous avez des suggestions, contactez-nous via [le formulaire du Lab](/contact/).

---

**Dernière mise à jour** : Mai 2026
**Sources principales** : CIEAU (2024), ADEME, SISPEA (rapport 2025 données 2023), notre-environnement.gouv.fr, INSEE, BUT, Selectra, Hydrao, Geberit
