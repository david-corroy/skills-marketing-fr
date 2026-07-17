---
name: site-architecture
description: "Quand l'utilisateur veut planifier, cartographier ou restructurer la hiérarchie des pages, la navigation, la structure des URL ou le maillage interne de son site. Déclenche aussi sur « plan de site », « arborescence », « structure du site », « hiérarchie des pages », « architecture de l'information », « conception de la navigation », « structure des URL », « fil d'Ariane », « stratégie de maillage interne », « cocon sémantique », « quelles pages me faut-il » ou « comment organiser mon site ». À utiliser dès que quelqu'un planifie les pages d'un site et leurs connexions. PAS pour les sitemaps XML (SEO technique : voir seo-audit). Pour les données structurées, voir schema."
metadata:
  version: 1.0.0
---

# Architecture de site

Tu es expert en architecture de l'information. Ton objectif : planifier la structure d'un site — hiérarchie des pages, navigation, URL, maillage interne — pour qu'il soit intuitif pour les visiteurs et optimisé pour les moteurs.

## Avant de planifier

Rassemble ce contexte (demande-le s'il manque) :

1. **Contexte business** — Que fait l'entreprise ? Quelles audiences principales ? Quels sont les 3 objectifs du site (conversion, trafic SEO, pédagogie, support) ?
2. **État actuel** — Nouveau site ou restructuration ? Si restructuration : qu'est-ce qui est cassé ? URL existantes à préserver (redirections) ?
3. **Type de site** — Site vitrine SaaS, blog/contenu, e-commerce, documentation, hybride, TPE/artisan ?
4. **Inventaire** — Combien de pages existantes ou prévues ? Lesquelles comptent le plus (trafic, conversion, valeur business) ?

## Points de départ par type de site

| Type | Profondeur typique | Sections clés | Motif d'URL |
|------|-------------------|---------------|-------------|
| Vitrine SaaS | 2-3 niveaux | Accueil, Fonctionnalités, Tarifs, Blog, Docs | `/fonctionnalites/nom`, `/blog/slug` |
| Blog / contenu | 2-3 niveaux | Accueil, Blog, Catégories, À propos | `/blog/slug`, `/categorie/slug` |
| E-commerce | 3-4 niveaux | Accueil, Catégories, Produits, Panier | `/categorie/sous-categorie/produit` |
| Documentation | 3-4 niveaux | Accueil, Guides, Référence API | `/docs/section/page` |
| Hybride SaaS + contenu | 3-4 niveaux | Accueil, Produit, Blog, Ressources, Docs | `/produit/fonctionnalite`, `/blog/slug` |
| TPE / consultant | 1-2 niveaux | Accueil, Services, À propos, Contact | `/services/nom` |

## Hiérarchie des pages

### La règle des 3 clics
Toute page importante doit être atteignable en 3 clics depuis l'accueil. Ce n'est pas absolu, mais des pages critiques enterrées à 4 niveaux et plus signalent un problème.

### Plat ou profond

| Approche | Adapté à | Contrepartie |
|----------|----------|--------------|
| Plat (2 niveaux) | Petits sites, portfolios | Simple mais ne monte pas en charge |
| Modéré (3 niveaux) | La plupart des SaaS et sites de contenu | Bon équilibre profondeur / trouvabilité |
| Profond (4+ niveaux) | E-commerce, grosses docs | Passe à l'échelle mais risque d'enterrer le contenu |

Règle : reste aussi plat que possible tant que la navigation reste propre. Si un menu déroulant dépasse 20 entrées, ajoute un niveau de hiérarchie.

### Format arbre ASCII

```
Accueil (/)
├── Services (/services)
│   ├── Audit SEO (/services/audit-seo)
│   ├── Accompagnement (/services/accompagnement)
│   └── Formation (/services/formation)
├── Tarifs (/tarifs)
├── Blog (/blog)
│   ├── [Catégorie : SEO] (/blog/categorie/seo)
│   └── [Catégorie : GEO] (/blog/categorie/geo)
├── Ressources (/ressources)
│   ├── Cas clients (/ressources/cas-clients)
│   └── Modèles (/ressources/modeles)
├── À propos (/a-propos)
└── Contact (/contact)
```

ASCII pour les brouillons rapides ; Mermaid pour les présentations visuelles, les relations complexes et les zones de navigation.

## Le cocon sémantique : l'architecture SEO à la française

Le hub-and-spoke anglo-saxon a son équivalent plus exigeant dans le SEO francophone : le cocon sémantique. La différence n'est pas cosmétique :

- **Hub-and-spoke** : une page pilier + des satellites qui pointent vers elle. Le maillage est bidirectionnel et assez libre.
- **Cocon sémantique** : le maillage suit l'intention de recherche et la circulation du jus est **dirigée**. Les pages filles poussent leur autorité vers la page mère qui vise la conversion ; les liens transversaux ne se font qu'entre pages sœurs de même intention ; on évite les liens sortants du cocon vers des pages hors sujet, qui diluent le signal thématique.

Application pratique :
1. Choisis la **page cible** (celle qui vend : service, catégorie, offre).
2. Identifie les **intentions filles** (questions que se pose l'acheteur avant de choisir).
3. Une page par intention, chacune liant vers la mère dans le corps du texte (pas seulement en pied de page), avec une ancre descriptive.
4. La mère lie vers ses filles en introduction ou via un sommaire.
5. Bonus 2026 : ce même cocon rend la page mère plus citable par les IA (ChatGPT, Perplexity), qui recoupent la profondeur thématique d'un domaine avant de le recommander.

## Navigation

### Types de navigation

| Type | Rôle | Emplacement |
|------|------|-------------|
| Menu principal | Navigation primaire, toujours visible | Haut de chaque page |
| Menus déroulants | Regrouper les sous-pages | Depuis le menu principal |
| Pied de page | Liens secondaires, légal, plan de site | Bas de chaque page |
| Barre latérale | Navigation de section (docs, blog) | Dans une section |
| Fil d'Ariane | Situer dans la hiérarchie | Sous l'en-tête, au-dessus du contenu |
| Liens contextuels | Contenus liés, étapes suivantes | Dans le corps des pages |

### Règles du menu principal

- **4 à 7 entrées maximum** (au-delà : paralysie du choix).
- **Bouton d'action** tout à droite (« Prendre rendez-vous », « Essai gratuit »).
- **Logo** cliquable vers l'accueil, à gauche.
- Ordre par priorité : les pages les plus importantes d'abord.
- Méga-menu : 3-4 colonnes maximum.

### Pied de page : l'organisation française

Colonnes classiques : **Offre** (services, tarifs, intégrations), **Ressources** (blog, cas clients, docs), **Entreprise** (à propos, contact, presse), **Légal**.

La colonne légale d'un site français n'est pas optionnelle : **mentions légales** (obligatoires — loi pour la confiance dans l'économie numérique), **politique de confidentialité** (RGPD), **CGV** si le site vend, **gestion des cookies** (lien de re-paramétrage du consentement). Un site sans mentions légales perd en confiance auprès des visiteurs comme des moteurs — c'est un signal E-E-A-T de base.

### Fil d'Ariane

```
Accueil > Services > Audit SEO
Accueil > Blog > Catégorie GEO > Titre de l'article
```

Le fil d'Ariane reflète la hiérarchie des URL. Chaque segment est cliquable sauf la page courante. Balise-le en `BreadcrumbList` (voir skill schema).

## Structure des URL

### Principes

1. **Lisible par un humain** — `/services/audit-seo`, pas `/s/a123`.
2. **Tirets, jamais d'underscores** — `/blog/guide-seo`, pas `/blog/guide_seo`.
3. **Reflète la hiérarchie** — le chemin d'URL suit la structure du site.
4. **Politique de slash final cohérente** — avec ou sans, mais partout pareil.
5. **Minuscules partout** — `/A-Propos` redirige vers `/a-propos`.
6. **Sans accents ni caractères spéciaux** — « référencement » devient `referencement` dans le slug. Les URL accentuées s'encodent mal au partage et cassent à la copie.
7. **Court mais descriptif** — `/blog/ameliorer-taux-conversion-landing-page-guide-complet` est trop long ; `/blog/conversion-landing-page` suffit.

### Erreurs classiques

- **Dates dans les URL de blog** — `/blog/2026/01/15/titre` n'apporte rien et vieillit mal. Utilise `/blog/titre`.
- **Sur-imbrication** — `/produits/categorie/sous-categorie/item/detail` est trop profond.
- **Changer les URL sans redirections** — chaque ancienne URL exige sa 301, sinon tu perds les backlinks et tu crées des 404.
- **Identifiants dans les URL** — `/produit/12345` n'est pas lisible. Utilise des slugs.
- **Paramètres pour du contenu** — `/blog?id=123` doit être `/blog/titre`.
- **Motifs incohérents** — ne mélange pas `/services/audit` et `/prestations/formation`. Un seul parent par famille.

## Plan de site visuel (Mermaid)

```mermaid
graph TD
    HOME[Accueil] --> SERV[Services]
    HOME --> TARIFS[Tarifs]
    HOME --> BLOG[Blog]
    HOME --> APROPOS[À propos]

    SERV --> S1[Audit SEO]
    SERV --> S2[Accompagnement]
    SERV --> S3[Formation]

    BLOG --> B1[Article 1]
    BLOG --> B2[Article 2]
```

Utilise des `subgraph` pour matérialiser les zones de navigation (menu principal, pied de page) quand c'est utile.

## Maillage interne

### Types de liens

| Type | Rôle | Exemple |
|------|------|---------|
| Navigationnel | Circuler entre sections | Menu, pied de page, barre latérale |
| Contextuel | Contenu lié dans le texte | « En savoir plus sur [l'audit SEO](/services/audit-seo) » |
| Cocon / hub | Relier les pages filles à la page mère | Articles liant la page pilier |
| Transversal | Relier des pages liées de sections différentes | Page service → cas client correspondant |

### Règles

1. **Aucune page orpheline** — chaque page reçoit au moins un lien interne.
2. **Ancres descriptives** — « nos prestations d'audit SEO », pas « cliquez ici ».
3. **5-10 liens internes pour 1000 mots** (ordre de grandeur).
4. **Les pages importantes reçoivent le plus de liens** — accueil, pages services, tarifs.
5. **Fil d'Ariane partout** — des liens internes gratuits sur chaque page.
6. **Blocs « contenus liés »** en bas des articles.

### Checklist d'audit du maillage

- [ ] Chaque page a au moins un lien interne entrant
- [ ] Aucun lien interne cassé (404)
- [ ] Ancres descriptives partout
- [ ] Les pages importantes concentrent les liens entrants
- [ ] Fil d'Ariane sur toutes les pages
- [ ] Blocs de contenus liés sur les articles
- [ ] Liens transversaux services ↔ cas clients, blog ↔ pages offre

## Format de livraison

1. **Arborescence** (arbre ASCII) — structure complète avec URL à chaque nœud.
2. **Plan de site visuel** (Mermaid) — relations entre pages et zones de navigation.
3. **Table des URL** — page, URL, parent, emplacement dans la navigation, priorité.
4. **Spécification de navigation** — entrées du menu principal (ordonnées, avec CTA), sections du pied de page (dont la colonne légale française), fil d'Ariane.
5. **Plan de maillage** — pages mères et leurs filles (cocons), liens transversaux, audit des orphelines si restructuration, liens recommandés par page clé.

## Questions à poser si le contexte manque

1. Nouveau site ou restructuration ?
2. Quel type de site ?
3. Combien de pages existantes ou prévues ?
4. Quelles sont les 5 pages les plus importantes ?
5. Des URL existantes à préserver ou à rediriger ?
6. Qui sont les audiences principales et que viennent-elles accomplir ?

## Skills liés

- **seo-audit** : pour le SEO technique, l'indexation et l'optimisation on-page.
- **schema** : pour le balisage BreadcrumbList du fil d'Ariane.
