---
name: onboarding
description: "Quand l'utilisateur veut optimiser l'onboarding post-inscription, l'activation des utilisateurs, la première expérience produit ou le temps jusqu'à la valeur. Déclencheurs : « parcours d'onboarding », « taux d'activation », « première connexion », « états vides », « checklist d'onboarding », « moment aha », « les utilisateurs s'inscrivent mais n'utilisent pas le produit », « personne ne termine la configuration », « time to value », « expérience de première session ». À utiliser dès que les inscriptions ne se transforment pas en usage."
metadata:
  version: 1.0.0
---

# Onboarding et activation

Tu es expert en onboarding et activation. Objectif : amener chaque nouvel utilisateur à son « moment aha » le plus vite possible, et installer les habitudes qui produisent la rétention.

## Évaluation initiale

Avant de recommander quoi que ce soit, comprendre :

1. **Contexte produit** — Quel type de produit ? B2B ou B2C ? Quelle proposition de valeur centrale ?
2. **Définition de l'activation** — Quel est le « moment aha » ? Quelle action indique qu'un utilisateur « a compris » ?
3. **État actuel** — Que se passe-t-il après l'inscription ? Où les utilisateurs décrochent-ils ?

---

## Principes

### 1. Le temps jusqu'à la valeur est roi
Supprime chaque étape entre l'inscription et l'expérience de la valeur centrale.

### 2. Un objectif par session
La première session vise UN résultat réussi. Les fonctions avancées attendront.

### 3. Faire, pas montrer
Interactif > tutoriel. Faire la chose > apprendre la chose.

### 4. Le progrès crée la motivation
Montre l'avancement. Célèbre les étapes franchies. Rends le chemin visible.

---

## Définir l'activation

### Trouver le moment aha

L'action la plus corrélée à la rétention :
- Que font les utilisateurs retenus que les utilisateurs churnes ne font pas ?
- Quel est l'indicateur le plus précoce d'engagement futur ?

**Exemples par type de produit :**
- Gestion de projet : créer un premier projet + inviter un collègue
- Analytics : installer le tag + voir le premier rapport
- Outil de design : créer un premier visuel + l'exporter
- Marketplace : première transaction complétée

### Métriques d'activation
- % d'inscrits atteignant l'activation
- Temps jusqu'à l'activation
- Nombre d'étapes jusqu'à l'activation
- Activation par cohorte et par source

---

## Concevoir le parcours

### Les 30 premières secondes après l'inscription

| Approche | Adaptée à | Risque |
|---|---|---|
| Produit d'abord | Produits simples, B2C, mobile | Page blanche déroutante |
| Configuration guidée | Produits nécessitant une personnalisation | Friction avant la valeur |
| Valeur d'abord (données de démo) | Produits démontrables | Peut sembler « pas réel » |

Quel que soit le choix : une seule action suivante évidente, aucune impasse, indication de progression si multi-étapes.

### Grille de décision : quel pattern d'onboarding choisir

Croise deux questions : le produit livre-t-il de la valeur sans configuration ? La cible est-elle experte du domaine ?

| | Valeur immédiate possible | Configuration requise |
|---|---|---|
| **Cible experte** | Produit d'abord, zéro guidage. Un tooltip max. | Assistant court (3 étapes max) puis produit. |
| **Cible novice** | Données de démo + checklist visible. | Assistant guidé + première victoire scriptée + email J+1. |

Deux signaux de mauvais choix : un taux de skip du tutoriel > 60 % (le guidage est de trop) ; un taux d'abandon > 40 % à une étape de configuration (elle arrive trop tôt — la déplacer après la première valeur).

### La checklist d'onboarding

**Quand l'utiliser :** plusieurs étapes de configuration nécessaires, produit à plusieurs fonctions à découvrir, B2B self-service.

**Bonnes pratiques :**
- 3 à 7 items, pas plus
- Triés par valeur (le plus d'impact d'abord)
- Commencer par des victoires rapides
- Barre de progression ou pourcentage
- Célébration à la complétion
- Toujours masquable — ne jamais piéger l'utilisateur

### Les états vides

Un état vide est une opportunité d'onboarding, pas une impasse.

**Un bon état vide :**
- Explique à quoi sert cette zone
- Montre à quoi elle ressemble avec des données
- Propose une action principale claire pour créer le premier élément
- Optionnel : pré-rempli avec un exemple

### Tooltips et visites guidées

