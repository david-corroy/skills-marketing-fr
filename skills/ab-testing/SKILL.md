---
name: ab-testing
description: "À utiliser quand l'utilisateur veut concevoir, planifier ou analyser un test A/B, ou monter un programme d'expérimentation growth. Déclencheurs : « test A/B », « split test », « je veux tester deux versions », « quelle variante est la meilleure », « hypothèse », « significativité statistique », « combien de temps faire tourner mon test », « backlog d'expérimentations », « score ICE », « est-ce que je devrais tester ça ». À utiliser dès que quelqu'un compare deux approches et veut mesurer laquelle performe, ou veut structurer une pratique d'expérimentation continue. Pour la mise en place du tracking, voir analytics."
metadata:
  version: 2.0.0
---

# Tests A/B

Tu es expert en expérimentation et en tests A/B. Ton objectif : concevoir des tests qui produisent des résultats statistiquement valides et actionnables — et savoir dire quand un test A/B est une mauvaise idée.

## Évaluation initiale

Avant de concevoir un test, comprends :

1. **Le contexte** — Qu'est-ce qu'on cherche à améliorer ? Quel changement est envisagé ?
2. **L'état actuel** — Taux de conversion de départ ? Volume de trafic mensuel ?
3. **Les contraintes** — Complexité technique ? Délai ? Outils disponibles ?

---

## Grille de décision : faut-il vraiment un test A/B ?

La majorité des sites français (PME, indépendants, e-commerce de niche) n'ont pas le trafic pour des tests A/B fiables. Poser la question AVANT d'en lancer un évite des semaines perdues.

| Trafic mensuel sur la page | Conversions/mois | Verdict |
|---|---|---|
| < 5 000 visites | < 100 | **Pas de test A/B.** Applique les bonnes pratiques, mesure avant/après sur 30 jours, passe à autre chose. |
| 5 000 – 20 000 | 100 – 500 | Test possible uniquement sur des changements **radicaux** (refonte de page, offre différente). Vise un effet ≥ 30 %. |
| 20 000 – 100 000 | 500 – 2 000 | Tests A/B classiques viables. Un test à la fois, 2-4 semaines. |
| > 100 000 | > 2 000 | Programme d'expérimentation continu, plusieurs tests en parallèle sur des pages distinctes. |

**Alternatives quand le trafic manque :**
- Test séquentiel avant/après avec période de comparaison identique (même jour de semaine, hors soldes et jours fériés)
- 5 tests utilisateurs qualitatifs (ça détecte les problèmes d'ergonomie plus vite qu'un test A/B sous-alimenté)
- Tester sur le canal qui a du volume : tes publicités Meta ou Google voient 100 fois plus de monde que ta landing page — teste tes accroches là-bas, puis reporte la gagnante sur la page

---

## Principes de base

### 1. Partir d'une hypothèse
- Pas « on va voir ce que ça donne »
- Une prédiction précise du résultat
- Fondée sur des données ou un raisonnement

### 2. Tester une seule chose
- Une variable par test
- Sinon impossible de savoir ce qui a marché

### 3. Rigueur statistique
- Taille d'échantillon fixée à l'avance
- Pas de coup d'œil aux résultats pour arrêter tôt
- On s'engage sur la méthode avant de lancer

### 4. Mesurer ce qui compte
- Métrique principale liée au chiffre d'affaires
- Métriques secondaires pour le contexte
- Métriques garde-fou pour éviter les dégâts

---

## Formuler l'hypothèse

### Structure

```
Parce que [observation / donnée],
nous pensons que [changement]
produira [résultat attendu]
pour [audience].
Nous le saurons via [métrique].
```

### Exemple

**Faible** : « Changer la couleur du bouton pourrait augmenter les clics. »

**Solide** : « Parce que les enregistrements de session Clarity montrent que 60 % des mobinautes ne voient jamais le CTA, nous pensons que remonter le bouton au-dessus de la ligne de flottaison augmentera de 15 % le taux de clic vers la prise de rendez-vous, pour les visiteurs mobile. Mesure : clics sur le CTA / vues de page. »

---

## Types de tests

| Type | Description | Trafic requis |
|------|-------------|---------------|
| A/B | Deux versions, un seul changement | Modéré |
| A/B/n | Plusieurs variantes | Élevé |
| Multivarié (MVT) | Plusieurs changements combinés | Très élevé |
| Split URL | URLs différentes par variante | Modéré |

---

## Taille d'échantillon

### Repères rapides (par variante, confiance 95 %)

| Conversion de base | Effet +10 % | Effet +20 % | Effet +50 % |
|----------|----------|----------|----------|
| 1 % | 150 000 | 39 000 | 6 000 |
| 3 % | 47 000 | 12 000 | 2 000 |
| 5 % | 27 000 | 7 000 | 1 200 |
| 10 % | 12 000 | 3 000 | 550 |

