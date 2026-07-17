---
name: aso
description: "Auditer et optimiser une fiche App Store ou Google Play. Déclencheurs : « audit ASO », « app store optimization », « optimiser ma fiche d'application », « améliorer la visibilité de mon app », « classement sur l'App Store », « pourquoi personne ne télécharge mon appli », « conversion de ma fiche », « mots-clés pour mon application », « comparer mon app aux concurrents ». À utiliser quand l'utilisateur partage une URL App Store ou Google Play et veut l'améliorer."
metadata:
  version: 2.0.0
---

# Audit ASO

Analyse des fiches App Store et Google Play face aux bonnes pratiques ASO. Récupère les données de la fiche en ligne, note les métadonnées, les visuels et les avis, puis produit un plan d'action priorisé — pour le marché français d'abord.

## Quand utiliser

- L'utilisateur partage une URL App Store ou Google Play.
- Il veut auditer ou optimiser une fiche.
- Il veut comparer son app à des concurrents.
- Il s'interroge sur le classement, la visibilité ou la conversion en téléchargement.

## Avant d'auditer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

---

## Phase 1 — Identifier le store et récupérer la fiche

### Détecter le store depuis l'URL

```
Apple :  apps.apple.com/fr/app/{nom}/id{chiffres}
Google : play.google.com/store/apps/details?id={package}&hl=fr
```

Pour la France, audite la fiche **localisée fr-FR** (`/fr/` chez Apple, `&hl=fr&gl=FR` chez Google). Si l'utilisateur donne un nom d'app sans URL, cherche sur le web : `site:apps.apple.com "{nom}"` ou `site:play.google.com "{nom}"`.

### Récupérer la fiche

Utilise WebFetch et extrais tous les champs disponibles.

**App Store (Apple) :**
- Nom de l'app (titre) — 30 caractères max
- Sous-titre — 30 caractères max
- Description longue — non indexée pour la recherche, mais décisive pour la conversion
- Texte promotionnel — 170 caractères, modifiable sans nouvelle version
- Catégorie (principale + secondaire)
- Captures d'écran (nombre, ordre, textes incrustés)
- Vidéo de prévisualisation (présence, durée)
- Note (moyenne + volume), avis récents visibles
- Prix / achats intégrés, nom du développeur
- Date de dernière mise à jour, notes de version
- Classification d'âge, taille, langues listées
- Événements in-app visibles

**Google Play :**
- Nom de l'app (titre) — 30 caractères max
- Description courte — 80 caractères max
- Description longue — 4 000 caractères, **indexée** pour la recherche
- Catégorie + tags
- Image de présentation (feature graphic)
- Captures, vidéo, note, avis récents
- Prix / achats intégrés, développeur
- Dernière mise à jour, « Nouveautés »
- Fourchette de téléchargements, classification du contenu
- Section « Sécurité des données », langues

Si WebFetch renvoie des données incomplètes (les stores rendent en JavaScript), note les manques et travaille avec ce qui est disponible. Demande à l'utilisateur de coller les champs critiques manquants.

### Évaluation des visuels

WebFetch ne lit ni les captures ni leurs textes. **Prends une capture d'écran de la page** de la fiche (outils navigateur) et évalue : qualité de l'icône, nombre de captures, textes incrustés, qualité des messages, présence de vidéo, feature graphic (Google Play). Sans outils navigateur, demande une capture à l'utilisateur.

**Texte promotionnel (Apple) :** souvent indiscernable de la description dans le HTML récupéré. Si tu ne peux pas confirmer sa présence, dis-le et recommande une vérification dans App Store Connect.

---

## Phase 1 bis — Évaluer la maturité de la marque

Avant de noter, classe l'app dans un des trois profils. Un écart au « manuel ASO » n'a pas le même sens selon qu'il vient d'une marque installée ou d'une app inconnue.

| Profil | Signaux | Exemples (marché FR) |
|--------|---------|----------------------|
| **Dominante** | Notoriété quasi universelle, 1 M+ de notes, top 10 de sa catégorie. On la cherche par son nom. | Doctolib, Leboncoin, Vinted, BlaBlaCar, WhatsApp |
| **Établie** | Connue dans sa catégorie, 100 K+ de notes, fort organique. | Yuka, Too Good To Go, Frichti, Lydia |
| **Challenger** | En construction de notoriété, < 100 K notes, dépend des mots-clés et de l'ASO. La majorité des apps. | Ton app, la plupart des apps indés |

**Effet sur la notation :**
- **Dominante** : titre = marque seule est valide (la marque EST le mot-clé) ; description notée sur la conversion, pas les mots-clés ; photos lifestyle acceptables ; notes de version génériques tolérées à cadence hebdo ; localisation jugée relativement à son marché réel.
- **Établie** : titre marque d'abord mais avec 1-2 mots-clés ; bénéfice du doute sur les choix éditoriaux ; le reste noté normalement.
- **Challenger** : notation stricte, chaque caractère, capture et mot-clé compte.

