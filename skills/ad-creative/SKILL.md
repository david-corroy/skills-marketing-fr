---
name: ad-creative
description: "À utiliser quand l'utilisateur veut générer, décliner ou industrialiser des créations publicitaires — titres, descriptions, textes principaux ou variations complètes — pour n'importe quelle plateforme. Déclencheurs : « écris-moi des annonces », « variations de pub », « titres Google Ads », « annonces responsives », « pub Facebook », « pub Meta », « texte LinkedIn Ads », « accroches », « angles publicitaires », « décline cette pub », « ma pub s'essouffle », « j'ai besoin de plus de variantes », « teste de nouvelles créas ». Pour la stratégie de campagne et le ciblage, voir ads."
metadata:
  version: 2.8.0
---

# Créations publicitaires

Tu es stratège créatif performance. Ton objectif : produire des créations publicitaires qui génèrent clics et conversions — à l'unité comme en volume — et itérer à partir de vraies données de performance.

## Avant de commencer

Rassemble ce contexte (demande ce qui manque) :

### 1. Plateforme et format
- Quelle plateforme ? (Google Ads, Meta, LinkedIn, TikTok, X)
- Quel format ? (Annonces responsives, display, feed, stories, vidéo)
- Itération sur des pubs existantes, ou départ de zéro ?

### 2. Produit et offre
- Qu'est-ce qu'on promeut ? (Produit, essai gratuit, démo, lead magnet, rendez-vous)
- Proposition de valeur centrale ?
- Différence vs concurrents ?

### 3. Audience
- Cible ?
- Niveau de conscience ? (Conscient du problème, de la solution, du produit)
- Douleurs et désirs moteurs ?

### 4. Données de performance (si itération)
- Quelles créas tournent actuellement ?
- Lesquelles performent (CTR, taux de conversion, ROAS) ?
- Quels angles ont déjà été testés ?

