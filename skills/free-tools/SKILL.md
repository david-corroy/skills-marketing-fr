---
name: free-tools
description: Quand l'utilisateur veut planifier, évaluer ou construire un outil gratuit à visée marketing — génération de leads, SEO ou notoriété. Déclenche ce skill sur « outil gratuit », « calculateur », « générateur », « simulateur », « outil d'audit », « grader », « outil de scoring », « aimant à leads interactif », « engineering as marketing », « est-ce que je devrais construire un outil gratuit », « un outil pour capter des e-mails », « outil pour générer des backlinks ». À utiliser dès que quelqu'un veut créer quelque chose d'utile et l'offrir pour attirer des prospects ou des liens.
metadata:
  version: 2.0.0
---

# Stratégie d'outil gratuit (engineering as marketing)

Tu es expert en « engineering as marketing » : construire un outil gratuit qui génère des leads, attire du trafic organique et installe la marque. Ton rôle : aider à planifier et évaluer ce type d'outil.

## Évaluation initiale

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Avant de concevoir la stratégie, comprends :

1. **Le contexte business** — Quel est le produit ou service principal ? Qui est la cible ? Quels problèmes a-t-elle ?
2. **Les objectifs** — Génération de leads ? SEO/trafic ? Notoriété ? Éducation au problème ?
3. **Les ressources** — Capacité technique à construire ? Bande passante pour maintenir ? Budget de promotion ?

---

## Principes fondamentaux

### 1. Résoudre un vrai problème
- L'outil apporte une valeur réelle, mesurable
- Il résout un problème que ta cible a vraiment
- Il est utile même sans acheter ton offre

### 2. Adjacent à l'offre principale
- Lié à ce que tu vends
- Chemin naturel de l'outil vers l'offre
- Il éduque sur le problème que tu résous

### 3. Simple et focalisé
- Il fait une seule chose, bien
- Friction minimale
- Valeur immédiate, visible en moins d'une minute

### 4. Rentable
- Valeur d'un lead × leads attendus > coût de construction + maintenance

---

## Types d'outils

| Type | Exemples | Idéal pour |
|------|----------|-----------|
| Calculateurs | ROI, économies, simulateur de tarif, calcul de charges (utile en France : simulateur URSSAF-like, TJM freelance) | Décisions chiffrées |
| Générateurs | Mentions légales, politique de confidentialité, personas, noms | Créer vite un livrable |
| Analyseurs | Audit de site, score SEO, analyse de lisibilité | Évaluer l'existant |
| Testeurs | Prévisualisation de balises title/meta, test de vitesse | Vérifier que ça marche |
| Bibliothèques | Templates, checklists interactives, snippets | Matériel de référence |
| Interactifs | Quiz, diagnostics, tutoriels | Faire comprendre |

---

## Cadre d'idéation

### Partir des douleurs

1. **Que googlise ta cible ?** — requêtes réelles, questions récurrentes (Search Console, forums, groupes LinkedIn/Facebook FR)
2. **Quelles tâches manuelles sont pénibles ?** — tableurs, calculs répétitifs
3. **De quoi a-t-elle besoin AVANT d'acheter ?** — diagnostic, comparaison, estimation
4. **Quelle info lui manque ?** — benchmarks, données inaccessibles

### Valider l'idée

- **Demande de recherche** : volume sur les requêtes « [truc] calculateur », « [truc] gratuit » ? Concurrence ?
- **Unicité** : qu'est-ce qui existe déjà ? Comment être 10x meilleur — pas 10 % ?
- **Qualité des leads** : cette audience recoupe-t-elle tes acheteurs ?
- **Faisabilité** : quel MVP en combien de jours ?

Avant toute décision, regarde ce que les concurrents qui rankent proposent déjà. Un outil, ça se benchmarke comme une page.

---

## Capture de leads

### Options de gating

| Approche | Avantages | Inconvénients |
|----------|-----------|---------------|
| Tout gated (e-mail avant usage) | Capture maximale | Usage plus faible |
| Partiellement gated (résultat partiel libre, rapport complet contre e-mail) | Le bon équilibre, le pattern le plus courant | — |
| Libre + e-mail optionnel | Portée maximale | Capture faible |
| Totalement libre | Pur SEO/marque | Zéro lead direct |

### Bonnes pratiques
- Échange de valeur explicite : « Recevez votre rapport complet »
- Friction minimale : e-mail seul, pas de formulaire à 8 champs
- Montrer un aperçu de ce qu'on va recevoir
- Optionnel : une seule question qualifiante pour segmenter

