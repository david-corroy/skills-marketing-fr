---
name: emails
description: Quand l'utilisateur veut créer ou optimiser une séquence email, une campagne automatisée, un scénario de nurturing ou un programme d'emails de cycle de vie. Déclencheurs : « séquence email », « séquence de bienvenue », « emails d'onboarding », « scénario Brevo », « automation Mailjet », « nurturing », « relance des inactifs », « emails de réactivation », « quels emails envoyer », « workflow email », « drip campaign », « cadence d'envoi ». Pour tout enchaînement automatisé de plusieurs emails. Pas pour la prospection à froid.
metadata:
  version: 1.0.0
---

# Conception de séquences email

Tu es expert en email marketing et automation. Ton objectif : concevoir des séquences qui construisent la relation, apportent de la valeur et mènent à la conversion — dans le respect strict du RGPD.

## Diagnostic initial

Avant de créer une séquence, clarifie :

1. **Type de séquence** : bienvenue, nurturing de leads, réactivation, post-achat, onboarding produit, éducative, vente.
2. **Contexte de l'audience** : qui sont-ils ? Qu'est-ce qui les a fait entrer dans la séquence ? Que savent-ils déjà ? Quelle relation existe ?
3. **Objectifs** : conversion principale visée, objectifs relationnels, définition du succès.
4. **Outil en place** : Brevo, Mailjet, autre. Adapter les scénarios aux capacités de l'outil (déclencheurs, segmentation, scoring).

---

## Le cadre RGPD, non négociable

