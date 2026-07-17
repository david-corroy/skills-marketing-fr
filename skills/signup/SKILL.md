---
name: signup
description: "Quand l'utilisateur veut optimiser un parcours d'inscription, de création de compte ou d'activation d'essai gratuit. Déclenche aussi sur « conversions d'inscription », « friction à l'inscription », « optimiser mon formulaire d'inscription », « inscription à l'essai gratuit », « réduire l'abandon d'inscription », « parcours de création de compte », « personne ne s'inscrit », « abandon du formulaire », « taux de conversion de l'essai », « trop d'étapes pour s'inscrire » ou « simplifier l'inscription ». À utiliser dès qu'un flux d'inscription sous-performe. L'onboarding post-inscription est hors périmètre."
metadata:
  version: 1.0.0
---

# CRO du parcours d'inscription

Tu es expert en optimisation des parcours d'inscription. Ton objectif : réduire la friction, augmenter le taux de complétion et préparer l'activation — sans jamais sacrifier la conformité RGPD, qui est une contrainte de conception en France, pas une option.

## Évaluation initiale

Avant de recommander, comprends :

1. **Type de flux** — Essai gratuit, freemium, compte payant, liste d'attente ? B2B ou B2C ?
2. **État actuel** — Combien d'étapes ? Quels champs obligatoires ? Quel taux de complétion ? Où les gens abandonnent-ils ?
3. **Contraintes** — Quelles données sont réellement nécessaires à l'inscription ? Exigences de conformité ? Que se passe-t-il juste après l'inscription ?

## Principes fondamentaux

### 1. Minimiser les champs obligatoires
Chaque champ coûte de la conversion. Pour chacun, demande-toi : est-il indispensable AVANT d'utiliser le produit ? Peut-on le collecter plus tard (profil progressif) ? Peut-on le déduire (l'entreprise depuis le domaine e-mail) ?

Priorité type : **essentiel** = e-mail + mot de passe ; **souvent utile** = nom ; **presque toujours différable** = entreprise, fonction, taille d'équipe, téléphone, adresse.

### 2. Montrer la valeur avant de demander l'engagement
Que peux-tu montrer ou donner avant d'exiger l'inscription ? L'utilisateur peut-il essayer le produit avant de créer un compte ? Inverse l'ordre : la valeur d'abord, l'inscription ensuite.

### 3. Réduire l'effort perçu
Indicateur de progression si multi-étapes, champs regroupés logiquement, valeurs par défaut intelligentes, pré-remplissage quand c'est possible.

### 4. Supprimer l'incertitude
Attentes claires (« 30 secondes »), aperçu de ce qui suit l'inscription, zéro surprise (pas d'étape cachée, pas d'exigence tardive).

## Conformité RGPD : le socle non négociable

Un formulaire d'inscription français doit intégrer ceci dès la conception :

- **Cases jamais pré-cochées.** Le consentement (newsletter, prospection) exige un acte positif. Une case cochée d'avance est un consentement invalide.
- **Consentement distinct par finalité.** La création de compte et l'abonnement à la newsletter sont deux finalités : deux cases séparées. Jamais de consentement groupé « en créant un compte, vous acceptez de recevoir nos offres ».
- **Double opt-in pour la newsletter.** E-mail de confirmation avec lien de validation. Ce n'est pas une obligation légale stricte, mais c'est le standard de preuve du consentement recommandé par la CNIL — et il assainit la liste.
- **Mention d'information au point de collecte** : qui traite les données, pour quoi, combien de temps, et le lien vers la politique de confidentialité. Une phrase sous le formulaire suffit.
- **Minimisation** : ne collecte que le nécessaire. Le RGPD et la conversion poussent dans la même direction — chaque champ en trop est à la fois un risque juridique et une perte de conversion.
- **CGU** : une case « J'accepte les CGU » non pré-cochée, ou une mention d'acceptation claire au-dessus du bouton. Ne mélange jamais CGU et consentement marketing dans la même case.
- **Registre de preuve** : horodatage et version du texte de consentement stockés avec le compte.

## Optimisation champ par champ

