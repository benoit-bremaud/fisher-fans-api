# Fisher Fans — Devoir 1 : questions restantes pour le professeur (version 2)

**Contexte :** le professeur a indiqué oralement qu'il fallait respecter le cahier des charges sans le modifier pour l'adapter à la réalité. Les questions **déjà tranchées** ne figurent donc plus parmi les questions ouvertes : BF27 s'applique à tout bateau ; BF26 exige un bateau enregistré ; le propriétaire = organisateur = capitaine ; pas de conducteur distinct. L'équipe retient 12 personnes maximum à bord, capitaine compris.

## Questions à poser (triées par impact)

| Priorité | ID | Référence | Question |
|---|---|---|---|
| P0 | Q01 | Présentation p. 10, BF2–BF27 | La **location d'un bateau entier** mentionnée dans la présentation est-elle attendue en recette, alors qu'aucun BF ne définit la réservation d'un bateau entier ? |
| P0 | Q02 | Annexe 3 et annexe 4 | Pour les sorties récurrentes, une réservation doit-elle viser une **occurrence datée précise** ? Quelle est la règle de répétition d'une sortie (jours, dates, fréquence) ? |
| P0 | Q03 | Annexe 3 et annexe 4 | Comment calculer le **prix total** d'une réservation si la sortie utilise un tarif **global** au lieu d'un prix par personne ? |
| P0 | Q04 | BF8–BF11, BN6 | Que deviennent les sorties/réservations lorsqu'on supprime **un utilisateur, son bateau ou une sortie** ? Quels champs sont anonymisés/conservés ? |
| P0 | Q05 | BF1, BF8–BF23 | Quels utilisateurs peuvent **lire, modifier ou supprimer** les profils, bateaux, sorties, réservations et pages des carnets ? |
| P0 | Q06 | BF6, BF17 | Un **organisateur peut-il réserver sa propre sortie** ? Un même utilisateur peut-il effectuer plusieurs réservations sur une même occurrence ? |
| P0 | Q07 | BF15, BF17, annexe 3 | Comment gérer la **modification d'une sortie déjà réservée** (date, bateau, prix, places) et les annulations de réservations ? |
| P1 | Q08 | BF7, BF12, BF16, BF18, annexe 5 | Le carnet est-il créé à la demande ou automatiquement, et comment **créer une nouvelle page** si aucun BF ne demande explicitement cette opération ? |
| P1 | Q09 | BF16 et BF18 | BF16 et BF18 correspondent-ils à **la même modification de page**, BF18 ne faisant que préciser l'utilisateur ? |
| P1 | Q10 | BF5, BF15, annexe 3 | Un même bateau peut-il être affecté à **deux sorties aux horaires qui se chevauchent** ? |
| P1 | Q11 | BF20–BF23 | Les filtres doivent-ils accepter **toutes** les caractéristiques de chaque ressource, y compris les informations personnelles, ou seulement un sous-ensemble publiable ? |
| P1 | Q12 | Annexe 1 | Les comptes **professionnels** ont-ils des permissions spécifiques, ou seulement des champs supplémentaires de profil ? |
| P1 | Q13 | BF24 et annexe 2 | La recherche par **bounding box** porte-t-elle bien sur le **port d'attache** et comment traiter une boîte traversant la longitude ±180° ? |
| P1 | Q14 | BF25 | Quel format de **codes d'erreurs métier** est attendu au-delà du statut HTTP (par exemple `PERMIS_REQUIS`, `BATEAU_REQUIS`) ? |
| P1 | Q15 | BN7–BN8 | Quels critères **mesurables** de performance et de montée en charge seront utilisés pour évaluer ces deux exigences ? |
| P1 | Q16 | BF1, BF3 | L'inscription est-elle accessible sans identification préalable bien que le reste de l'API soit privé ? |
| P1 | Q17 | Annexes 1–5 | Quels champs sont obligatoires ou facultatifs, et quels contrôles précis de format/unicité sont attendus **au-delà des formats indiqués** dans les annexes ? |
| P1 | Q18 | Modalités p. 5–7 | Quelles sont les **dates des quatre devoirs Moodle** et où consulter le plan de présentation disponible sur Moodle ? |

## Questions clôturées après échange avec le professeur / décision de groupe

| Ancien sujet | Réponse désormais appliquée |
|---|---|
| « Peut-on enregistrer un canoë sans permis ? » | **Non** : BF27 est appliqué tel quel à tous les types de bateaux, sans exception. |
| « Peut-on créer une sortie sans bateau enregistré ? » | **Non** : BF26 est appliqué. |
| « L'organisateur peut-il être un tiers ou un conducteur distinct ? » | **Non** : même personne = propriétaire, organisateur et capitaine. |
| « Faut-il compter 12 places de réservation quel que soit le bateau ? » | **Non** : 12 personnes **maximum à bord**, capitaine inclus ; le nombre de passagers réels dépend de la capacité propre au bateau (au plus 11). |

> Le refus de modifier le CDC est une **consigne orale rapportée**. Le modèle d'occurrences, les règles de prix et d'annulation n'ont pas été validés par le professeur. Aucune réponse n'est présumée pour les questions ouvertes.
