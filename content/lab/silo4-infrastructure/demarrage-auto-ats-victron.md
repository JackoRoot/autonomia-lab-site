---
title: "Démarrage auto ATS : Connecter un groupe sur un onduleur Victron."
linkTitle: "ATS démarrage auto Victron"
slug: "lab_silo4_demarrage-auto-ats-victron"
title_tag: "Schéma ATS démarrage auto groupe sur Victron"
meta_description: "Câblage contact sec et configuration Cerbo GX pour démarrage automatique groupe électrogène."
date: "2026-08-31"
signataire: "Frank Vasseur"
silo: 4
mot_cle: "schema groupe electrogene ats demarrage auto"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Le `schema groupe electrogene ats demarrage auto` sur un onduleur Victron repose sur le câblage d'un contact sec, non d'une ligne de puissance. 80% des échecs de démarrage proviennent d'une erreur de connexion sur le bornier du Multiplus ou du Cerbo GX. L'inversion des fils COM/NO empêche l'onduleur de piloter le groupe.

## Principe de fonctionnement : Contact Sec vs Inverseur de Puissance

Le pilotage d'un groupe électrogène par un onduleur-chargeur Victron (gammes Multiplus/Quattro) ne transfère aucune puissance. L'onduleur agit comme un automate de contrôle via un relais interne à contact sec. Ce relais ferme une boucle de commande basse tension qui ordonne au groupe de démarrer.

L'onduleur-chargeur est l'inverseur de source (ATS) principal de l'installation. En cas de coupure réseau, il bascule sur batterie en moins de 20 ms. Le groupe électrogène n'est qu'une source d'énergie secondaire, sollicitée uniquement quand les seuils de batterie sont atteints.

Le groupe ne démarre donc pas pour alimenter directement les charges, mais pour recharger les batteries et assister l'onduleur.

## Câblage du relais : 2 fils, 0 Volt

Le raccordement physique s'effectue via un câble 2 conducteurs blindés à paires torsadées, entre le bornier relais programmable du Victron et le bornier de démarrage à distance du groupe électrogène. Ce dernier doit impérativement être équipé d'une interface de démarrage automatique.

**Côté Onduleur Victron (Multiplus/Quattro) :**
Le raccordement se fait sur les bornes du relais programmable. La configuration standard utilise les bornes :
*   COM (Commun)
*   NO (Normalement Ouvert)

Aucune tension ne doit être injectée dans ce relais. Il s'agit d'un simple interrupteur piloté.

**Côté Groupe Électrogène :**
Le câble est connecté aux bornes "Remote Start" ou "ATS" du groupe. Le manuel du constructeur du groupe spécifie l'emplacement exact. Le non-respect du brochage (inversion COM/NO) est la cause principale de dysfonctionnement.

## Configuration Venus OS : Les seuils de 20% SOC

Le pilotage logique s'effectue depuis l'interface de supervision, généralement un Cerbo GX. Le menu "Generator start/stop" permet de calibrer les conditions de déclenchement.

Les paramètres fondamentaux à configurer sont :
*   **Démarrage sur état de charge (SOC) :** Le seuil de déclenchement bas. Une valeur de 20% à 30% est un standard de terrain pour préserver la durée de vie d'un parc batterie LFP.
*   **Démarrage sur demande de puissance :** Calibré en Watts, ce seuil démarre le groupe si l'appel de puissance dépasse la capacité de l'onduleur et des batteries pendant une durée définie (ex: 3000 W pendant plus de 10 secondes).
*   **Conditions d'arrêt :** Le groupe est consigné à l'arrêt lorsque l'état de charge de la batterie atteint un seuil haut (ex: 90% SOC) pour éviter un fonctionnement à faible charge, inefficace et coûteux en carburant.

La fonction "Test run" doit être activée pour un fonctionnement mensuel de maintenance, garantissant la fiabilité du groupe.

## Régime de neutre du groupe : Le piège du TT flottant

Lorsqu'un groupe électrogène devient la source principale, le régime de neutre de l'installation est modifié. En France, le réseau de distribution public est en régime TT. Le neutre est mis à la terre au transformateur de distribution, et l'installation possède sa propre prise de terre locale (norme NF C 15-100).

