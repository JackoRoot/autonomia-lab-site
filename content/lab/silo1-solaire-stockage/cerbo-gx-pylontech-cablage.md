---
title: "Cerbo GX et Pylontech : Le schéma de câblage CAN-bus définitif."
linkTitle: "Cerbo GX & Pylontech"
slug: "lab_silo1_cerbo-gx-pylontech-cablage"
title_tag: "Victron Cerbo GX & Pylontech : Schéma de câblage CAN-bus"
meta_description: "Schéma de câblage CAN-bus pour Victron Cerbo GX et Pylontech. Évitez les erreurs de terminaison 120 Ω."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "victron cerbo gx pylontech can bus"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

Un défaut de communication entre un Victron Cerbo GX et des batteries Pylontech via le CAN-bus est dans la grande majorité des cas imputable à l'utilisation d'un câble inadapté ou à une absence de terminaison. Le protocole Pylontech impose une vitesse de bus de 500 kbit/s (Victron Compatibility Manual, 2023) et une résistance de fin de ligne de 120 Ω (ISO 11898 ; Victron GX Product Manual) pour stabiliser le signal et éviter la corruption des données du BMS.

Une communication BMS (Battery Management System) instable entre un Cerbo GX et un parc Pylontech n'est jamais un défaut matériel. C'est une erreur de protocole ou de câblage. L'écosystème Victron est conçu pour une intégration transparente, à condition que la topologie du réseau de communication respecte les contraintes physiques du bus CAN.

Le constat terrain est récurrent : des installateurs utilisent un simple câble Ethernet RJ45, entraînant des déconnexions aléatoires du BMS et des mises en sécurité injustifiées de l'onduleur. Ce document établit la procédure de raccordement validée.

## Synoptique matériel : 3 composants, 1 protocole

L'architecture de communication repose sur trois éléments physiques stricts. Toute substitution ou composant non certifié invalide le support technique du constructeur.

*   **Superviseur :** Victron Cerbo GX. Le port de communication à utiliser est l'un des deux ports VE.Can.
*   **Stockage :** Parc batteries Pylontech (séries US2000, US3000, US5000). Le port à utiliser est le port "CAN" de la batterie maître.
*   **Liaison physique :** Câble Victron Energy "VE.Can to CAN-bus BMS Type B". La référence exacte est ASS030720018 (Victron VE.Can to CAN-bus BMS cables manual, 2026).

Le protocole utilisé est le CAN 2.0B. Il requiert une impédance de ligne constante pour garantir l'intégrité des trames de données échangées entre le BMS et le superviseur.

## Câblage physique : Le câble Type B et la terminaison 120 Ω

L'erreur la plus fréquente est la confusion entre les différents types de câbles RJ45 proposés par Victron. Un câble VE.Bus ou un câble Ethernet standard ne fonctionnera pas. Le brochage est différent.

Le câble "VE.Can to CAN-bus BMS Type B" est spécifiquement conçu pour le brochage des batteries Pylontech. Le type A est destiné à d'autres marques de batteries (BYD, LG Chem).

| Paramètre | Câble VE.Can to CAN-bus Type A | Câble VE.Can to CAN-bus Type B | Source | Date de validité |
|-----------|--------------------------------|--------------------------------|--------|-----------------|
| Compatibilité | LG Chem Resu, AXIstorage | **Pylontech US-series**, Peimar | Victron Documentation | 2025 |
| Brochage CAN-H | Broche 7 | Broche 4 | Victron VE.Can to CAN-bus BMS cables manual, 2026 | 2025 |
| Brochage CAN-L | Broche 8 | Broche 5 | Victron VE.Can to CAN-bus BMS cables manual, 2026 | 2025 |

**Procédure de raccordement :**

1.  Sectionner et consigner l'alimentation DC du parc batterie et l'alimentation AC de l'onduleur.
2.  Connecter une extrémité du câble Type B au port "CAN" de la batterie Pylontech maître.
3.  Connecter l'autre extrémité à l'un des deux ports VE.Can du Cerbo GX.
4.  Insérer la résistance de terminaison VE.Can (bouchon bleu fourni par Victron) sur le second port VE.Can libre du Cerbo GX.

L'absence de cette résistance de 120 Ω génère une réflexion du signal en bout de ligne, ce qui corrompt les trames de données. Le BMS devient alors illisible pour le Cerbo GX.

## Configuration du Cerbo GX : 500 kbit/s ou rien

Une fois le câblage physique validé, la configuration logicielle est l'étape finale. L'interface du Cerbo GX (via écran tactile, console distante sur VRM ou connexion directe) permet de définir la vitesse du bus de communication.

Pylontech impose une vitesse de 500 kbit/s. Toute autre valeur (250 kbit/s par défaut) résultera en une absence de détection du parc de stockage.

**Procédure de configuration :**

1.  Accéder au menu du Cerbo GX.
2.  Naviguer vers `Paramètres > Services > VE.Can port`.
3.  Sélectionner le profil "CAN-bus BMS (500 kbit/s)".
4.  Redémarrer le Cerbo GX pour appliquer la modification.

Après le redémarrage, le système doit immédiatement identifier le BMS Pylontech et l'afficher dans la liste des appareils connectés.

## Validation fonctionnelle : 3 indicateurs à vérifier

Le succès de l'opération est validé par l'observation de trois données précises sur l'interface de supervision.

*   **Détection du BMS :** Dans la liste des appareils, une entrée "Pylontech" doit apparaître, avec son état de charge (SoC) en pourcentage.
*   **Cohérence des données :** La tension et le courant affichés sur l'interface du Cerbo GX doivent correspondre aux valeurs réelles mesurées au multimètre sur les bornes de la batterie maître.
*   **Absence d'alarmes :** Le journal d'alarmes du Cerbo GX ne doit remonter aucun défaut lié au BMS ou à la communication CAN.

Si ces trois points sont validés, l'installation est fonctionnelle et stable. Le Cerbo GX pilotera désormais la charge et la décharge de l'onduleur en se basant sur les limites (tension, courant, température) transmises en temps réel par le BMS Pylontech.


---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Cerbo GX et Pylontech CAN-bus

**Quel câble pour Victron et Pylontech ?**
Le seul câble validé est la référence Victron "VE.Can to CAN-bus BMS Type B". Un câble Ethernet standard (RJ45) ou un câble VE.Bus provoquera des erreurs de communication en raison d'un brochage incorrect.

**Pourquoi mon Cerbo GX ne voit pas ma Pylontech ?**
Vérifiez trois points : 1) Le câble utilisé est bien un Type B. 2) La vitesse du port VE.Can sur le Cerbo GX est configurée sur "CAN-bus BMS (500 kbit/s)". 3) La résistance de terminaison de 120 Ω est bien insérée sur le port VE.Can libre.

**Faut-il une résistance de terminaison CAN-bus pour Pylontech ?**
Oui, une seule, de 120 Ω. Elle doit être placée en fin de bus, c'est-à-dire sur le port VE.Can non utilisé du Cerbo GX. Elle est fournie avec le Cerbo GX. L'oublier est la cause la plus courante d'instabilité.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*