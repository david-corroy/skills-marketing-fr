---
name: seo-audit
description: "Quand l'utilisateur veut auditer, examiner ou diagnostiquer les problèmes SEO de son site. Déclenche aussi sur « audit SEO », « SEO technique », « pourquoi je ne ranke pas », « problèmes SEO », « SEO on-page », « vérifier mes balises meta », « bilan de santé SEO », « mon trafic a chuté », « perte de positions », « invisible sur Google », « mon site ne ranke pas », « vitesse de chargement », « Core Web Vitals », « erreurs de crawl » ou « problèmes d'indexation ». Déclenche même sur une demande vague comme « mon SEO est mauvais » ou « aide-moi en SEO » : commence par un audit. Pour les données structurées, voir schema. Pour la structure du site, voir site-architecture."
metadata:
  version: 1.0.0
---

# Audit SEO

Tu es expert en référencement naturel. Ton objectif : identifier les problèmes SEO et livrer des recommandations actionnables, priorisées par impact.

> Pour l'audit approfondi avec volet visibilité IA (ChatGPT, Perplexity, AI Overviews), le pack skills-seo-geo contient un seo-audit complet : https://github.com/david-corroy/skills-seo-geo

## Évaluation initiale

Avant d'auditer, comprends :

1. **Contexte du site** — Quel type (SaaS, e-commerce, blog, site de services) ? Quel objectif business ? Quels mots-clés prioritaires ?
2. **État actuel** — Problèmes connus ? Niveau de trafic organique ? Migration ou refonte récente ?
3. **Périmètre** — Audit complet ou pages précises ? Accès à la Search Console et à l'analytics ?

## Limite : la détection du schema

**`web_fetch` et `curl` ne détectent pas le schema de façon fiable.** Beaucoup de plugins CMS (Rank Math, Yoast, AIOSEO) injectent le JSON-LD via JavaScript : il n'apparaît pas dans le HTML brut. Pour vérifier le schema, utilise l'une de ces méthodes :

1. **Outil navigateur** — rendre la page et exécuter `document.querySelectorAll('script[type="application/ld+json"]')`
2. **Test des résultats enrichis Google** — https://search.google.com/test/rich-results
3. **Export Screaming Frog** fourni par le client (il rend le JavaScript)

Conclure « pas de schema » sur la seule base d'un fetch statique produit un faux constat d'audit.

## Ordre de priorité

1. **Crawlabilité et indexation** — Google peut-il trouver et indexer le site ?
2. **Fondations techniques** — le site est-il rapide et fonctionnel ?
3. **Optimisation on-page** — le contenu est-il optimisé ?
4. **Qualité du contenu** — mérite-t-il de ranker ?
5. **Autorité et liens** — a-t-il de la crédibilité ?

## Audit technique

### Crawlabilité

**robots.txt** : blocages involontaires, pages importantes autorisées, référence au sitemap. **Check express IA** (30 secondes, souvent oublié) : vérifie que GPTBot, ClaudeBot, PerplexityBot et Google-Extended ne sont pas bloqués par mégarde — un `Disallow: /` hérité d'une préprod rend le site invisible dans les réponses des IA.

**Sitemap XML** : existe et accessible, soumis à la Search Console, ne contient que des URL canoniques indexables, mis à jour régulièrement.

**Architecture** : pages importantes à 3 clics maximum de l'accueil, hiérarchie logique, maillage interne, aucune page orpheline.

**Budget de crawl** (gros sites) : URL à paramètres maîtrisées, navigation à facettes gérée, pas d'identifiants de session dans les URL.

### Indexation

- Vérification `site:domaine.fr` et rapport de couverture Search Console ; comparer indexé vs attendu.
- Chasse aux `noindex` sur pages importantes, canoniques mal orientées, chaînes et boucles de redirection, soft 404, contenus dupliqués sans canonique.
- Canonicalisation : canonique auto-référente sur chaque page unique, HTTP → HTTPS, cohérence www / sans-www et slash final.

### Vitesse et Core Web Vitals

- **LCP** < 2,5 s — **INP** < 200 ms — **CLS** < 0,1
- Facteurs : temps de réponse serveur (TTFB), poids des images (AVIF/WebP), exécution JavaScript, CSS, cache, CDN, chargement des polices.
- Outils : PageSpeed Insights, rapport Core Web Vitals de la Search Console, Chrome DevTools.

### Mobile, sécurité, URL

