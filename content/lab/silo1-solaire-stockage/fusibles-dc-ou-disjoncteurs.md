---
title: "Fusibles DC ou Disjoncteurs sur vos strings ? La norme l'exige."
linkTitle: "Fusibles DC vs Disjoncteurs"
slug: "lab_silo1_fusibles-dc-ou-disjoncteurs"
title_tag: "Protection DC PV : Fusible ou Disjoncteur ? Norme UTE"
meta_description: "Choix entre fusibles gPV et disjoncteurs DC pour strings PV. Calibre et conformité UTE C 15-712-1."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "protection dc string fusible ou disjoncteur"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

La norme UTE C 15-712-1 impose une protection DC par string, fusible ou disjoncteur, contre les courants de retour dès que 3 chaînes ou plus sont en parallèle. Le calibre se calcule sur le courant de court-circuit (Isc) du panneau, majoré d'un facteur de sécurité de 1,25. Une tension d'isolement supérieure à la tension à vide (Voc) du string est non-négociable.

## Le risque n'est pas la surproduction, mais le courant de retour > 2A

La protection en courant continu sur un string photovoltaïque ne vise pas à sectionner en cas de production solaire excessive. Elle a une seule fonction : isoler une chaîne défaillante pour l'empêcher de recevoir du courant des chaînes saines.

En cas d'ombrage partiel sévère ou de court-circuit interne d'une cellule, un string peut voir sa tension chuter drastiquement. S'il est en parallèle avec au moins deux autres strings, le différentiel de tension s'inverse. La chaîne défaillante ne se comporte plus en générateur mais en récepteur. Elle sert de charge pour les autres, qui y injectent un courant de retour.

Ce courant inverse, non maîtrisé, provoque une dissipation par effet Joule dans les cellules du module défaillant, entraînant un risque d'incendie avéré. Le seuil de déclenchement de la protection est donc calibré pour couper avant que ce courant de retour n'atteigne un niveau destructeur.

## UTE C 15-712-1 : Le cadre réglementaire de la protection DC

Le guide UTE C 15-712-1, qui fait office de référence pour les installations photovoltaïques raccordées au réseau ou non, est formel. La protection contre les surintensités est obligatoire dans le coffret de sectionnement DC si le nombre de strings (N) en parallèle est supérieur ou égal à 3.

En dessous de 3 strings, la norme considère que le courant de retour potentiel (limité à (N-1) x Isc) ne peut excéder le courant inverse maximal supporté par un module (I<sub>R</sub>), une donnée constructeur. Au-delà de ce seuil de 3 strings, l'installation d'une protection individuelle par chaîne devient une exigence non dérogatoire pour l'obtention du Consuel.

Le dispositif, qu'il s'agisse d'un fusible ou d'un disjoncteur, doit être installé sur le pôle positif et le pôle négatif de chaque string, sauf si l'un des pôles est mis à la terre (régime de neutre spécifique, rare en résidentiel).

## Fusible gPV vs Disjoncteur DC : Le comparatif terrain

Le choix entre la protection dc par fusible ou disjoncteur est un arbitrage technique et financier. Les deux technologies répondent à la norme, mais leur comportement sur le terrain et leur maintenance diffèrent. Le fusible est un consommable. Le disjoncteur est un équipement.

| Paramètre | Fusible cylindrique gPV 10x38 | Disjoncteur modulaire DC | Source | Date de validité |
|---|---|---|---|---|
| **Coût unitaire** | entre 8,00 et 10,00 € HT (Sonepar/Rexel, 2023) | 35,00 € HT (ABB S202MUC, Rexel, 2023) | Sonepar/Rexel, 2023 | Avril 2026 |
| **Pouvoir de coupure (PdC)** | 10 kA (IEC 60269-6) | 6 kA (IEC 60947-2) | IEC 60269-6 / IEC 60947-2 | Avril 2026 |
| **Réarmement** | Impossible (remplacement) | Manuel (immédiat) | Constat terrain | Avril 2026 |
| **Usure** | Aucune (destruction franche) | Mécanique (fatigue après défauts) | IEC 60947-2 (Norme appareillage BT) | Avril 2026 |
| **Encombrement (par string)** | 1 module DIN (porte-fusible) | 2 modules DIN | Constat terrain | Avril 2026 |

Le fusible de type gPV ("general Purpose for Photovoltaic") est conçu pour couper des courants faibles (typiquement 1,25 à 1,5 fois son calibre) et résister aux cycles thermiques jour/nuit sans dégradation. Son pouvoir de coupure élevé en fait une sécurité passive absolue. Le disjoncteur DC, plus onéreux et plus volumineux, offre l'avantage du réarmement, utile lors de phases de diagnostic.

