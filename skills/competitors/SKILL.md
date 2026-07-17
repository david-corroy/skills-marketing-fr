---
name: competitors
description: "Créer des pages comparatives et des pages « alternative à » pour le SEO et l'aide à la vente. Déclencheurs : « page alternative », « page vs », « comparatif concurrent », « [Produit] vs [Produit] », « alternative à [Produit] », « pages de comparaison », « comment on se compare à X », « battle card », « analyse concurrentielle », « mes concurrents sont recommandés par ChatGPT ». Couvre quatre formats : alternative (singulier), alternatives (pluriel), vous vs concurrent, concurrent vs concurrent — plus l'audit des concurrents cités par les IA. Pour les supports commerciaux internes, voir sales-enablement."
metadata:
  version: 2.0.1
---

# Pages comparatives et alternatives

Tu es expert en pages comparatives et « alternative à ». Objectif : des pages qui se classent sur les requêtes concurrentielles, aident réellement les acheteurs en phase d'évaluation, positionnent le produit efficacement — et restent dans les clous du droit français de la publicité comparative.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Comprends :

1. **Le produit**
   - Proposition de valeur, différenciateurs clés
   - Client idéal, modèle de prix
   - Forces et faiblesses honnêtes

2. **Le paysage concurrentiel**
   - Concurrents directs et adjacents
   - Positionnement de chacun
   - Volume de recherche des requêtes concurrentielles

3. **Les objectifs**
   - Capter du trafic SEO
   - Armer les commerciaux
   - Convertir les utilisateurs des concurrents
   - Être recommandé par les IA à la place des concurrents

---

## Le cadre légal français — à lire avant d'écrire

En France, une page qui compare nommément votre produit à un concurrent relève de la **publicité comparative** (articles L.122-1 à L.122-5 du code de la consommation). Elle est licite si et seulement si :

1. Elle **n'est pas trompeuse** — chaque affirmation sur le concurrent doit être exacte et vérifiable à la date de publication.
2. Elle porte sur des biens ou services **répondant aux mêmes besoins** ou ayant le même objectif.
3. Elle compare **objectivement** des caractéristiques **essentielles, pertinentes, vérifiables et représentatives** — prix, fonctionnalités, limites chiffrées. Pas de jugements de valeur invérifiables (« bien meilleur », « largement supérieur »).

Interdits en plus : dénigrement du concurrent, confusion entre les marques, tirer indûment profit de la notoriété d'autrui. Citer la marque du concurrent est permis dans ce cadre — c'est même le principe — mais uniquement pour comparer, jamais dans un usage qui laisse croire à un lien commercial.

**Réflexes pratiques :**
- Chaque ligne de tableau comparatif doit être sourçable (page tarifs du concurrent, documentation, date de relevé).
- Affiche la date de vérification des données (« tarifs relevés le [date] ») et mets à jour au moins trimestriellement — une comparaison exacte hier et fausse aujourd'hui devient trompeuse.
- Reconnaître les forces du concurrent n'est pas seulement honnête : c'est ta meilleure protection juridique et ton meilleur argument de crédibilité.

Le droit et la conversion pointent dans la même direction : factuel, sourcé, daté, équilibré.

---

## Principes

### 1. L'honnêteté construit la confiance
- Reconnais les forces du concurrent, sois exact sur tes limites.
- Le lecteur est en train de comparer : il vérifiera tes affirmations.

### 2. La profondeur bat la surface
- Va au-delà des cases cochées : explique *pourquoi* les différences comptent.
- Cas d'usage et scénarios concrets. Montre, ne te contente pas d'affirmer.

### 3. Aide-le à décider
- Des outils différents pour des besoins différents.
- Dis clairement pour qui tu es le bon choix — et pour qui c'est le concurrent.

### 4. Architecture modulaire
- Les données concurrent sont centralisées : une source de vérité par concurrent, les mises à jour se propagent à toutes les pages.

---

## Qui est cité par ChatGPT et Perplexity à votre place ?

Avant de produire la moindre page, audite le terrain de bataille IA. Les acheteurs demandent désormais « quel outil pour [besoin] ? » à ChatGPT ou Perplexity avant de taper quoi que ce soit dans Google. Si l'IA recommande vos concurrents, vos pages comparatives se battent sur un terrain déjà perdu.

### Le protocole d'audit

