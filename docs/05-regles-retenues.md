# Fisher Fans — Règles retenues pour le devoir 1 (version 2)

**Date :** 20 novembre 2026  
**Source de référence :** cahier des charges du professeur, pages 11 à 23.  
**Échange oral rapporté par l'équipe :** le professeur a demandé de respecter les exigences du CDC sans les adapter aux usages réels.

## Décisions connues : ne pas reposer ces questions

| ID | Règle appliquée | Fondement | Conséquence dans notre modèle |
|---|---|---|---|
| R01 | Tout utilisateur doit avoir un **numéro de permis renseigné dans son profil** avant de créer **n'importe quel bateau**, y compris un canoë. | **BF27**, consigne orale du professeur | Création BATEAU refusée si `UTILISATEUR.numero_permis` est absent. Pas d'exception selon le type ou la motorisation. |
| R02 | Seul un utilisateur possédant déjà un bateau enregistré peut créer une sortie de pêche. | **BF26** | Une SORTIE doit référencer un BATEAU enregistré appartenant à l'utilisateur qui la crée. |
| R03 | **Propriétaire du bateau = organisateur de la sortie = capitaine de la sortie** (une seule personne). | Choix explicitement indiqué par l'équipe en suivant strictement son interprétation du CDC | `SORTIE.organisateur_id == BATEAU.proprietaire_id`. Pas d'entité conducteur/capitaine et pas de délégation. |
| R04 | On retient un plafond de **12 personnes réellement à bord**, capitaine/organisateur compris. | Convention de périmètre communiquée par l'équipe ; **ne figure pas sous cette forme dans le CDC** | Si 1 capitaine est présent, au plus 11 places pour des passagers : `capacite_passagers_max <= 11` ; `1 + capacite_passagers_max <= 12`. |
| R05 | **Un seul dépôt GitHub** pour le groupe : `benoit-bremaud/fisher-fans-api`. | Modalités p. 5 + décision de l'équipe | Dépôt public existant ; attendre l'invitation avant de pousser fichiers/branches/issues. |

### Interprétation exacte de la capacité

L'annexe 2 prévoit une capacité maximale **en nombre de passagers**. Nous la représentons par `BATEAU.capacite_passagers_max` (hors capitaine) et calculons la capacité réelle à bord comme `1 + capacite_passagers_max`. Cette interprétation traduit la règle d'équipe des 12 personnes à bord en restant proche du libellé de l'annexe. **Ce n'est pas une règle de droit généralisable à toutes les embarcations.**

Exemple : bateau doté de 11 places passagers = 11 passagers + 1 capitaine = 12 personnes à bord. Si le bateau possède 5 places passagers, la sortie ne peut pas en proposer 6, même si le plafond du projet est 12.

### Règles de cohérence dérivées (propositions d'implémentation)

- À la création d'une SORTIE, vérifier que le créateur est le propriétaire du BATEAU choisi et qu'il possède bien ce bateau enregistré (R02/R03).
- Le capitaine n'occupe **pas une réservation de passager** : les réservations consomment les places passagers uniquement.
- La capacité d'une sortie `nombre_passagers_proposes` ne dépasse pas `BATEAU.capacite_passagers_max` ; les réservations actives d'une occurrence ne doivent pas excéder les places proposées (modalités de statut et d'annulation à clarifier).
- Prévenir les incohérences si un bateau est supprimé ou si son propriétaire change alors qu'il existe des sorties (BF9, BF14, BF15) ; la politique exacte est à clarifier.

## Hypothèses techniques, NON validées par le professeur

- H01 — `OCCURRENCE_SORTIE` représente chaque créneau daté pour les sorties journalières ou récurrentes (annexe 3) et sert de cible unique à une réservation (annexe 4).
- H02 — Un utilisateur a au plus un carnet, dont les pages correspondent aux captures (BF7, annexe 5).
- H03 — Les règles de prix global, de modification/annulation, de confidentialité et les données conservées après suppression restent à clarifier.
- H04 — Laravel, PostgreSQL, Sanctum, tests, CI et conventions REST sont des orientations techniques proposées et non exigées par le CDC (hormis JSON, HTTPS, versionnement, OpenAPI 3.1).

## Tests métier à préparer

| Test | Action | Résultat attendu |
|---|---|---|
| TC-BF27-01 | Créer un bateau sans numéro de permis dans le profil | Refus, quel que soit le type de bateau |
| TC-BF27-02 | Créer un canoë avec numéro de permis renseigné | Contrôle BF27 satisfait |
| TC-BF26-01 | Créer une sortie sans bateau enregistré | Refus |
| TC-OWN-01 | Créer une sortie avec le bateau d'un autre utilisateur | Refus : organisateur différent du propriétaire |
| TC-OWN-02 | Créer une sortie avec son propre bateau | Contrôles BF26 et propriété satisfaits |
| TC-CAP-01 | Déclarer un bateau de 12 places passagers | Refus dans la convention « 12 personnes à bord dont le capitaine » |
| TC-CAP-02 | Déclarer un bateau de 11 places passagers | Capacité totale de 12 personnes, autorisée |
| TC-CAP-03 | Proposer 8 places sur un bateau limité à 5 passagers | Refus |

> Ces scénarios vérifient les règles ciblées ; ils ne garantissent pas le succès global d'une requête si une autre validation échoue.
