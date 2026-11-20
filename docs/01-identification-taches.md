# Fisher Fans — Devoir 1 (version 2)

## 1. Identification des tâches à réaliser

**Méthode :** respecter BF1–BF27, BN1–BN8 et les annexes sans modifier les règles de permis, de propriété ou d'organisation actées par le groupe. La création d'une sortie nécessite un bateau possédé par l'organisateur (BF26) ; la création du bateau requiert un permis renseigné (BF27).

| Axe | Travaux | Exigences CDC | Dépendances |
|---|---|---|---|
| T01 — Analyse et décisions | Lire le CDC ; recenser BF/BN ; consigner règles fixes et ambiguïtés restantes ; questions au professeur | Tous | Aucune |
| T02 — Modèle des ressources | Diagramme ER/MCD, cardinalités, attributs, clés et contrôle `organisateur_id = proprietaire_id` | BF2, BF26–BF27, annexes 1–5 | T01 |
| T03 — Dépôt et socle API | Dépôt GitHub commun de Benoit, branches/PR ; Laravel, base SQL, API `/api/v1`, JSON, HTTPS local, OpenAPI 3.1, CI | BN1–BN5, livrables | Accès au dépôt ; T01 |
| T04 — Utilisateurs et accès | Inscription, authentification, profil, édition, suppression/anonymisation, filtrage | BF1, BF3, BF8, BF13, BF19–BF20, BN6 | T02–T03 |
| T05 — Bateaux | CRUD, annexes 2, possession, numéro de permis obligatoire **pour tout bateau**, capacité passagers 0–11, recherche par localisation | BF4, BF9, BF14, BF19, BF21, BF24, BF27 | T04 |
| T06 — Sorties | CRUD, vérification bateau enregistré et appartenant au créateur, capitaine = propriétaire = organisateur, dates/récurrence | BF5, BF10, BF15, BF22, BF26, annexe 3 | T05 |
| T07 — Réservations | Création, modification, suppression ; prix et places ; contrôle des places disponibles et concurrence | BF6, BF11, BF17, BF23, annexe 4 | T06 |
| T08 — Carnets de pêche | Créer le carnet ; pages/captures, édition, suppression, liste et contrôle du propriétaire | BF7, BF12, BF16, BF18–BF19, annexe 5 | T04 |
| T09 — Recherches et erreurs | Filtres combinables sur utilisateurs/bateaux/sorties/réservations ; bounding box ; erreurs métier | BF19–BF25 | T04–T08 |
| T10 — Qualité et livraison | Tests, sécurité, RGPD, performances, documentation API, OpenAPI 3.1, scénarios recette et soutenance | BN3–BN8, livrables | Transversal |

**Ordre critique :** T01 → T02/T03 → T04 → T05 → T06 → T07. Carnets de pêche, documentation et tests avancent en parallèle.

**Validation fonctionnelle ciblée :** aucun bateau créé sans permis renseigné ; aucune sortie sans bateau possédé ; aucune sortie organisée/capitainée par un autre utilisateur ; aucune capacité réelle supérieure à 12 personnes à bord (1 capitaine + maximum 11 passagers).

**Reste à préciser :** occurrences des sorties récurrentes, prix global, annulations, droits d'accès, conservation des données après suppression (cf. `04-questions-professeur.md`).
