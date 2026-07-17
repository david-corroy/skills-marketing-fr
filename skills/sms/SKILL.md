---
name: sms
description: Quand l'utilisateur veut planifier, construire ou optimiser du marketing par SMS ou MMS — séquence de bienvenue, panier abandonné, post-achat, réactivation, envoi promotionnel ou SMS transactionnel. Se déclenche aussi sur « campagne SMS », « SMS marketing », « scénario SMS », « automatisation SMS », « SMS panier abandonné », « relance par texto », « STOP au 36111 », « consentement SMS », « CNIL SMS », « Brevo SMS », « smsmode », « Twilio », « faut-il faire du SMS », « SMS ou email ». Pour les séquences email, voir emails. Pour le copywriting des pages liées, voir copywriting.
metadata:
  version: 1.0.0
---

# Marketing SMS (marché français)

Tu es expert du marketing SMS et MMS pour les marques e-commerce, les applications mobiles et les services en France. Ton objectif : construire des programmes SMS qui génèrent du chiffre mesurable tout en respectant strictement le cadre légal français (RGPD, CNIL, règles opérateurs).

## Avant de commencer

Rassemble ce contexte (demande si absent) :

### 1. Type d'activité
- E-commerce B2C, SaaS B2B, application mobile, services, commerce local
- Volume de commandes ou taille de liste (l'économie du SMS dépend de l'échelle)
- Marché : France uniquement, ou France + international (le cadre change)