1. **Construis un panel de 15-30 prompts acheteurs** : « meilleur [catégorie] pour [cas d'usage] », « alternative à [concurrent leader] », « [concurrent A] ou [concurrent B] ? », « que choisir pour [problème] avec un budget de [X] € ? ».
2. **Passe le panel dans ChatGPT (recherche activée), Perplexity et Google AI Overviews.** Note pour chaque réponse : marques recommandées, ordre de recommandation, **sources citées** (les liens).
3. **Analyse les sources, pas seulement les marques.** C'est l'information stratégique : quels comparatifs tiers, quels articles de presse, quels fils Reddit, quels sites d'avis alimentent la réponse ? Ce sont ces pages-là qui décident qui l'IA recommande.
4. **Croise en tableau :**

| Prompt | Marques recommandées | Vous ? | Sources citées | Vous présent dans ces sources ? |
|--------|---------------------|:------:|----------------|:-------------------------------:|

### Le plan d'action qui en découle

- **Entrer dans les sources qui font autorité** : figurer dans les comparatifs tiers cités, obtenir des avis sur les plateformes reprises (G2, Capterra, Trustpilot, avis Google), exister dans les fils Reddit et forums que l'IA reprend.
- **Rendre tes propres pages comparatives citables** : réponse directe en tête de page (40-80 mots), tableau structuré, données datées et sourcées — le format que les moteurs de réponse extraient.
- **Corriger les inexactitudes** : si l'IA décrit mal ton produit (prix périmé, fonctionnalité « manquante » qui existe), c'est un problème d'entité et de fraîcheur des sources — traite-le en priorité via le skill ai-seo.
- **Refaire l'audit chaque mois** : mêmes prompts, mêmes moteurs, suivi de tendance.

**Lucidité nécessaire :** tes propres pages « alternatives à X » obtiennent souvent des *citations* dans les réponses IA, mais la *recommandation* dépend du consensus web extérieur (avis, forums, presse). Pour une marque émergente, un classement auto-promotionnel peut même faire surfacer les concurrents dans la réponse pendant que tu ne récoltes que la citation. Publie pour l'intention de recherche, mais investis en parallèle les sources tierces.

---

## Les formats de pages

### Format 1 : Alternative à [Concurrent] (singulier)

**Intention** : l'utilisateur cherche activement à quitter un concurrent précis.

**URL** : `/alternatives/[concurrent]` ou `/alternative-[concurrent]`

**Mots-clés** : « alternative à [Concurrent] », « [Concurrent] alternative », « quitter [Concurrent] », « remplacer [Concurrent] »

**Structure :**
1. Pourquoi on cherche une alternative (valider la douleur)
2. Résumé : vous, l'alternative (positionnement rapide)
3. Comparaison détaillée (fonctionnalités, service, prix)
4. Qui devrait changer (et qui ne devrait pas)
5. Chemin de migration
6. Preuve sociale de clients qui ont migré
7. CTA

### Format 2 : Alternatives à [Concurrent] (pluriel)

**Intention** : l'utilisateur explore ses options, plus tôt dans le parcours.

**URL** : `/alternatives/[concurrent]-alternatives` ou `/alternatives-a-[concurrent]`

**Mots-clés** : « alternatives à [Concurrent] », « meilleures alternatives à [Concurrent] », « outils comme [Concurrent] »

**Structure :**
1. Pourquoi chercher une alternative (douleurs fréquentes)
2. Les critères d'un bon remplaçant (grille de lecture)
3. Liste des alternatives (vous en premier, mais avec de vraies options)
4. Tableau comparatif de synthèse
5. Fiche détaillée de chaque alternative
6. Recommandation par cas d'usage
7. CTA

**Important** : inclus 4 à 7 alternatives réelles. Être authentiquement utile construit la confiance et se classe mieux.

### Format 3 : Vous vs [Concurrent]

**Intention** : comparaison directe entre vous et un concurrent nommé.

**URL** : `/vs/[concurrent]` ou `/comparatif/[vous]-vs-[concurrent]`

**Mots-clés** : « [Vous] vs [Concurrent] », « [Concurrent] vs [Vous] », « [Vous] ou [Concurrent] »

**Structure :**
1. Résumé express (différences clés en 2-3 phrases — c'est le bloc que les IA extraient)
2. Tableau comparatif d'un coup d'œil
3. Comparaison détaillée par catégorie (fonctionnalités, prix, support, prise en main, intégrations)
4. Pour qui [Vous] est le bon choix
5. Pour qui [Concurrent] est le bon choix (sois honnête)
6. Témoignages de clients qui ont migré
7. Accompagnement à la migration
8. CTA

### Format 4 : [Concurrent A] vs [Concurrent B]

**Intention** : l'utilisateur compare deux concurrents (pas vous directement).

**URL** : `/comparatif/[concurrent-a]-vs-[concurrent-b]`

**Structure :**
1. Vue d'ensemble des deux produits
2. Comparaison par catégorie
3. Pour qui chacun est fait
4. La troisième option (vous)
5. Tableau à trois colonnes
6. CTA

**Pourquoi ça marche** : capte le trafic des requêtes concurrentielles et te positionne en connaisseur du marché. Rappel : le cadre de la publicité comparative s'applique aussi quand tu compares deux tiers.

---

## Sections essentielles

**Résumé express** — chaque page ouvre sur les différences clés en 2-3 phrases, pour les lecteurs pressés et les moteurs de réponse.

**Comparaisons rédigées** — au-delà des tableaux : pour chaque dimension, un paragraphe qui explique la différence et quand elle compte.

**Comparaison des prix** — palier par palier, ce qui est inclus, les coûts cachés, et un calcul de coût total pour une taille d'équipe type. Datée.

**Pour qui c'est fait** — explicite pour chaque option. Les recommandations honnêtes convertissent.

**Section migration** — ce qui se transfère, ce qui se reconfigure, l'accompagnement proposé, citations de clients qui ont changé.

---

## Architecture de contenu

### Données concurrent centralisées

Crée une source de vérité unique par concurrent :
- Positionnement et audience cible
- Prix (tous les paliers) + date de relevé
- Évaluation des fonctionnalités
- Forces et faiblesses
- Idéal pour / pas fait pour
- Plaintes récurrentes (extraites des avis publics)
- Notes de migration
- **Visibilité IA : recommandé par quels moteurs, sur quels prompts, via quelles sources**

Toutes les pages puisent dans ce fichier : une mise à jour se propage partout.

---

## Processus de recherche

Pour chaque concurrent :

1. **Recherche produit** — inscris-toi, utilise-le, documente fonctionnalités, UX, limites.
2. **Recherche tarifaire** — prix actuels, contenu des offres, coûts cachés. Capture d'écran datée.
3. **Extraction d'avis** — G2, Capterra, Trustpilot, avis Google : thèmes récurrents de louanges et de plaintes.
4. **Retours clients** — parle aux clients qui ont migré (dans les deux sens).
5. **Recherche de contenu** — leur positionnement, leurs propres pages comparatives, leur changelog.

**Cadence de mise à jour :**
- **Trimestrielle** : vérifier les prix, les évolutions majeures — obligation de fond en publicité comparative, pas juste de l'hygiène.
- **Sur signalement** : un client mentionne un changement chez le concurrent.
- **Annuelle** : refonte complète des données + nouvel audit IA complet.

---

## SEO des pages comparatives

### Ciblage

| Format | Mots-clés principaux |
|--------|---------------------|
| Alternative (singulier) | alternative à [Concurrent] |
| Alternatives (pluriel) | meilleures alternatives à [Concurrent] |
| Vous vs Concurrent | [Vous] vs [Concurrent], [Vous] ou [Concurrent] |
| Concurrent vs Concurrent | [A] vs [B], [A] ou [B] |

### Maillage interne
- Lier les pages concurrentielles entre elles.
- Lier depuis les pages fonctionnalités vers les comparatifs pertinents.
- Créer une page hub qui référence tout le contenu comparatif.

### Données structurées
Schéma FAQ pour les questions du type « Quelle est la meilleure alternative à [Concurrent] ? » — c'est aussi un format que les moteurs de réponse extraient volontiers.

---

## Format de sortie

**Fiche concurrent** — profil complet en YAML, réutilisable sur toutes les pages.

**Contenu de page** — URL, balises meta, copie complète section par section, tableaux comparatifs, CTA, date de relevé des données.

**Plan du chantier** — pages recommandées, priorisées par volume de recherche et par présence dans les réponses IA.

---

## Questions à poser

1. Pour quelles raisons les clients migrent-ils vers vous ?
2. As-tu des citations de clients qui ont changé d'outil ?
3. Quels sont tes prix face à ceux des concurrents ?
4. Proposes-tu un accompagnement à la migration ?
5. As-tu déjà testé ce que ChatGPT et Perplexity répondent sur ta catégorie ?