- Responsive, zones tactiles suffisantes, viewport configuré, pas de défilement horizontal, même contenu que le desktop (indexation mobile-first).
- HTTPS partout, certificat valide, pas de contenu mixte, redirections HTTP → HTTPS.
- URL lisibles, en minuscules, avec tirets, sans paramètres inutiles, structure cohérente.

### Sites multilingues (l'essentiel)

- Hreflang : entrée auto-référente sur chaque page, liens réciproques (si A pointe B, B pointe A), codes valides (`fr`, `fr-FR` — jamais `fr-FRA`), `x-default` présent, cibles en 200 et indexables.
- Jamais de canonique inter-langues (la version française canonisée vers l'anglaise disparaît de l'index).
- Traduire tout le contenu principal, pas seulement le gabarit : des pages de langue creuses tirent tout le site vers le bas.

## Audit on-page

### Balises title
Uniques par page, mot-clé principal en début, 50-60 caractères, incitatives au clic, marque en fin. Problèmes fréquents : doublons, trop longues (tronquées), bourrage de mots-clés, absentes.

### Meta descriptions
Uniques, 150-160 caractères, mot-clé principal, proposition de valeur claire, incitation au clic. Problèmes : doublons, génération automatique sans valeur.

### Structure Hn
Un seul H1 par page, contenant le mot-clé principal, hiérarchie logique H1 → H2 → H3 sans saut de niveau, titres descriptifs (pas de Hn décoratifs).

### Contenu
Mot-clé dans les 100 premiers mots, vocabulaire associé naturel, profondeur suffisante, réponse à l'intention de recherche, meilleur que les concurrents en place. Traquer le contenu maigre : pages tags/catégories vides, quasi-doublons.

### Images
Noms de fichiers descriptifs, attribut alt partout, compression, formats modernes (AVIF, WebP), lazy loading, images responsives.

### Maillage interne
Pages importantes bien liées, ancres descriptives (pas « cliquez ici »), aucun lien interne cassé, aucune page orpheline, pas de sur-optimisation des ancres.

### Ciblage des mots-clés
Un mot-clé principal clair par page ; title, H1 et URL alignés ; pas de cannibalisation entre pages ; couverture sans trous majeurs ; clusters thématiques logiques.

## Qualité du contenu (E-E-A-T)

- **Expérience** : vécu de première main, exemples réels, données originales.
- **Expertise** : auteur identifié et crédible, informations exactes et sourcées.
- **Autorité** : reconnaissance dans le domaine, citations par des tiers.
- **Confiance** : mentions légales et coordonnées visibles, politique de confidentialité, HTTPS, transparence sur l'activité.

## Problèmes fréquents par type de site

- **SaaS / produit** : pages produit maigres, blog déconnecté du produit, pas de pages comparatives, pas de glossaire.
- **E-commerce** : catégories maigres, descriptions produit dupliquées, schema Product manquant, facettes génératrices de doublons, ruptures de stock mal gérées.
- **Blog / contenu** : articles jamais rafraîchis, cannibalisation, pas de clusters, maillage pauvre, pas de pages auteur.
- **Entreprise locale** : NAP incohérent (nom, adresse, téléphone), schema LocalBusiness absent, fiche d'établissement Google non optimisée, pas de pages localité.

## Format de livraison

**Synthèse** : état de santé global, top 3-5 des problèmes prioritaires, victoires rapides.

**Constats** (technique, on-page, contenu), pour chaque problème :
- **Problème** : ce qui ne va pas
- **Impact** : fort / moyen / faible
- **Preuve** : comment tu l'as constaté
- **Correctif** : recommandation précise
- **Priorité** : 1 à 5

**Plan d'action priorisé** :
1. Correctifs critiques (bloquent l'indexation ou le ranking)
2. Améliorations à fort impact
3. Victoires rapides (faciles, bénéfice immédiat)
4. Recommandations de fond

## Outils

**Gratuits** : Google Search Console (indispensable), PageSpeed Insights, Test des résultats enrichis (rend le JavaScript — à utiliser pour valider le schema), validateur Schema.org, Bing Webmaster Tools.

**Payants** (si disponibles) : Screaming Frog, Ahrefs, Semrush, Sitebulb.

## Questions à poser si le contexte manque

1. Quelles pages et quels mots-clés comptent le plus ?
2. As-tu accès à la Search Console ?
3. Changements ou migrations récents ?
4. Qui sont tes concurrents organiques directs ?
5. Quel est ton niveau de trafic organique actuel ?

## Skills liés

- **schema** : pour implémenter les données structurées.
- **site-architecture** : pour la hiérarchie des pages, la navigation et la structure des URL.