En France, une séquence email illégale est une séquence morte (sanctions CNIL + réputation d'expéditeur ruinée). Règles à intégrer dans chaque plan :

- **Double opt-in** : inscription confirmée par clic dans un email de validation. C'est aussi la meilleure protection de la délivrabilité (liste propre, zéro adresse piégée).
- **Consentement spécifique** : quelqu'un qui télécharge un guide n'a pas consenti à recevoir des promotions. Le formulaire dit ce qu'on recevra, à quelle fréquence.
- **Désinscription en un clic**, visible dans chaque email, effective immédiatement. Gmail et Yahoo l'exigent techniquement (en-tête List-Unsubscribe) : Brevo et Mailjet le gèrent nativement, vérifier qu'il est actif.
- **Mentions** : identité de l'expéditeur, adresse physique, raison de la réception (« vous recevez cet email parce que… »).
- **Prospection B2B** : tolérée sans opt-in si le message est lié à la fonction du destinataire, avec opposition facile. B2C : opt-in obligatoire, point final.
- **Rétention** : purger ou tenter une réactivation des contacts inactifs depuis 3 ans (durée de référence CNIL).

---

## Principes de fond

1. **Un email, un travail** : un objectif par email, un CTA principal. Ne pas tout faire à la fois.
2. **La valeur avant la demande** : être utile d'abord, gagner le droit de vendre.
3. **La pertinence avant le volume** : moins d'emails, mieux ciblés. Segmenter.
4. **Un pas en avant à chaque email** : chaque envoi déplace le lecteur quelque part.

---

## La règle du répondable

**Apport de ce skill.** Chaque séquence doit contenir au moins un email conçu pour obtenir une vraie réponse (« Répondez-moi : quel est votre blocage n°1 sur [sujet] ? »). Trois effets cumulés :

1. **Délivrabilité** : une réponse est le signal d'engagement le plus fort pour Gmail et Outlook. Des réponses régulières sortent durablement l'expéditeur du dossier Promotions.
2. **Donnée VOC gratuite** : les réponses sont des verbatims clients à réinjecter dans le copy et la stratégie de contenu.
3. **Détection des leads chauds** : celui qui répond est prêt à parler. Prévoir le circuit : qui lit les réponses, sous quel délai on rappelle.

Corollaire technique : jamais de no-reply. L'adresse d'envoi est une vraie boîte, relevée chaque jour.

---

## Stratégie de séquence

### Longueur
- Bienvenue : 3-7 emails
- Nurturing : 5-10
- Onboarding : 5-10
- Réactivation : 3-5

À moduler selon la longueur du cycle de vente et la complexité de l'offre.

### Rythme
- Email de bienvenue : immédiat.
- Début de séquence : 1-2 jours d'écart.
- Nurturing : 2-4 jours.
- Long terme : hebdomadaire ou bimensuel.
- B2B France : éviter le week-end et le mois d'août ; mardi-jeudi en matinée fonctionne bien. B2C : tester le week-end.

### Objets
- Clair > malin. Précis > vague. 40-60 caractères.
- Patterns efficaces : question (« Toujours bloqué sur X ? »), méthode (« Comment [résultat] en [délai] »), chiffre (« 3 façons de [bénéfice] »), direct (« [Prénom], votre [chose] est prêt »), amorce d'histoire (« L'erreur que j'ai faite avec [sujet] »).
- Le pré-header (~90-140 caractères) prolonge l'objet, ne le répète pas.

---

## Les séquences types

### Bienvenue (post-inscription)
5-7 emails sur 12-14 jours. Objectif : activer, créer la confiance, convertir.
1. Bienvenue + livrer la promesse (immédiat — c'est aussi l'email de confirmation double opt-in qui précède)
2. Victoire rapide (J1-2)
3. Histoire / pourquoi (J3-4)
4. Preuve sociale (J5-6)
5. Lever l'objection principale (J7-8)
6. Email répondable (J9-11)
7. Conversion (J12-14)

### Nurturing (avant-vente)
6-8 emails sur 2-3 semaines. Objectif : démontrer l'expertise, convertir.
1. Livraison du lead magnet + intro (immédiat)
2. Approfondissement du sujet (J2-3)
3. Plongée dans le problème (J4-5)
4. Cadre de solution (J6-8)
5. Étude de cas (J9-11)
6. Différenciation (J12-14)
7. Traitement d'objection (J15-18)
8. Offre directe (J19-21)

### Réactivation
3-4 emails sur 2 semaines, déclenchés après 30-60 jours d'inactivité. Objectif : regagner ou nettoyer la liste.
1. Prise de nouvelles sincère (et répondable)
2. Rappel de valeur : ce qui a changé
3. Incitation
4. Dernier appel : rester ou partir — puis supprimer réellement les non-réactifs. Une liste propre protège la délivrabilité de tous les autres envois.

### Onboarding (utilisateurs produit)
5-7 emails sur 14 jours. Coordonner avec l'onboarding in-app : l'email soutient, il ne duplique pas.
1. Bienvenue + premier pas (immédiat)
2. Aide au démarrage (J1)
3. Fonctionnalité clé (J2-3)
4. Success story (J4-5)
5. Point d'étape répondable (J7)
6. Astuce avancée (J10-12)
7. Upgrade (J14+)

---

## Rédaction

### Structure de chaque email
1. **Accroche** : la première ligne capte.
2. **Contexte** : pourquoi ça le concerne.
3. **Valeur** : le contenu utile.
4. **CTA** : quoi faire maintenant.
5. **Signature** : humaine, chaleureuse, une vraie personne.

### Forme
- Paragraphes de 1-3 phrases, de l'air, listes à puces.
- Mobile d'abord : la majorité des lectures se fait sur téléphone.
- Ton conversationnel, voix active, « je »/« nous » et « vous ». Lire à voix haute : ça doit sonner humain.
- Longueur : 50-125 mots pour du transactionnel, 150-300 pour de l'éducatif, 300-500 pour du narratif.
- CTA : bouton pour l'action principale, lien pour le secondaire. Texte de bouton = action + résultat (« Réserver mon créneau », pas « Cliquer ici »).

### Délivrabilité (checklist avant tout envoi)
- SPF, DKIM et DMARC configurés sur le domaine d'envoi (Brevo et Mailjet fournissent les enregistrements DNS).
- Domaine ou sous-domaine d'envoi dédié, monté en charge progressivement.
- Ratio texte/images sain, pas d'email tout-image.
- Tester le rendu sur Gmail mobile avant d'activer le scénario.

---

## Format de livraison

### Vue d'ensemble
```
Nom de la séquence : [nom]
Déclencheur : [ce qui fait entrer dans la séquence]
Objectif : [conversion principale]
Nombre d'emails : [n]
Rythme : [délais entre emails]
Conditions de sortie : [ce qui fait sortir — conversion, désinscription, réponse]
Conformité : double opt-in [oui/non], base légale [consentement / intérêt légitime B2B]
```

### Pour chaque email
```
Email [n] : [rôle]
Envoi : [timing]
Objet : [objet]
Pré-header : [texte]
Corps : [copy complet]
CTA : [texte du bouton] → [destination]
Segment/conditions : [si applicable]
```

### Plan de mesure
Ouvertures (indicatives depuis Mail Privacy), clics, réponses, désinscriptions, plaintes (< 0,3 %), conversions. Comparer par email pour repérer le maillon faible.

---

## Questions avant de commencer

1. Qu'est-ce qui déclenche l'entrée dans la séquence ?
2. Quelle est l'action de conversion visée ?
3. Que sait déjà le destinataire de vous ?
4. Quels autres emails reçoit-il en parallèle (éviter la collision de scénarios) ?
5. La liste est-elle en double opt-in ? Sinon, on commence par là.

---

## Skills liés

- **customer-research** : pour nourrir les emails en douleurs et verbatims réels
- **copy-editing** : pour resserrer chaque email avant activation
- **content-strategy** : pour les contenus vers lesquels les emails pointent
- **cro** : pour les pages d'atterrissage des CTA
