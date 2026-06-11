# Heavy shop audit

## Npm analize
- Projet: heavy-shop
- Assets: 6 fichiers / 60.8 KB
- Data: 2 fichiers / 27.5 KB
- Frontend attendu sur http://localhost:5173
- Backend attendu sur http://localhost:4100

## Lighthouse

### Accueil

---

**Performance**

**Score** : 60

**Métrique** :
- First Contentful Paint : 5.7s, critique
- Largest Contentful Paint : 10.7 s, critique
- Total Blocking Time : 30ms, bon
- Cumulative Layout Shift : 0.066, bon
- Speed Index : 5.7 s, mauvais

**Insigths** :
- LCP request discovery (critique) : Optimize LCP by making the LCP image discoverable from the HTML immediately, and avoiding lazy-loading
- Network dependency tree (critique) : Avoid chaining critical requests by reducing the length of chains, reducing the download size of resources, or deferring the download of unnecessary resources to improve page load.
- Minify JavaScript (critique) - Est savings of **709 KiB** : Minifying JavaScript files can reduce payload sizes and script parse time. 
- Reduce unused JavaScript (critique) - Est savings of 636 KiB : Reduce unused JavaScript and defer loading scripts until they are required to decrease bytes consumed by network activity.
- Page prevented back/forward cache restoration (1 failure, critique) : Many navigations are performed by going back to a previous page, or forwards again. The back/forward cache (bfcache) can speed up these return navigations. 
- Image elements do not have explicit width and height (warning) : Set an explicit width and height on image elements to reduce layout shifts and improve CLS.

**Synthèse et action** :

Deux principaux axes problématiques :
- le javascript trop volumineux avec notamment du code inutile. Il faut :
     - Supprimer les bibliothèques inutilisées.
     - Charger les scripts uniquement lorsqu'ils sont nécessaires (lazy loading, code splitting).

- Chargement initial trop complexe qui peut être imputé à deux facteurs : LCP request discovery et Network dependency tree. Il faut :
    - Pour le LCP, on peut afficher l'image directement dans le html, éviter le lazy loading voir utiliser un preload (si pertinent)
    - Pour le Network, réduire la chaine entre les ressources

En complétement, il y a aussi un problème de cache et de dimensions des images (dimensions non définies).

---

**Accessibilité**

**Score** : 95, très bon

---

**Best practices**

**Score** : 96, très bon

---

**SEO**

**Score** : 83

**Insigths** :
- Document does not have a meta description : Format your HTML in a way that enables crawlers to better understand your app’s content.
- robots.txt is not valid (17 erreurs relevées) : If your robots.txt file is malformed, crawlers may not be able to understand how you want your website to be crawled or indexed.
![alt text](<Capture d'écran 2026-06-11 113012.png>)
![alt text](<Capture d'écran 2026-06-11 113054.png>)

**Synthèse et action** :

Le principal axe lié à l'éco-conception sont les erreurs relevées par robots.txt pour rendre le code plus propre. Mais ce n'est pas une action prioritaire.

---

### Page recherche

---

**Performance**

**Score** : 61

**Métrique** :
- First Contentful Paint : 5.7s, critique
- Largest Contentful Paint : 10.9 s, critique
- Total Blocking Time : 30ms, bon
- Cumulative Layout Shift : 0.066, bon
- Speed Index : 5.7 s, mauvais

**Synthèse et action** :

Retour et action identique à ceux de la page *Accueil*.

---

**Accessibilité**

**Score** : 89

**Synthèse et action** :

Problème de label notamment dans les formulaires, problème de hiérarchie des titres et absence d'un main landmark. A corriger éventuellement pour une meilleur accessibilité et un code plus propre. Non prioritaire.

---

**Best practices**

**Score** : 96, très bon

---

**SEO**

**Score** : 83

**Synthèse et action** :

La même chose que pour la page *Accueil*.

---

### Catalogue

L'analyse devait se faire via EcoIndex mais suite a des difficultés, elle s'est faîtes sur Lightouse. Les résultats sont les mêmes que pour les autres pages.