Quand le groupe est actif, l'installation est isolée du réseau. Le neutre du groupe est "flottant". Il est impératif de le lier à la prise de terre de l'habitation pour recréer un régime de neutre sûr et permettre le fonctionnement des protections différentielles.
Certains onduleurs Victron gèrent cette opération via un relais de terre interne. Si ce n'est pas le cas, un contacteur externe doit être asservi au fonctionnement du groupe pour lier son neutre à la terre. L'absence de cette liaison peut invalider la protection des personnes.

| État de l'installation | Régime de neutre | Liaison Neutre-Terre | Source de la liaison |
|-------------------------|------------------|----------------------|----------------------|
| Réseau public présent | TT | Assurée | Transformateur Enedis |
| Groupe électrogène actif | Potentiellement IT | **À créer** | Groupe -> Prise de terre locale |

Cette opération est une source d'erreurs courantes, pouvant mener à une [LIEN INTERNE : Erreur 11 Victron Multiplus II : Résoudre le défaut de relais de terre.].

## Tableau comparatif : ATS interne (Deye) vs Pilotage externe (Victron)

La stratégie de couplage d'un groupe électrogène diffère selon les constructeurs d'onduleurs.

| Paramètre | Architecture Victron (Multiplus/Quattro) | Architecture Deye Hybride | Source / Date |
|---|---|---|---|
| **Fonction ATS** | Intégrée à l'onduleur (AC-out) | Intégrée à l'onduleur (Port Load) | Victron / Deye, 2026 |
| **Pilotage Groupe** | Contact sec externe (relais programmable) | Contact sec externe (port Gen/G-start) | Victron / Deye, 2026 |
| **Transit de puissance (Pass-through)** | Calibre du Multiplus (ex: 50A pour un 5kVA) | Jusqu'à 63 A sur les modèles récents | Deye, 2026 |
| **Complexité câblage** | Câblage de puissance centralisé sur l'onduleur | Câblage de puissance centralisé sur l'onduleur | Analyse terrain |
| **Point de défaillance** | Unité unique (onduleur) | Unité unique (onduleur) | Analyse terrain |

La topologie Victron, comme celle de Deye, centralise la fonction ATS dans l'onduleur, rendant un boîtier ATS externe redondant pour la plupart des installations résidentielles.


> **Mention de responsabilité des données**
> Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.

---

### **Expertises Croisées**

- **Hydraulique & Eau :** [LIEN INTERNE : Pompe immergée à 50m : Calculer la HMT sans griller le moteur.]
- **Thermique & Habitat :** [LIEN INTERNE : PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).]
- **Infrastructure :** [LIEN INTERNE : Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.]

### FAQ : Démarrage automatique groupe électrogène sur onduleur Victron

**Quel type de groupe électrogène pour un Victron ?**
Le groupe doit disposer d'une entrée "démarrage à distance" ou "contact sec" (Remote Start). Les modèles à démarrage manuel par clé ou lanceur sont incompatibles avec un pilotage automatique. La compatibilité doit être vérifiée sur la fiche technique du groupe.

**Pourquoi mon groupe ne démarre pas avec mon Multiplus ?**
Les causes les plus fréquentes sont un mauvais câblage du contact sec (inversion des bornes COM/NO) ou une configuration incorrecte des seuils de démarrage/arrêt dans Venus OS (Cerbo GX). Vérifier également que le mode "Auto" est bien activé sur le groupe lui-même.

**Faut-il un ATS externe avec un onduleur Victron ?**
Non. L'onduleur Multiplus ou Quattro est lui-même un inverseur de source automatique (ATS) ultra-rapide. Il gère la bascule entre le réseau, les batteries et l'entrée AC (groupe ou autre). Le relais interne sert uniquement à *commander* le démarrage du groupe, pas à commuter sa puissance.

**Quelle section de câble pour le contact sec ?**
Le signal de commande est en très basse tension et très faible courant. La chute de tension n'est pas un facteur dimensionnant sur ce type de boucle de commande. La section sera précisée selon les préconisations du constructeur du groupe électrogène.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*