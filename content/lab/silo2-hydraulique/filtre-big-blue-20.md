---
title: "Porte-filtre Big Blue 20 pouces : Dimensionner la filtration sédiment et charbon."
linkTitle: "Filtre Big Blue 20""
slug: "lab_silo2_filtre-big-blue-20"
title_tag: "Filtre eau Big Blue 20 pouces : Guide débit et charbon"
meta_description: "Dimensionnement porte-filtre Big Blue 20\". Choix cartouche sédiment vs charbon actif, calcul perte de charge et débit maximal sans cavitation."
date: "2026-05-11"
signataire: "Frank Vasseur"
silo: 2
mot_cle: "filtre a eau big blue 20 pouces charbon actif"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Un filtre à eau Big Blue 20 pouces charbon actif sous-dimensionné peut chuter le débit de 4 m³/h (BWT/Pentek, 2022-2023) à 0,15 m³/h (Modélisation hydrodynamique, 2026), créant une cavitation sur le surpresseur. Le dimensionnement correct impose une analyse de la perte de charge cumulée et du seuil de filtration en microns, sous peine de remplacer la pompe avant les cartouches.

## Filtration sédiment : Le seuil de 5 µm comme standard de protection

L'objectif du premier porte-filtre est l'abattement des Matières En Suspension (MES). Il s'agit d'une barrière physique protégeant les équipements en aval (adoucisseur, stérilisateur UV, osmoseur) et la cartouche de charbon actif. Le paramètre critique est le seuil de filtration, exprimé en microns (µm).

Un seuil trop élevé (> 25 µm) laisse passer les particules fines qui colmateront prématurément la cartouche charbon. Un seuil trop bas (< 5 µm) sur une eau chargée engendre une perte de charge rapide et un remplacement excessif des consommables. L'architecture standard pour une eau de forage ou de réseau est une cartouche de 5 µm.

| Seuil de filtration | Application typique | Contaminants ciblés |
|--------------------|-----------------------|---------------------|
| 25 µm à 50 µm | Pré-filtration eau de pluie brute | Sables, limons grossiers |
| 5 µm à 10 µm | Standard pour eau de forage / réseau | Particules fines, rouille, argile |
| 1 µm | Protection osmoseur | Turbidité, protection membranaire |

Les cartouches plissées offrent une surface de contact supérieure aux cartouches bobinées, ce qui se traduit par une durée de vie prolongée avant colmatage pour un même seuil de filtration.

## Charbon actif en bloc (CTO) : Adsorption du chlore à >95% et limites

Le second porte-filtre contient une cartouche de charbon actif. Son mode d'action n'est pas une filtration mécanique mais une adsorption. Les micropores du charbon piègent les molécules responsables du goût, des odeurs et certains composés chimiques. Le format "bloc" (CTO - Chlorine, Taste, Odor) est privilégié par rapport au "granulé" (GAC) pour sa densité, qui évite la création de chemins préférentiels pour l'eau (phénomène de "channeling").

Son efficacité est ciblée. Il excelle sur le chlore libre, les résidus de pesticides et certains Composés Organiques Volatils (COV). Il n'a aucun effet sur les nitrates, le calcaire (TH), les métaux lourds ou les contaminants microbiologiques. Le données techniques disponibles confirme que l'élimination des nitrates requiert des technologies membranaires comme l'[LIEN INTERNE : Potabilisation de forage (ERP & Domestique) : Norme UV-C et Osmose.].

| Type de cartouche | Efficacité Chlore | Rétention sédiments | Risque de relargage |
|-------------------|-------------------|---------------------|--------------------|
| Charbon Actif Bloc (CTO) | > 95% | Oui (5 µm typique) | Faible |
| Charbon Actif Granulé (GAC) | 90% | Non | Élevé en fin de vie |

## Débit nominal vs perte de charge : L'impact sur 3 m³/h

Le dimensionnement hydraulique constitue un point de défaillance critique des installations. Un porte-filtre Big Blue 20 pouces est une restriction sur la ligne d'eau principale. Cette restriction génère une perte de charge (exprimée en bar), qui s'additionne à chaque élément de la filière.

Une cartouche neuve présente une perte de charge initiale. Au fur età mesure de son colmatage, cette valeur augmente jusqu'à brider le débit global du système. Le calcul doit garantir que même avec des filtres en fin de vie, le débit reste suffisant pour les appareils en aval.

