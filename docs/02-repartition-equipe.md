# Fisher Fans — Devoir 1 (version 2)

## 2. Répartition des tâches : Benoit, Max et le troisième membre (toi)

**Statut :** proposition équilibrée à confirmer entre les trois membres selon leurs compétences et disponibilités. L'équipe utilisera le **dépôt public existant de Benoit**, `benoit-bremaud/fisher-fans-api`, une fois les invitations de collaboration acceptées. Aucun accès en écriture ni dépôt parallèle n'est présumé.

| Membre | Pour le devoir du 20/11/2026 | Développement principal prévu | Relecture par un autre membre |
|---|---|---|---|
| **Benoit** | Contrôler utilisateurs/bateaux dans le MCD et relever exigences des annexes 1–2 ; documenter BF27 sans exception et plafond de capacité | Socle Laravel, comptes/authentification, bateaux et permissions | Max relit le module bateaux ; tu vérifies les règles de capacité |
| **Max** | Contrôler sorties/récurrence et annexe 3 ; vérifier la règle propriétaire = organisateur = capitaine ; revoir les cardinalités | Sorties, occurrences et carnets de pêche | tu relis sorties/récurrence ; Benoit relit carnet |
| **Toi** | Assembler les 4 documents ; maintenir diagramme Mermaid ; traiter réservations/annexe 4, questions et rendu | Réservations, filtres géographiques, intégration, OpenAPI/documentation/recette | Benoit relit réservations ; Max relit MCD |

### Actions collectives pour le devoir

1. Vérifier que `SORTIE.organisateur_id == BATEAU.proprietaire_id` et que le capitaine **n'est pas une entité distincte**.
2. Vérifier BF27 : permis renseigné obligatoirement **avant** d'enregistrer tout bateau, même canoë ; BF26 : bateau enregistré et possédé avant toute sortie.
3. Vérifier la convention projet : au plus **12 personnes réelles à bord**, dont **1 capitaine**, donc au plus **11 places passagers**.
4. Valider ensemble les cardinalités proposées et la question des occurrences datées.
5. Relire les questions encore ouvertes et rendre les quatre éléments demandés.

### Fonctionnement Git prévu

- **Dépôt unique :** `benoit-bremaud/fisher-fans-api` ; invitations pour toi et Max attendues.
- **Branches séparées :** `feature/auth-boats`, `feature/trips-log`, `feature/bookings-search` (noms indicatifs).
- **Pull Requests :** relecture croisée ; mise à jour du MCD et du CDC de référence lors d'un arbitrage documenté.
- **Intégration :** chaque développeur écrit les tests et la documentation de son module ; l'OpenAPI et la recette finale sont revus par les trois.

> Les responsabilités ci-dessus ne correspondent pas à des tickets GitHub déjà attribués.
