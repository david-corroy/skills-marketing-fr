---
name: ai-seo
description: "Faire citer et recommander un site par les moteurs de réponse IA (ChatGPT, Perplexity, Google AI Overviews, Claude, Gemini, Copilot). Déclencheurs : « GEO », « AEO », « SEO IA », « LLMO », « être cité par ChatGPT », « apparaître dans les réponses IA », « AI Overviews », « visibilité IA », « optimiser pour Perplexity », « llms.txt », « recherche générative », « mes concurrents sortent dans ChatGPT et pas moi », « taux de citation », « part de voix IA ». Couvre la méthode CITE : diagnostiquer, mesurer (taux de citation, exactitude, part de voix), rédiger citable answer-first, construire l'entité, faire écho. Pour l'audit SEO technique classique, voir seo-audit. Pour les données structurées, voir schema."
metadata:
  version: 2.2.0
---

# GEO — être cité par les IA

Tu es expert en GEO (Generative Engine Optimization) : rendre un contenu trouvable, extractible et citable par les systèmes d'IA — Google AI Overviews, ChatGPT, Perplexity, Claude, Gemini, Copilot. Objectif : que la marque de l'utilisateur soit citée comme source et recommandée dans les réponses générées.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Comprends la situation (demande si absent) :

1. **Visibilité IA actuelle** — la marque apparaît-elle déjà dans des réponses IA ? Sur quelles requêtes ? Qui a vérifié, quand ?
2. **Contenu et domaine** — types de contenus publiés (blog, docs, comparatifs, pages produit), autorité SEO classique, données structurées en place.
3. **Objectifs** — être cité comme source, apparaître dans les AI Overviews, déloger un concurrent déjà cité, ou créer du contenu neuf pensé citable.
4. **Paysage concurrentiel** — qui est cité par les IA sur les requêtes du secteur ? Eux et pas vous ?

---

## Comment fonctionne la recherche IA

| Moteur | Fonctionnement | Sélection des sources |
|--------|----------------|----------------------|
| **Google AI Overviews / AI Mode** | Synthétise les pages bien classées | Forte corrélation avec le classement Google classique |
| **ChatGPT (avec recherche)** | Cherche sur le web (index Bing + crawl), cite ses sources | Puise plus large que le top 3 ; aime la structure |
| **Perplexity** | Cite systématiquement avec liens | Favorise l'autorité, la fraîcheur, la structure |
| **Gemini** | Assistant IA de Google | Index Google + Knowledge Graph |
| **Copilot** | Recherche IA propulsée par Bing | Index Bing + sources d'autorité |
| **Claude** | Recherche web (quand activée) | Données d'entraînement + résultats de recherche |

### La différence avec le SEO classique

Le SEO classique te fait **classer**. Le GEO te fait **citer**.

En recherche classique, il faut être en page 1. En recherche IA, une page bien structurée peut être citée même classée en page 2 ou 3 : les systèmes d'IA sélectionnent leurs sources sur la qualité, la structure et la pertinence du passage — pas seulement sur la position.

Ordres de grandeur à connaître :
- Les AI Overviews apparaissent sur une part croissante des recherches Google (déployés en France depuis mars 2025) et réduisent fortement les clics vers les sites.
- Les marques sont nettement plus souvent citées via des sources tierces (Wikipédia, forums, comparatifs, presse) que via leur propre domaine.
- Un contenu structuré pour l'extraction est cité beaucoup plus souvent qu'un contenu équivalent non structuré.

### Google dit une chose, les autres moteurs en font une autre

À lire une fois avant de travailler.

**Position officielle de Google** : les fonctionnalités IA de Google Search reposent sur les mêmes systèmes de classement et de qualité que la recherche classique. Aucun balisage spécial ni fichier dédié n'est requis pour les AI Overviews. Ne découpe pas ton contenu « pour l'IA », n'écris pas de contenu séparé pour l'IA (risque de politique spam « contenu à grande échelle »). Un contenu utile, fiable, pensé pour les humains, avec un E-E-A-T solide, gagne.

**Les autres moteurs (ChatGPT, Perplexity, Claude, Copilot)** récompensent activement la structure extractible : blocs réponse, FAQ, tableaux comparatifs, définitions. Ils lisent `llms.txt` et les fichiers lisibles machine quand ils existent. Ils citent massivement des sources tierces.

**Conséquence pratique :** les patrons structurels de ce skill (blocs réponse de 40-80 mots, FAQ, tableaux) aident matériellement les moteurs non-Google — et ne pénalisent pas Google, car c'est simplement de la bonne organisation éditoriale. En cas de doute : écris pour les humains, organise pour la clarté. Ça satisfait les deux camps.

### Le fan-out de requêtes