| État de la cartouche | Perte de charge pour 3 m³/h | Source | Date de validité |
|----------------------|-----------------------------|--------|------------------|
| Sédiment 5 µm (neuve) | 0,07 bar (BWT, 2016) | - | - |
| Charbon CTO (neuve) | ~1,63 bar (Calcul ingénierie, 2026) | - | - |
| Sédiment 5 µm (colmatée) | 1,0 bar (BWT, 2016) | - | - |

Le débit maximal annoncé par les constructeurs est une valeur théorique sans perte de charge. Pour un débit de 3 m³/h, la perte de charge cumulée des deux filtres neufs peut atteindre 1,84 bar (Calcul ingénierie, 2026).

## Architecture de montage : Les 3 vannes et 2 manomètres obligatoires

Une installation correcte n'est pas une option. Elle conditionne la maintenance et le diagnostic. Le montage en série des deux porte-filtres (sédiment en premier, charbon en second) doit impérativement intégrer un by-pass et des points de mesure.

Le synoptique correct est le suivant :
1.  **Vanne d'arrêt amont :** Pour isoler complètement la filière de filtration.
2.  **Manomètre N°1 :** Mesure de la pression d'entrée.
3.  **Porte-filtre N°1 (Sédiment).**
4.  **Porte-filtre N°2 (Charbon).**
5.  **Manomètre N°2 :** Mesure de la pression de sortie.
6.  **Vanne d'arrêt aval :** Pour consigner la sortie.
7.  **Vanne de by-pass :** Installée en parallèle des filtres, elle permet de continuer à alimenter le logement en eau non-filtrée pendant une opération de maintenance.

L'absence de manomètres rend impossible le suivi du colmatage. L'absence de by-pass impose une coupure d'eau générale pour un simple changement de cartouche.

## Seuil de colmatage : Remplacement à 0,8 bar de pression différentielle

Le remplacement des cartouches ne se décide pas sur un calendrier mais sur une mesure de performance. La différence de pression (delta-P) entre le manomètre N°1 (amont) et le manomètre N°2 (aval) est l'indicateur unique de l'état de colmatage.

Une fois l'installation mise en service avec des cartouches neuves, relever le delta-P initial à un débit standard (ex: 0,2 bar). Le seuil de remplacement est atteint lorsque ce delta-P augmente de 0,6 à 0,8 bar par rapport à la valeur initiale. Attendre un delta-P supérieur à 1 bar met la pompe du surpresseur sous contrainte anormale.

Pour une cartouche charbon, un remplacement tous les 12 mois est une base de travail pour éviter le développement bactérien, même si le colmatage n'est pas atteint.

---
### Expertises Croisées
- **Hydraulique & Eau :** [LIEN INTERNE : Pompe immergée à 50m : Calculer la HMT sans griller le moteur.]
- **Thermique & Habitat :** [LIEN INTERNE : PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).]
- **Infrastructure :** [LIEN INTERNE : Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.]

### FAQ : Porte-filtre Big Blue 20 pouces
<details>
<summary>Quelle cartouche Big Blue 20 pouces pour l'eau de pluie ?</summary>
Pour une eau de pluie, la configuration standard est une pré-filtration à 50 µm en amont de la cuve, suivie d'un train de filtration en sortie de pompe avec sédiment 10 µm, puis charbon actif bloc 5 µm, et enfin un stérilisateur UV-C.
</details>
<details>
<summary>Quand changer un filtre à charbon actif ?</summary>
Le remplacement est dicté par deux facteurs. Le premier est le colmatage, indiqué par une chute de pression de 0,8 bar. Le second est la saturation : même non colmatée, une cartouche doit être changée tous les 12 mois maximum pour prévenir tout risque de prolifération bactérienne.
</details>
<details>
<summary>Peut-on mettre un filtre Big Blue avant un surpresseur ?</summary>
Non. Un filtre se place toujours après la pompe ou le surpresseur. Placer un filtre en aspiration crée une dépression qui peut provoquer la cavitation de la pompe et endommager le moteur. La seule exception est une crépine de pied de puits.
</details>
<details>
<summary>Quelle est la perte de débit avec un filtre Big Blue 20 pouces ?</summary>
Un filtre ne réduit pas le débit, il augmente la perte de charge. Pour un débit donné, la pression en sortie sera plus faible. Si la pression disponible est déjà faible, le débit final au point d'usage sera réduit. Une installation correcte avec des filtres propres ne doit pas générer plus de 1,0 bar (BWT, 2016) de perte de charge à 3 m³/h.
</details>

> Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*