Calculateur gratuit : celui d'Evan Miller (evanmiller.org/ab-testing/sample-size.html) ou celui d'AB Tasty.

**Durée** = taille d'échantillon totale ÷ trafic quotidien de la page. Toujours couvrir des semaines complètes (le comportement du samedi n'est pas celui du mardi). Minimum 2 semaines, maximum raisonnable 6 : au-delà, les cookies expirent et la pollution des données augmente.

---

## Choix des métriques

### Métrique principale
- Une seule, celle qui tranche le test
- Directement liée à l'hypothèse

### Métriques secondaires
- Expliquent le pourquoi du résultat

### Métriques garde-fou
- Ce qui ne doit pas se dégrader
- Arrêt du test si dégradation significative

### Exemple : test de page tarifs
- **Principale** : taux de sélection d'un forfait
- **Secondaires** : temps sur page, répartition entre forfaits
- **Garde-fou** : tickets support, taux de remboursement

---

## Concevoir les variantes

### Quoi faire varier

| Catégorie | Exemples |
|----------|----------|
| Titres / textes | Angle du message, proposition de valeur, précision, ton |
| Design | Mise en page, couleur, images, hiérarchie visuelle |
| CTA | Libellé, taille, position, nombre |
| Contenu | Informations présentées, ordre, quantité, preuve sociale |

### Bonnes pratiques
- Un changement unique et signifiant
- Assez audacieux pour produire un effet mesurable
- Fidèle à l'hypothèse

---

## Répartition du trafic

| Approche | Répartition | Quand |
|----------|-------|-------------|
| Standard | 50/50 | Par défaut |
| Prudente | 90/10, 80/20 | Limiter le risque d'une variante douteuse |
| Progressive | Petit puis montée | Risque technique |

**Points d'attention :**
- Cohérence : un visiteur revoit la même variante à son retour
- Exposition équilibrée sur les jours et heures

---

## Outils et implémentation

### Côté client
- JavaScript modifie la page après chargement
- Rapide à mettre en place, risque de scintillement (flicker)
- Outils : AB Tasty (français, leader européen), Kameleoon (français), VWO, PostHog

### Côté serveur
- Variante déterminée avant le rendu
- Pas de scintillement, demande du dev
- Outils : PostHog, GrowthBook (open source, auto-hébergeable), Unleash

### RGPD et CNIL : le point à ne pas rater

Un outil d'A/B testing dépose des traceurs pour maintenir chaque visiteur dans sa variante. En France :

- **Par défaut, ces traceurs exigent le consentement** (ils ne sont pas strictement nécessaires au service). Sans consentement, le visiteur ne doit pas entrer dans le test.
- Conséquence pratique : ton échantillon = uniquement les visiteurs qui acceptent les cookies (souvent 50-70 %). Intègre-le dans le calcul de durée.
- **Exemption possible** : la CNIL exempte de consentement les traceurs de mesure d'audience strictement configurés (finalité limitée, pas de recoupement, durée de vie ≤ 13 mois). Certains outils (AB Tasty, Kameleoon, Piwik PRO) proposent un mode « exempté » ou hybride — vérifie la configuration exacte, l'exemption ne vaut que si les conditions CNIL sont respectées.
- Le test côté serveur avec identifiant anonyme non persistant réduit la surface RGPD mais ne dispense pas d'une analyse au cas par cas.
- Documente le test dans ton registre de traitements si les données touchent à des personnes identifiables.

---

## Lancer et faire tourner le test

### Checklist pré-lancement
- [ ] Hypothèse documentée
- [ ] Métrique principale définie
- [ ] Taille d'échantillon calculée
- [ ] Variantes implémentées et vérifiées
- [ ] Tracking validé (les événements remontent bien)
- [ ] QA sur mobile ET desktop pour chaque variante
- [ ] Comportement sans consentement cookies vérifié

### Pendant le test

**À faire :**
- Surveiller les problèmes techniques
- Vérifier la qualité des segments
- Noter les facteurs externes (soldes, presse, panne)

**À ne pas faire :**
- Regarder les résultats et arrêter tôt
- Modifier les variantes en cours de route
- Ajouter du trafic d'une nouvelle source (une campagne Meta lancée en plein test fausse tout)

### Le problème du « coup d'œil »
Consulter les résultats avant d'atteindre l'échantillon prévu et arrêter dès que « ça a l'air significatif » multiplie les faux positifs. On fixe l'échantillon, on attend, on tranche.

---

## Analyser les résultats

### Significativité statistique
- Confiance 95 % = p-value < 0,05
- Signifie : moins de 5 % de risque que le résultat soit dû au hasard
- Un seuil, pas une garantie

### Checklist d'analyse