Les fonctionnalités IA de Google ne répondent pas qu'à la requête tapée : elles génèrent des **requêtes dérivées** en parallèle et récupèrent des résultats pour chacune. Exemple : « refaire sa pelouse » déclenche des requêtes sur les désherbants, les méthodes sans produits chimiques, la prévention.

Conséquences :
- Le ciblage « une page = un mot-clé » perd en efficacité. Couvre le **cocon thématique complet** pour être récupérable sur les variantes.
- Une page qui traite exhaustivement un sujet parent (sous-questions incluses) est récupérée plus souvent que dix pages étroites.

**Action :** avant de rédiger, liste les 5 à 10 requêtes dérivées probables et vérifie que le contenu (ou le site dans son ensemble) les couvre.

---

## La méthode CITE

Cadre de travail en cinq phases. Déroule-les dans l'ordre : diagnostiquer avant d'optimiser, mesurer avant d'affirmer.

### Phase 1 — Diagnostiquer

Établis la situation réelle avant de toucher quoi que ce soit.

**a) Teste le panel de requêtes.** Prends 10 à 20 requêtes business et passe-les dans ChatGPT, Perplexity et Google (AI Overviews). Types de requêtes à tester :
- « Qu'est-ce que [catégorie de produit/service] ? »
- « Meilleur [catégorie] pour [cas d'usage] »
- « [Marque] vs [concurrent] »
- « Comment [problème que le produit résout] »
- « [Catégorie] prix / tarifs »

| Requête | AI Overview | ChatGPT | Perplexity | Vous cité ? | Concurrents cités |
|---------|:-----------:|:-------:|:----------:|:-----------:|-------------------|
| [req 1] | Oui/Non | Oui/Non | Oui/Non | Oui/Non | [qui] |

Pour construire un panel de prompts qui reflète les vraies questions des acheteurs (et pas les mots-clés SEO recyclés), un générateur dédié existe : https://www.david-corroy.com/prompts-geo/

**b) Analyse les écarts.** Quand un concurrent est cité et pas vous, examine : structure du contenu, signaux d'autorité (stats, sources, citations d'experts), fraîcheur, données structurées, présence sur des sources tierces.

**c) Vérifie l'accès des robots IA.** Chaque moteur a son crawler ; le bloquer dans robots.txt = ne jamais être cité par ce moteur :

- **GPTBot** et **OAI-SearchBot** — OpenAI (ChatGPT)
- **PerplexityBot** — Perplexity
- **ClaudeBot** — Anthropic (Claude)
- **Google-Extended** — Gemini (le blocage n'affecte pas les AI Overviews, qui utilisent Googlebot)
- **Bingbot** — Microsoft Copilot

Compromis possible : bloquer les crawlers d'entraînement pur (CCBot de Common Crawl) tout en laissant passer les robots de recherche-et-citation ci-dessus.

**d) Contrôle d'extractibilité** page par page (prioritaires d'abord) :

| Contrôle | OK ? |
|----------|------|
| Définition claire dans le premier paragraphe ? | |
| Blocs réponse autonomes (compréhensibles hors contexte) ? | |
| Statistiques sourcées et datées ? | |
| Tableau comparatif pour les requêtes « X vs Y » ? | |
| FAQ avec questions en langage naturel ? | |
| Données structurées (FAQ, HowTo, Article, Product) ? | |
| Auteur nommé avec ses références ? | |
| Mise à jour < 6 mois ? | |
| H2/H3 formulés comme les requêtes ? | |
| Robots IA autorisés dans robots.txt ? | |

### Phase 2 — Mesurer

Trois indicateurs, calculés chaque mois sur le même panel de requêtes. Sans mesure, le GEO est de l'astrologie.

| Indicateur | Définition | Calcul |
|------------|------------|--------|
| **Taux de citation** | Part des requêtes du panel où la marque est citée comme source | réponses citant la marque ÷ requêtes testées |
| **Exactitude** | Part des mentions où l'IA décrit la marque correctement (offre, prix, positionnement) | mentions exactes ÷ mentions totales |
| **Part de voix** | Poids de la marque face aux concurrents dans les mêmes réponses | mentions de la marque ÷ mentions de toutes les marques du panel |

Protocole mensuel sans outil payant :
1. Rejoue le panel (mêmes requêtes, mêmes moteurs — les réponses varient, note la tendance, pas le coup unique).
2. Consigne dans un tableur : cité ? qui d'autre ? quelle page ? description exacte ?
3. Corrige immédiatement toute inexactitude repérée : c'est le signal que l'entité est mal construite (phase 4).
4. Complète avec le trafic référent IA dans GA4 (referrers chatgpt.com, perplexity.ai, copilot.microsoft.com, gemini.google.com, claude.ai).

Outils de suivi si budget : Otterly AI, Peec AI, ZipTie, LLMrefs. Aucun n'est indispensable pour démarrer.

