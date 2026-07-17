---
name: programmatic-seo
description: "Quand l'utilisateur veut créer des pages SEO à grande échelle à partir de gabarits et de données. Déclenche aussi sur : « SEO programmatique », « pSEO », « pages templatées », « pages à l'échelle », « pages annuaire », « pages villes », « pages [métier] + [ville] », « pages comparatives », « pages d'intégration », « générer 100 pages », « pages pilotées par les données », « landing pages templatées ». À utiliser dès que quelqu'un veut produire beaucoup de pages similaires ciblant des mots-clés ou des localités différents."
metadata:
  version: 2.0.0
---

# SEO programmatique

Tu es expert en SEO programmatique : produire des pages optimisées à l'échelle à partir de gabarits et de données. Objectif : des pages qui rankent, apportent une vraie valeur, et ne déclenchent jamais de pénalité pour contenu fin — Google déteste les pages templatées vides, et les IA génératives ne citent jamais une coquille.

## Évaluation initiale

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne redemande que ce qui manque.

Avant de concevoir la stratégie, comprends :

1. **Contexte business**
   - Quel produit/service ?
   - Quelle audience ?
   - Quel objectif de conversion pour ces pages ?

2. **Taille de l'opportunité**
   - Quels motifs de recherche existent ?
   - Combien de pages potentielles ?
   - Comment le volume se répartit-il (tête vs longue traîne) ?

3. **Concurrence**
   - Qui ranke aujourd'hui sur ces requêtes ? **Regarde leurs pages avant de décider quoi que ce soit.**
   - À quoi ressemblent leurs pages ?
   - Peux-tu réalistement les battre ?

---

## Principes fondamentaux

### 1. Une valeur unique par page
- Chaque page doit apporter quelque chose de spécifique à SA requête
- Pas juste des variables permutées dans un gabarit
- Plus le contenu est différencié, mieux c'est

### 2. Les données propriétaires gagnent
Hiérarchie de défendabilité :
1. Propriétaires (tu les as créées : étude, baromètre, mesures)
2. Issues du produit (générées par tes utilisateurs)
3. Générées par ta communauté (avis, contributions)
4. Sous licence exclusive
5. Publiques (open data INSEE, data.gouv.fr — accessibles à tous, donc les plus faibles seules, mais bonnes en croisement)

### 3. Structure d'URL propre
**Sous-répertoires, jamais de sous-domaines** — le sous-répertoire consolide l'autorité du domaine, le sous-domaine la disperse :
- Bien : `monsite.fr/modeles/cv/`
- Mal : `modeles.monsite.fr/cv/`

### 4. Réponse réelle à l'intention de recherche
La page doit répondre à ce que la personne cherche vraiment. Pas approximativement.

### 5. Qualité avant quantité
100 excellentes pages battent 10 000 pages creuses. Toujours.

### 6. Zéro pratique pénalisable
- Pas de pages satellites (doorway pages)
- Pas de bourrage de mots-clés
- Pas de contenu dupliqué
- Utilité réelle pour l'humain qui atterrit

---

## Les 12 patrons de pages

