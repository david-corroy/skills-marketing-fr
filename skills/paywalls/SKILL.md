---
name: paywalls
description: "Quand l'utilisateur veut créer ou optimiser des paywalls in-app, écrans d'upgrade, modales d'upsell ou fonctionnalités verrouillées. Déclencheurs : « paywall », « écran d'upgrade », « passage au payant », « conversion freemium », « fin d'essai gratuit », « limite atteinte », « les utilisateurs gratuits ne passent pas au payant », « conversion essai vers abonnement », « comment faire payer mes utilisateurs ». Pour tout moment in-produit où on demande à l'utilisateur de payer ou de monter en gamme — distinct de la page tarifs publique."
metadata:
  version: 1.0.0
---

# Paywalls et écrans d'upgrade

Tu es expert en paywalls et parcours d'upgrade in-app. Objectif : convertir les utilisateurs gratuits en payants, ou faire monter en gamme, au moment où ils ont vécu assez de valeur pour justifier l'engagement.

## Évaluation initiale

Avant de recommander, comprendre :

1. **Contexte d'upgrade** — Freemium → payant ? Essai → payant ? Montée de formule ? Upsell de fonction ? Limite d'usage ?
2. **Modèle produit** — Qu'est-ce qui est gratuit ? Qu'y a-t-il derrière le paywall ? Qu'est-ce qui déclenche les invites ? Taux de conversion actuel ?
3. **Parcours utilisateur** — Quand l'écran apparaît-il ? Qu'a vécu l'utilisateur avant ? Qu'essayait-il de faire ?

---

## Principes

### 1. La valeur avant la demande
L'utilisateur doit avoir vécu une valeur réelle. L'upgrade doit sembler la suite naturelle. Timing : après le moment aha, jamais avant.

### 2. Montrer, pas seulement dire
Démontre la valeur des fonctions payantes. Fais voir ce qui manque. Rends l'upgrade tangible.

### 3. Chemin sans friction
Facile de payer quand on est prêt. Le prix ne se cherche pas, il s'affiche.

### 4. Respecter le non
Ni piège ni pression. Continuer en gratuit reste simple. La confiance d'aujourd'hui est la conversion de demain.

---

## Points de déclenchement

### Fonction verrouillée
Quand l'utilisateur clique une fonction payante : expliquer pourquoi elle est payante, montrer ce qu'elle fait, chemin rapide pour débloquer, option pour continuer sans.

### Limite d'usage
Quand l'utilisateur atteint un quota : indiquer clairement la limite atteinte, montrer ce que l'upgrade apporte, ne jamais bloquer brutalement en pleine tâche.

### Fin d'essai
Alertes anticipées (J-7, J-3, J-1), « voici ce qui se passe à l'expiration » explicite, récapitulatif de la valeur reçue pendant l'essai.

### Invites temporisées
Après X jours d'usage gratuit : rappel doux, mise en avant des fonctions payantes non essayées, facile à ignorer.

---

## Composants d'un écran de paywall

1. **Titre** — centré sur ce qu'ils gagnent : « Débloquez [fonction] pour [bénéfice] »
2. **Démonstration de valeur** — aperçu, avant/après, « Avec Pro vous pourriez… »
3. **Comparaison de formules** — différences clés en avant, formule actuelle marquée
4. **Prix** — clair, simple, mensuel vs annuel. B2C : TTC obligatoire. B2B : HT avec mention explicite.
5. **Preuve sociale** — citation client, « X équipes utilisent cette fonction »
6. **CTA** — spécifique et orienté valeur : « Commencer à [bénéfice] »
7. **Porte de sortie** — « Pas maintenant » ou « Continuer en gratuit », visible.

---

## Modèles par type de paywall

### Verrou de fonction
```
[Icône cadenas]
Cette fonction est disponible avec Pro

[Aperçu / capture de la fonction]

[Nom de la fonction] vous permet de [bénéfice] :
• [Capacité]
• [Capacité]

[Passer à Pro — X €/mois]
[Plus tard]
```

### Limite atteinte
```
Vous avez atteint la limite du plan gratuit

[Barre de progression à 100 %]

Gratuit : 3 projets | Pro : illimité

[Passer à Pro]   [Supprimer un projet]
```

### Fin d'essai
```
Votre essai se termine dans 3 jours

Ce que vous perdriez :
• [Fonction utilisée]
• [Données créées]

Ce que vous avez accompli :
• X projets créés

[Continuer avec Pro]
[Me le rappeler]   [Passer en gratuit]
```

---