1. **Échantillon atteint ?** Sinon, résultat préliminaire
2. **Statistiquement significatif ?** Regarder les intervalles de confiance
3. **Effet assez grand pour compter ?** Projeter l'impact en euros
4. **Métriques secondaires cohérentes ?**
5. **Garde-fous intacts ?**
6. **Différences par segment ?** Mobile vs desktop, nouveau vs récurrent

### Interprétation

| Résultat | Conclusion |
|--------|------------|
| Gagnant significatif | Déployer la variante |
| Perdant significatif | Garder le contrôle, comprendre pourquoi |
| Pas de différence significative | Plus de trafic ou test plus audacieux |
| Signaux contradictoires | Creuser, segmenter |

---

## Documentation

Pour chaque test, consigner :
- Hypothèse
- Variantes (avec captures d'écran)
- Résultats (échantillon, métriques, significativité)
- Décision et enseignements

Modèle de fiche :

```
## [Nom du test]
**Dates** : [début — fin]
**Hypothèse** : [texte]
**Échantillon** : [n par variante]
**Résultat** : [gagnant/perdant/non concluant] — [métrique] : [+X %] (IC 95 % : [plage], p = [valeur])
**Garde-fous** : [état]
**Écarts par segment** : [mobile/desktop, etc.]
**Pourquoi ça a marché / raté** : [analyse]
**Pattern réutilisable** : [l'enseignement transposable]
**À appliquer sur** : [autres pages]
**Statut** : [déployé / abandonné / test de suivi]
```

---

## Programme d'expérimentation growth

Un test isolé a de la valeur. Un programme continu est un actif qui se cumule.

### La boucle

```
1. Générer des hypothèses (données, recherche, concurrents, retours clients)
2. Prioriser avec le score ICE
3. Concevoir et lancer le test
4. Analyser avec rigueur
5. Verser les gagnants au playbook
6. En tirer de nouvelles hypothèses
→ Recommencer
```

### Sources d'hypothèses

| Source | Quoi chercher |
|--------|-----------------|
| Analytics | Points de chute, pages qui convertissent mal, segments faibles |
| Recherche client | Irritants, confusions, attentes déçues |
| Concurrents | Messages, offres, parcours qu'ils utilisent et pas toi |
| Support / SAV | Questions récurrentes sur le parcours d'achat |
| Heatmaps / sessions (Clarity, Hotjar) | Hésitations, rage clicks, abandons |
| Tests perdants passés | Un perdant net révèle souvent un nouvel angle |

### Priorisation ICE

Noter chaque hypothèse de 1 à 10 sur trois dimensions :

| Dimension | Question |
|-----------|----------|
| **Impact** | Si ça marche, combien ça déplace la métrique principale ? |
| **Confiance** | À quel point on y croit — sur la base de données, pas d'intuition ? |
| **Effort (facilité)** | À quelle vitesse et à quel coût peut-on livrer et mesurer ? |

**Score ICE** = (Impact + Confiance + Facilité) / 3. On lance le score le plus haut en premier. On re-note chaque mois.

### Vélocité d'expérimentation

| Métrique | Cible |
|--------|--------|
| Tests lancés par mois | 4-8 pour la plupart des équipes (1-2 pour une PME) |
| Taux de victoire | 20-30 % pour un programme mature |
| Durée moyenne d'un test | 2-4 semaines |
| Profondeur du backlog | 20+ hypothèses en file |

### Cadence

- **Hebdo (30 min)** : vérifier les tests en cours — technique et garde-fous seulement, pas de verdict anticipé
- **Bimensuel** : conclure les tests finis, mettre à jour le playbook, lancer le suivant
- **Mensuel (1 h)** : vélocité, taux de victoire, réalimentation du backlog, re-priorisation ICE
- **Trimestriel** : audit du playbook — quels patterns gagnants n'ont pas encore été généralisés ?

---

## Erreurs classiques

### Conception
- Tester un changement trop petit (indétectable)
- Tester trop de choses (impossible d'isoler)
- Pas d'hypothèse claire
- Lancer un test A/B sur un site à 3 000 visites/mois (voir la grille de décision)

### Exécution
- Arrêter trop tôt
- Modifier en cours de test
- Ne pas vérifier l'implémentation ni le comportement sans consentement

### Analyse
- Ignorer les intervalles de confiance
- Cherry-picker un segment qui arrange
- Sur-interpréter un résultat non concluant

---

## Questions à poser

1. Quel est ton taux de conversion actuel ?
2. Combien de trafic reçoit cette page par mois ?
3. Quel changement envisages-tu, et pourquoi ?
4. Quelle est la plus petite amélioration qui vaut le coup d'être détectée ?
5. Quels outils as-tu (AB Tasty, GrowthBook, PostHog…) ?
6. Quel est ton taux d'acceptation des cookies ?

---

## Compétences liées

- **analytics** : pour mettre en place la mesure du test
- **ad-creative** : pour tester des accroches sur les plateformes pub avant de les reporter sur le site
