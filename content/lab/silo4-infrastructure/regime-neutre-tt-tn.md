---
title: "Régime de neutre (TT vs TN) : L'impact sur votre onduleur hybride."
linkTitle: "Régime neutre TT/TN"
slug: "lab_silo4_regime-neutre-tt-tn"
title_tag: "Régime de neutre TT vs TN : Impact Solaire & Onduleur"
meta_description: "Analyse technique TT, TN, IT. Impact sur protections différentielles et conformité NF solaire."
date: "2026-05-01"
signataire: "Frank Vasseur"
silo: 4
mot_cle: "regime de neutre tt tns it solaire"
draft: false
---

> **Sécurité** — Cet article est un support de compréhension technique à titre éducatif uniquement. Les valeurs, calculs et schémas présentés ne remplacent pas l'expertise d'un installateur certifié. Toute installation doit être réalisée et validée par un professionnel qualifié RGE. Autonomia Lab décline toute responsabilité en cas d'application directe de ces informations.

En France, le régime de neutre TT est la norme imposée par le distributeur pour toute installation résidentielle, y compris solaire. La protection des personnes y dépend d'un dispositif différentiel 30 mA et d'une prise de terre locale de résistance inférieure à 100 Ω. Un onduleur hybride non compatible avec le régime de neutre TT ou TNS provoquera des défauts d'isolement au raccordement. Le régime IT est exclu du domaine domestique.

## Définitions : TT, TN, IT — 3 Architectures de Sécurité

La norme NF C 15-100 (2026) définit trois schémas de liaison à la terre (SLT), ou régimes de neutre. Le choix n'est pas libre pour un particulier : le distributeur Enedis livre systématiquement l'énergie en régime TT. Les régimes TN et IT sont réservés aux sites industriels ou tertiaires disposant de leur propre transformateur HTA/BT.

**Régime TT (Terre-Terre)**
Le neutre du transformateur de distribution est mis à la terre. Les masses métalliques de l'installation (carcasses d'équipements) sont connectées à une prise de terre locale, électriquement distincte de celle du distributeur. La boucle de défaut passe par le sol. La protection des personnes est assurée par des dispositifs différentiels résiduels (DDR) (NF C 15-100, 2026).

**Régime TN (Terre-Neutre)**
Le neutre du transformateur est mis à la terre. Les masses de l'installation sont interconnectées au conducteur de neutre. Un défaut d'isolement devient un court-circuit franc, provoquant le déclenchement des protections magnéto-thermiques.
- **TN-C :** Le neutre et le conducteur de protection (PE) sont confondus (conducteur PEN). Interdit dans les locaux à risque d'incendie (NF C 15-100, 2026).
- **TN-S :** Le neutre et le PE sont séparés sur toute l'installation.

**Régime IT (Isolé-Terre)**
Le neutre du transformateur est isolé de la terre (ou relié via une forte impédance). Les masses sont reliées à la terre. Ce régime garantit une continuité de service au premier défaut d'isolement, qui est simplement signalé par un Contrôleur Permanent d'Isolement (CPI). Il est utilisé dans les blocs opératoires ou les processus industriels critiques (NF C 15-100, 2026).

| Paramètre d'Analyse | Régime TT (Résidentiel) | Régime TN-S (Tertiaire) | Régime IT (Critique) |
|---|---|---|---|
| **Continuité de service** | Coupure au 1er défaut | Coupure au 1er défaut | Maintien au 1er défaut |
| **Protection principale** | Dispositif Différentiel Résiduel (DDR) | Disjoncteur magnéto-thermique | CPI + Disjoncteur au 2nd défaut |
| **Boucle de défaut** | Impédance élevée (via le sol) | Impédance faible (métallique) | Impédance très élevée (capacitive) |
| **Source** | NF C 15-100 | NF C 15-100 | NF C 15-100 |
| **Date de validité** | 2026 | 2026 | 2026 |

## Régime TT : La Contrainte des 100 Ohms et le Rôle du Différentiel

En régime TT, la sécurité repose sur la relation `RA x IΔn ≤ UL` (NF C 15-100, 2026).
- **UL** est la tension de contact limite de sécurité, fixée à 50 V en alternatif pour les locaux secs.
- **IΔn** est la sensibilité du dispositif différentiel.
- **RA** est la résistance de la prise de terre de l'installation.

Le disjoncteur de branchement Enedis dispose d'une protection différentielle de 500 mA (0,5 A). Pour garantir la sécurité, la résistance de la prise de terre doit donc être au maximum de 50 V / 0,5 A = 100 Ω. Cette valeur est un seuil non négociable vérifié par le Consuel (NF C 15-100, 2026).

