---
title: "Point de rosée : Le danger des ponts thermiques en isolation intérieure."
linkTitle: "Point de rosée isolation"
slug: "lab_silo3_point-rosee-isolation"
title_tag: "Condensation et Point de Rosée : Risque isolation ITI"
meta_description: "Analyse technique point de rosée en isolation intérieure. Calcul Glaser et solutions anti-moisissures."
date: "2026-10-26"
signataire: "Frank Vasseur"
silo: 3
mot_cle: "condensation pont thermique isolation interieure"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

La **condensation sur un pont thermique en isolation intérieure** est un risque structurel. La norme NF EN ISO 13788 (méthode de Glaser) fournit un cadre pour calculer le point de rosée, mais son modèle ignore le transport capillaire de l'eau. Cette omission mène à des diagnostics de condensation erronés, particulièrement avec les isolants biosourcés, et peut causer des dégradations irréversibles du bâti.

## Point de rosée : Le calcul normatif selon ISO 13788

L'apparition de condensation interstitielle dans une paroi est un phénomène physique régi par la pression partielle de vapeur d'eau. La méthode de Glaser, encadrée par la norme NF EN ISO 13788, modélise ce risque en régime stationnaire. Le principe consiste à superposer deux profils à travers l'épaisseur de la paroi isolée.

Le premier profil est celui des températures. Il est calculé en fonction de la résistance thermique de chaque matériau composant le mur. Une température est déterminée à chaque interface entre les couches (parpaing, isolant, parement). À partir de ces températures, on déduit la courbe de pression de vapeur saturante : la quantité maximale de vapeur d'eau que l'air peut contenir à une température donnée avant de condenser.

Le second profil est celui de la pression de vapeur d'eau réelle, calculée depuis l'intérieur (ambiance chaude et humide) vers l'extérieur (ambiance froide et sèche). Si la courbe de pression réelle croise la courbe de pression de saturation, le point de rosée est atteint. L'eau passe de l'état gazeux à l'état liquide à cet emplacement précis dans l'isolant.

## Limites de Glaser : Pourquoi le calcul ignore 70% du problème réel

Le calcul normatif est un synoptique théorique. Sur un chantier, il omet des vecteurs de transport d'humidité qui modifient radicalement le diagnostic. Trois phénomènes critiques sont ignorés par la méthode de Glaser, la rendant particulièrement inadaptée aux matériaux modernes.

**1. La capacité hygroscopique :** Certains isolants, notamment biosourcés, agissent comme des tampons. Ils peuvent absorber et stocker une quantité importante de vapeur d'eau par sorption, sans qu'il y ait condensation liquide. Cette capacité de stockage n'est pas prise en compte.

**2. Le transport capillaire :** Dès l'apparition d'eau liquide, des matériaux comme la fibre de bois la redistribuent par capillarité des zones humides vers les zones plus sèches. Ce mécanisme favorise le séchage de la paroi et s'oppose à l'accumulation de condensat. Le calcul standard, ignorant ce transport, surestime le risque pathologique.

**3. Les fuites d'air :** Le modèle suppose une paroi parfaitement étanche. En réalité, les défauts de mise en œuvre (jonctions, gaines) créent des passages pour l'air. Le transport d'humidité par convection peut être des dizaines de fois supérieur à celui par simple diffusion (Fraunhofer IBP/CSTB, 2024).

| Phénomène Physique | Pris en compte par ISO 13788 | Impact Terrain |
|--------------------|------------------------------|----------------|
| Diffusion (Loi de Fick) | Oui | Transfert lent et prédictible |
| Capacité hygroscopique | Non | Tamponne les pics d'humidité, retarde la condensation |
| Transport capillaire | Non | Redistribue l'eau liquide, accélère le séchage |
| Fuites d'air (convection) | Non | Transfert d'humidité massif et non maîtrisé |

Les simulations dynamiques (type WUFI) intègrent ces paramètres et offrent une évaluation du risque de condensation beaucoup plus proche des conditions réelles mesurées sur site.

## Fibre de bois vs Laine de verre : La gestion de l'humidité en conditions réelles

Le comportement d'un isolant face à la condensation dépend directement de sa structure interne et de sa composition chimique. Une comparaison factuelle des deux technologies les plus courantes en isolation par l'intérieur (ITI) met en évidence des différences fondamentales.

La laine de verre, issue de la fusion de sable et de verre recyclé, est non hygroscopique et non capillaire. Ses fibres ne stockent pas l'eau. Si le point de rosée est atteint, l'eau liquide s'accumule dans les interstices, stagne, et dégrade la structure de l'isolant. Le tassement qui en résulte annule localement la performance thermique et crée un pont thermique aggravé.