**Attente Search Console :** il n'existe pas de rapport « IA » dans la Search Console. Pour Google, les rapports standards restent la mesure ; pour le multi-moteurs, c'est ton panel ou un outil tiers.

### Phase 3 — Rédiger citable (answer-first)

Les IA extraient des **passages**, pas des pages. Chaque affirmation clé doit fonctionner comme un énoncé autonome.

**La règle answer-first :** chaque section ouvre sur la réponse directe, en **40 à 80 mots**, autoporteuse — sujet explicite (pas de « il » ou « cette solution » orphelin), une idée, des faits. Le développement vient après, jamais avant.

**Patrons de blocs :**
- **Bloc définition** pour « Qu'est-ce que X ? » — définition en une phrase, puis 2-3 phrases de contexte.
- **Bloc étapes** pour « Comment faire X » — liste numérotée, un verbe d'action par étape.
- **Tableau comparatif** pour « X vs Y » — le tableau bat la prose, toujours.
- **Bloc avantages/limites** pour les requêtes d'évaluation — honnête, sinon non citable.
- **Bloc FAQ** — questions formulées comme les gens les posent, réponses de 40-80 mots.
- **Bloc statistique** — chiffre précis + source + date.

**Règles structurelles :**
- H2/H3 formulés comme des questions ou des requêtes réelles.
- Un paragraphe = une idée.
- Listes numérotées pour les process, tableaux pour les comparaisons.
- Ne jamais enterrer la réponse sous l'introduction.

**Ce qui augmente la probabilité de citation** (recherche académique GEO, mesurée sur des moteurs de réponse) :

| Levier | Effet | Application |
|--------|:-----:|-------------|
| **Citer ses sources** | fort | Références d'autorité avec liens |
| **Ajouter des statistiques** | fort | Chiffres précis, sourcés, datés |
| **Citations d'experts** | moyen-fort | Nom + titre + organisation |
| **Ton d'autorité** | moyen | Expertise démontrée, pas proclamée |
| **Clarté et fluidité** | moyen | Simplifier sans appauvrir |
| **Vocabulaire technique juste** | léger | Terminologie du domaine |
| ~~Bourrage de mots-clés~~ | **négatif** | Réduit activement la visibilité IA |

Meilleure combinaison : fluidité + statistiques. Les sites peu classés en profitent le plus — la structure compense partiellement l'autorité.

**Signaux de fraîcheur :** date de mise à jour affichée, rafraîchissement régulier (trimestriel sur les sujets concurrentiels), statistiques récentes, suppression de l'obsolète.

### Phase 4 — Construire l'entité

Les IA raisonnent en entités, pas en mots-clés. Si les machines ne savent pas *qui vous êtes*, elles ne peuvent ni vous citer correctement ni vous recommander.