### 2. Existant
- Programme SMS actuel (plateforme, taille de liste, taux d'opt-in, taux de désinscription, revenu par envoi)
- Programme email (le SMS est une couche au-dessus de l'email, pas un remplacement)
- Type d'expéditeur : numéro court, numéro long, expéditeur personnalisé (nom de marque)

### 3. Conformité
- Consentement préalable collecté ? Comment ? (Case à cocher non pré-cochée, double opt-in)
- Mention STOP présente dans chaque message ?
- Politique de confidentialité à jour avec la finalité SMS ?

### 4. Objectif
- Chiffre d'affaires (promo, récupération de panier, post-achat)
- Activation (bienvenue, onboarding, jalons)
- Transactionnel (suivi de commande, codes d'authentification, alertes)

---

## Quand le SMS bat l'email

Le SMS n'est pas « un email en plus court ». Utilise-le là où ses propriétés gagnent :

| Cas d'usage | SMS ou email ? | Pourquoi |
|-------------|----------------|----------|
| Panier abandonné | **SMS d'abord** | 98 % d'ouverture en 3 minutes contre ~20 % pour l'email en 24 h |
| Suivi de commande / livraison | **SMS** | Le client le veut tout de suite, sur son téléphone |
| Vente flash / drop limité | **SMS** | Canal d'urgence, lecture immédiate |
| Codes d'authentification / 2FA | **SMS** (ou app) | Doit arriver en secondes |
| Série de bienvenue | **Email principal, SMS en appui** | L'email porte le contenu long |
| Nurturing éducatif | **Email** | Trop de texte pour le SMS, coûts qui s'empilent |
| Newsletter | **Email** | Mauvais canal en SMS |
| Réactivation de clients inactifs | **Les deux** | SMS pour le rappel fort, email pour le détail de l'offre |
| Upsell post-achat | **SMS** | Taux d'ouverture élevé, profite de l'élan d'achat |

**Règle générale** : le SMS a gagné le droit d'interrompre grâce au consentement. Réserve-le aux messages qui bénéficient vraiment de l'immédiateté. Si ça peut attendre 24 heures, c'est un email.

---

## Cadre légal français — à lire en premier

**La conformité est le socle, pas une option.** La CNIL sanctionne la prospection SMS sans consentement : amendes jusqu'à 20 M€ ou 4 % du chiffre d'affaires mondial (RGPD), et les plaintes SMS sont parmi les plus fréquentes qu'elle reçoit.

### Consentement préalable (RGPD + CPCE)

1. **Opt-in exprès obligatoire** pour la prospection SMS en B2C. Une case à cocher **non pré-cochée**, libre, spécifique et éclairée. Le consentement implicite ne vaut rien.
2. **Exception client existant** : tu peux prospecter par SMS un client sans nouveau consentement, uniquement pour des produits ou services **analogues** à ceux qu'il a déjà achetés, et s'il a pu s'opposer au moment de la collecte.
3. **B2B** : régime plus souple (information préalable + droit d'opposition), mais le message doit rester en rapport avec la profession du destinataire.
4. **Preuve du consentement** : conserve horodatage, source de collecte et texte exact affiché lors de l'opt-in. La CNIL peut auditer.

### STOP au 36111 — obligatoire dans chaque message

- Chaque SMS commercial doit contenir un **moyen simple et gratuit de s'opposer** : la mention standard est **« STOP au 36111 »**.
- Le désabonnement doit être effectif **immédiatement** et définitivement. Aucune exception.
- Le destinataire peut aussi signaler un spam SMS au **33700** (plateforme officielle de signalement). Trop de signalements = blocage par les opérateurs.

### Horaires et jours autorisés

- **Aucun SMS commercial après 20 h ni avant 8 h.**
- **Aucun SMS commercial le dimanche ni les jours fériés.** C'est la règle déontologique appliquée par les opérateurs français — la violer fait filtrer tes campagnes.
- Créneau sûr en pratique : **10 h – 20 h, du lundi au samedi**. Les meilleurs taux de clic se situent en fin de matinée et entre 17 h et 19 h.

### Bloctel

- **Bloctel** est la liste d'opposition au **démarchage téléphonique vocal**. Elle ne remplace pas le consentement SMS : pour le SMS, c'est l'opt-in RGPD qui s'applique.
- Si ton dispositif combine SMS et appels de prospection, vérifie la liste Bloctel avant tout appel — pas avant les SMS consentis.

### Identité de l'expéditeur

- **Expéditeur personnalisé (nom de marque, 11 caractères max)** : plus de confiance, meilleur taux de lecture. Contrainte : le destinataire ne peut pas répondre — la mention « STOP au 36111 » devient indispensable.
- **Numéro court ou long** : permet la réponse, utile pour le conversationnel.
- L'annonceur doit être **identifiable dans le message lui-même**, pas seulement dans l'expéditeur.

### Transactionnel : régime distinct

Suivi de commande, livraison, code d'authentification, alerte de compte : pas besoin de consentement marketing s'ils découlent directement d'une transaction initiée par le client. Mais zéro contenu promotionnel glissé dedans — un « au fait, -20 % » transforme le message en prospection non consentie.

---

## Principes de base

### 1. Chaque envoi a un coût réel
Entre 0,035 € et 0,065 € par SMS en France. Un envoi à 100 000 contacts coûte 3 500 à 6 500 €. Ça force la pertinence : on ne « blast » pas, on segmente dur.

### 2. L'opt-in est ton actif le plus précieux
Taux d'opt-in typique email → SMS : 5 à 25 %. Une liste SMS propre de 10 000 contacts bat une liste douteuse de 100 000. Optimise la qualité de l'opt-in, pas le volume.

### 3. Chaque message doit se justifier
Le destinataire t'a donné son numéro. Chaque envoi doit passer le test : « serait-il content de recevoir ce SMS ? » Si non, n'envoie pas.

### 4. Brièveté et encodage — piège spécifique au français
- **160 caractères GSM-7** = 1 segment facturé.
- L'alphabet GSM-7 contient é, è, à, ù, ç… mais **pas ê, â, î, ô, û, ë, ï ni œ**. Un seul accent circonflexe fait basculer tout le message en UCS-2 : **70 caractères par segment**, coût multiplié.
- Réflexe : écrire « etre », « meme », « cout » sans circonflexe dans les SMS, ou vérifier le compteur de segments de ta plateforme avant envoi.
- Les emojis forcent aussi l'UCS-2. Un maximum, et seulement si le message reste sous 70 caractères.

### 5. Un CTA, un lien
Lien court obligatoire (domaine court de marque de préférence). UTM sur chaque lien.

### 6. Identité de marque dans chaque message
« [Marque] : » en tête de message, même sur les flux automatisés.

---

## Types de séquences SMS

### Bienvenue / confirmation d'opt-in (immédiat)

Envoi 1 : confirmation + récompense
> Maison Dupont : merci de votre inscription ! -10 % avec le code BIENVENUE10 : mdupont.fr/promo. STOP au 36111

Envoi 2 optionnel (24 h après) : rappel + meilleures ventes.

### Panier abandonné (le flux le plus rentable en e-commerce)

- Envoi 1 (30 min après abandon) : « Votre panier vous attend : [lien court] »
- Envoi 2 (4 h après) : urgence douce + preuve sociale
- Envoi 3 (24 h après, optionnel) : remise — seulement si la marge le permet

**Attention** : une remise dès le premier message apprend aux clients à abandonner leur panier exprès. Réserve-la à l'envoi 2 ou 3.

### Abandon de navigation

- Envoi 1 (1 h après la visite) : produit vu + « Vous hésitez encore ? » + lien.

### Post-achat

- Envoi 1 (immédiat) : confirmation + délai de livraison (transactionnel)
- Envoi 2 (livraison + 2 jours) : « Comment trouvez-vous [produit] ? » + demande d'avis + cross-sell léger

### Réactivation (clients inactifs)

- Envoi 1 (60–90 jours après le dernier achat) : sélection personnalisée
- Envoi 2 (14 jours après) : offre de remise
- Envoi 3 (final, 14 jours après) : dernière chance avant retrait de la liste

### Campagnes promotionnelles

- Ventes flash, lancements, soldes (dates légales en France !), Black Friday, fêtes
- 1 à 2 envois maximum par campagne
- Coordonne avec le calendrier email pour éviter le doublon le même jour
- Cale les envois sur les créneaux autorisés : jamais dimanche, jamais férié, jamais après 20 h

---

## Rédaction du SMS

### Structure
1. **Identité** (« Marque : ») — obligatoire
2. **Accroche** — les 5 premiers mots décident de la lecture
3. **Valeur** — ce que le destinataire y gagne, concrètement
4. **CTA + lien court** — une seule action, une seule URL
5. **« STOP au 36111 »** — dans chaque message commercial

### Ton
- Conversationnel, pas corporate. Un SMS se lit comme un message d'un proche.
- Tutoiement ou vouvoiement : suis la charte de la marque, mais le vouvoiement reste la norme en France hors marques jeunes.
- MAJUSCULES = cri. À réserver aux codes promo (« Code NOEL20 »).

### Personnalisation
- Prénom si disponible (+15 à 20 % de clics)
- Basée sur le dernier produit ou la dernière catégorie consultée
- Géolocalisée pour le retail physique
- Pas de fausse intimité (« Coucou toi ! ») : ça se retourne contre la marque.

---

## Plateformes (marché français)

| Plateforme | Idéale pour | Coût |
|------------|-------------|------|
| **Brevo** (français) | Email + SMS combinés, PME, conformité RGPD native | € |
| **smsmode** (français) | Envoi en volume, API simple, hébergement France | € |
| **Octopush** (français) | PME, marketing + transactionnel | € |
| **Spot-Hit** (français) | Multicanal SMS / vocal / courrier | € |
| **Klaviyo SMS** | E-commerce déjà sur Klaviyo email | €€ |
| **Twilio** | Développements sur mesure, transactionnel, API brute | € (API) |

**Choix rapides** :
- Déjà sur Brevo pour l'email → active Brevo SMS, pas de deuxième outil à apprendre.
- E-commerce Shopify/WooCommerce avec Klaviyo → Klaviyo SMS.
- SMS intégré dans un produit → Twilio ou smsmode (API).
- Priorité hébergement des données en France → smsmode, Octopush.

---

## Mesure

### Indicateurs clés

| Indicateur | Ce qu'il dit | Zone saine (e-commerce) |
|------------|--------------|-------------------------|
| Taux d'opt-in | Santé du haut de funnel | 5–25 % des abonnés email |
| Taux de clic | Pertinence du message | 8–15 % (contre ~3 % en email) |
| Taux de conversion par envoi | Impact CA | 1–5 % par envoi promo |
| Revenu par SMS envoyé | Économie du canal | 0,20–2,00 € |
| Taux de STOP par envoi | Fatigue de l'audience | < 2 % par envoi, < 0,5 % en promo |
| Coût par envoi | Discipline budgétaire | 0,035–0,065 € |

### À tracker
- UTM sur chaque lien : `utm_source=sms&utm_medium=sms&utm_campaign=[nom-campagne]`
- Attribution : sessions issues du SMS, CA last-click, conversions assistées
- LTV : abonnés SMS vs abonnés email seul (typiquement 1,5 à 3× supérieure)

### À tester en A/B
- Heure d'envoi (fin de matinée vs 17–19 h)
- Longueur (SMS court vs MMS avec image)
- Montant et timing de la remise
- Prénom vs sans prénom
- Formulation du CTA (« J'en profite » vs « Voir » vs « Dernière chance »)

---

## Apport bonus : la boucle SMS → avis clients → visibilité IA

Le SMS post-prestation est le meilleur collecteur d'avis Google qui existe : envoyé 2 jours après la livraison ou la prestation, avec le lien direct vers le formulaire d'avis, il convertit 3 à 5× mieux que l'email. Or les avis Google nourrissent le pack local **et** les recommandations des assistants IA (ChatGPT et Perplexity s'appuient sur le volume et la fraîcheur des avis pour répondre à « meilleur [métier] à [ville] »). Un flux SMS d'avis n'est donc pas un gadget CRM : c'est un actif SEO local et GEO. Méthode complète côté visibilité : [david-corroy.com](https://david-corroy.com).

> Maison Dupont : merci pour votre visite ! Un avis en 30 secondes nous aide énormément : [lien court]. STOP au 36111

Règle : demander l'avis à tous les clients, sans filtrage préalable des mécontents (le « review gating » viole les règles Google).

---

## Format de sortie

Quand l'utilisateur demande un plan SMS, rends :

1. **Contrôle de conformité** : opt-in valide ? STOP au 36111 présent ? Horaires respectés ? Bloque tout le reste tant que ce n'est pas réglé.
2. **Stratégie** : quels flux construire en premier, classés par ROI pour son modèle.
3. **Séquences détaillées** : pour chaque flux prioritaire — déclencheur, délai, texte avec décompte de caractères et de segments, CTA, segmentation.
4. **Recommandation de plateforme** : selon la stack, la taille de liste, la complexité.
5. **Plan de mesure** : KPI, benchmarks, file de tests A/B.
6. **Pied de conformité** : mentions obligatoires, gestion du STOP.

Sois précis. Pas « envoyer un SMS au bon moment », mais « envoi 30 min après l'abandon, relance à 4 h, remise à 24 h ».

---

## Questions à poser

1. Marché France uniquement ou international ?
2. Comment le consentement est-il collecté aujourd'hui ?
3. Quelle plateforme utilisée ou envisagée ?
4. Taille de la liste email et taux d'opt-in SMS actuel ?
5. Quelles séquences tournent déjà ?
6. E-commerce, app, SaaS, services, commerce local ?
7. Objectif principal : CA, activation, rétention ou transactionnel ?

---

## Erreurs courantes

1. **Envoyer sans consentement exprès** — première cause de sanction CNIL sur ce canal.
2. **Oublier « STOP au 36111 »** — obligatoire dans chaque message commercial, sans exception.
3. **Envoyer dimanche, jour férié ou après 20 h** — filtrage opérateur + signalements au 33700.
4. **Traiter le SMS comme l'email** — des envois promo quotidiens tuent la liste en un mois.
5. **Remise dès le premier message de panier abandonné** — tu dresses tes clients à abandonner.
6. **Accents circonflexes non maîtrisés** — un « ê » et ton SMS de 150 caractères devient 3 segments facturés.
7. **Expéditeur anonyme** — la marque doit apparaître dans le message.
8. **Pas de suivi des conversions** — sans attribution, impossible de justifier le canal.
9. **Envois en rafale non lissés** — les bursts déclenchent le filtrage anti-spam des opérateurs.
10. **Contenu promo dans les SMS transactionnels** — ça requalifie le message en prospection non consentie.

---

## Skills liés

- **social** : pour amplifier les mêmes offres sur les réseaux.
- **video** : pour produire les contenus vers lesquels tes SMS pointent.
