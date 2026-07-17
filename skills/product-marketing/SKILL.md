---
name: product-marketing
description: "Quand l'utilisateur veut créer ou mettre à jour son document de contexte marketing produit. Déclenche aussi sur : « contexte produit », « contexte marketing », « positionnement », « qui est ma cible », « décris mon produit », « ICP », « profil client idéal », « persona », ou quand il en a assez de répéter les mêmes infos de base à chaque tâche marketing. À lancer au début de tout nouveau projet, avant les autres skills marketing — il crée `.agents/product-marketing.md`, le document que tous les autres skills lisent pour connaître le produit, l'audience et le positionnement."
metadata:
  version: 2.0.0
---

# Contexte marketing produit

Tu aides l'utilisateur à créer et maintenir son document de contexte marketing. Ce document capture le positionnement et les messages de fond, une fois pour toutes. Les autres skills marketing s'y réfèrent : plus besoin de tout répéter.

Emplacement : `.agents/product-marketing.md`.

## Déroulé

### Étape 1 : vérifier l'existant

Regarde d'abord si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`). Si le fichier est ailleurs qu'à l'emplacement canonique, propose de le déplacer.

**S'il existe :**
- Lis-le et résume ce qui est capturé
- Demande quelles sections mettre à jour
- Ne collecte que pour ces sections

**S'il n'existe pas, deux options :**

1. **Brouillon automatique depuis le projet** (recommandé) : tu étudies le dépôt — README, pages du site, textes marketing, métadonnées — et tu rédiges une V1. L'utilisateur corrige et complète. Bien plus rapide que partir de zéro.
2. **Partir de zéro** : tu parcours les sections une par une, en conversation.

Après le brouillon, demande : « Qu'est-ce qui est faux ? Qu'est-ce qui manque ? »

### Étape 2 : collecter

**En mode brouillon auto :**
1. Lis le projet : README, pages d'accueil et de service, page à propos, meta descriptions, docs existantes
2. Rédige toutes les sections avec ce que tu trouves
3. Présente et demande les corrections
4. Itère jusqu'à validation

**En mode conversation :**
Une section à la fois. Jamais toutes les questions d'un coup.

Pour chaque section :
1. Explique brièvement ce que tu captures
2. Pose les questions
3. Confirme
4. Passe à la suivante

Exige le **verbatim client** : les phrases exactes des clients valent plus que des descriptions léchées. C'est leur langage qui rend les textes efficaces — et c'est en français courant que tes clients parlent, pas en franglais marketing.

---

## Sections à capturer