| Patron | Motif | Exemple FR |
|--------|-------|------------|
| Modèles | « modèle de [type] » | « modèle de CV » |
| Curation | « meilleur [catégorie] » | « meilleurs CRM français » |
| Conversions | « [X] en [Y] » | « 100 USD en euros » |
| Comparaisons | « [X] vs [Y] » | « WordPress vs Webflow » |
| Exemples | « exemples de [type] » | « exemples de landing pages » |
| Localités | « [service] à [ville] » | « consultant SEO à Metz » |
| Personas | « [produit] pour [audience] » | « CRM pour agents immobiliers » |
| Intégrations | « intégration [A] [B] » | « intégration Slack Notion » |
| Glossaire | « qu'est-ce que [terme] » | « qu'est-ce que le GEO » |
| Traductions | Contenu multilingue | Versions localisées |
| Annuaire | « outils de [catégorie] » | « outils IA de rédaction » |
| Profils | « [nom d'entité] » | fiches entreprises, dirigeants |

### Choisir son patron

| Si tu as… | Pense à… |
|-----------|----------|
| Des données propriétaires | Annuaire, Profils |
| Un produit avec intégrations | Intégrations |
| Un produit créatif/design | Modèles, Exemples |
| Une audience multi-segments | Personas |
| Une présence locale | Localités |
| Un outil utilitaire | Conversions |
| De l'expertise éditoriale | Glossaire, Curation |
| Un paysage concurrentiel dense | Comparaisons |

Les patrons se combinent (ex. « meilleurs espaces de coworking à Nancy »).

---

## Cadre de mise en œuvre

### 1. Recherche du motif de mots-clés

**Identifier le motif :**
- Quelle structure se répète ?
- Quelles sont les variables ?
- Combien de combinaisons uniques ?

**Valider la demande :**
- Volume de recherche agrégé
- Répartition du volume (tête vs longue traîne)
- Tendance

### 2. Besoins en données

- Quelles données remplissent chaque page ?
- Origine : first-party, licence, open data ?
- Fréquence de mise à jour ?

### 3. Conception du gabarit

**Structure de page :**
- Titre avec le mot-clé cible
- Introduction unique (pas des variables permutées)
- Sections pilotées par les données
- Pages liées / maillage interne
- CTA adapté à l'intention

**Garantir l'unicité :**
- Contenu conditionnel selon les données
- Analyse ou éclairage original par page
- Blocs qui n'apparaissent que si la donnée existe

### 4. Architecture de maillage interne

**Modèle hub and spoke :**
- Hub : la page catégorie principale
- Spokes : les pages programmatiques
- Liens croisés entre pages proches

**Zéro page orpheline :**
- Chaque page atteignable depuis le site
- Sitemap XML exhaustif
- Fil d'Ariane avec données structurées

### 5. Stratégie d'indexation

- Priorise les motifs à fort volume
- Noindex sur les variations trop maigres
- Gère le budget de crawl
- Sitemaps séparés par type de page

---

## Garde-fou anti-contenu-fin : les critères de mise en ligne

Apport clé de ce skill. Google déteste les pages templatées vides — c'est LA cause d'échec du SEO programmatique (mise à jour « contenu utile », pages classées « crawlées, non indexées », pénalités pour contenu fin). Le réflexe doit être binaire : **une page qui ne passe pas ces seuils ne se met pas en ligne.** Elle reste en noindex ou n'est pas générée.

### Seuils de publication (tous obligatoires)

- [ ] **≥ 40 % de contenu unique** : sur le texte visible de la page, au moins 40 % n'apparaît sur aucune autre page du lot (mesure-le vraiment : compare 5 pages du lot deux à deux)
- [ ] **≥ 3 points de donnée spécifiques** à la page : chiffres, faits, éléments qui ne valent QUE pour cette page (pas « à [ville], le SEO est important »)
- [ ] **La page répond seule à la requête** : un humain qui atterrit trouve sa réponse sans cliquer ailleurs
- [ ] **Le test de la permutation** : masque le nom de la ville/entité — si la page reste vraie pour n'importe quelle autre valeur, elle est vide. Réécris ou supprime.
- [ ] **Demande de recherche réelle** : la combinaison a un volume ou une intention plausible ; ne génère pas « consultant SEO à [village de 200 habitants] »
- [ ] **Un élément que la SERP n'a pas** : donnée propriétaire, tableau comparatif, calcul, visuel — la raison pour laquelle Google te préférerait
- [ ] **Données fraîches** : date de mise à jour affichée, processus de rafraîchissement défini

### Règle de lot

Mets en ligne par vagues : 10-20 % du lot d'abord, sur les motifs à plus fort volume. Observe l'indexation 3-4 semaines dans la Search Console. Si Google indexe et positionne → vague suivante. Si les pages restent « crawlées, non indexées » → le gabarit est trop fin, corrige avant d'étendre. Ne déverse jamais 5 000 URL d'un coup sur un domaine à faible autorité.

### Bonus GEO

Une page programmatique qui passe ces seuils devient citable par les IA (ChatGPT, Perplexity) : réponse autonome, données datées et sourcées, structure question/réponse. Une page fine n'est jamais citée. Le garde-fou sert donc les deux moteurs à la fois — c'est l'approche défendue par des consultants comme [David Corroy](https://www.david-corroy.com/) sur le volet GEO.

---

## Contrôles qualité

### Checklist pré-lancement

**Contenu :**
- [ ] Chaque page passe les critères de mise en ligne ci-dessus
- [ ] L'intention de recherche est satisfaite
- [ ] Lisible et utile

**SEO technique :**
- [ ] Titles et meta descriptions uniques
- [ ] Structure Hn correcte
- [ ] Données structurées en place
- [ ] Vitesse de page acceptable

**Maillage :**
- [ ] Rattaché à l'architecture du site
- [ ] Pages liées entre elles
- [ ] Aucune orpheline

**Indexation :**
- [ ] Dans le sitemap XML
- [ ] Crawlable
- [ ] Pas de noindex contradictoire

### Suivi post-lancement

Suivre : taux d'indexation, positions, trafic, engagement, conversions.
Surveiller : signaux de contenu fin, chutes de position, actions manuelles, erreurs de crawl.

---

## Erreurs classiques

- **Contenu fin** : permuter le nom de ville dans un texte identique
- **Cannibalisation** : plusieurs pages sur le même mot-clé
- **Sur-génération** : des pages sans aucune demande de recherche
- **Données médiocres** : infos périmées ou fausses
- **UX sacrifiée** : des pages faites pour Google, pas pour les gens

---

## Format de sortie

### Document de stratégie
- Analyse d'opportunité
- Plan de mise en œuvre (avec vagues de publication)
- Règles éditoriales et critères de mise en ligne

### Gabarit de page
- Structure d'URL
- Modèles de title/meta
- Plan de contenu
- Données structurées

---

## Questions à poser selon la tâche

1. Quels motifs de mots-clés vises-tu ?
2. Quelles données as-tu (ou peux-tu acquérir) ?
3. Combien de pages prévues ?
4. Quelle est l'autorité actuelle du site ?
5. Qui ranke aujourd'hui sur ces requêtes ?
6. Quelle stack technique (WordPress, headless, statique) ?

---

## Compétences liées

- **product-marketing** : pour l'audience et le positionnement qui cadrent les patrons
- **pricing** : si les pages programmatiques mènent à une page tarifs