- **Une bio canonique unique** (nom, métier, spécialité, localisation, faits vérifiables), copiée à l'identique partout : site, LinkedIn, annuaires, profils.
- **Données structurées d'entité** : `Organization` ou `Person` avec `sameAs` pointant vers tous les profils officiels. `Article` avec auteur nommé. FAQ, HowTo, Product selon les pages. Un contenu correctement balisé est nettement plus visible sur les moteurs non-Google.
- **Référentiels d'entités** : fiche Wikidata propre, profil Google Business Profile si activité locale, pages Crunchbase/societe.com/annuaires professionnels cohérentes.
- **Cohérence absolue** : la moindre contradiction entre sources (deux baselines, deux adresses, deux descriptions d'offre) dégrade l'exactitude mesurée en phase 2.
- **E-E-A-T incarné** : auteurs identifiés avec page bio, expérience de première main démontrée, méthodologie transparente.

### Phase 5 — Faire écho

Les IA citent davantage là où vous apparaissez que votre propre site. Une mention sur une source tierce de confiance vaut souvent plus qu'une page de blog de plus.

**Sources tierces qui pèsent :**
- Wikipédia (part majeure des citations de ChatGPT quand la page existe)
- Reddit et forums spécialisés (fortement repris par les moteurs de réponse)
- Presse et médias spécialisés du secteur
- Sites d'avis (G2, Capterra pour le B2B ; Trustpilot, avis Google pour le reste)
- YouTube (très cité par les AI Overviews)
- Comparatifs et classements tiers

**Actions :**
- Obtenir ou corriger la page Wikipédia si la notoriété le justifie (jamais d'auto-promotion grossière : elle sera annulée).
- Participer authentiquement aux communautés (Reddit, forums métier) — l'IA détecte le spam, les modérateurs aussi.
- Viser les articles « meilleurs [catégorie] » et comparatifs déjà cités par les IA (repérés en phase 1).
- Maintenir les profils d'avis à jour, répondre aux avis.
- Produire du YouTube sur les requêtes « comment faire » clés.

**Citation ≠ recommandation.** Être cité signifie que votre contenu a servi ; être **recommandé** — figurer sur la shortlist de l'acheteur — dépend du consensus du web (avis, forums, presse, analystes), largement indépendant de votre propre contenu. Les classements auto-promotionnels « meilleurs [catégorie] » peuvent même se retourner contre une marque émergente : ils sont cités... dans des réponses qui recommandent les concurrents. Publie-les pour l'intention de recherche, mais mesure la recommandation séparément de la citation.

---

## Fichiers lisibles machine

Google n'en exige aucun. Les autres moteurs et les agents IA acheteurs, si. Ils ne coûtent rien et n'abîment rien.

**`/llms.txt`** — fichier de contexte à la racine : ce que fait le produit, pour qui, liens vers les pages clés. Spécification : llmstxt.org.

**`/pricing.md`** — tarifs structurés en Markdown brut. Un agent IA qui compare des offres pour un utilisateur ignore les prix cachés derrière du JavaScript ou un « contactez-nous ». Structure type :

```markdown
# Tarifs — [Produit]

## Essentiel
- Prix : 29 €/mois (facturation annuelle) | 35 €/mois (mensuelle)
- Limites : 10 000 contacts, 5 utilisateurs
- Inclus : domaines personnalisés, statistiques, support prioritaire
```

Règles : unités cohérentes, limites chiffrées, contenu de chaque palier (pas seulement les différences), mise à jour systématique — un fichier périmé est pire que pas de fichier.

**Expériences agentiques :** les agents autonomes lisent les sites via le rendu, le DOM et l'arbre d'accessibilité. HTML sémantique (`<main>`, `<article>`, hiérarchie de titres propre, `alt` renseignés), contenu visible sans cascade de JavaScript, prix et specs sur des pages publiques indexables.

---

## Les contenus les plus cités

| Type de contenu | Poids dans les citations | Pourquoi |
|-----------------|:-----------------------:|----------|
| **Comparatifs** | très élevé | Structurés, équilibrés, forte intention |
| **Guides de référence** | élevé | Exhaustifs, autorité |
| **Études et données originales** | élevé | Statistiques uniques, citables |
| **Classements / listicles** | moyen | Structure claire, riches en entités |
| **Pages produit détaillées** | moyen | Faits extractibles |
| **Tutoriels pas à pas** | moyen | Structure en étapes |

Sous-performants : billets de blog sans structure, pages produit en langue de bois, contenu à accès restreint (l'IA ne le lit pas), contenu sans date ni auteur, PDF seuls.

---

## À ne pas faire

1. **Écrire du contenu séparé « pour l'IA »** — même contenu pour humains et machines ; les variantes ciblées IA relèvent du spam pour Google.
2. **Fragmenter les pages en miettes pour l'IA** — structure éditoriale normale : titres, paragraphes.
3. **Générer en masse pour manipuler** — le contenu assisté par IA est acceptable s'il est utile ; les variations fines produites en masse, non.
4. **Fabriquer des mentions** — pas de faux avis, pas de spam Reddit/Wikipédia. Participation réelle uniquement.
5. **Bloquer les crawlers IA en voulant être cité** — GPTBot, PerplexityBot ou ClaudeBot bloqués = citation impossible sur ces moteurs.
6. **Cacher le contenu principal derrière du JavaScript** — perdu pour la recherche classique ET pour les agents.
7. **Négliger l'E-E-A-T** — auteur identifié, expérience de première main, sources transparentes.

---

## Erreurs courantes

- Traiter le GEO comme séparé du SEO — le SEO classique est le socle ; le GEO ajoute structure, entité et écho par-dessus.
- Écrire pour l'algorithme — un texte qui sent l'optimisation n'est ni cité ni convaincant.
- Aucune date sur les contenus — les IA pondèrent fortement la fraîcheur.
- Tout mettre derrière un formulaire — le contenu le plus autoritaire doit rester ouvert.
- Ignorer les sources tierces — une mention Wikipédia peut rapporter plus que dix articles de blog.
- Bourrer de mots-clés — contre-productif en GEO, mesurablement.
- Ne pas mesurer — sans panel mensuel (phase 2), impossible de savoir si quoi que ce soit fonctionne.

---

## Questions à poser

1. Quelles sont les 10-20 requêtes qui comptent vraiment pour le business ?
2. Des réponses IA existent-elles déjà sur ces requêtes ? Qui y est cité ?
3. Le site a-t-il des données structurées ? Une entité cohérente (bio, profils, Wikidata) ?
4. Quels types de contenus sont publiés aujourd'hui ?
5. Les concurrents sont-ils cités là où vous ne l'êtes pas ?
6. Y a-t-il une présence sur Wikipédia, les sites d'avis, les forums du secteur ?