## Calcul du calibre : La formule 1,25 x Isc expliquée

Le dimensionnement du calibre de la protection (I<sub>n</sub>) ne dépend pas de la puissance (Wc) du panneau, mais de son courant de court-circuit (Isc), la valeur la plus élevée qu'il puisse générer.

La règle de calcul imposée par la norme est la suivante :
**I<sub>n</sub> ≥ 1,25 x I<sub>sc</sub>**

Le facteur de 1,25 sert de marge de sécurité pour encaisser les pics d'irradiance (effet de bord de nuage) sans déclenchement intempestif.

**Exemple de calcul pour un string :**
*   Panneau de 400 Wp
*   Isc (donnée fiche technique STC) : 10,4 A
*   Calcul : 10,4 A x 1,25 = 13,0 A

Le calibre normalisé immédiatement supérieur est **16 A**. Il faut donc sélectionner un fusible ou un disjoncteur de 16 A. Pour la tension, la règle est similaire : la tension d'isolement du dispositif doit être supérieure à la tension à vide (Voc) maximale du string, elle-même majorée par un facteur de sécurité thermique de 1,15 (IEC 62548 / UTE C 15-712-1) pour tenir compte du froid.

## Pouvoir de coupure (kA) : La sécurité anti-arc électrique

Le pouvoir de coupure (PdC) est le paramètre le plus critique pour la sécurité. Il représente le courant de court-circuit maximal que le dispositif peut interrompre sans se détruire ou créer un arc électrique persistant.

Un arc électrique en courant continu est extrêmement difficile à éteindre. Contrairement à l'alternatif qui passe par zéro 100 fois par seconde, le DC maintient un plasma conducteur qui peut faire fondre le plastique du coffret et déclencher un incendie.

Un fusible gPV standard présente un pouvoir de coupure élevé de 10 kA (IEC 60269-6), ce qui est amplement suffisant pour un court-circuit franc sur une installation résidentielle. Le disjoncteur doit impérativement être un modèle spécifique "DC", conçu avec des chambres de coupure d'arc (soufflage magnétique) adaptées. L'utilisation d'un [Disjoncteur Courbe D ou C ? Le choix vital pour les gros compresseurs.](/lab_silo4_disjoncteur-courbe-d-vs-c/) de type AC est formellement interdite et dangereuse.

## Intégration dans le coffret DC : Schéma unifilaire et sectionneur

Les protections par fusibles ou disjoncteurs s'intègrent dans le coffret de sectionnement DC, placé entre les panneaux et l'onduleur. Ce coffret contient obligatoirement :

1.  **Un sectionneur général DC :** Permet de consigner l'installation pour intervenir sur l'onduleur en toute sécurité.
2.  **Les protections de string :** Un porte-fusible ou un disjoncteur par chaîne.
3.  **Un parafoudre DC :** Pour la protection contre les surtensions. Le choix entre [Consuel Photovoltaïque : Faut-il un parafoudre Type 1 ou Type 2 ?](/lab_silo1_consuel-parafoudre-t1-t2/) dépend de la présence d'un paratonnerre et de la zone géographique.

Le câblage doit être réalisé avec du câble solaire double isolation (H1Z2Z2-K) et le serrage des connexions doit être fait au couple préconisé par le fabricant pour éviter tout point d'échauffement. Une mauvaise connexion est une source de panne et d'incendie aussi sûre qu'un mauvais [Section de câble batterie 48V : Ne jouez pas avec l'incendie (Abaques).](/lab_silo1_section-cable-batterie-48v/).


---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Protection DC strings

**Un fusible DC est-il obligatoire pour 2 strings de panneaux ?**
Non. La norme française UTE C 15-712-1 rend la protection individuelle par string obligatoire à partir de 3 chaînes en parallèle. En dessous, le courant de retour maximal en cas de défaut est jugé non destructeur pour les modules.

**Quel calibre de fusible pour un panneau solaire 500W ?**
Le calibre ne dépend pas de la puissance (Wc) mais du courant de court-circuit (Isc) indiqué sur la fiche technique du panneau. La formule est : Calibre ≥ 1,25 x Isc. Pour un panneau avec un Isc de X A, le calcul donne 1,25 × X A. Le calibre normalisé supérieur est alors sélectionné.

**Puis-je utiliser un disjoncteur AC pour protéger un circuit DC ?**
Interdiction formelle. Un disjoncteur AC est conçu pour couper un courant qui s'annule naturellement 100 fois par seconde. En DC, l'arc électrique est continu. Un disjoncteur AC ne parviendra pas à l'éteindre et sera détruit, avec un risque d'incendie majeur dans le coffret.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*