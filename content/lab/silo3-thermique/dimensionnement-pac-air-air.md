---
title: "Dimensionnement PAC Air-Air : La formule exacte (Volume x Delta T)."
linkTitle: "Dimensionnement PAC air-air"
slug: "lab_silo3_dimensionnement-pac-air-air"
title_tag: "Dimensionnement PAC air-air : La formule Volume x Delta T"
meta_description: "Calculez la puissance PAC en BTU. Formule exacte pour éviter surconsommation et usure prématurée."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 3
mot_cle: "dimensionnement pac air air m2 btu"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Un sous-dimensionnement de 20% sur une PAC air-air force l'appoint électrique et peut augmenter significativement la facture en hiver (ADEME/Hellowatt/La Maison des Energies/Cozynergy, 2026). Le correct dimensionnement d'une PAC air-air en m2 ou BTU ne dépend pas d'un ratio empirique mais du calcul des déperditions thermiques : Volume (m³) x Coefficient d'isolation (G) x Delta de Température (°C). Ignorer cette formule invalide le retour sur investissement.

## La formule de calcul des déperditions : V x G x ΔT

Le calcul de puissance d'une pompe à chaleur air-air se base sur la compensation des déperditions thermiques de l'habitat. La formule à appliquer est `P = V x G x ΔT`.

*   **P** = Puissance requise en Watts (W) pour maintenir la température de consigne par la température de base extérieure.
*   **V** = Volume total des pièces à chauffer, exprimé en mètres cubes (m³).
*   **G** = Coefficient d'isolation globale du logement, en W/m³.°C.
*   **ΔT** (Delta T) = Différence entre la température intérieure de consigne et la température extérieure de base de la zone géographique, en degrés Celsius (°C).

Toute approche basée sur une surface en m² est une simplification qui ignore la hauteur sous plafond et mène à des erreurs de dimensionnement.

## Étape 1 : Calcul du Volume à chauffer (en m³)

La première variable est le volume, non la surface. Le calcul est une simple multiplication de la surface au sol par la hauteur sous plafond.

Pour un logement de 120 m² avec une hauteur sous plafond standard de 2,50 m :
`Volume (V) = 120 m² x 2,50 m = 300 m³`

Cette valeur de 300 m³ est la base de travail. Un calcul en m² aurait ignoré 600 m³ d'air à traiter dans une maison avec une hauteur de 5 m (type mezzanine), faussant intégralement le résultat.

## Étape 2 : Définir le coefficient d'isolation G (W/m³.°C)

Le coefficient G quantifie la performance de l'enveloppe du bâtiment. Il dépend de l'année de construction et des normes thermiques respectées. Une valeur G basse indique une bonne isolation.

| Norme d'isolation & Type d'habitat | Coefficient G (W/m³.°C) | Source & Date |
|------------------------------------|---------------------------|---------------|
| Logement non isolé (avant 1974) | 1,8 à 2,0 | RT 2005/RT 2012 (CSTB, 2005-2012) |
| Logement isolé (RT 2005) | 1,1 | RT 2005/RT 2012 (CSTB, 2005-2012) |
| Logement très bien isolé (RT 2012) | 0,7 | RT 2005/RT 2012 (CSTB, 2005-2012) |
| Logement passif (RE 2020) | 0,4 | (RE2020/ADEME, 2026) |

Le non-respect de l'étanchéité à l'air, mesurée par infiltrométrie (`Blower Door Test`), peut majorer ce coefficient de manière significative en conditions réelles (RE2020/SOLIDEO, 2024). La norme RE2020 impose un seuil de fuite inférieur à 0.6 vol·h⁻¹ (SOLIDEO, 2024).

## Étape 3 : Déterminer le ΔT (°C) de votre zone climatique

Le ΔT est l'écart entre la température de confort souhaitée (généralement 20°C ou 21°C) et la température de base extérieure, qui est la température la plus froide statistiquement atteinte sur 5 jours dans une région donnée.

`ΔT = T° confort - T° de base extérieure`

Les températures de base varient fortement sur le territoire.