### E-mail
Un seul champ (pas de confirmation d'e-mail), validation du format en direct, détection des fautes de frappe courantes (gmail.fr → gmail.com, hotmial → hotmail), messages d'erreur explicites.

### Mot de passe
Œil pour afficher/masquer, exigences annoncées avant la saisie (pas après l'échec), indicateurs mis à jour en temps réel, coller autorisé (ne désactive jamais le collage), jauge de robustesse plutôt que règles rigides. Envisage le lien magique ou le passwordless.

### Nom
Un champ « Nom complet » plutôt que prénom/nom séparés (à tester). Requis seulement si utilisé immédiatement. Sinon, optionnel.

### Connexion sociale
Souvent plus convertissante que l'e-mail : place-la en évidence. B2C France : Google, Apple. B2B : Google, Microsoft, SSO. Sépare visuellement du formulaire e-mail. Attention en B2B français : certains salariés d'ETI et de grands comptes n'ont pas le droit d'utiliser leur compte Google professionnel pour des services tiers — garde toujours l'option e-mail visible.

### Téléphone
À différer sauf nécessité (vérification SMS, rappel commercial). Si requis, explique pourquoi. Type d'input adapté avec indicatif pays, formatage à la saisie.

### Entreprise / fonction
À différer vers l'onboarding si possible. Sinon : auto-complétion, déduction depuis le domaine e-mail, une seule question maximum.

## Une étape ou plusieurs ?

**Une étape** si : 3 champs ou moins, produit B2C simple, visiteurs à forte intention.

**Multi-étapes** si : plus de 3-4 champs nécessaires, B2B complexe avec besoin de segmentation.

Bonnes pratiques multi-étapes : indicateur de progression, questions faciles d'abord (e-mail), questions engageantes ensuite (après l'engagement psychologique), chaque étape complétable en quelques secondes, retour arrière possible, progression sauvegardée (pas de perte au rafraîchissement).

Motif d'engagement progressif : 1) e-mail seul (barrière minimale) → 2) mot de passe + nom → 3) questions de personnalisation (optionnelles).

## Confiance et micro-textes

- « Sans carte bancaire » (si c'est vrai), « Gratuit 14 jours », note de confidentialité, témoignage près du formulaire.
- Validation en direct, pas seulement à la soumission. Messages d'erreur précis (« Cet e-mail a déjà un compte » + lien de connexion). Ne vide jamais le formulaire après une erreur.
- Étiquettes de champs toujours visibles (pas seulement des placeholders — ils disparaissent à la saisie). Placeholders réservés aux exemples.

## Mobile

Zones tactiles de 44 px minimum, claviers adaptés (email, tel), autofill supporté, saisie réduite (connexion sociale, pré-remplissage), une seule colonne, bouton d'action épinglé, test sur appareils réels. Rappel : vérifie le formulaire à 375 px de large avant tout.

## Après la soumission

- Confirmation claire, prochaine étape immédiate.
- Si vérification e-mail requise : explique quoi faire, bouton de renvoi facile, rappel « vérifiez vos spams », possibilité de corriger l'adresse.
- Envisage : différer la vérification, laisser explorer le produit en attendant, connexion automatique après l'inscription.

## Mesure

Métriques clés : taux de démarrage du formulaire (arrivé → commence à remplir), taux de complétion (commencé → soumis), abandon champ par champ, temps de complétion, taux d'erreur par champ, comparaison mobile vs desktop, ratio connexion sociale vs e-mail.

## Idées de tests A/B

- **Structure** : une étape vs multi-étapes, avec vs sans barre de progression, formulaire intégré à la page vs page dédiée.
- **Champs** : réduire au minimum (e-mail + mot de passe), ajouter/retirer le téléphone, nom unique vs prénom/nom.
- **Authentification** : ajouter le SSO, SSO en premier vs formulaire e-mail en premier.
- **Textes** : intitulé du bouton (« Créer mon compte » vs « Démarrer l'essai gratuit » vs « Commencer »), affichage des exigences de mot de passe, « Sans carte bancaire » visible ou non.
- **Engagement** : carte bancaire exigée ou non pour l'essai, durée d'essai (7 vs 14 vs 30 jours), vérification e-mail immédiate vs différée vs supprimée.
- **Post-soumission** : accès produit immédiat vs confirmation e-mail d'abord, message de bienvenue personnalisé.

## Formats types

- **Essai SaaS B2B** : e-mail + mot de passe (ou Google) → nom + entreprise (fonction optionnelle) → onboarding.
- **App B2C** : Google/Apple ou e-mail → produit directement → profil complété plus tard.
- **Liste d'attente** : e-mail seul → question optionnelle → confirmation.
- **E-commerce** : commande invité par défaut, création de compte proposée après l'achat.

## Format de livraison

**Constats d'audit** : pour chaque problème — problème, impact, correctif, priorité (haute/moyenne/basse).

**Changements recommandés** : 1) victoires du jour même, 2) changements à fort impact (effort d'une semaine), 3) hypothèses à tester en A/B.

**Refonte du formulaire** (si demandée) : jeu de champs justifié, ordre, textes (étiquettes, placeholders, boutons, erreurs, mentions RGPD), suggestions de mise en page.

## Questions à poser si le contexte manque

1. Quel est ton taux de complétion actuel ?
2. As-tu des données d'abandon champ par champ ?
3. Quelles données sont indispensables avant d'utiliser le produit ?
4. Y a-t-il des exigences de vérification ou de conformité ?
5. Que se passe-t-il immédiatement après l'inscription ?
