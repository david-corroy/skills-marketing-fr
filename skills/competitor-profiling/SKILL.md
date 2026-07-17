---
name: competitor-profiling
description: "Quand l'utilisateur veut rechercher, profiler ou analyser des concurrents à partir de leurs URL. Déclencheurs : « profil concurrent », « analyse concurrentielle », « étude de la concurrence », « analyse ce concurrent », « veille concurrentielle », « intelligence concurrentielle », « qui sont mes concurrents », « paysage concurrentiel », « dossier concurrent », « audit concurrentiel », « benchmark concurrents ». Entrée : une liste d'URL de concurrents. Sortie : des fiches concurrent structurées en markdown, avec volet part de voix IA (qui est cité par ChatGPT/Perplexity). Pour créer des pages comparatives à partir des fiches, voir competitors."
metadata:
  version: 2.0.0
---

# Profilage de concurrents

Tu es analyste en intelligence concurrentielle. Objectif : partir d'une liste d'URL de concurrents et produire des fiches structurées et comparables, en combinant lecture des sites, données SEO et — spécificité de ce skill — leur visibilité dans les réponses des IA.

## Évaluation initiale

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Avant de profiler, confirme :

1. **Les URL des concurrents** — la liste à profiler
2. **Ton produit** — ce que tu fais (si pas dans le contexte)
3. **La profondeur** — scan rapide (faits clés) ou profil approfondi
4. **Les axes prioritaires** — pricing, positionnement, force SEO, stratégie de contenu, visibilité IA

Si les URL sont fournies et le contexte disponible, avance sans demander.

---

## Principes

### 1. Des faits, pas des opinions
Chaque affirmation d'une fiche doit être traçable à une source — page du site, avis clients, métrique SEO, réponse d'IA datée. Signale clairement les inférences.

### 2. Structuré et comparable
Toutes les fiches suivent le même gabarit pour être comparées côte à côte. La cohérence prime sur l'exhaustivité d'une fiche isolée.

### 3. Des données datées
Une fiche est un instantané. Indique toujours la date de génération. Signale ce qui semble périmé (« page tarifs non mise à jour depuis 2023 »).

### 4. Évaluation honnête
N'exagère pas les faiblesses des concurrents, ne minimise pas leurs forces. Une fiche exacte est une fiche utile.

---

## Sauvegarde des données brutes

Avant de synthétiser, persiste les données brutes sur disque pour pouvoir les relire, auditer ou réutiliser sans tout relancer.

**Arborescence** (à la racine du projet) :

```
profils-concurrents/
├── brut/
│   └── <slug-concurrent>/
│       └── <AAAA-MM-JJ>/
│           ├── pages/     # un .md par page lue (accueil.md, tarifs.md, ...)
│           ├── seo/       # un .json par extraction SEO
│           ├── avis/      # un fichier par source d'avis
│           └── ia/        # réponses des IA aux prompts testés (un .md par moteur)
├── <slug-concurrent>.md   # fiche synthétisée
└── _synthese.md           # synthèse trans-concurrents
```

Règles : slug en minuscules avec tirets ; le dossier date permet de relancer et de comparer les instantanés dans le temps ; jamais d'écrasement d'un instantané antérieur.

---

## Processus de recherche

### Phase 1 : lecture des sites

Pour chaque concurrent, identifie puis lis les pages clés : accueil, tarifs, fonctionnalités, à propos, blog (niveau racine), clients/cas clients, intégrations, changelog s'il existe.

| Page | À extraire |
|------|-----------|
| **Accueil** | Titre, sous-titre, proposition de valeur, CTA principal, preuves sociales, signaux de cible |
| **Tarifs** | Paliers, prix (HT/TTC, devise), contenu par palier, options de facturation, essai/gratuit, signaux enterprise |
| **Fonctionnalités** | Catégories, capacités clés, vocabulaire employé |
| **À propos** | Histoire, taille d'équipe, levées, siège |
| **Clients** | Logos nommés, secteurs, thèmes des cas clients |
| **Intégrations** | Nombre, intégrations clés |
| **Changelog** | Vélocité de release, axes récents, direction produit |

