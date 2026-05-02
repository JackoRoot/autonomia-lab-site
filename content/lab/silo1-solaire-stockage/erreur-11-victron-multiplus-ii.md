---
title: "Erreur 11 Victron Multiplus II : Résoudre le défaut de relais de terre."
linkTitle: "Erreur 11 Victron"
slug: "lab_silo1_erreur-11-victron-multiplus-ii"
title_tag: "Erreur 11 Victron Multiplus II : Diagnostic du relais"
meta_description: "Erreur 11 sur Victron Multiplus II : diagnostic du défaut de relais de terre et causes de la panne."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 1
mot_cle: "erreur 11 victron multiplus 2"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

L'erreur 11 sur un Victron Multiplus 2 signale un échec du test automatique du relais de terre, une sécurité interne obligatoire avant tout couplage au réseau. Ce défaut bloque le transfert de charge et interdit l'injection. Les causes physiques sont une continuité de terre défaillante (résistance > 1 Ω), un courant de fuite en amont, ou une défaillance matérielle du relais interne.

## Synoptique du défaut : La séquence de test en 4 étapes

Le firmware du Multiplus-II exécute une séquence de vérification non désactivable pour s'assurer de l'intégrité de la liaison équipotentielle avant de se coupler au réseau ou de basculer en mode onduleur. L'erreur 11 est le résultat d'un échec lors de cette procédure.

L'architecture de ce test interne suit un protocole précis :
1.  **Isolation :** L'onduleur ouvre ses relais de couplage AC-in et AC-out pour s'isoler des sources et des charges.
2.  **Fermeture du relais de terre :** Le relais interne dédié à la liaison Neutre-Terre est enclenché.
3.  **Injection de courant de test :** Un courant de faible intensité est injecté dans la boucle. La valeur exacte de ce courant n'est pas documentée.
4.  **Mesure et validation :** Le DSP mesure la réponse du circuit. Si la valeur lue sort des tolérances attendues, l'erreur 11 est déclenchée et l'appareil se met en sécurité.

## Cause N°1 : Rupture de continuité de la liaison de terre (< 1 Ω)

Le constat terrain majoritaire pointe vers un défaut physique de la mise à la terre de l'installation. Le test du Multiplus-II est sensible à toute résistance anormale sur la boucle de terre. La norme NF C 15-100 impose une résistance de liaison dont la valeur limite est de < 1 Ω (Victron Community, 2023 ; NF C 15-100). Pour ce test spécifique, le seuil interne du Multiplus-II est de < 1 Ω (Victron Community, 2023 ; Pre-RMA Bench Test Instructions, Victron, 2024).

Les points de contrôle sont :
*   **Serrage au couple :** Vérifier le serrage de la cosse de terre sur le châssis du Multiplus-II. Une connexion lâche est l'une des causes les plus fréquentes de ce type de défaut. Le couple de serrage à appliquer est de 1,6 Nm (Victron Community, 2024 ; Pre-RMA Bench Test Instructions, Victron, 2024).
*   **Section du conducteur :** Le câble de liaison équipotentielle doit avoir une section minimale de 4 mm² (Victron, 2024 ; NF C 15-100).
*   **Continuité globale :** Mesurer à l'ohmmètre la continuité entre le châssis de l'onduleur et le piquet de terre principal. Une valeur stable et inférieure à 1 Ω est attendue.

Une oxydation au niveau du piquet de terre ou de la barrette de répartition du tableau peut également introduire une résistance parasite suffisante pour déclencher le défaut.

## Cause N°2 : Déclenchement par courant de fuite en amont (> 30 mA)

Le Multiplus-II est sensible aux courants de fuite présents sur l'installation, même lorsqu'il est en attente. Un défaut d'isolement sur une charge connectée en amont de l'onduleur peut injecter un courant résiduel sur le conducteur de terre.