Les circuits terminaux (prises, éclairage) doivent être protégés par des différentiels haute sensibilité de 30 mA (0,03 A).
Dans une installation solaire, l'onduleur hybride doit être certifié compatible avec le régime TT. Un défaut d'isolement sur un panneau ou un câble DC peut injecter des courants de fuite qui seront détectés par le différentiel, provoquant une coupure.

## Régime TN : Impédance de Boucle et Déclenchement en < 0,4 seconde

Le régime TN vise à transformer tout défaut d'isolement en court-circuit. La protection est assurée par le déclencheur magnétique du disjoncteur, qui doit opérer en moins de 0,4 seconde pour une tension de 230 V (NF C 15-100, 2026).

Le déclenchement est conditionné par le calcul de l'impédance de boucle de défaut (Zs). La norme NF C 15-100 impose l'utilisation d'un facteur de 0,8 sur la tension nominale pour ce calcul, une approche plus conservatrice que la norme internationale CEI 60364 qui utilise 0,95 (NF C 15-100, 2026).

Cette contrainte dimensionne la longueur et la section maximale des câbles. Un câble trop long ou sous-dimensionné augmente l'impédance de boucle, et le courant de défaut risque de ne pas atteindre le seuil magnétique du disjoncteur. Le déclenchement reposerait alors sur le bilame thermique, avec un temps de coupure de plusieurs secondes, créant un risque d'incendie. Le choix d'un [Disjoncteur Courbe D ou C ? Le choix vital pour les gros compresseurs.](/lab_silo4_disjoncteur-courbe-d-vs-c/) est également critique.

## Impact sur l'Onduleur Hybride : Le Relais de Terre et les Normes

Un onduleur hybride, en mode secours (off-grid), doit créer son propre référentiel de neutre. Pour cela, il ferme un relais interne qui connecte son neutre de sortie à la terre. C'est une création locale d'un régime TN-S.

Le point critique survient au retour du réseau public. Si l'onduleur ne sectionne pas ce relais de terre avant de se reconnecter au réseau TT, deux liaisons neutre-terre coexistent : celle du transformateur Enedis et celle de l'onduleur. Cette double liaison crée une boucle pour les courants de neutre, qui est vue comme un courant de fuite par le différentiel principal. Le résultat est un déclenchement systématique.

Les onduleurs conformes gèrent cette transition automatiquement. Les modèles non conformes ou mal configurés sont une source de pannes récurrentes. De plus, la présence d'électronique de puissance impose un [Interrupteur Différentiel Type B : Exigé (et cher) en stockage DC.](/lab_silo4_differentiel-type-b/) pour se prémunir des courants de fuite continus qui peuvent "aveugler" un différentiel de type AC ou A (NF C 15-100, 2026).


---

> **Les données présentées résultent d'une analyse de sources officielles, de normes techniques et d'études indépendantes à la date indiquée. Elles peuvent évoluer.**

---
### Expertises Croisées
- **Hydraulique & Eau :** [Pompe immergée à 50m : Calculer la HMT sans griller le moteur.](/lab_silo2_calcul-hmt-pompe-50m/)
- **Thermique & Habitat :** [PAC Air-Eau en relève de fioul : Le schéma (Bouteille de mélange).](/lab_silo3_pac-releve-fioul-schema/)
- **Infrastructure :** [Disjoncteur Courbe D ou C ? Le choix vital pour les gros compresseurs.](/lab_silo4_disjoncteur-courbe-d-vs-c/)

---
### FAQ : Régime de neutre TT, TN et IT pour onduleur hybride

**Quelle est la valeur de terre maximale en régime TT ?**
La résistance maximale de la prise de terre autorisée en résidentiel est de 100 Ω. Cette valeur est calculée pour garantir que la tension de contact ne dépasse pas 50 V en cas de défaut sur un appareil protégé par le disjoncteur principal de 500 mA (NF C 15-100, 2026).

**Pourquoi mon différentiel saute avec mon onduleur solaire ?**
Un déclenchement différentiel peut provenir du relais de terre de l'onduleur qui reste fermé lors du couplage au réseau, créant une double liaison neutre-terre. Il peut aussi s'agir d'un courant de fuite DC, nécessitant un différentiel de type A ou B.

**Puis-je avoir un régime TN dans une maison individuelle ?**
Non. En France, le réseau de distribution public basse tension pour les clients résidentiels est exclusivement en régime TT. Le régime TN est déployé sur des sites industriels ou tertiaires qui possèdent leur propre poste de transformation (NF C 15-100, 2026).

**Le régime de neutre IT est-il pertinent pour une installation solaire domestique ?**
Non. Le régime IT est une architecture complexe conçue pour la continuité de service absolue (hôpitaux, industrie lourde). Il requiert un contrat de maintenance avec du personnel qualifié pour intervenir au premier défaut, ce qui le rend inadapté et non conforme pour un usage résidentiel.

*Frank Vasseur — Expert Systèmes Énergétiques & Thermiques, Autonomia Lab*