### 1. Vue d'ensemble du produit
- Description en une ligne
- Ce que ça fait (2-3 phrases)
- Catégorie (le « rayon » où le client te cherche — le mot qu'il tape dans Google et dans ChatGPT)
- Type (SaaS, marketplace, e-commerce, service, conseil)
- Modèle économique et prix

### 2. Audience cible
- Type d'entreprise visée (secteur, taille, maturité)
- Décideurs visés (fonctions, services)
- Cas d'usage principal (le problème n°1 résolu)
- Jobs to be done (2-3 missions pour lesquelles on « t'embauche »)
- Scénarios d'usage concrets

### 3. Personas (B2B uniquement)
Si plusieurs parties prenantes achètent, capture pour chacune :
- Utilisateur, Champion, Décideur, Payeur, Influenceur technique
- Ce qui compte pour elle, son problème, la valeur promise

### 4. Problèmes et points de douleur
- Le problème de fond avant de te trouver
- Pourquoi les solutions actuelles échouent
- Ce que ça leur coûte (temps, argent, opportunités)
- La tension émotionnelle (stress, peur, doute)

### 5. Paysage concurrentiel
- **Concurrents directs** : même solution, même problème
- **Concurrents secondaires** : autre solution, même problème
- **Concurrents indirects** : approche opposée (dont : ne rien faire, ou le faire en interne)
- En quoi chacun déçoit les clients

### 6. Différenciation
- Différenciateurs clés (ce que les alternatives n'ont pas)
- Comment tu t'y prends autrement
- Pourquoi c'est mieux (bénéfices)
- Pourquoi on te choisit toi

### 7. Objections et anti-personas
- Top 3 des objections entendues en vente, et les réponses
- Qui n'est PAS un bon client (anti-persona)

### 8. Dynamique de bascule
Les quatre forces JTBD :
- **Poussée** : ce qui les fait fuir la solution actuelle
- **Attraction** : ce qui les attire chez toi
- **Habitude** : ce qui les retient dans l'existant
- **Anxiété** : ce qui les inquiète dans le changement

### 9. Langage client
- Comment ils décrivent le problème (verbatim)
- Comment ils te décrivent (verbatim)
- Mots à utiliser
- Mots à bannir
- Glossaire des termes maison

### 10. Voix de marque
- Ton (professionnel, décontracté, incisif…)
- Style (direct, conversationnel, technique)
- Personnalité (3-5 adjectifs)
- Position sur le franglais : quels anglicismes sont assumés, lesquels sont interdits

### 11. Preuves
- Chiffres et résultats citables
- Clients notables / logos
- Extraits de témoignages
- Thèmes de valeur et preuves associées

### 12. Objectifs
- Objectif business principal
- Action de conversion clé (ce que le visiteur doit faire)
- Métriques actuelles (si connues)

### 13. Fiche d'identité entité — pour Google ET les IA

Section spécifique : ce document ne sert pas qu'aux textes marketing, il fixe l'**identité d'entité** que les moteurs et les IA génératives (ChatGPT, Perplexity, Gemini) doivent retrouver partout à l'identique. Une entité décrite de dix façons différentes est une entité que les IA citent mal, ou pas du tout.

Capture, en version figée et copiable :
- **Nom canonique** de la marque/personne (une seule graphie, toujours la même)
- **Bio/description unique** (2-3 phrases) à réutiliser verbatim : site, LinkedIn, Malt, annuaires, signatures d'articles invités, profils presse
- **Catégorie déclarée** (ex. « consultant SEO et GEO ») — le même syntagme partout
- **Faits stables** : date de création, localisation, chiffres clés vérifiables
- **Profils officiels** (liste sameAs) : les URL exactes à référencer en schema.org

Règle d'usage : tout skill qui produit du contenu public (page, article, communiqué, profil) reprend cette fiche telle quelle. Zéro variation créative sur l'identité.

---

## Étape 3 : créer le document

Après collecte, crée `.agents/product-marketing.md` structuré ainsi :

```markdown
# Contexte marketing produit

*Dernière mise à jour : [date]*

## Vue d'ensemble
**Une ligne :**
**Ce que ça fait :**
**Catégorie :**
**Type :**
**Modèle économique :**

## Audience cible
**Entreprises visées :**
**Décideurs :**
**Cas d'usage principal :**
**Jobs to be done :**
-
**Scénarios :**
-

## Personas
| Persona | Ce qui compte | Problème | Valeur promise |
|---------|---------------|----------|----------------|
| | | | |

## Problèmes et douleurs
**Problème de fond :**
**Pourquoi les alternatives échouent :**
-
**Ce que ça coûte :**
**Tension émotionnelle :**

## Concurrence
**Direct :** [Concurrent] — déçoit parce que…
**Secondaire :** [Approche] — déçoit parce que…
**Indirect :** [Alternative] — déçoit parce que…

## Différenciation
**Différenciateurs :**
-
**Notre approche :**
**Pourquoi c'est mieux :**
**Pourquoi on nous choisit :**

## Objections
| Objection | Réponse |
|-----------|---------|
| | |

**Anti-persona :**

## Dynamique de bascule
**Poussée :**
**Attraction :**
**Habitude :**
**Anxiété :**

## Langage client
**Le problème, dans leurs mots :**
- « [verbatim] »
**Nous, dans leurs mots :**
- « [verbatim] »
**Mots à utiliser :**
**Mots à bannir :**
**Glossaire :**
| Terme | Sens |
|-------|------|
| | |

## Voix de marque
**Ton :**
**Style :**
**Personnalité :**

## Preuves
**Chiffres :**
**Clients :**
**Témoignages :**
> « [citation] » — [qui]
**Thèmes de valeur :**
| Thème | Preuve |
|-------|--------|
| | |

## Objectifs
**Objectif business :**
**Action de conversion :**
**Métriques actuelles :**

## Fiche d'identité entité
**Nom canonique :**
**Bio unique (verbatim, à copier partout) :**
**Catégorie déclarée :**
**Faits stables :**
**Profils officiels (sameAs) :**
-
```

---

## Étape 4 : valider et sauvegarder

- Montre le document complet
- Demande les derniers ajustements
- Sauvegarde dans `.agents/product-marketing.md`
- Conclus : « Les autres skills marketing utiliseront ce contexte automatiquement. Relance ce skill quand le positionnement évolue. »

---

## Conseils

- **Sois précis** : « quelle est LA frustration n°1 qui les amène chez toi ? », pas « quel problème résous-tu ? »
- **Capture les mots exacts** : le verbatim client bat la reformulation
- **Demande des exemples** : « tu peux me donner un cas concret ? » débloque les vraies réponses
- **Valide au fil de l'eau** : résume chaque section avant de passer à la suivante
- **Saute ce qui ne s'applique pas** : tous les produits n'ont pas besoin de toutes les sections (les personas B2B pour du B2C, par exemple)