| Zone Climatique | Ville de référence | Température de base | ΔT (pour 21°C confort) |
|-----------------|--------------------|---------------------|--------------------------|
| Zone A (Sud-Est) | Marseille | -3,5°C | 24,5°C |
| Zone B (Ouest) | Bordeaux | -6,5°C | 27,5°C |
| Zone C (Centre) | Lyon | -9,5°C | 30,5°C |
| Zone D (Nord) | Lille | -9,5°C | 30,5°C |
| Zone E (Est) | Strasbourg | -9,5°C | 30,5°C |

*Températures de base : (NF EN 12831, CAP RENOV, 2021)*

Le choix de la température de confort est un paramètre engageant. Chaque degré supplémentaire augmente la consommation électrique de 7 % (Primeo/ADEME/EDF, 2025).

## Calcul final (Watts) et conversion en BTU/h

Avec les données collectées, le calcul de la puissance (P) peut être finalisé.
Exemple pour une maison de 300 m³ (120 m² x 2,5m), norme RT 2012 (G = 0,7), située à Lyon (ΔT = 30°C) :

`P = 300 m³ x 0,7 W/m³.°C x 30°C = 6300 W`

La puissance nécessaire est de 6,3 kW. Cette valeur correspond à la puissance calorifique que la PAC doit fournir à la température de base de -9°C pour maintenir 21°C à l'intérieur, sans recours à un appoint.

Pour le **dimensionnement de la PAC air-air en BTU** (British Thermal Unit), la conversion est directe :
`1 Watt ≈ 3.41 BTU/h`
`6300 W x 3.41 = 21 483 BTU/h`

Il faudra donc sélectionner un équipement capable de fournir une puissance nominale de 6,3 kW ou 21 500 BTU/h.

## Le risque du sous-dimensionnement : une perte de COP de 100%

Sous-dimensionner une PAC en se basant sur une température extérieure moyenne est une erreur critique. Par grand froid (ex: -15°C), une machine sous-dimensionnée ne parvient plus à atteindre le point de consigne.

Elle déclenche alors son appoint électrique, généralement une résistance. Le Coefficient de Performance (COP) du système s'effondre à 1,0, contre un COP nominal de 4,2 (A7/W20, EN 14825 — ADEME/PAC Expertise/Eurovent, 2026) ou un SCOP saisonnier de 2,8 à 3,0 en zone H1 (ADEME/Hellowatt, 2024). La consommation électrique est alors multipliée par trois pour un confort dégradé.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Dimensionnement PAC Air-Air

**Comment calculer la puissance d'une PAC air-air pour 100m² ?**
Le calcul ne se fait pas en m² mais en m³. Multipliez 100 m² par votre hauteur sous plafond (ex: 2,5m) pour obtenir le volume (250 m³). Appliquez ensuite la formule P = Volume x G (isolation) x ΔT (différence de température) pour obtenir les Watts nécessaires.

**C'est quoi les BTU pour une PAC ou une climatisation ?**
Le BTU (British Thermal Unit) est une unité d'énergie. Pour les PAC, on utilise les BTU/h, qui mesurent la puissance de chauffage ou de refroidissement. 1 Watt équivaut à environ 3.41 BTU/h. Un appareil de 3,5 kW (3500 W) a une puissance d'environ 12 000 BTU/h.

**Quelle puissance de PAC pour une maison mal isolée ?**
Pour une maison mal isolée (avant 1974), le coefficient G est élevé (ex: 1,8 W/m³.°C). Pour un volume de 300 m³ à Lyon (ΔT 30°C), le besoin est de `300 x 1,8 x 30 = 16 200 W` soit 16,2 kW. L'isolation est le premier chantier à adresser avant d'installer une PAC.

**Faut-il surdimensionner une PAC air-air ?**
Non. Une PAC surdimensionnée fonctionnera par cycles courts et répétés ("short cycling"), ce qui provoque une usure prématurée du compresseur, une surconsommation électrique au démarrage et un mauvais contrôle de l'hygrométrie. Le dimensionnement doit être exact.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*