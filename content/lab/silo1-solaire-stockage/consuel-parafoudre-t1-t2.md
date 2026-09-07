---
title: "Consuel Photovoltaïque : Faut-il un parafoudre Type 1 ou Type 2 ?"
linkTitle: "Parafoudre T1 ou T2"
slug: "lab_silo1_consuel-parafoudre-t1-t2"
title_tag: "Consuel Photovoltaïque : Parafoudre Type 1 ou Type 2 ?"
meta_description: "Parafoudre Type 2 ou Type 1 pour le Consuel ? Analyse technique des ondes de choc et obligations normatives."
date: "2026-09-07"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "consuel photovoltaique parafoudre type 2 ou type 1"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

La présence d'un paratonnerre externe sur le bâtiment impose l'installation d'un parafoudre Type 1 en tête d'installation, testé sous une onde de choc 10/350 µs. Sans cet équipement, le dossier Consuel est systématiquement refusé. Pour les installations photovoltaïques standards sans paratonnerre, un parafoudre Type 2 (onde 8/20 µs) est requis au minimum, notamment en zone AQ2.

## Synoptique de la menace : Onde de choc 10/350 µs vs 8/20 µs

Le dimensionnement d'une protection contre la foudre ne répond pas à une menace unique, mais à deux phénomènes physiques distincts. Le Consuel valide une architecture de protection adaptée à la menace réelle du site, modélisée par des ondes de choc normalisées. Il ne s'agit pas de la même énergie ni du même courant à écouler.

Le coup de foudre direct (impact sur le bâtiment ou une ligne électrique) est caractérisé par un transfert d'énergie massif et une longue durée. Le coup de foudre indirect (impact à proximité) génère une surtension par induction, avec un pic de courant rapide mais une énergie totale plus faible.

| Paramètre | Onde de choc (Foudre directe) | Onde de choc (Foudre indirecte) |
|-----------|-------------------------------|---------------------------------|
| Norme de test | 10/350 µs | 8/20 µs |
| Parafoudre associé | **Type 1** | **Type 2** |
| Courant testé | Iimp (Courant impulsionnel) | Imax (Courant maximal de décharge) |
| Énergie écoulée | Très élevée | Modérée |
| Source | ABB, Guide technique | ABB, Guide technique |
| Date de validité | 2020 | 2020 |

Le choix entre un parafoudre de Type 1 ou Type 2 pour une installation photovoltaïque n'est donc pas une préférence, mais une réponse à une analyse de risque normée.

## Parafoudre Type 1 : L'obligation en cas de paratonnerre externe

Le critère de décision est binaire. Si le bâtiment (résidentiel, agricole ou tertiaire) est équipé d'un Système de Protection contre la Foudre (SPF), tel qu'un paratonnerre, la norme NF C 15-100 est intransigeante : un parafoudre de Type 1 est obligatoire en tête d'installation.

Cet équipement est le seul capable d'écouler le courant partiel d'un coup de foudre direct. Sa technologie repose généralement sur un éclateur à gaz, conçu pour supporter des courants impulsionnels (Iimp) de plusieurs dizaines de kiloampères.

Point de vigilance terrain : l'installation d'un SPF modifie les exigences de mise à la terre. La résistance de la prise de terre de l'installation ne doit alors pas excéder 10 Ω, contre 100 Ω pour une installation standard (NF C 15-100). Le contrôleur Consuel vérifie systématiquement cette valeur au telluromètre.

## Parafoudre Type 2 : Le standard pour les installations sans paratonnerre

Pour la majorité des installations photovoltaïques résidentielles non équipées de paratonnerre, le parafoudre de Type 2 constitue la protection standard exigée. Son installation est obligatoire si l'un des critères suivants est rempli :

*   Le niveau kéraunique (densité de foudroiement) de la zone est supérieur à 25 (zone AQ2).
*   L'alimentation du bâtiment est assurée, même partiellement, par une ligne aérienne.
*   La sécurité des personnes ou des biens critiques est engagée (installations médicales, etc.).

La technologie des parafoudres Type 2 repose sur des varistances à oxyde de métal (MOV). Contrairement à l'éclateur, son temps de réponse est extrêmement court, de l'ordre de 25 nanosecondes (Source : Dehn, 2022). Il est conçu pour écouler les surtensions induites (onde 8/20 µs) et les surtensions de manœuvre du réseau. Sa capacité d'écoulement (Imax) est inférieure à celle d'un Type 1, mais suffisante pour ce type de menace.

## Coordination des protections : La règle des 10 mètres de câblage

La physique des parafoudres impose des règles de câblage strictes. Le temps de réponse d'un éclateur (Type 1) est de l'ordre de 100 ns, contre 25 ns pour une varistance (Type 2). Pour assurer une protection efficace, il est nécessaire de coordonner les dispositifs.

Si un parafoudre Type 1 est installé en tête, un parafoudre Type 2 doit être placé en aval pour la protection fine. Une longueur de câble d'au moins 10 mètres doit les séparer. Cette longueur agit comme une inductance de découplage, qui "ralentit" le front d'onde et laisse le temps au Type 1 de s'amorcer pour écouler le courant principal, tandis que le Type 2 écrête la tension résiduelle.

Cette règle s'applique aussi aux équipements sensibles. Si l'onduleur photovoltaïque se situe à plus de 10 mètres de câble du tableau principal où est installé le parafoudre Type 2, la norme impose l'installation d'un second parafoudre Type 2 (ou Type 3) au plus près de l'onduleur. Omettre ce point est un motif de non-conformité au Consuel.


---

### **Expertises Croisées**
- **Hydraulique & Eau :** [LIEN INTERNE : Pompe immergée à 50m : Calculer la HMT sans griller le moteur.]
- **Thermique & Habitat :** [LIEN INTERNE : PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).]
- **Infrastructure :** [LIEN INTERNE : Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.]

---

### FAQ : Consuel photovoltaïque et parafoudres

**Parafoudre obligatoire pour le consuel photovoltaïque ?**
Oui, un parafoudre est obligatoire dans la majorité des cas pour obtenir la conformité Consuel. Au minimum, un parafoudre de Type 2 est requis si votre logement est dans une zone à risque (AQ2) ou alimenté par une ligne aérienne, ce qui couvre une grande partie du territoire.

**Quand mettre un parafoudre type 1 ou type 2 ?**
Un parafoudre Type 1 est exclusivement requis si le bâtiment possède un système de protection externe contre la foudre (paratonnerre). Dans tous les autres cas d'obligation (zone AQ2, ligne aérienne), un parafoudre de Type 2 est la norme pour une installation photovoltaïque résidentielle.

**Quelle est la différence de coût entre Type 1 et Type 2 ?**
Un parafoudre de Type 1 représente un investissement significativement plus élevé. Basé sur une technologie d'éclateur capable d'écouler des courants très importants, son coût peut atteindre plusieurs centaines d'euros. Un parafoudre modulaire de Type 2 (technologie MOV) est plus courant et son prix se situe généralement entre 40 € et 120 € (données marché FR, 2026).

---
> Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*