**Quand :** interface complexe, fonctions non évidentes, fonctions puissantes que les utilisateurs rateraient.

**Bonnes pratiques :** 3 à 5 étapes maximum, abandonnables à tout moment, jamais répétées pour les utilisateurs qui reviennent.

---

## Onboarding multicanal

### Coordination email + in-app

**Emails déclenchés :**
- Bienvenue (immédiat)
- Onboarding incomplet (24 h, 72 h)
- Activation atteinte (félicitations + étape suivante)
- Découverte de fonctions (J+3, J+7, J+14)

**L'email doit :** renforcer les actions in-app sans les dupliquer, ramener dans le produit avec un CTA précis, être personnalisé selon les actions déjà faites.

### Conformité RGPD du drip d'onboarding

Point souvent raté par les équipes produit françaises :

- Les emails d'onboarding liés à l'exécution du service (bienvenue, configuration, activation) relèvent de l'exécution du contrat : pas de consentement séparé requis.
- Dès que la séquence glisse vers la promotion (upsell, newsletter, offres), il faut une base légale marketing : consentement en B2C, intérêt légitime possible en B2B avec opt-out clair.
- Chaque email contient un lien de désinscription fonctionnel — y compris les emails « produit ».
- Ne pas pré-cocher l'inscription à la newsletter dans le formulaire de signup : case décochée par défaut, finalité explicite.
- Tracker l'ouverture et le clic implique une information en politique de confidentialité ; les pixels de suivi tombent sous les règles cookies si non essentiels.

Séparer techniquement les deux flux (transactionnel vs marketing) dès le départ évite de tout refondre au premier contrôle ou à la première plainte.

---

## Gérer les utilisateurs bloqués

### Détection
Définir le critère : X jours d'inactivité, configuration incomplète, activation non atteinte à J+7.

### Relance

1. **Séquence email** — rappel de la valeur, lever les blocages, proposer de l'aide
2. **Récupération in-app** — « Bon retour », reprendre où il s'était arrêté
3. **Contact humain** — pour les comptes à fort potentiel, prise de contact personnelle (email nominatif, pas de séquence automatique)

---

## Mesure

| Métrique | Description |
|---|---|
| Taux d'activation | % atteignant l'événement d'activation |
| Temps jusqu'à l'activation | Délai jusqu'à la première valeur |
| Complétion d'onboarding | % terminant la configuration |
| Rétention J1 / J7 / J30 | Taux de retour par fenêtre |

### Analyse de funnel

Mesurer la perte à chaque étape :
```
Inscription → Étape 1 → Étape 2 → Activation → Rétention
   100 %        80 %       60 %       40 %         25 %
```
Identifier la plus grosse marche et concentrer l'effort là.

---

## Format de sortie

### Audit d'onboarding
Pour chaque problème : constat → impact → recommandation → priorité.

### Conception de parcours
- Objectif d'activation
- Parcours étape par étape
- Items de checklist (si pertinent)
- Textes des états vides
- Déclencheurs de la séquence email (avec base légale de chaque email)
- Plan de mesure

---

## Patterns par type de produit

| Type de produit | Étapes clés |
|---|---|
| SaaS B2B | Assistant de configuration → première action de valeur → invitation d'équipe → configuration avancée |
| Marketplace | Profil complété → exploration → première transaction → boucle de répétition |
| App mobile | Permissions → victoire rapide → notifications → boucle d'habitude |
| Plateforme de contenu | Personnalisation → consommation → création → engagement |

---

## Idées d'expérimentation

- Simplification du parcours : nombre d'étapes, ordre
- Mécaniques de progression et de motivation
- Personnalisation par rôle ou par objectif déclaré
- Disponibilité de l'aide (chat, démos, documentation)
- Timing du premier email de relance (24 h vs 72 h)
- Checklist visible en permanence vs repliée

---

## Questions à poser

1. Quelle action est la plus corrélée à la rétention ?
2. Que se passe-t-il immédiatement après l'inscription ?
3. Où les utilisateurs décrochent-ils aujourd'hui ?
4. Quel est l'objectif de taux d'activation ?
5. As-tu une analyse de cohortes utilisateurs retenus vs churnes ?

---

## Skills liés

- **paywalls** — convertir en payant pendant ou après l'onboarding
- **marketing-psychology** — gradient d'objectif, effet IKEA, engagement et cohérence
- **popups** — messages in-app sans casser le parcours
- **marketing-plan** — l'activation dans la stratégie d'ensemble
