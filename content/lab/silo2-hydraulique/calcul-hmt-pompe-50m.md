---
title: "Pompe immergée à 50m : Calculer la HMT sans griller le moteur."
linkTitle: "Calcul HMT pompe 50m"
slug: "lab_silo2_calcul-hmt-pompe-50m"
title_tag: "Calcul HMT pompe immergée forage 50m : Guide terrain"
meta_description: "Calculez la Hauteur Manométrique Totale (HMT) pour pompe 50m. Évitez la surchauffe et la cavitation."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 2
mot_cle: "calcul hmt pompe immergee forage 50m"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Le calcul HMT pour une pompe immergée en forage de 50m additionne trois charges : la hauteur géométrique (50m + dénivelé au point d'usage), la pression de service requise (ex: 3 bars = 30m), et les pertes de charge (friction dans les tuyaux). Ignorer les pertes de charge conduit à un sous-dimensionnement, une surchauffe moteur et une destruction par cavitation.

## HMT : Les 3 composantes du calcul pour 50m de profondeur

La Hauteur Manométrique Totale (HMT) représente l'énergie totale que la pompe doit fournir au fluide. Elle est la somme de trois contraintes physiques distinctes. Le calcul ne tolère aucune approximation. Un sous-dimensionnement de la HMT se traduit par un débit insuffisant au point d'usage ou, dans le pire des cas, par la défaillance prématurée du moteur.

L'équation constitutive est la suivante :
`HMT (en mètres) = Hauteur géométrique + Pression de service + Pertes de charge`

Chaque composant doit être évalué avec précision pour sélectionner une pompe dont le point de fonctionnement correspond aux besoins réels de l'installation.

## Hauteur géométrique : L'erreur classique des 50 mètres

La hauteur géométrique est la différence d'altitude totale entre le niveau d'eau dynamique dans le forage et le point de distribution le plus élevé. Une erreur courante consiste à ne considérer que la profondeur du forage.

**Décomposition du calcul :**
1.  **Hauteur d'aspiration :** Profondeur du forage jusqu'au niveau de l'eau. Pour un forage à 50m, cette valeur constitue la base.
2.  **Hauteur de refoulement :** Dénivelé vertical entre la surface du sol et le point d'eau le plus haut (ex: douche au 1er étage, à 4m du sol).

Calcul pour un forage de 50m avec un point d'usage à 4m de hauteur :
*Hauteur géométrique = 50 m + 4 m = 54 m*

Cette valeur de 54 mètres est la charge statique minimale que la pompe doit vaincre avant même de fournir de la pression.

## Pertes de charge : 1,2 bar de perte pour 100m de PEHD 32mm

Les pertes de charge représentent l'énergie dissipée par le frottement de l'eau contre les parois des tuyaux et les accidents de parcours (coudes, vannes, clapets). Elles dépendent du débit, du diamètre et de la longueur de la tuyauterie. L'équation de Darcy-Weisbach modélise ce phénomène.

Utiliser un diamètre de tuyau trop faible pour réduire les coûts d'installation est une erreur technique grave. Cela bride la pompe, augmente les pertes de charge et la consommation électrique.

Le tableau suivant illustre l'impact du diamètre du tuyau PEHD sur 100 mètres pour un débit standard de 3 m³/h.

| Diamètre Tuyau (PEHD) | Pertes de charge (en mCE) | Pression perdue (en bar) | Source | Date de validité |
|-----------------------|---------------------------|-------------------------|--------|-----------------|
| 25 mm (1") | 27,2 m | 2,7 bar | Calcul Darcy-Weisbach (NF EN 805, 2000) | Avril 2026 |
| 32 mm (1"1/4) | 12,1 m | 1,2 bar | Calcul Darcy-Weisbach (NF EN 805, 2000) | Avril 2026 |
| 40 mm (1"1/2) | 5,5 m | 0,5 bar | Calcul Darcy-Weisbach (NF EN 805, 2000) | Avril 2026 |

Le choix d'un PEHD de 32 mm au lieu de 25 mm divise les pertes de charge par deux. Pour une installation à 50m de profondeur, cette différence est déterminante. Un [Clapet anti-retour : Pourquoi le modèle laiton à battant est obligatoire.](/lab_silo2_clapet-anti-retour-laiton/) de qualité est également un point de contrôle essentiel.

## Pression de service : 3 bars minimum pour un usage domestique

La pression de service est la pression résiduelle souhaitée au point d'usage. Pour un confort domestique standard, une pression de 3 bars est un minimum fonctionnel.

La conversion en mètres de colonne d'eau (mCE) est directe :
*1 bar = 10,2 mCE*

Pour une pression de service de 3 bars, la pompe doit donc fournir une charge supplémentaire de :
*Pression de service = 3 bars x 10,2 = 30,6 m*

### Calcul final de la HMT à 50m

En reprenant l'exemple d'un forage à 50m, un point d'usage à 4m, une longueur de tuyau de 100m en PEHD 32mm et une pression de service de 3 bars :

1.  **Hauteur géométrique :** 50 m + 4 m = 54 m
2.  **Pertes de charge :** 12,1 m (selon tableau)
3.  **Pression de service :** 30,6 m

*HMT = 54 + 12,1 + 30,6 = 96,7 mètres*

La pompe immergée devra être capable de fournir un débit de 3 m³/h à une HMT de 97 mètres.

## Cavitation et NPSH : Le risque à grande profondeur

La cavitation est la vaporisation de l'eau à basse pression ("ébullition à froid"), suivie de l'implosion violente des bulles de vapeur. Ce phénomène érode les turbines et détruit la pompe. Il produit un bruit caractéristique de passage de graviers.

Le NPSH (Net Positive Suction Head) est la marge de sécurité contre la cavitation.
*   **NPSHd (disponible) :** dépend de l'installation (pression atmosphérique, hauteur d'aspiration).
*   **NPSHr (requis) :** dépend de la pompe (donnée constructeur).

La règle impérative est : NPSHd > NPSHr.

Pour une pompe immergée, l'eau exerce une pression positive sur l'aspiration de la pompe (la pompe est "en charge"). Le risque de cavitation est donc faible, sauf en cas de sous-dimensionnement extrême du tuyau de refoulement qui créerait une dépression anormale.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Clapet anti-retour : Pourquoi le modèle laiton à battant est obligatoire.](/lab_silo2_clapet-anti-retour-laiton/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Calcul HMT pompe immergée

**C'est quoi la HMT d'une pompe ?**
La HMT (Hauteur Manométrique Totale) est la pression totale qu'une pompe doit fournir. Elle se mesure en mètres et additionne la hauteur physique à remonter, la pression désirée à la sortie, et les frottements dans les tuyaux.

**Quelle section de tuyau pour une pompe immergée 50m ?**
Pour un débit domestique (2-4 m³/h), un tuyau en polyéthylène (PEHD) de 32 mm de diamètre est le minimum technique recommandé. Un diamètre inférieur, comme 25 mm, génère des pertes de charge excessives, ce qui fatigue le moteur et réduit le débit.

**Ma pompe immergée surchauffe, est-ce la HMT ?**
Un mauvais calcul de la HMT est une cause principale de surchauffe. Si la HMT réelle est supérieure à celle pour laquelle la pompe est conçue, le moteur force en permanence pour atteindre un point de fonctionnement hors de sa courbe de rendement, ce qui entraîne une surchauffe et une usure accélérée.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*