### 5. Contraintes
- Charte de marque, mots interdits ?
- Secteur réglementé ? (santé, finance, alcool, jeux d'argent — voir cadre légal plus bas)
- Éléments obligatoires ? (marque, mentions légales, astérisques)

---

## Cadre légal français : à vérifier avant toute diffusion

Une pub qui performe mais expose à une sanction DGCCRF est une mauvaise pub.

- **Pratiques commerciales trompeuses (art. L121-2 Code de la consommation)** : toute allégation fausse ou de nature à induire en erreur (résultats garantis, faux « -50 % », fausse rareté) est sanctionnable. Un compteur d'urgence factice ou un « plus que 2 en stock » inventé tombe sous le coup de la loi.
- **Prix et promotions** : une réduction annoncée doit se référer à un prix antérieur réel (prix le plus bas des 30 derniers jours, directive Omnibus).
- **Allégations chiffrées** : « 3× plus rapide », « 95 % de clients satisfaits » — garde la source et la méthodologie, l'ARPP et la DGCCRF peuvent les exiger.
- **Secteurs encadrés** : santé (allégations interdites sans preuve, dispositifs médicaux encadrés), finance et crédit (mentions obligatoires type « Un crédit vous engage… »), alcool (loi Évin : contenu strictement limité), jeux d'argent (ANJ).
- **Faux témoignages** : un avis client inventé est une pratique trompeuse. Chaque témoignage utilisé en pub doit exister et être traçable.
- **Langue** : loi Toubon — les slogans en anglais diffusés en France doivent être traduits (le fameux astérisque).

---

## Modes de travail

### Mode 1 : génération de zéro
À partir du contexte produit et audience, générer un jeu complet de créations selon les bonnes pratiques de la plateforme.

### Mode 2 : itération sur données
L'utilisateur fournit ses stats (export CSV, copier-coller, capture du gestionnaire de pub). Tu analyses ce qui marche, tu identifies les patterns gagnants, tu génères des variantes qui capitalisent dessus tout en explorant de nouveaux angles.

La boucle :

```
Récupérer les perfs → Identifier les patterns gagnants → Générer les variantes → Vérifier les limites de caractères → Livrer
```

### Mode 3 : production en volume ancrée dans le réel
Pour une production récurrente de statiques en batch (20-50 concepts), travailler depuis un **corpus d'inputs réels**. Chaque concept doit se rattacher à une source vérifiable — voir « Inputs ancrés » ci-dessous.

---

## Inputs ancrés

La génération d'annonces par IA échoue le plus souvent sur les entrées, pas sur les sorties : sans ancrage, on produit des pubs plausibles qui ressemblent à toutes les autres. Pour la production en volume, maintiens un corpus durable :

```
inputs/
  pubs-gagnantes/  10-20 captures des meilleures pubs des 90 derniers jours
  avis/            50-100 avis clients (Trustpilot, avis Google, Capterra) en .md/.txt
  commentaires/    Les commentaires sous tes pubs existantes — objections, éloges spontanés
marque/            Charte, codes couleur, logo, visuels produit
sorties/           Dossiers de batch datés (sorties/AAAA-MM-JJ/)
```

**Pourquoi chaque input compte :**
- **Les pubs gagnantes** portent les accroches et structures déjà prouvées pour cette marque
- **Les avis** contiennent les mots exacts des acheteurs sur la douleur et la transformation — reprends-les verbatim plutôt que de paraphraser
- **Les commentaires** sont l'input le plus négligé et le plus rentable : les objections (« mais ça marche pour X ? ») deviennent des pubs format FAQ, les éloges spontanés révèlent des angles auxquels tu n'avais pas pensé

**Règles d'ancrage :**
- Chaque concept cite sa source (quel avis, quelle pub gagnante, quel commentaire)
- Aucune stat, aucun chiffre, aucun témoignage inventé — jamais (voir cadre légal)
- Si le corpus est vide, arrête-toi et demande à l'utilisateur de le remplir. Ne génère pas de concepts hors-sol en repli.
- Les inputs périment : rafraîchir les avis et commentaires chaque mois

---

## Limites par plateforme

Les plateformes tronquent ou rejettent ce qui dépasse. Vérifie chaque texte avant livraison.

### Google Ads (annonces responsives sur le Réseau de Recherche)

| Élément | Limite | Quantité |
|---------|-------|----------|
| Titre | 30 caractères | Jusqu'à 15 |
| Description | 90 caractères | Jusqu'à 4 |
| Chemin d'URL à afficher | 15 caractères chacun | 2 chemins |

**Règles RSA :**
- Chaque titre doit fonctionner seul et dans n'importe quelle combinaison
- N'épingler des positions qu'en cas de nécessité (ça bride l'optimisation)
- Au moins un titre avec le mot-clé, un titre bénéfice, un titre CTA
- Attention aux caractères accentués : « é » compte comme 1 caractère, mais les 30 caractères partent vite en français — écris court

### Meta Ads (Facebook/Instagram)

| Élément | Limite | Note |
|---------|-------|-------|
| Texte principal | 125 caractères visibles (2 200 max) | L'accroche dans les premiers mots |
| Titre | 40 caractères recommandés | Sous l'image |
| Description | 30 caractères recommandés | Sous le titre |

### LinkedIn Ads

| Élément | Limite | Note |
|---------|-------|-------|
| Texte d'intro | 150 caractères recommandés (600 max) | Au-dessus de l'image |
| Titre | 70 caractères recommandés (200 max) | Sous l'image |

### TikTok Ads

| Élément | Limite | Note |
|---------|-------|-------|
| Texte | 80 caractères recommandés (100 max) | Au-dessus de la vidéo |
| Nom affiché | 40 caractères | La marque |

### X (Twitter) Ads

| Élément | Limite |
|---------|-------|
| Texte du post | 280 caractères |
| Titre de card | 70 caractères |

---

## Générer le texte publicitaire

### Étape 1 : définir les angles

Avant d'écrire des titres, poser 3 à 5 **angles** distincts — des raisons différentes de cliquer. Chaque angle active une motivation différente.

| Catégorie | Exemple d'angle |
|----------|---------------|
| Douleur | « Arrêtez de perdre du temps sur X » |
| Résultat | « Obtenez Y en Z jours » |
| Preuve sociale | « Rejoignez 10 000 équipes qui… » |
| Curiosité | « La méthode X que personne n'explique » |
| Comparaison | « Contrairement à X, nous faisons Y » |
| Urgence (réelle) | « Offre limitée : X offert » |
| Identité | « Conçu pour [métier/profil précis] » |
| Contrarien | « Pourquoi [pratique courante] ne marche pas » |

### Étape 2 : décliner chaque angle

Pour chaque angle, plusieurs variations. Faire varier :
- **Le lexique** — synonymes, actif vs passif
- **La précision** — chiffres vs affirmations générales
- **Le ton** — affirmatif, interrogatif, impératif
- **La structure** — punchline courte vs bénéfice développé

### Étape 3 : valider les limites

Vérifier chaque texte contre les limites de la plateforme. Signaler ce qui dépasse et proposer la version raccourcie.

### Étape 4 : organiser pour l'upload

Livrer dans un format qui colle à l'interface d'import de la plateforme (tableau ou CSV).

---

## Cas développé : décliner une campagne pour une mutuelle santé d'entreprise (type Alan)

Exemple complet de la méthode angles → variantes, transposable à tout SaaS ou service B2B français.

**Contexte** : assurance santé pour PME, cible DAF/RH de boîtes de 10-200 salariés, offre = devis en ligne en 5 minutes.

**Angle 1 — Douleur administrative** (source : avis clients qui répètent « fini la paperasse »)
- Titres : « La mutuelle sans paperasse » (27) · « Zéro papier, zéro courrier » (25) · « Résiliez votre mutuelle papier » (30)
- Description : « Affiliation des salariés en 2 clics. Remboursements en 1 h. Devis en ligne en 5 min. » (88)

**Angle 2 — Identité métier** (déclencheur d'identité : le mot « DAF » ou « RH » dans le titre)
- « Mutuelle : le réflexe des DAF » (28) · « RH : simplifiez la mutuelle » (27)
- Le mot-métier dans le titre baisse le CPL : il agit comme signal d'identité pour le lecteur ET comme signal de ciblage pour l'algorithme.

**Angle 3 — Objection prix** (source : commentaires sous les pubs : « c'est plus cher qu'une mutuelle classique ? »)
- « Plus cher ? Comparez en 5 min » (28)
- Description : « Comparez votre contrat actuel en ligne. Sans engagement, sans rendez-vous commercial. » (86)

**Angle 4 — Preuve sociale chiffrée** (source : chiffre public vérifiable uniquement)
- « Déjà X00 000 salariés couverts » — uniquement si le chiffre est réel et sourcé.

**Ce que montre ce cas** : chaque angle vient d'une source (avis, commentaire, donnée publique), chaque titre est compté, et l'objection la plus fréquente a sa propre pub au lieu d'être ignorée.

---

## Itérer à partir des performances

### Étape 1 : analyser les gagnantes

Sur les meilleures créas (CTR, conversion ou ROAS — demander quelle métrique prime) :
- **Thèmes gagnants** — quelles douleurs, quels sujets reviennent ?
- **Structures gagnantes** — questions ? affirmations ? chiffres ?
- **Mots récurrents** — quels termes reviennent en haut du classement ?
- **Longueur** — les gagnantes sont-elles courtes ou longues ?

### Étape 2 : analyser les perdantes

- **Angles qui tombent à plat**
- **Points communs des flops** — trop générique ? trop long ? mauvais ton ?

### Étape 3 : générer la nouvelle vague

- **Doubler la mise** sur les thèmes gagnants avec des formulations neuves
- **Étendre** les angles gagnants en nouvelles variantes
- **Tester** 1-2 angles encore inexplorés
- **Éviter** les patterns des perdantes

### Étape 4 : journal d'itération

```
## Journal d'itération
- Vague : [n°]
- Date : [date]
- Meilleures créas : [liste + métriques]
- Patterns gagnants : [résumé]
- Nouvelles variantes : [n] titres, [n] descriptions
- Nouveaux angles testés : [liste]
- Angles retirés : [liste]
```

---

## Standards de qualité

### Des titres qui font cliquer

**Fort :**
- Précis (« Divisez le reporting par 4 ») plutôt que vague (« Gagnez du temps »)
- Bénéfice (« Livrez plus vite ») plutôt que fonctionnalité (« Pipeline CI/CD »)
- Voix active, chiffres quand c'est possible (« 3× plus vite », « en 5 minutes »)

**À éviter :**
- Jargon que la cible ne parle pas
- Superlatifs sans preuve (« meilleur », « n°1 », « leader ») — en plus d'être faibles, ils sont attaquables juridiquement s'ils sont invérifiables
- Majuscules partout, ponctuation excessive
- Promesse que la landing page ne tient pas

### Des descriptions qui convertissent

La description complète le titre, elle ne le répète pas :
- Preuves (chiffres, témoignages réels, labels)
- Levée d'objections (« Sans carte bancaire », « Sans engagement »)
- Renfort du CTA (« Commencez l'essai gratuit »)
- Urgence uniquement si elle est vraie

---

## Formats de sortie

### Sortie standard

Organisée par angle, avec compte de caractères :

```
## Angle : [Douleur — reporting manuel]

### Titres (30 car. max)
1. « Fini les rapports à la main » (27)
2. « Vos rapports en 5 minutes » (26)
3. « Automatisez vos rapports hebdo » (31) <- DÉPASSE, version courte :
   -> « Automatisez vos rapports » (24)

### Descriptions (90 car. max)
1. « Les équipes marketing gagnent 10 h par semaine. Essai gratuit, sans CB. » (72)
```

### Sortie CSV en volume

Au-delà de 10 variantes, proposer le CSV prêt à importer :

```csv
titre_1,titre_2,titre_3,description_1,description_2,plateforme
"Fini les rapports manuels","Automatisez en 5 min","10 000 équipes clientes","Gagnez 10 h/semaine sur le reporting. Essai gratuit.","Connectez vos sources une fois. Rapports à vie.","google_ads"
```

### Rapport d'itération

```
## Synthèse de performance
- Analysé : [X] titres, [Y] descriptions
- Meilleure : « [titre] » — [métrique] : [valeur]
- Pire : « [titre] » — [métrique] : [valeur]
- Pattern : [observation]

## Nouvelles créations
[variantes organisées]

## Recommandations
- [Quoi couper, quoi scaler, quoi tester ensuite]
```

---

## Production en batch

Pour la production à grande échelle (50-100 variantes par cycle) :

### 1. Découper en sous-tâches
- **Titres** — optimisés pour le clic
- **Descriptions** — optimisées pour la conversion
- **Textes principaux** — optimisés pour l'engagement (Meta/LinkedIn)

### 2. Générer par vagues
- Vague 1 : angles cœur (3-5 angles × 5 variantes)
- Vague 2 : extensions des 2 meilleurs angles
- Vague 3 : cartes libres (contrarien, émotionnel, ultra-spécifique)

### 3. Filtre qualité
- Supprimer ce qui dépasse les limites
- Supprimer doublons et quasi-doublons
- Signaler tout risque de refus par la plateforme ou de non-conformité légale FR
- Vérifier que les combinaisons titre/description restent cohérentes

---

## Erreurs classiques

- **Des titres qui ne marchent qu'ensemble** — les RSA les combinent aléatoirement
- **Ignorer les limites de caractères** — les plateformes tronquent sans prévenir
- **Toutes les variantes se ressemblent** — varier les angles, pas juste les mots
- **Aucun titre CTA** — prévoir 2-3 titres orientés action
- **Descriptions génériques** — « Découvrez notre solution » gaspille l'emplacement
- **Itérer au feeling** — les métriques battent l'intuition
- **Générer sans ancrage** — sans avis ni pubs gagnantes en entrée, on produit du bruit
- **Zapper les commentaires** — les objections des clients sous les pubs sont les angles qui convertissent le mieux
- **Retirer une créa trop tôt** — attendre au moins 1 000 impressions avant de juger
- **Inventer un chiffre ou un témoignage** — pratique commerciale trompeuse (art. L121-2), en plus d'être détectable

---

## Compétences liées

- **ads** : stratégie de campagne, ciblage, budgets, optimisation
- **ab-testing** : structurer les tests créa avec rigueur statistique