La fibre de bois, à l'inverse, possède une structure poreuse ouverte. Ses fibres peuvent absorber une quantité significative d'eau en fonction de l'humidité relative ambiante (Fraunhofer IBP/CSTB, 2026) sans dégradation notable de leur conductivité thermique. Cette capacité de sorption, couplée à un transport capillaire efficace, permet à la paroi de gérer des épisodes de condensation temporaires en stockant puis en évacuant l'humidité vers l'extérieur lorsque les conditions le permettent.

| Paramètre | Laine de Verre (standard) | Fibre de Bois (panneau dense) | Source | Date de validité |
|-----------|---------------------------|-------------------------------|--------|-----------------|
| Capacité hygroscopique | Très faible (NF EN ISO 13788/CSTB, 2026) | Élevée (NF EN ISO 13788/Fraunhofer IBP/CSTB, 2026) | NF EN ISO 13788/CSTB | Avril 2026 |
| Transport capillaire | Nul | Actif | NF EN ISO 13788/CSTB | Avril 2026 |
| Comportement à saturation | Tassement, perte de R | Stockage, redistribution | NF EN ISO 13788/CSTB | Avril 2026 |

Le choix d'un isolant capillaire et hygroscopique comme la fibre de bois ou la ouate de cellulose offre une sécurité passive contre les défauts mineurs de mise en œuvre ou les conditions d'usage sévères (salle de bain, cuisine). Cela ne dispense pas d'une mise en œuvre rigoureuse.

## Le pare-vapeur : Positionnement et valeur Sd minimale de 18m

Pour maîtriser la migration de la vapeur d'eau et empêcher la **condensation sur un pont thermique en isolation intérieure**, l'installation d'une membrane d'étanchéité à l'air et de gestion de la vapeur est impérative. Son efficacité dépend de deux facteurs : sa technicité et son positionnement.

La performance d'un pare-vapeur est définie par sa valeur Sd (épaisseur de diffusion équivalente à une couche d'air), exprimée en mètres. Plus le Sd est élevé, plus la membrane est étanche à la vapeur d'eau.

*   **Règle de positionnement :** Le pare-vapeur doit toujours être installé du côté chaud de l'isolant, c'est-à-dire entre l'isolant et le parement intérieur (plaque de plâtre). Le placer côté froid (entre l'isolant et le mur extérieur) bloquerait la vapeur à l'intérieur de l'isolant, garantissant la condensation.
*   **Règle de continuité :** L'efficacité du pare-vapeur est celle de son point le plus faible. Les lés doivent être pontés avec un chevauchement conforme aux prescriptions du fabricant (100 mm minimum, NF DTU 31.2, 2026) et collés avec un ruban adhésif dédié. Les jonctions avec les menuiseries, les planchers, les plafonds et le passage des gaines électriques doivent être traitées avec des mastics ou manchettes d'étanchéité spécifiques. Un serrage au couple inadapté des boîtiers électriques peut déchirer la membrane et créer une fuite majeure.

Pour une isolation intérieure standard en climat continental (type Lyon), une valeur Sd minimale de 18 m (Règles de l'art / CPT 3560, 2026) est requise pour un pare-vapeur (DTU 25.41). Dans des locaux à forte hygrométrie (piscine, buanderie collective), des valeurs Sd significativement plus élevées sont exigées : Sd ≥ 90 m pour les piscines couvertes (Isover Stopvap 90 / NF DTU 31.4, 2023), voire Sd > 200 m pour les locaux EC à évaporation constante. L'utilisation de membranes hygrovariables (dont le Sd s'adapte à l'humidité ambiante) peut également être une option pour favoriser le séchage de la paroi en été.

---

### Expertises Croisées
- **Hydraulique & Eau :** [LIEN INTERNE : Pompe immergée à 50m : Calculer la HMT sans griller le moteur.]
- **Thermique & Habitat :** [LIEN INTERNE : PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).]
- **Infrastructure :** [LIEN INTERNE : Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.]

---

### FAQ : Point de rosée et ponts thermiques

**C'est quoi un pont thermique ?**
Un pont thermique est une zone de l'enveloppe du bâtiment où la résistance thermique est localement réduite. Il s'agit d'un point faible, souvent à la jonction de deux parois (mur/plancher, mur/menuiserie), qui provoque une surface intérieure plus froide et devient un point de condensation préférentiel.

**Comment savoir si j'ai de la condensation dans mes murs ?**
Les symptômes visibles sont l'apparition de moisissures (taches noires), le décollement du papier peint ou le cloquage de la peinture, principalement dans les angles des murs ou derrière les meubles. Une odeur de moisi persistante est également un indicateur de condensation interstitielle.

**Un pare-vapeur est-il toujours obligatoire en isolation intérieure ?**
Oui, les Documents Techniques Unifiés (DTU) qui encadrent les règles de l'art en France l'imposent pour toute isolation thermique par l'intérieur. Son absence ou une pose défectueuse engage la responsabilité décennale de l'installateur en cas de désordres liés à l'humidité.

> Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*