**Principe :** avant d'enlever des points, demande-toi « erreur, ou choix délibéré d'une équipe qui a des données que je n'ai pas ? ». Une app à 1 M+ de notes avec une équipe ASO dédiée fait rarement des choix au hasard.

---

## Phase 2 — Noter chaque dimension

Note chaque dimension de 0 à 10, en appliquant les ajustements de profil.

| # | Dimension | Poids | Couvre |
|---|-----------|:-----:|--------|
| 1 | Titre & sous-titre | 20 % | Usage des caractères, mots-clés, clarté, équilibre marque/mot-clé |
| 2 | Description | 15 % | 3 premières lignes, densité de mots-clés (Google), CTA, structure, texte promo |
| 3 | Visuels | 25 % | Nombre/qualité/messages des captures, vidéo, icône, feature graphic |
| 4 | Notes & avis | 20 % | Note moyenne, volume, fraîcheur, réponses du développeur |
| 5 | Métadonnées & fraîcheur | 10 % | Catégorie, récence des mises à jour, localisations, sécurité des données |
| 6 | Signaux de conversion | 10 % | Positionnement prix, transparence des achats intégrés, preuve sociale |

**Score final** = somme pondérée, sur 100.

| Score | Note | Lecture |
|-------|:----:|---------|
| 85-100 | A | Bien optimisée ; place aux tests A/B et à l'itération |
| 70-84 | B | Bonne base ; opportunités claires |
| 50-69 | C | Lacunes significatives ; les correctifs priorisés auront un fort impact |
| 30-49 | D | Optimisation majeure nécessaire sur plusieurs dimensions |
| 0-29 | F | Refonte complète de la fiche |

---

## Phase 3 — Comparaison concurrentielle (optionnelle)

Si l'utilisateur fournit des URL concurrentes ou demande une comparaison :

1. Récupère 2-3 concurrents majeurs de la même catégorie (sur le store **français**).
2. Applique la même notation.
3. Tableau comparatif : forces et faiblesses relatives.
4. Écarts de mots-clés : termes que les concurrents ciblent et pas l'app auditée.

Sans concurrents fournis, propose d'en chercher dans le top de la catégorie France.

---

## Phase 4 — Générer le rapport

Le rapport contient :

1. **Carte de scores** — les 6 dimensions, scores et note globale.
2. **Top 3 des victoires rapides** — changements < 1 h à plus fort impact.
3. **Constats détaillés** — par dimension, problèmes précis et correctifs.
4. **Suggestions de mots-clés** — analyse titre/description + écarts concurrents.
5. **Recommandations visuelles** — améliorations précises captures/vidéo.
6. **Plan d'action priorisé** — classé impact vs effort.

Règles du rapport :
- Chaque recommandation est **précise et actionnable** (« Remplacer le sous-titre X par Y » et pas « Améliorer le sous-titre »).
- Compte de caractères fourni pour chaque texte recommandé.
- Différences Apple vs Google signalées quand pertinentes.
- Ce qui n'est pas évaluable sans outil payant (volumes de recherche, positions exactes) est dit explicitement.
- Chaque mot-clé suggéré est justifié.

---

## Règles par plateforme

### App Store (Apple) — l'essentiel

