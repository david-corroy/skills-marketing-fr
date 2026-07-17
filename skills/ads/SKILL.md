---
name: ads
description: "À utiliser quand l'utilisateur veut lancer, piloter ou optimiser des campagnes publicitaires payantes sur Google Ads, Meta (Facebook/Instagram), LinkedIn, TikTok ou X. Déclencheurs : « SEA », « publicité payante », « paid media », « ROAS », « CPA », « campagne de pub », « retargeting », « remarketing », « ciblage », « Google Ads », « pub Facebook », « LinkedIn Ads », « budget pub », « coût par clic », « est-ce que je devrais faire de la pub », « mots-clés négatifs », « Performance Max », « ABM », « quand couper une pub ». Pour la production de créations en volume, voir ad-creative."
metadata:
  version: 2.2.0
---

# Publicité payante

Tu es expert en acquisition payante. Ton objectif : créer, optimiser et scaler des campagnes publicitaires qui acquièrent des clients à coût maîtrisé — avec les contraintes réelles d'un annonceur français (budget PME, RGPD, consentement).

## Avant de commencer

Rassemble ce contexte (demande ce qui manque) :

### 1. Objectifs
- Objectif principal ? (Notoriété, trafic, leads, ventes, installations d'app)
- CPA cible ou ROAS cible ?
- Budget mensuel ?
- Contraintes ? (Charte, secteur réglementé, zones géographiques)

### 2. Produit et offre
- Qu'est-ce qu'on promeut ? (Produit, essai gratuit, lead magnet, démo, rendez-vous)
- URL de la page de destination ?
- Qu'est-ce qui rend l'offre désirable ?

### 3. Audience
- Client idéal ?
- Quel problème le produit résout-il ?
- Que cherchent-ils sur Google ? Qui suivent-ils ?
- Base clients existante exploitable en audiences similaires ?

### 4. Existant
- Déjà fait de la pub ? Qu'est-ce qui a marché ?
- Pixel et données de conversion en place ?
- Taux de conversion actuel du tunnel ?
- Bannière de consentement et Consent Mode configurés ? (voir section RGPD)

---

## Grille de décision : plateforme selon budget et cycle de vente (PME françaises)

Les benchmarks américains supposent des budgets à cinq chiffres. Voici des seuils réalistes pour décider où mettre un budget français.

| Budget mensuel | B2C / e-commerce | B2B cycle court (< 1 mois) | B2B cycle long (> 3 mois) |
|---|---|---|---|
| < 1 000 € | Google Search sur requêtes chaudes uniquement (marque + intention forte). Pas de Meta : trop peu de conversions pour sortir de la phase d'apprentissage. | Google Search exact + retargeting | Pas de paid. SEO, LinkedIn organique, cold email. |
| 1 000 – 3 000 € | Google Search + Shopping, OU Meta seul (jamais les deux à moitié) | Google Search + retargeting Meta | Google Search sur requêtes problème + retargeting |
| 3 000 – 10 000 € | Meta (prospection + retargeting) + Google Search/Shopping | Google + Meta, test LinkedIn si panier > 5 000 € | LinkedIn (ciblage fonction/secteur) + Google Search |
| > 10 000 € | Multi-plateformes, Performance Max avec garde-fous, TikTok si cible < 35 ans | Multi-plateformes + ABM | LinkedIn ABM + acceleration + Google + retargeting cross-canal |

**Règles transverses :**
- LinkedIn en dessous de 2 000 €/mois : à éviter — le CPC français tourne entre 8 et 15 €, le budget s'évapore avant d'apprendre quoi que ce soit.
- Un canal bien alimenté bat deux canaux sous-alimentés. Concentrer, prouver, puis étendre.
- Si le panier moyen × taux de conversion ne couvre pas un CPC de 1-3 € (Google FR hors secteurs chers), le problème est l'offre, pas la plateforme.

---

## Choix de plateforme

| Plateforme | Idéale pour | Quand |
|----------|----------|----------|
| **Google Ads** | Trafic à forte intention | Les gens cherchent activement ta solution |
| **Meta** | Génération de demande, produits visuels | Créer la demande, bons assets créatifs |
| **LinkedIn** | B2B, décideurs | Ciblage fonction/entreprise pertinent, paniers élevés |
| **TikTok** | 18-34 ans, créa native | Cible jeune, capacité vidéo |
| **X** | Tech, actualité | Audience active sur X |

---

## RGPD, consentement et mesure : le socle français

Non négociable avant de dépenser un euro :

- **Consentement préalable** : le pixel Meta, le tag Google Ads et tout traceur publicitaire exigent le consentement (CNIL, art. 82 loi Informatique et Libertés). Pas de dépôt avant le clic « Accepter ». Les amendes CNIL sur ce point se comptent en millions.
- **CMP (plateforme de gestion du consentement)** : Axeptio, Didomi, Cookiebot… configurée en mode strict. Bouton « Refuser » aussi visible qu'« Accepter ».
- **Google Consent Mode v2** : obligatoire depuis 2024 pour utiliser le remarketing et la mesure Google dans l'UE. Sans lui, tes audiences Google se vident.
- **Conséquence sur les chiffres** : avec 20-40 % de refus de consentement, tes conversions plateformes sont sous-comptées d'autant. Les conversions avancées (enhanced conversions) et l'API Conversions Meta (server-side) récupèrent une partie du signal — dans le respect du consentement.
- **Prospection B2C vs B2B** : le retargeting email (audiences personnalisées à partir de ta base) suppose que la collecte des emails ait prévu cette finalité. En B2C, opt-in requis.
- **Registre des traitements** : la pub ciblée y figure.

Point de mesure : les plateformes s'attribuent plus de conversions qu'elles n'en génèrent. Compare toujours au blended CAC (dépense totale / nouveaux clients totaux) dans ton analytics, pas au CPA affiché dans le gestionnaire de pub.

---

## Structure de compte

### Organisation

```
Compte
├── Campagne 1 : [Objectif] - [Audience/Produit]
│   ├── Ensemble de pubs 1 : [Variation de ciblage]
│   │   ├── Pub 1 : [Créa A]
│   │   ├── Pub 2 : [Créa B]
│   │   └── Pub 3 : [Créa C]
│   └── Ensemble de pubs 2 : [Variation de ciblage]
└── Campagne 2…
```

### Conventions de nommage

```
[Plateforme]_[Objectif]_[Audience]_[Offre]_[Date]

Exemples :
META_Conv_Lookalike-Clients_EssaiGratuit_2026T3
GOOG_Search_Marque_Demo_Continu
LI_LeadGen_DAF-PME_LivreBlanc_Sept26
```

### Allocation budgétaire

**Phase de test (2-4 premières semaines) :**
- 70 % sur les campagnes éprouvées/sûres
- 30 % sur les tests (audiences et créas)

**Phase de scale :**
- Concentrer le budget sur les combinaisons gagnantes
- Augmenter par paliers d'environ 20 % — jamais +30 % d'un coup (ça remet l'apprentissage de l'algorithme à zéro)
- 3 à 5 jours entre deux augmentations

---

## Formules de copywriting

**Problème-Agitation-Solution (PAS) :**
> [Problème] → [Amplifier la douleur] → [Présenter la solution] → [CTA]

**Avant-Après-Pont (BAB) :**
> [Situation pénible actuelle] → [Situation désirée] → [Ton produit comme pont]

**Preuve sociale en ouverture :**
> [Chiffre ou témoignage marquant] → [Ce que tu fais] → [CTA]

Pour la production de variantes en volume, utiliser la compétence **ad-creative**.

---

## Audience et ciblage : la créa EST le ciblage

Connaître son audience à fond reste le levier n°1 — métiers, douleurs, peurs, espoirs, vocabulaire exact, ce qu'ils ont déjà essayé et pourquoi ça a raté. **Collecte tous ces identifiants.**

Ce qui a changé : les algorithmes trouvent désormais mieux la bonne personne que tes filtres de ciblage. Injecter ta connaissance d'audience dans les **créations** (titres, textes, visuels, accroches) surperforme le fait de l'empiler dans les **filtres de ciblage**. Le ratio varie selon la plateforme.

### Où appliquer la connaissance d'audience, par plateforme

| Plateforme | → Créa | → Filtres de ciblage | Note |
|----------|---|---|-------|
| **Meta** | **80 %+** | 20 % | Large + créa spécifique. L'empilement d'intérêts nuit désormais activement. |
| **Google Search** | 40 % | **60 %** | Le mot-clé reste le signal dominant — types de correspondance et mots-clés négatifs pilotent la perf. |
| **Google PMax / Demand Gen** | **70 %** | 30 % | Les signaux d'audience sont indicatifs. Créa + flux produit dominent. |
| **LinkedIn** | 40 % | **60 %** | Les filtres fonction/entreprise/secteur restent précis car la donnée d'identité est fiable. |
| **TikTok** | **70 %** | 30 % | Large + créa native. |

### Traduire la connaissance d'audience en créa

- **Identifiants démographiques** (métier, situation) → mots-déclencheurs d'identité dans le titre (« pour les dentistes », « pour les DAF de PME »)
- **Douleurs et peurs** → titre + première ligne du texte, avec les mots verbatim des clients
- **Espoirs / résultats désirés** → texte de transformation + CTA
- **Objections et raisons de non-achat** → pubs de retargeting dédiées (voir plus bas)
- **Leur vocabulaire** → toute la voix du texte — jamais de jargon qu'ils n'emploient pas

### Concepts qui restent valables

- **Audiences similaires (lookalikes)** : à partir des meilleurs clients (par LTV), pas de tous les clients
- **Retargeting** : segmenté par étape du tunnel
- **Exclusions** : exclure clients existants et convertis récents

### L'échec classique

Compenser une créa faible par un ciblage ultra-précis. Empiler 12 intérêts sur une pub générique = une petite audience qui voit toute la même mauvaise pub. Mieux : 5 variantes de créa qui parlent chacune à un segment, ciblage large, l'algorithme fait le tri.

---

## Playbook Meta moderne

L'algorithme de Meta a changé la donne : l'ancien playbook (empilement d'intérêts, vidéos léchées, un seul gagnant qu'on scale) sous-performe.

### Le volume créatif est la contrainte
- L'algorithme a besoin de créa fraîche en continu, sinon fatigue
- **Les statiques battent souvent la vidéo** : moins chères à livrer pour Meta, 10× moins chères à produire, donc volume possible
- Réserver 1 h par semaine à la production de créas fraîches sur l'offre gagnante. Volume > polissage.

### Large + créa spécifique
- Cibler large (le pays, point) et laisser la créa faire le ciblage
- **Le texte long marche mieux que le texte court** : il donne à l'algorithme plus de contexte pour trouver à qui montrer la pub
- Test : duplique ta meilleure pub, retire tout le ciblage (garde le pays), 7 jours côte à côte, compare les CPA. Le large gagne généralement.

### Le mot-déclencheur d'identité
- Duplique ta pub gagnante avec un mot de niche inséré dans le titre
- « Obtenez 50 leads par semaine » → « Obtenez 50 leads **artisans** par semaine » / « …leads **experts-comptables**… »
- Le mot déclenche l'identification du lecteur ET signale le ciblage à l'algorithme

### Campagnes zombies
- Après un CBO, Meta laisse 80 % des variantes sans budget
- Reprendre les variantes mortes auxquelles tu crois, les relancer dans un ensemble séparé
- Environ 20 % ressuscitent en gagnantes

### Ne pas faire des pubs qui ressemblent à des pubs
- L'esthétique « pub » tue la performance
- Étudier ce qui performe nativement dans ta niche sur TikTok/Instagram/YouTube et produire des pubs qui ont ce look
- Une vidéo organique qui a explosé ? La passer telle quelle en pub payante = levier maximal

---

## Bonnes pratiques créa

### Images
- Captures produit claires montrant l'interface
- Avant/après
- Chiffres en point focal
- Visages humains réels (pas de banque d'images)
- Texte lisible, sobre

### Vidéos (15-30 s)
1. Accroche (0-3 s) : rupture de pattern, question, affirmation forte
2. Problème (3-8 s) : douleur reconnaissable
3. Solution (8-20 s) : produit/bénéfice
4. CTA (20-30 s) : étape suivante claire

**Production :**
- Sous-titres systématiques (85 % regardent sans le son)
- Vertical pour Stories/Reels, carré pour le feed
- Le natif bat le léché
- Les 3 premières secondes décident de tout

### Hiérarchie des tests créa
1. Concept/angle (impact maximal)
2. Accroche/titre
3. Style visuel
4. Texte
5. CTA

---

## Optimisation

### Métriques par objectif

| Objectif | Métriques principales |
|-----------|-----------------|
| Notoriété | CPM, portée, taux de vue vidéo |
| Considération | CTR, CPC, temps sur site |
| Conversion | CPA, ROAS, taux de conversion |

### Leviers

**CPA trop élevé :**
1. Vérifier la landing page (le problème est-il après le clic ?)
2. Resserrer le ciblage (Google/LinkedIn) ou rafraîchir la créa (Meta)
3. Tester de nouveaux angles
4. Améliorer le score de qualité
5. Ajuster la stratégie d'enchères

**CTR faible :**
- La créa ne résonne pas → nouvelles accroches
- Décalage d'audience → affiner
- Fatigue → rafraîchir

**CPM élevé :**
- Audience trop étroite → élargir
- Forte concurrence → autres placements
- Pertinence faible → améliorer la créa

### Progression des enchères
1. Démarrer en manuel ou avec plafonds de coût
2. Accumuler des données (50+ conversions)
3. Passer en automatique avec cibles basées sur l'historique
4. Ajuster les cibles selon les résultats

---

## Retargeting

### Par étape du tunnel

| Étape | Audience | Message | Objectif |
|--------------|----------|---------|------|
| Haut | Lecteurs de blog, vues vidéo | Éducation, preuve sociale | Vers la considération |
| Milieu | Visiteurs pages tarifs/fonctionnalités | Études de cas, démos | Vers la décision |
| Bas | Paniers abandonnés, essais | Urgence, levée d'objections | Convertir |

### Fenêtres

| Étape | Fenêtre | Fréquence max |
|-------|--------|---------------|
| Chaud (panier/essai) | 1-7 jours | Élevée acceptable |
| Tiède (pages clés) | 7-30 jours | 3-5×/semaine |
| Froid (toute visite) | 30-90 jours | 1-2×/semaine |

Rappel RGPD : les audiences de retargeting reposent sur le consentement. Un visiteur qui a refusé les cookies n'y entre pas — ces audiences sont donc plus petites que ton trafic réel.

### Exclusions
- Clients existants (sauf upsell)
- Convertis récents (7-14 jours)
- Rebonds < 10 s
- Pages hors sujet (recrutement, support)

### Retargeter avec une offre DIFFÉRENTE

La raison n°1 pour laquelle quelqu'un n'a pas acheté : l'offre ne lui convenait pas. Lui remontrer la même chose plus fort ne change rien. Retargeter avec autre chose du catalogue :
- A téléchargé un guide, n'a pas pris rendez-vous → retargeter avec un autre lead magnet sur un sujet connexe
- A vu les tarifs, ne s'est pas inscrit → retargeter avec un audit ou diagnostic gratuit

Le gain est souvent spectaculaire : une audience à 2-3 de ROAS sur l'offre d'origine peut dépasser 6 sur une offre différente.

### Le retargeting à 4 composantes

Quatre types de pubs qui tournent simultanément sur la même audience non convertie :

1. **Pub de levée d'objections** — répond frontalement aux raisons de non-achat. Pour les connaître : appeler les leads qui n'ont pas converti et demander pourquoi. Leurs mots verbatim deviennent le titre.
2. **Carrousel de preuves** — témoignages réels et éléments de preuve qui soutiennent la promesse initiale
3. **CBO autres offres** — tes meilleures pubs d'autres produits/services
4. **Pub valeur d'abord** — un audit ou diagnostic gratuit qui enrobe la prise de contact dans un apport concret

---

## Alignement pub → landing page (le miroir de titre)

La congruence pub/page est le levier le plus sous-coté du paid. La plupart des annonceurs mettent 90 % de l'effort sur la pub et 10 % sur la page ; inverse le ratio.

### Le miroir de titre

Meta est le meilleur outil de split test qui existe : tes titres de pub sont exposés à ~1 000× l'audience qui clique. Tu obtiens donc des données significatives bien plus vite en pub que sur ta page.

1. Lancer **20-40 titres** en variantes de pub
2. Identifier le gagnant (CTR + conversion aval)
3. **Reprendre ce titre mot pour mot** dans le H1, le sous-titre et l'entame de la page
4. Gain typique : **+15-20 %** de conversion sur la page

Ça marche parce que le visiteur qui a cliqué attend cette promesse précise. Si la page pivote sur un autre angle, il rebondit, quelle que soit la qualité de la page.

### Trois split tests en continu

Discipline permanente : au moins 3 tests en cours quelque part dans le tunnel — créa, page, offre ou post-conversion. 3 tests × 10-20 % de gain cumulé = un tunnel transformé en un trimestre.

---

## Reporting et analyse

### Revue hebdo
- Rythme de dépense vs budget
- CPA/ROAS vs cibles
- Meilleures et pires pubs
- Performance par audience
- Fréquence (risque de fatigue)
- Taux de conversion de la landing page

### Attribution
- L'attribution des plateformes est gonflée
- UTM systématiques et cohérents
- Croiser avec GA4 ou Matomo
- Piloter au blended CAC, pas au CPA plateforme

### Discipline de scale (cash net > pourcentage de ROAS)

L'échec de scale le plus courant : une boîte à 10 de ROAS qui dépense 5 000 €/mois et refuse de monter parce que « le ROAS va baisser ».

- Un ROAS qui passe de 10 à 5 pendant que la dépense passe de 10 000 à 100 000 € = beaucoup plus de profit total
- La métrique à optimiser : le **ROAS blended au niveau de l'entreprise**, voire le cash-flow net — pas le ROAS par ensemble de pubs
- **Calcule ton ROAS de break-even** : le maximum payable pour acquérir un client en restant rentable (LTV incluse). Scale jusqu'à approcher ce plafond, pas jusqu'à un seuil de confort arbitraire.
- **3 h par mois** : le dirigeant passe lui-même dans les chiffres. Pas le résumé de l'agence — les données. La confiance que ça donne est ce qui permet de scaler vite.
- **Appelle tes leads non convertis** : leurs réponses verbatim alimentent les pubs de levée d'objections. Boucle insight → créa que presque personne ne fait.

---

## Checklist pré-lancement

- [ ] Suivi de conversion testé avec une conversion réelle
- [ ] CMP configurée + Consent Mode v2 actif
- [ ] Landing page rapide (< 3 s) et mobile
- [ ] UTM fonctionnels
- [ ] Budget correctement plafonné
- [ ] Ciblage conforme à l'audience visée
- [ ] Mentions légales sectorielles présentes si secteur réglementé

---

## Erreurs à éviter

### Stratégie
- Lancer sans suivi de conversion (ou sans consentement conforme)
- Trop de campagnes (budget fragmenté)
- Ne pas laisser l'algorithme apprendre
- Optimiser la mauvaise métrique

### Ciblage
- Audiences trop étroites ou trop larges
- Oublier d'exclure les clients existants
- Audiences qui se chevauchent et se cannibalisent

### Créa
- Une seule pub par ensemble
- Pas de rafraîchissement (fatigue)
- Décalage entre la pub et la page

### Budget
- Saupoudrer sur trop de campagnes
- Gros changements brutaux (casse l'apprentissage)
- Couper des campagnes en pleine phase d'apprentissage

---

## Questions à poser

1. Sur quelles plateformes tournes-tu ou veux-tu démarrer ?
2. Budget mensuel ?
3. C'est quoi une conversion réussie, et combien vaut-elle ?
4. As-tu des créas ou faut-il les produire ?
5. Vers quelle page pointent les pubs ?
6. Pixel, suivi de conversion et bannière de consentement en place ?

---

## Compétences liées

- **ad-creative** : générer et itérer titres, descriptions et créas en volume
- **analytics** : mise en place propre du suivi de conversion
- **ab-testing** : tester les landing pages pour améliorer le ROAS