### RGPD — non négociable en France
- Case de consentement **non pré-cochée** si tu comptes envoyer autre chose que le rapport demandé
- Finalité claire au moment de la collecte (« votre e-mail sert à vous envoyer le rapport et nos conseils SEO, désinscription en un clic »)
- Lien vers la politique de confidentialité sous le formulaire
- Double opt-in recommandé si l'outil alimente une newsletter
- Registre des traitements à jour ; durée de conservation définie (la CNIL recommande 3 ans après le dernier contact)

---

## Cas concret : l'audit express

Le pattern « analyseur + e-mail » appliqué en vrai : un outil qui **note le site du visiteur sur 100** (SEO + lisibilité par les IA), affiche le score immédiatement, et propose le rapport détaillé contre e-mail. Exemple live : https://www.david-corroy.com/audit-express/

Pourquoi ce pattern fonctionne :
- **Le score est un déclencheur émotionnel.** Un 54/100 pique. Le visiteur veut savoir pourquoi — le rapport détaillé devient irrésistible.
- **L'input est trivial** : une URL. Zéro friction à l'entrée, la friction (e-mail) arrive après la preuve de valeur.
- **Chaque exécution qualifie le lead** : tu connais son site, son score, ses faiblesses. Le premier e-mail de nurturing peut être hyper-personnalisé.
- **L'objet de l'analyse EST ton expertise.** L'outil démontre ce que tu vends au lieu de le raconter.

### L'extension qui change tout : le badge gagné

Ajoute un palier de réussite : au-dessus d'un seuil (ex. ≥ 70/100), le site « gagne » un badge (« Prêt pour les IA », « Site conforme », etc.) avec un code d'intégration HTML fourni.

Mécanique :
1. Le visiteur teste son site, obtient un bon score.
2. L'outil lui propose un badge à afficher fièrement sur son site.
3. Le code embed du badge contient **un lien vers ton outil**.
4. Chaque badge posé = un backlink entrant automatique + de la preuve sociale pour l'outil.

C'est une boucle : l'outil génère des badges, les badges génèrent des liens, les liens font ranker l'outil, l'outil génère plus de leads. Règles d'hygiène : lien en dofollow assumé mais ancre neutre (le nom de l'outil, pas ta requête money), et un seuil assez exigeant pour que le badge garde de la valeur.

---

## SEO de l'outil

### Stratégie de mots-clés
**Page de l'outil** : « calculateur [truc] », « générateur [truc] », « [type d'outil] gratuit », « simulateur [truc] »

**Contenus satellites** : « comment [cas d'usage] », « qu'est-ce que [concept] », maillés vers l'outil

### Pourquoi les outils attirent des liens
- Réellement utiles : on les cite en référence
- Uniques : on ne peut pas linker « n'importe quelle page » à la place
- Partageables : amplification sociale naturelle
- Et si tu ajoutes le badge : les liens viennent tout seuls

---

## Construire ou assembler

### Développement sur mesure
Quand : concept unique, cœur de la marque, forte valeur stratégique, capacité dev disponible. Un outil dans un thème WordPress (template de page + un peu de JS) suffit souvent — pas besoin d'une app séparée.

### No-code
Options : Tally, Typeform, Outgrow, Involve.me, Bubble, Webflow
Quand : vitesse avant tout, pas de dev, test de concept. Vérifie l'hébergement des données (RGPD : privilégie un hébergement UE).

### Intégrer l'existant
Quand : un bon outil en marque blanche existe et ce n'est pas ton différenciateur.

---

## Périmètre MVP

### Outil minimum viable
1. La fonctionnalité cœur uniquement — une chose, fiable
2. UX essentielle — input clair, output évident, **ça marche sur mobile à 375px**
3. Capture basique — e-mail collecté, leads envoyés quelque part d'utile (CRM, tableur, autorépondeur)

### À sauter au départ
Comptes utilisateurs, sauvegarde des résultats, fonctions avancées, design parfait, tous les cas limites.

---

## Grille d'évaluation

Note chaque facteur de 1 à 5 :

| Facteur | Note |
|---------|------|
| Demande de recherche existante | ___ |
| Adéquation audience / acheteurs | ___ |
| Unicité vs l'existant | ___ |
| Chemin naturel vers l'offre | ___ |
| Faisabilité de construction | ___ |
| Charge de maintenance (inversée) | ___ |
| Potentiel de liens entrants | ___ |
| Potentiel de partage | ___ |

**25+** : candidat solide | **15-24** : prometteur | **<15** : à reconsidérer

---

## Questions à poser

1. Quels outils ta cible utilise-t-elle aujourd'hui comme solution de contournement ?
2. Comment génères-tu tes leads actuellement ?
3. Quelles ressources techniques as-tu ?
4. Quel délai, quel budget ?
5. Un score, un badge ou un rapport : lequel colle le mieux à ton expertise ?
