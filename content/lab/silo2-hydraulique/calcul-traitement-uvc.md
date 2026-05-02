---
title: "Stérilisateur UV-C : Calculer le débit max pour garantir 40 mJ/cm²."
linkTitle: "Calcul UV-C 40 mJ/cm²"
slug: "lab_silo2_calcul-traitement-uvc"
title_tag: "Calcul traitement UV-C : Garantir le dosage 40 mJ/cm²"
meta_description: "Dimensionnement stérilisateur UV-C. Calcul du débit max (m3/h) pour garantir l'effet germicide."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 2
mot_cle: "traitement uv c debit m3/h dosage millijoules"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Le dosage UV-C réglementaire pour la potabilisation d'eau de forage est fixé à 40 millijoules par centimètre carré (mJ/cm²). Le traitement UV-C et son débit en m3/h sont directement liés à la puissance de la lampe et à la turbidité de l'eau. Dépasser le débit nominal annule l'effet germicide et expose le réseau à une contamination microbiologique.

## Dosage UV-C : La norme de 40 mJ/cm² pour l'inactivation de l'ADN

La désinfection par ultraviolets de type C (UV-C) repose sur une action physique. Le rayonnement à une longueur d'onde de 253,7 nanomètres irradie l'eau et pénètre le noyau des micro-organismes (bactéries, virus, protozoaires). Cette exposition modifie la structure de leur ADN et ARN, les rendant incapables de se répliquer et donc inoffensifs.

Le seuil d'efficacité pour la potabilisation d'une eau brute est une dose germicide de 40 mJ/cm². Cette valeur garantit l'inactivation de 99,99% des pathogènes résistants comme *Escherichia coli*, dont la présence est un indicateur de contamination fécale (seuil réglementaire à 0 UFC/100 mL, Code de la santé publique, 2021). En deçà de ce dosage, l'eau n'est pas considérée comme traitée.

## Calcul du débit (m³/h) : La relation entre puissance (W) et transmittance (%)

Le débit maximal admissible dans un réacteur UV-C est une fonction directe de trois paramètres : la puissance de la lampe, la dose cible et la clarté de l'eau (transmittance). La formule de dimensionnement est la suivante :

`Débit (m³/h) = (Puissance UV-C en W * 3.6) / (Dose en mJ/cm² * Surface en m²)`

En pratique, les constructeurs fournissent des abaques qui intègrent ces variables. Le paramètre critique est la transmittance UV (UVT), qui mesure le pourcentage de lumière UV-C traversant l'eau sur 1 cm. Une eau claire aura une UVT élevée (ex: 98%), une eau chargée en sédiments ou en fer dissous aura une UVT faible.

Un traitement UV-C n'est viable qu'avec une eau préalablement filtrée. Toute turbidité crée des "zones d'ombre" protégeant les bactéries du rayonnement. Une filtration sédimentaire à 5 microns en amont est un prérequis technique non négociable.

| Paramètre | Eau brute (forage) | Eau filtrée (5 µm) | Impact sur le débit |
|---|---|---|---|
| Transmittance UVT | 75% | 95% | Débit max. multiplié par 2,5 (Viqua/Atlantic UV, 2020-2021) |
| Turbidité | > 5 NTU | < 1 NTU | Traitement UV-C non conforme |

*Pour chaque baisse de 10% de l'UVT, le débit maximal admissible doit être réduit d'environ 36 à 38% pour maintenir la dose létale de 40 mJ/cm² (Viqua/Atlantic UV, 2021).*

Pour un réacteur équipé d'une lampe de 55 W, le débit maximal pour atteindre 40 mJ/cm² avec une UVT de 95% doit être calculé selon les abaques du constructeur (NF EN 14897, 2006). Si le débit de la pompe dépasse cette valeur, le temps d'exposition diminue et la dose germicide délivrée chute sous le seuil de conformité.

## Les 3 facteurs de déclassement terrain

La performance théorique d'un stérilisateur UV-C se dégrade en conditions réelles. Trois points de vigilance conditionnent la pérennité du traitement.

**1. Le colmatage de la gaine quartz :** La lampe UV-C est isolée de l'eau par une gaine en quartz. Le calcaire, le fer et le manganèse peuvent précipiter à sa surface, créant un film opaque qui bloque le rayonnement. Un nettoyage trimestriel est impératif.

**2. La turbidité en amont :** Un [Porte-filtre Big Blue 20 pouces : Dimensionner la filtration sédiment et charbon.](/lab_silo2_filtre-big-blue-20/) sous-dimensionné ou colmaté laisse passer des particules. Ces dernières protègent les pathogènes, rendant le traitement inefficace même avec une lampe neuve.

**3. Le vieillissement de la lampe :** Une lampe UV-C a une durée de vie effective de 9 000 heures (Viqua, 2025). Au-delà, elle produit toujours de la lumière visible, mais son rendement dans le spectre germicide de 253,7 nm s'est effondré. Le remplacement annuel est une opération de maintenance préventive, pas curative.

## Schéma de montage et points de contrôle

L'intégration d'un stérilisateur UV-C dans un réseau hydraulique suit des règles strictes pour garantir son efficacité et sa maintenabilité.

L'appareil doit être le dernier élément de la chaîne de traitement, positionné après la filtration et juste avant le réseau de distribution. Il se monte verticalement pour une purge d'air efficace, avec l'entrée d'eau par le bas.

Un bypass avec vannes d'isolement doit être installé pour permettre le remplacement de la lampe et le nettoyage de la gaine quartz sans couper l'alimentation en eau de l'habitation. Il est interdit d'installer un clapet anti-retour en sortie immédiate du réacteur.

Le contrôle de fonctionnement s'effectue via un compteur horaire ou une alarme visuelle/sonore qui signale la fin de vie de la lampe. Les modèles professionnels intègrent un capteur UV qui mesure l'intensité réelle et alerte en cas de chute de performance due à l'eau ou au matériel.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Stérilisateur UV-C

**Un traitement UV-C est-il suffisant pour rendre l'eau de pluie potable ?**
Non. Un traitement UV-C seul ne retire ni les sédiments, ni les goûts, ni les odeurs, ni les polluants chimiques. Il est une étape de désinfection finale qui doit obligatoirement être précédée d'une filtration mécanique (5 microns) et d'une filtration sur charbon actif.

**Quelle puissance UV pour une maison de 4 personnes ?**
Le dimensionnement ne dépend pas du nombre de personnes mais du débit instantané maximal de la pompe. Pour un débit donné, la puissance minimale de la lampe doit être déterminée selon les abaques du constructeur pour garantir les 40 mJ/cm² (NF EN 14897, 2006).

**Quand changer la lampe UV de mon stérilisateur ?**
La lampe doit être remplacée après 9 000 heures d'utilisation, soit un an de fonctionnement continu (Viqua, 2025). Même si elle s'allume encore, son efficacité germicide chute drastiquement après cette période. Noter la date d'installation sur le réacteur.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*