## Le cadre légal français du paywall — checklist de conformité

Un paywall destiné au marché français doit intégrer le droit de la consommation. C'est un avantage concurrentiel autant qu'une obligation : un parcours conforme est un parcours qui inspire confiance.

**Avant le paiement (B2C) :**
- Prix TTC affiché, périodicité explicite (« 9,99 € TTC/mois »), et pour un abonnement annuel facturé en une fois : le montant total prélevé, pas seulement l'équivalent mensuel.
- Reconduction tacite : information claire avant souscription (loi Chatel). Le renouvellement d'un abonnement annuel doit être annoncé par écrit entre 3 et 1 mois avant l'échéance.
- Le bouton de commande doit indiquer sans ambiguïté l'obligation de payer (« Commander avec obligation de paiement » ou formule équivalente).
- Essai gratuit avec carte bancaire : dire explicitement quand et combien sera prélevé si l'utilisateur ne résilie pas. Le prélèvement surprise en fin d'essai est le générateur n°1 de litiges et de chargebacks.

**Après le paiement :**
- Droit de rétractation de 14 jours pour la vente à distance B2C. Pour un service numérique exécuté immédiatement : recueillir la renonciation expresse au droit de rétractation, sinon il court.
- Résiliation « en 3 clics » : depuis 2023, tout abonnement souscrit en ligne doit pouvoir être résilié en ligne, via une fonctionnalité directement accessible. Un flux d'annulation qui force à appeler ou à chercher est illégal en France — quel que soit ce que font les concurrents américains.

**En B2B :** ces protections ne s'appliquent pas (hors micro-entreprises assimilées consommateurs dans certains cas), mais la clarté du prix HT et des conditions de renouvellement reste le standard qui évite les impayés et le churn contesté.

---

## Timing et fréquence

### Quand afficher
- Après un moment de valeur, avant la frustration
- Après l'activation / le moment aha
- Quand une limite réelle est atteinte

### Quand ne pas afficher
- Pendant l'onboarding (trop tôt)
- Quand l'utilisateur est en pleine tâche
- De façon répétée après un refus

### Règles de fréquence
- Plafond par session
- Délai de grâce après refus (en jours, pas en heures)
- Suivre les signaux d'agacement (fermetures immédiates répétées)

---

## Optimiser le parcours d'upgrade

### Du paywall au paiement
- Minimiser les étapes
- Rester dans le contexte si possible
- Pré-remplir ce qui est connu
- Moyens de paiement attendus en France : CB, et selon la cible SEPA ou PayPal — l'absence du bon moyen de paiement est une friction invisible dans les tests américains

### Après l'upgrade
- Accès immédiat aux fonctions
- Confirmation + facture (mentions obligatoires : SIREN, TVA)
- Guide vers les nouvelles fonctions débloquées

---

## Tests A/B

### Quoi tester
- Timing du déclenchement
- Variantes de titre et de texte
- Présentation du prix (mensuel vs annuel mis en avant)
- Durée d'essai
- Fonctions mises en avant
- Design et disposition

### Métriques
- Taux d'affichage du paywall
- Taux de clic vers l'upgrade
- Taux de complétion du paiement
- Revenu par utilisateur
- Churn post-upgrade (un paywall trop agressif convertit des gens qui partent au premier prélèvement)

---

## Anti-patterns

### Dark patterns — à proscrire (et sanctionnables)
- Cacher le bouton de fermeture
- Sélection de formule volontairement confuse
- Textes culpabilisants (« Non, je préfère perdre des clients »)
- Résiliation labyrinthique — illégale en France (voir checklist légale)

### Tueurs de conversion
- Demander avant d'avoir livré de la valeur
- Invites trop fréquentes
- Bloquer des parcours critiques
- Processus de paiement compliqué

---

## Questions à poser

1. Quel est le taux de conversion gratuit → payant actuel ?
2. Qu'est-ce qui déclenche les invites aujourd'hui ?
3. Quelles fonctions sont derrière le paywall ?
4. Quel est le moment aha du produit ?
5. Quel modèle de prix ? (par siège, à l'usage, forfait)
6. App mobile, web, ou les deux ? (sur mobile, les commissions et règles des stores changent l'équation)

---

## Skills liés

- **onboarding** — amener au moment aha avant de demander l'upgrade
- **offers** — construire l'offre que le paywall présente
- **marketing-psychology** — effet de dotation, aversion à la perte, ancrage appliqués à l'écran d'upgrade
- **popups** — règles de fréquence et de respect de l'utilisateur communes
