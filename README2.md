# Fisher Fans — Backend API (projet de groupe M2 2026–2027)

Projet pédagogique fictif : gestion d'utilisateurs, bateaux, sorties de pêche, réservations et carnets de pêche. **Date de livraison : 19 mars 2027.**

**Équipe :** Benoit, Max et le troisième membre (toi).  
**Dépôt commun retenu :** [benoit-bremaud/fisher-fans-api](https://github.com/benoit-bremaud/fisher-fans-api) (public ; invitations d'écriture attendues).  
**Statut :** cadrage, pas de code Laravel ni d'Issues créés par ces documents.

## Premier devoir — 20 novembre 2026 (version 2)

- [1. Identification des tâches](docs/01-identification-taches.md)
- [2. Répartition des tâches](docs/02-repartition-equipe.md)
- [3. Relations entre les ressources / MCD](docs/03-relations-ressources.md)
- [Diagramme Mermaid modifiable](docs/03-diagramme-ressources.mmd)
- [4. Questions restantes au professeur](docs/04-questions-professeur.md)
- [Règles retenues après échange](docs/05-regles-retenues.md)
- [Rendu synthétique des 4 parties](DEVOIR_1.md)

[**Ouvrir directement le diagramme sur Mermaid Live**](https://mermaid.live/edit#pako:eNqdVttu2zAM_RXDz-0P5C3LvK3Y0Ba57GmAwMhMIsyWVIoKWqT999Gx08aRvXbzQxCLpESdQx76kGtXYj7JkT4b2BLUv2wmz2p58-NmMV0Wq3n2_Hx97Q7ZJ3mbrrJJ5l0IWOKo4-JuvrwpxNHRFqwJqJCVN5XjLqbb6dIdA6vIpmoivIvUOnfmxvn5kN3NZqv5vLidFeo1TjvLBi23_qlHd868WBTzn9Plzd2tBBFqZ3j0Dn1n3GxQcxy78nM2m85vi6W6L2bfmoxKPEuoZ-u2v59-LVRr6F0gPeDQLjWPsZyZMrv__rYUmIzdZtbVyZon7C2XwHj8URZMCGA1JjFYg6myVXoAY4V-52waAiWhlEOy3pSVsBgYqsS2N1WVRlRgtxFDesIeGEhFSjeysUZyyiPVJoxZIYRIg9eV5DjyEJoqOG2Q0xB-8qhAs9mbAWswhDyWB-nW8tJrgr_z2yx5cp4kGZDNldi_fIz_EoMm49k4m9hqoIeI_WPAWkS1gTUZDYNRUgDsBnk4otKyoAgf4gAZR5e1lB_EtOwkwmMtHXAWV6I2NVSZhthko_AkCKeENXjQwoLywjBskYKq4bHvI8CsBTXtot6JS5qWd8QKmEHvMD27EiA4lkMWZ7cXphO2AhKZcAHhKc7HrveU3vfKodOq98uhE1VBMtJlOTT2FuORQpHrUJqysRtH9THjoDzJn4ehRjxSGAQwM9IX0qZmM0jAG0VNNbuAA0RLkT--sfwypubvI9SmeIlAI31s6k4Dd3IQqhLX5_0_5LIxtpfQ-WD4AFlaRxIh1jhEVTvsRpk8YVeBHsWLnQhsglpv5PyPwlydZkC34fm8en8_DWRl5I9qlcwF6YJ_Uhjt6kYfmgxTJGRZBorS9QBIzpRB_d6m08ZgFMnqt_3riLwwrJ2rEKx8NFRvQiHQ5Fe5SLsMzTKfHHLeiYbJp1SJG4gV5y9XuWiXWzxZnU-YIl7l0Tfbd19a7eLLH_jc9mI)

## Règles immuables pour le cadrage actuel

1. **BF27** : numéro de permis présent dans le profil avant de créer **tout** bateau ; aucun traitement différent pour un canoë ou autre bateau non motorisé.
2. **BF26** : il faut avoir un bateau enregistré avant de créer une sortie.
3. **Identité obligatoire** : propriétaire du bateau **=** organisateur **=** capitaine de la sortie. Aucun conducteur distinct.
4. **Convention d'équipe** : 12 personnes **maximum à bord**, capitaine inclus ; donc au plus **11 places passagers** par bateau, et potentiellement moins selon sa capacité réelle.
5. **Dépôt unique** de Benoit ; attendre l'invitation avant tout push.

Le CDC fait autorité ; les entités auxiliaires (comme `OCCURRENCE_SORTIE`) sont des choix de modélisation proposés pour représenter sans ambiguïté les exigences existantes, et non des ajouts fonctionnels.

## Périmètre technique proposé

API REST JSON, Laravel, SQL relationnel, HTTPS local, version `/api/v1`, OpenAPI 3.1, tests et CI. Déterminer les versions exactes avant installation. Ne pas committer de secrets, données personnelles réelles ou fichiers `.env` dans un dépôt public.