Si ce courant de fuite dépasse un certain seuil, il perturbe la mesure effectuée pendant la séquence de test. Le seuil de déclenchement n'est pas spécifié par le constructeur. Un interrupteur différentiel 30 mA (NF C 15-100) en amont qui déclenche de manière aléatoire est un symptôme direct de cette pathologie.

Pour le diagnostic, il faut sectionner tous les circuits en aval du différentiel principal, hors onduleur, et relancer le Multiplus-II. Si l'erreur disparaît, le défaut d'isolement se situe sur l'un des circuits déconnectés.

## Cause N°3 : Défaillance matérielle du relais interne

Une défaillance physique du relais électromécanique est une cause possible, bien que moins fréquente sur des appareils récents. La durée de vie d'un relais est exprimée en nombre de cycles de manœuvre.

| Type de Défaillance | Symptôme Observable | Source de la Donnée |
|---------------------|---------------------------------|-----------------------------|
| Bobine du relais coupée | Aucun "clic" audible lors du démarrage de la séquence de test | Victron Community, 2024 ; Pre-RMA Bench Test Instructions, Victron, 2024 |
| Contacts charbonnés | Haute résistance de contact, test échoue de manière intermittente | Victron Community, 2024 ; Pre-RMA Bench Test Instructions, Victron, 2024 |
| Contacts collés | Le relais reste fermé, provoquant un défaut immédiat | Victron Community, 2024 ; Pre-RMA Bench Test Instructions, Victron, 2024 |

Le remplacement de ce composant n'est pas une opération de maintenance standard et requiert une intervention sur la carte mère de l'appareil. Consulter le fabricant pour une procédure de retour matériel est la seule option viable. L'analyse du [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/) est un prérequis pour comprendre les contraintes subies par ce relais.

## Protocole de diagnostic terrain en 5 points

Face à une erreur 11, la procédure de dépannage doit être systématique et exécutée hors tension.

1.  **Consignation :** Mettre l'installation hors tension. Couper le disjoncteur AC-in, AC-out et la protection DC des batteries.
2.  **Mesure de la continuité de terre :** À l'aide d'un multimètre en mode ohmmètre, vérifier la résistance entre la borne de terre du châssis du Multiplus-II et la barrette de terre du tableau principal. La valeur doit être < 1 Ω.
3.  **Test d'isolement des charges :** Déconnecter toutes les charges en AC-out. Redémarrer le système (batteries puis onduleur). Si l'erreur persiste, le défaut ne vient pas des charges.
4.  **Vérification du raccordement Neutre :** S'assurer que les conducteurs de Neutre en entrée (AC-in) et en sortie (AC-out) ne sont pas pontés ensemble en aval de l'onduleur. Une telle configuration perturbe le test.
5.  **Mise à jour du firmware :** Vérifier via l'interface VictronConnect ou VRM si une version plus récente du firmware est disponible. Des mises à jour peuvent ajuster les tolérances du test de relais.

---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---

### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride.](/lab_silo4_regime-neutre-tt-tn/)

---

### FAQ : Erreur 11 Victron Multiplus II

**Peut-on désactiver le test de relais de terre Victron ?**
Non. Le test du relais de terre est une fonction de sécurité fondamentale imposée par les normes pour garantir la protection des personnes. Il ne peut pas être désactivé par l'utilisateur.

**L'erreur 11 victron multiplus 2 est-elle dangereuse ?**
L'erreur en elle-même est un état de protection qui rend l'appareil inopérant. Le danger provient de sa cause sous-jacente : une mise à la terre défectueuse, qui constitue un risque d'électrisation grave sur l'ensemble de l'installation.

**Un différentiel 30mA en amont peut-il causer l'erreur 11 ?**
Le différentiel lui-même ne cause pas l'erreur. Cependant, si un courant de fuite sur une autre partie de l'installation fait déclencher ce différentiel, ce même courant peut perturber le test du Multiplus-II et générer l'erreur 11.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*