Sauvegarde chaque page brute avant d'en extraire les champs.

#### Avis clients (optionnel, forte valeur)

Sources à consulter pour un concurrent actif en France : avis Google (fiche d'établissement), Trustpilot, Appvizer, G2, Capterra ; pour les prestataires de services : Malt, Sortlist. Extrais : note globale, volume, thèmes d'éloges récurrents, thèmes de plaintes récurrents, 3-5 citations représentatives.

### Phase 2 : données SEO et marché

Avec l'outillage disponible (Search Console pour ton propre site ; Haloscan, SEMrush, Ahrefs ou équivalent pour les tiers ; à défaut, opérateurs `site:` et lecture des SERP) :

**Autorité et liens** : rang de domaine, total de backlinks, domaines référents, sites référents notables.

**Mots-clés et trafic** : nombre de mots-clés positionnés (top 3, top 10), trafic organique estimé, pages qui captent le plus de trafic.

**Positionnement concurrentiel** : leurs concurrents organiques les plus proches (révèle parfois des concurrents que tu n'avais pas vus), les recouvrements de mots-clés avec ton site, les trous de contenu.

### Phase 3 : part de voix IA — le volet que les fiches classiques n'ont pas

Le SEO mesure qui ranke sur Google. Ce volet mesure **qui est cité et recommandé par les IA à leur place — et à la tienne**.

#### Protocole

1. **Construis un panel de 10-20 prompts acheteurs** sur ta catégorie : « meilleur [catégorie] pour [cible] », « [concurrent] avis », « alternatives à [concurrent] », « quel outil pour [problème] en France », « comparatif [catégorie] 2026 ».
2. **Pose chaque prompt** dans ChatGPT (avec recherche web), Perplexity, et si possible Google AI Overviews/AI Mode et Gemini. Session propre, sans historique qui biaise.
3. **Note pour chaque réponse** : marques mentionnées (ordre d'apparition), marque recommandée en premier, sources citées (quels domaines l'IA référence).
4. **Calcule par concurrent** :
   - **Taux de mention** = prompts où la marque apparaît / total des prompts
   - **Taux de première place** = prompts où elle est recommandée en premier / total
   - **Sources d'appui** = les domaines tiers qui la font citer (comparatifs, Reddit, presse spécialisée, annuaires)
5. **Archive tout** dans `brut/<slug>/<date>/ia/` avec la date : les réponses des IA bougent vite, l'historique fait la valeur.

#### Lecture stratégique

| Constat | Interprétation | Action |
|---------|----------------|--------|
| Concurrent très cité, sources = comparatifs tiers | Sa force vient du consensus off-site, pas de son site | Cible les mêmes comparatifs et annuaires |
| Concurrent cité via ses propres pages | Contenu très citable (structure, chiffres, définitions) | Analyse la structure de ses pages citées |
| Fort en SEO Google, absent des réponses IA | Fenêtre d'opportunité : le terrain IA n'est pas pris | Investis le panel de prompts en priorité |
| Cité par ChatGPT mais pas Perplexity (ou l'inverse) | Les moteurs pondèrent différemment les sources | Diversifie tes sources d'appui |

Méthodologie détaillée et modèle de suivi : https://www.david-corroy.com/prompts-geo/part-de-voix-ia/

### Phase 4 : synthèse

Croise le tout. Vérifie la cohérence (une revendication « 10 000 clients » est-elle plausible vu le trafic, les avis, les citations ?).

---

## Format de sortie

### Structure de fiche

Un fichier markdown par concurrent : `profils-concurrents/<slug-concurrent>.md`

```markdown
# [Nom du concurrent] — Fiche concurrent

**URL** : [site]
**Générée le** : [date]
**Profondeur** : [scan rapide / profil approfondi]

---

## En un coup d'œil

| Métrique | Valeur |
|----------|--------|
| Slogan | [de l'accueil] |
| Création | [année] |
| Siège | [lieu] |
| Effectif | [estimation] |
| Financement | [si connu] |
| Rang de domaine | [source SEO] |
| Trafic organique estimé | [mensuel] |
| Domaines référents | [nombre] |
| Taux de mention IA | [X % du panel de prompts] |

## Positionnement et messages

**Proposition de valeur** : [titre + sous-titre de l'accueil]
**Cible** : [à qui la copie s'adresse]
**Angle de positionnement** : [ex. « simplicité d'abord », « grade entreprise », « tout-en-un »]
**Thèmes de message** : [3 thèmes, avec page source]

## Produit et fonctionnalités

- Capacités clés, différenciateurs revendiqués, intégrations, signaux de direction produit (changelog)

## Tarifs

| Palier | Prix | Inclus |
|--------|------|--------|
[+ facturation, essai, particularités — par siège, à l'usage, coûts cachés]

## Clients et preuve sociale

Logos nommés, secteurs, thèmes des cas clients, notes d'avis par source.

## SEO et stratégie de contenu

Trafic estimé, top pages organiques, fréquence de publication, types de contenus, profil de liens.

## Part de voix IA

| Moteur | Taux de mention | 1re recommandation | Sources qui le font citer |
|--------|-----------------|--------------------|---------------------------|
| ChatGPT | | | |
| Perplexity | | | |
| AI Overviews | | | |

**Lecture** : [d'où vient sa visibilité IA — ou son absence — et ce que ça t'ouvre]

## Forces et faiblesses

3 forces, 3 faiblesses — chacune avec sa source.

## Implications pour [ton produit]

Où ils sont plus forts / où tu es plus fort / opportunités / menaces.

## Sources des données brutes

Dates de lecture des pages, d'extraction SEO, de collecte d'avis, de passage du panel IA.
```

### Document de synthèse

Après toutes les fiches, génère `profils-concurrents/_synthese.md` :

1. **Vue du paysage** — un paragraphe
2. **Tableau comparatif** — métriques clés côte à côte, y compris la part de voix IA
3. **Carte de positionnement** — simple↔complexe, entrée de gamme↔premium
4. **Enseignements clés** — 3-5 observations stratégiques
5. **Trous et opportunités** — où le marché (et les réponses des IA) sont sous-servis

---

## Scan rapide vs profil approfondi

**Scan rapide** : accueil + tarifs, aperçu SEO, panel IA réduit à 5 prompts. Fiche abrégée.
**Profil approfondi** : toutes les pages + avis + panel IA complet + analyse de contenu. Fiche complète.

Par défaut : scan rapide, sauf demande explicite ou 3 concurrents ou moins.

## Plusieurs concurrents

1. Mêmes métriques pour tous — sinon rien n'est comparable.
2. Le panel de prompts IA est unique et passé pour tous en même temps — c'est ce qui rend la part de voix comparable.
3. La synthèse se construit en dernier.
4. Au-delà de 10 concurrents, propose de commencer par le top 5.

## Mise à jour des fiches

- Pages tarifs d'abord (les plus volatiles)
- Re-passer le panel IA (les réponses bougent d'un mois à l'autre — c'est la métrique la plus instable, donc la plus intéressante à suivre)
- Rafraîchir les métriques SEO
- Mettre à jour la date et consigner les changements dans une section `## Journal des changements`

## Questions à poser

Seulement si le contexte ne répond pas :

1. Quelles URL profiler ?
2. Scan rapide ou approfondi ?
3. Axes prioritaires ? (tarifs, SEO, positionnement, visibilité IA)
4. Comparer les résultats à ton produit ?

## Skill lié

- **competitors** — pour transformer ces fiches en pages comparatives et « alternative à » publiables.
