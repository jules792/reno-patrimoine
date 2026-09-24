# Réno Patrimoine

Site vitrine français de rénovation et patrimoine, basé à Beaufour-Druval, Pays d’Auge. Identité charbon, chêne et rouge ; design responsive, animations discrètes et respect de la réduction des mouvements.

## Démarrer

Node.js 22.x. Aucune dépendance à installer.

```sh
npm run dev
```

Le site est disponible sur http://localhost:3000. Pour utiliser un autre port : `PORT=3001 npm start` sous un shell POSIX.

```sh
npm run build
npm test
npm start
```

`dist/` contient le site statique complet, prêt à servir. Le serveur local renvoie une véritable réponse 404 pour une page absente. En production, servir les répertoires via leur `index.html` et utiliser `404.html` pour les chemins inconnus, sans réécriture générale vers l’accueil.

## Contenu livré

- 125 pages indexables : accueil, 5 pages métiers, pages de présentation/contact, journal et 10 catégories, 100 articles, informations de site.
- 100 articles distincts avec réponse directe, conseils, exemple spécifique, liste de préparation, liens internes et ressource officielle complémentaire.
- 18 photographies originales générées et 1 monogramme adapté du visuel fourni. Les images d’inspiration sont identifiées comme telles, sans faux portfolio.
- Recherche locale insensible aux accents, filtres thématiques, pagination progressive ; les articles restent tous accessibles sans JavaScript.
- Images WebP en deux tailles, chargement différé, priorité au visuel d’accueil, polices hébergées localement.
- Balises canoniques, titres/descriptions, Open Graph, données structurées entreprise/service/article/fil d’Ariane, sitemap XML, robots.txt, plan HTML et llms.txt.
- Aucun formulaire factice : contact téléphonique réel et lien d’itinéraire. Aucun suivi publicitaire ajouté.

## Modifier le site

- `content/services.mjs` : métiers et catégories.
- `content/articles.mjs` : 100 textes et leurs métadonnées.
- `content/examples.mjs` : exemples propres à chaque article.
- `scripts/build.mjs` : génération des pages et coordonnées.
- `assets/site.css` et `assets/site.js` : design et interactions.
- `assets/` : visuels et polices ; les licences SIL des polices sont incluses.

Après modification, lancer `npm run build` puis `npm test`. Le dossier `dist/` est versionné afin de permettre un hébergement statique immédiat.

## Déploiement Vercel

Le fichier `vercel.json` configure le projet comme site statique : génération avec `npm run build`, sortie `dist`, URLs avec slash final. La racine Vercel est la racine du dépôt (aucun sous-dossier à renseigner). Node.js est fixé à 22.x.

Les métadonnées utilisent `SITE_URL` si elle est définie, sinon le domaine de production fourni par `VERCEL_PROJECT_PRODUCTION_URL`. Les variables système Vercel doivent être exposées au build. Pour un domaine personnalisé, définir explicitement `SITE_URL=https://votre-domaine.fr`.

## Domaine et publication

L’origine actuelle correspond à l’aperçu privé Sites. Pour un domaine public différent, reconstruire avec `SITE_URL=https://votre-domaine.fr npm run build` puis publier le dossier `dist/`. Cela met à jour les canoniques, Open Graph, données structurées, sitemap et llms.txt. Ne pas conserver l’adresse d’aperçu dans les métadonnées d’un autre domaine.

L’aperçu privé n’est pas indexable par les moteurs tant que son accès reste restreint. L’optimisation technique ne garantit pas de position ni de citation par une IA. Le fichier llms.txt est une facilité de lecture, pas un mécanisme officiel de classement.

Avant exploitation commerciale publique, faire confirmer les mentions légales complètes par l’exploitant : identité juridique/statut, responsable de publication, adresse e-mail, informations d’hébergement retenu et autres mentions applicables. Seuls le nom commercial, le SIRET, l’adresse et le téléphone fournis ont été reproduits. Aucune qualification, assurance, note client ou réalisation n’a été inventée.

## Vérification

`npm test` contrôle les 100 articles, 10 catégories, titres/descriptions distincts, données structurées, liens et ancres internes, images locales et dimensions déclarées, absence de marqueurs non résolus et cohérence du sitemap. Il inclut un contrôle négatif pour prouver qu’un lien manquant est bien détecté.

Les contrôles visuels portent sur mobile et ordinateur, le menu, la recherche, les filtres et la pagination. Les résultats des contrôles de structure couvrent 125 pages indexables et les 100 articles.

## Repères éditoriaux

- [Google Search : fonctions génératives et bonnes pratiques](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)
- [Ministère de la Culture : réhabilitation responsable du bâti ancien](https://www.culture.gouv.fr/thematiques/monuments-sites/monuments-historiques-sites-patrimoniaux/themes-environnementaux/la-gestion-ecologique-du-patrimoine-bati)
- [France Rénov’ : ventilation](https://france-renov.gouv.fr/renovation/vmc)
- [Mentions obligatoires d’un site professionnel](https://www.economie.gouv.fr/entreprises/developper-son-entreprise/innover-et-numeriser-son-entreprise/mentions-sur-votre-site-internet-les-obligations-respecter)
