# Backlog heavy-shop

## Contexte du projet

Le projet represente une boutique catalogue avec listes, recherche, detail produit, panier et checkout simplifie.

## Format attendu

Completer au minimum 3 user stories.
Remplacer chaque champ entre crochets par votre contenu.

## User story 1

- **Contexte**: En tant qu'utilisateur, <br>
        je veux charger uniquement les scripts nécessaires à la page consultée,<br>
        afin de réduire le temps de chargement et les données transférées.
- **Objectif**: Réduire le volume JavaScript chargé de 50%.
- **Bonne pratique d eco-conception ciblee**: Code splitting et suppression des dépendances inutilisées.
- **KPI associe**: Poids JavaScript téléchargé (KiB).
- **Repo ou ecran concerne**: Front-end global.
- **Critere de reussite**: Réduction d'au moins 500 KiB du bundle JS.
- **Niveau de priorite**: haute

## User story 2

- **Contexte**: En tant qu'utilisateur, <br>
        je veux accéder rapidement au contenu principal de la page, <br>
        afin de consulter les produits sans attente excessive.
- **Objectif**: Réduire le LCP de 10,7 s à moins de 4 s.
- **Bonne pratique d eco-conception ciblee**: Chargement prioritaire de la ressource LCP (preload, suppression du lazy loading sur l'image principale).
-**KPI associe**: Largest Contentful Paint.
- **Repo ou ecran concerne**: Page d'accueil, de recherche et de catalogue.
- **Critere de reussite**: LCP inférieur à 4 s.
- **Niveau de priorite**: haute

## User story 3

- **Contexte**: En tant qu'utilisateur, <br>
        je veux que les ressources essentielles soient chargées efficacement,<br>
        afin de limiter les échanges réseau inutiles.
- **Objectif**: Réduire le nombre de requêtes critiques.
- **Bonne pratique d eco-conception ciblee**: Réduction des chaînes de dépendances et mise en cache.
- **KPI associe**: Nombre de requêtes critiques et profondeur du dependency tree.
- **Repo ou ecran concerne**: Infrastructure front-end.
- **Critere de reussite**: Réduction de 30 % des requêtes critiques.
- **Niveau de priorite**: moyenne

## Notes

- Vous pouvez ajouter d autres user stories si necessaire.
- Le niveau de detail attendu doit permettre une priorisation exploitable.