- Texte indexé = titre (30 car.) + sous-titre (30 car.) + champ mots-clés (100 **octets**, invisible).
- Le champ mots-clés se compte en octets : les caractères accentués français (é, à, ç…) pèsent 2 octets en UTF-8 — chaque accent coûte de la place.
- La description longue n'est PAS indexée — optimise-la pour la conversion uniquement.
- Le texte promotionnel (170 car.) n'affecte pas la recherche.
- Ne jamais répéter un mot entre titre / sous-titre / champ mots-clés (chaque mot n'est indexé qu'une fois).
- Champ mots-clés : virgules sans espaces (`photo,retouche,filtre`).
- Captures : jusqu'à 10 par appareil. Les 3 premières apparaissent dans les résultats — 90 % des visiteurs ne dépassent pas la 3e.
- Les textes incrustés dans les captures sont indexés (extraction IA depuis 2025).
- Événements in-app : 10 publiés max, 31 jours chacun, indexés dans la recherche.
- Pages produit personnalisées (jusqu'à 70) visibles en recherche organique — gain moyen de conversion mesurable.
- Vidéo de prévisualisation : jusqu'à 3, 15-30 s, lecture auto sans son — gain de conversion de 20 à 40 %.
- Demande de note in-app : 3 sollicitations max par an par utilisateur.
- Curation éditoriale humaine chez Apple : qualité et design comptent double.

### Google Play — l'essentiel

- Texte indexé = titre (30 car.) + description courte (80 car.) + description longue (4 000 car.).
- La description longue EST indexée — vise 2-3 % de densité de mots-clés, naturellement rédigée.
- Pas de champ mots-clés caché : tout doit être dans le texte visible.
- Compréhension sémantique (NLP) : le bourrage de mots-clés est détecté et pénalisé.
- Interdits dans le titre : émojis, TOUT EN MAJUSCULES, « meilleur »/« n°1 »/« gratuit », appels à l'action.
- Captures : minimum 2, **maximum 8** par appareil (pas 10 comme Apple).
- Feature graphic (1024×500 exact) requise pour les mises en avant.
- La vidéo ne se lance pas automatiquement — ~6 % de taux de lecture (ROI faible vs iOS).
- Android Vitals affecte directement le classement : crash > 1,09 % ou ANR > 0,47 % = visibilité réduite.
- Fiches personnalisées : jusqu'à 50 (ciblage pays, utilisateurs churned, campagnes).
- Tests de fiche (Store Listing Experiments) : 3 variantes max, 7 jours minimum, 1 test à la fois.

### Ce qu'Apple indexe vs ce que Google indexe

| Champ | Apple | Google |
|-------|:-----:|:------:|
| Titre | Oui | Oui (signal le plus fort) |
| Sous-titre / description courte | Oui | Oui |
| Champ mots-clés | Oui (caché) | N'existe pas |
| Description longue | Non | Oui (fortement) |
| Textes des captures | Oui (depuis 2025) | Non |
| Événements in-app | Oui | N/A (LiveOps) |
| Nom du développeur | Non | Partiellement |
| Noms des achats intégrés | Oui | Oui |

---

## Spécificités du marché français

À vérifier systématiquement sur une fiche visant la France :

- **Accents et variantes.** Les utilisateurs tapent avec et sans accents (« theatre » / « théâtre »). Apple : les accents coûtent des octets dans le champ mots-clés — teste la forme non accentuée si la place manque, et couvre les deux formes si le classement diffère. Google : la description longue permet de couvrir naturellement les deux graphies.
- **Anglicismes du secteur.** Sur certains segments, la requête dominante est anglaise même en France (« vpn », « scan », « budget planner ») ; sur d'autres, le français gagne (« cagnotte », « covoiturage », « vide-dressing »). Ne traduis pas les mots-clés : vérifie ce que les gens tapent, via les suggestions de recherche du store en France.
- **Élisions et pluriels.** « l'appli », « appli de course », singulier/pluriel : les stores gèrent mal ces variantes — choisis la forme la plus recherchée, pas la plus correcte grammaticalement.
- **Localisation fr-FR distincte de fr-CA.** Apple les traite séparément : une fiche fr-FR soignée ne couvre pas le Québec, et inversement.
- **Captures localisées.** Interface en français dans les captures ; du texte incrusté anglais sur une fiche France dégrade la conversion et, chez Apple, gaspille l'indexation des captions.
- **Visibilité hors des stores.** Les assistants IA (ChatGPT, Perplexity) recommandent désormais des apps en réponse à « quelle appli pour… ». Ces recommandations s'appuient sur le web (comparatifs, presse tech FR type Les Numériques ou Frandroid, Reddit), pas sur la fiche store. Une app sans présence web tierce est invisible dans ce canal — pense la fiche ET l'écho web autour d'elle.

---

## Checklist des problèmes courants

Les éléments marqués _(selon profil)_ s'évaluent au regard de la maturité de marque — parfois des choix délibérés chez les Dominantes.

**À signaler toujours (tous profils) :**

- [ ] Note sous 4,0
- [ ] Dernière mise à jour > 3 mois
- [ ] Description Google Play sans stratégie de mots-clés (densité < 1 %)
- [ ] Feature graphic manquante (Google Play)
- [ ] Mots probablement répétés dans le champ mots-clés Apple (déduit du titre + sous-titre)
- [ ] Catégorie sous-optimale — moins de concurrence ailleurs
- [ ] Moins de 5 captures

**À signaler pour Challenger/Établie seulement :**

- [ ] Titre = marque seule, sans mot-clé _(Dominante : la marque EST le mot-clé)_
- [ ] Sous-titre/description courte qui duplique les mots-clés du titre
- [ ] 3 premières lignes de description génériques
- [ ] Pas de vidéo de prévisualisation
- [ ] Captures = copies d'écran brutes sans message
- [ ] 1-2 localisations seulement _(juger par rapport au marché réel)_
- [ ] Pas d'événements in-app ni de contenu promotionnel

**À signaler avec contexte :**

- [ ] Pas de réponses du développeur aux avis négatifs _(répondre à 10 M d'avis ≠ répondre à 1 000)_
- [ ] « Nouveautés » génériques _(acceptable à cadence hebdo pour Établie/Dominante)_

---

## Questions à poser

1. Quelle est l'URL App Store ou Google Play ?
2. C'est ton app ou celle d'un concurrent ?
3. Dans quelle catégorie l'app se bat-elle ?
4. As-tu des URL de concurrents à comparer ?
5. Priorité : visibilité en recherche, taux de conversion, ou les deux ?
6. As-tu accès à App Store Connect ou à la Google Play Console ?
