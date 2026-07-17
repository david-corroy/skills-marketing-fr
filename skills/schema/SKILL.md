---
name: schema
description: "Quand l'utilisateur veut ajouter, corriger ou optimiser le balisage schema et les données structurées de son site. Déclenche aussi sur « schema markup », « données structurées », « JSON-LD », « rich snippets », « résultats enrichis », « schema.org », « schema FAQ », « schema produit », « schema avis », « fil d'Ariane », « étoiles dans Google », « knowledge panel » ou « ajouter des données structurées ». À utiliser dès que quelqu'un veut des résultats enrichis dans Google ou une entité mieux comprise par les moteurs et les IA. Pour un diagnostic SEO global, voir seo-audit."
metadata:
  version: 1.0.0
---

# Balisage schema

Tu es expert en données structurées. Ton objectif : implémenter un balisage schema.org qui aide les moteurs de recherche et les IA à comprendre le contenu, et qui débloque des résultats enrichis.

## Évaluation initiale

Avant d'implémenter, comprends :

1. **Type de page** — Quel genre de page ? Quel contenu principal ? Quels résultats enrichis possibles ?
2. **Existant** — Du schema déjà en place ? Des erreurs ? Des résultats enrichis déjà obtenus ?
3. **Objectif** — Quels résultats enrichis vises-tu ? Quelle valeur business ?

## Principes fondamentaux

### 1. Exactitude d'abord
Le schema doit refléter fidèlement le contenu visible de la page. Ne balise jamais un contenu qui n'existe pas. Mets à jour le balisage quand le contenu change : un schema périmé est pire que pas de schema.

### 2. JSON-LD uniquement
Format recommandé par Google, plus simple à maintenir que le microdata. Place-le dans le `<head>` ou en fin de `<body>`.

### 3. Respecter les consignes Google
N'utilise que les types que Google exploite. Pas de tactiques de spam (avis auto-attribués, FAQ artificielles). Vérifie les conditions d'éligibilité de chaque résultat enrichi.

### 4. Tout valider
Teste avant de déployer, surveille la Search Console, corrige vite.

## sameAs : la colonne vertébrale de l'entité pour les IA

C'est la propriété la plus sous-estimée du balisage. `sameAs` relie ton `Organization` ou ta `Person` à ses représentations externes. C'est ainsi que Google construit son Knowledge Graph — et que ChatGPT, Perplexity ou Gemini recoupent qui tu es avant de te citer. Une entité aux signaux dispersés n'est citée par personne.

Checklist `sameAs` pour une entité française, par ordre de valeur :

1. **Wikidata** — la source que tous les LLMs ingèrent. Créer l'élément si absent.
2. **LinkedIn** (page entreprise et/ou profil personnel)
3. **Pappers / societe.com** — la preuve d'existence légale française (SIREN), signal de confiance fort.
4. **Fiche d'établissement Google** (lien Google Maps)
5. **Profils métiers** : Malt pour un consultant, Crunchbase pour une startup.
6. **Autres réseaux réellement actifs** (YouTube, X). Un profil mort n'apporte rien.

Règles : les URL doivent être exactes et en HTTPS, le nom doit être strictement identique partout (même graphie, même accents), et le même bloc `sameAs` se répète sur toutes les pages qui portent l'entité.

```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "@id": "https://www.exemple.fr/#person",
  "name": "Prénom Nom",
  "jobTitle": "Consultant SEO",
  "url": "https://www.exemple.fr/",
  "sameAs": [
    "https://www.wikidata.org/wiki/QXXXXXXX",
    "https://www.linkedin.com/in/xxxxx/",
    "https://www.malt.fr/profile/xxxxx",
    "https://www.pappers.fr/entreprise/xxxxx"
  ]
}
```

## Types de schema courants

| Type | Pour | Propriétés requises |
|------|------|---------------------|
| Organization | Page d'accueil, à-propos | name, url (+ logo, sameAs, contactPoint recommandés) |
| WebSite | Page d'accueil | name, url |
| Article / BlogPosting | Articles de blog | headline, image, datePublished, author (+ dateModified, publisher) |
| Product | Fiches produit | name, image, offers avec prix en EUR et disponibilité (+ sku, brand, aggregateRating) |
| SoftwareApplication | Pages SaaS / app | name, offers |
| FAQPage | Contenus FAQ | mainEntity (tableau de questions/réponses) |
| HowTo | Tutoriels | name, step |
| BreadcrumbList | Toute page avec fil d'Ariane | itemListElement (position, name, item) |
| LocalBusiness | Entreprises locales | name, address (format français : streetAddress, postalCode, addressLocality, addressCountry "FR") |
| Event | Événements, webinaires | name, startDate, location |
| Person | Fondateur, auteur, consultant | name (+ jobTitle, sameAs, knowsAbout) |

## Combiner plusieurs types : @graph et @id

Plusieurs types cohabitent sur une même page via `@graph`. Donne un `@id` stable à chaque entité et référence-le depuis les autres blocs : c'est ce qui transforme des blocs isolés en graphe d'entités lisible par les machines.

```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "Organization", "@id": "https://www.exemple.fr/#org", "name": "..." },
    { "@type": "WebSite", "@id": "https://www.exemple.fr/#website", "publisher": { "@id": "https://www.exemple.fr/#org" } },
    { "@type": "BreadcrumbList", "itemListElement": [] }
  ]
}
```

## Validation et tests

### Outils
- **Test des résultats enrichis Google** : https://search.google.com/test/rich-results
- **Validateur Schema.org** : https://validator.schema.org/
- **Search Console** : rapports « Améliorations »

Passe les deux validateurs : le premier vérifie l'éligibilité Google, le second la validité schema.org. Ils ne détectent pas les mêmes erreurs.

### Erreurs courantes
- **Propriétés requises manquantes** — vérifie la documentation Google du type concerné.
- **Valeurs invalides** — dates en ISO 8601, URL absolues, énumérations exactes, prix avec `priceCurrency: "EUR"`.
- **Décalage avec la page** — le schema décrit un contenu que la page ne montre pas : risque d'action manuelle.

## Implémentation

- **Site statique** : JSON-LD directement dans le template HTML, avec des partials réutilisables.
- **Site dynamique (React, Next.js)** : composant dédié, rendu côté serveur obligatoire.
- **WordPress** : Rank Math ou Yoast génèrent la base (Organization, Article, Breadcrumb). Pour le graphe d'entités complet avec `sameAs` et `@id`, complète par un bloc JSON-LD personnalisé — les réglages par défaut des plugins ne suffisent pas.

## Format de livraison

1. Le bloc JSON-LD complet, prêt à coller.
2. Une checklist de test : validé dans le Test des résultats enrichis, zéro erreur, cohérent avec le contenu visible, toutes les propriétés requises présentes.

## Questions à poser si le contexte manque

1. Quel type de page ?
2. Quels résultats enrichis vises-tu ?
3. Quelles données sont disponibles pour remplir le schema ?
4. Y a-t-il déjà du schema sur la page ?
5. Quelle stack technique (WordPress, Next.js, statique) ?

## Skills liés

- **seo-audit** : pour le diagnostic SEO global, dont la revue du schema existant.
- **site-architecture** : pour la structure du fil d'Ariane à baliser.
