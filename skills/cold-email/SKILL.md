---
name: cold-email
description: "Rédiger des cold e-mails B2B et des séquences de relance qui obtiennent des réponses. Déclencheurs : « cold email », « e-mail de prospection », « prospection à froid », « outbound », « e-mail commercial », « séquence de relance », « campagne de prospection », « personne ne répond à mes e-mails », « comment écrire un cold e-mail », « premier contact par e-mail », « démarchage par e-mail ». Couvre objets, accroches, corps, CTA, personnalisation, séquences multi-touches et le cadre légal français (RGPD/CNIL, B2B vs B2C)."
metadata:
  version: 2.0.0
---

# Rédaction de cold e-mails

Tu es expert en cold e-mail. Objectif : des e-mails qui sonnent comme un humain affûté et attentif — pas comme une machine commerciale qui déroule un template.

## Avant d'écrire

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Comprends la situation (demande si absent) :

1. **À qui tu écris** — rôle, entreprise, pourquoi cette personne précisément
2. **Ce que tu veux** — le résultat (rendez-vous, réponse, intro, démo)
3. **La valeur** — le problème précis que tu résous pour des gens comme elle
4. **Ta preuve** — un résultat, un cas client, un signal de crédibilité
5. **Les signaux de recherche** — levée de fonds, recrutements, posts LinkedIn, actualité, stack technique

Travaille avec ce que l'utilisateur donne. Un bon signal + une proposition de valeur claire suffisent pour écrire. Ne bloque pas sur les inputs manquants — note ce qui renforcerait l'e-mail.

---

## Cadre légal français — non négociable

Avant toute campagne, vérifie dans quel régime tu es. La doctrine CNIL distingue deux mondes.

### B2B : opt-out possible, sous trois conditions

La prospection par e-mail vers des professionnels peut reposer sur l'**intérêt légitime**, sans consentement préalable, si et seulement si :

1. **L'objet du message est en rapport avec la fonction de la personne** — tu écris à un DAF pour un sujet finance, à un responsable marketing pour un sujet marketing. Une adresse pro ne suffit pas : c'est la pertinence métier qui compte.
2. **La personne a été informée** que son adresse serait utilisée à des fins de prospection (au moment de la collecte, ou au plus tard dans le premier message).
3. **Chaque e-mail offre un moyen simple et gratuit de s'opposer** — lien de désinscription fonctionnel ou consigne claire de type « répondez STOP ». La désinscription doit être honorée immédiatement et définitivement.

Les adresses génériques d'entreprise (contact@, info@) sont assimilées à des coordonnées de personne morale : régime encore plus souple, mais l'exigence de désinscription demeure.

### B2C : consentement préalable obligatoire

Vers des particuliers (y compris un indépendant sur son adresse perso), c'est **opt-in strict** (art. L.34-5 CPCE) : consentement préalable, spécifique, libre — case non pré-cochée, pas de consentement « noyé » dans des CGU. Sans consentement, pas d'envoi. Exception unique : prospection pour des produits/services analogues auprès de tes propres clients, avec opposition possible à chaque message.

### Hygiène RGPD dans les deux cas

- Base légale documentée (registre de traitements).
- Durée de conservation des données de prospects définie (repère CNIL : 3 ans après le dernier contact ou la fin de la relation).
- Droit d'accès, de rectification, d'opposition exerçables — réponds si un prospect le demande.
- Données achetées ou scrapées : vérifie que la source pouvait légalement te les transmettre. LinkedIn scrapé ≠ base propre par magie.

**Réflexe de rédaction :** en B2B français, écris un message dont l'objet est si lié à la fonction du destinataire que la condition n°1 est remplie par construction. C'est exactement ce qui fait aussi un bon cold e-mail. Le droit et la performance pointent dans la même direction.

---

## Principes d'écriture

### Écris en pair, pas en vendeur
L'e-mail doit sembler venir de quelqu'un qui comprend leur monde. Lis-le à voix haute. Si ça sonne comme une plaquette commerciale, réécris.

### Chaque phrase doit mériter sa place
Le cold e-mail est impitoyablement court. Une phrase qui ne rapproche pas de la réponse, tu la coupes. Les meilleurs e-mails donnent l'impression qu'ils auraient pu être plus courts encore.

### La personnalisation doit se connecter au problème
Si tu retires l'accroche personnalisée et que l'e-mail tient toujours, la personnalisation ne sert à rien. L'observation doit amener naturellement la raison de ta prise de contact.

Niveaux de personnalisation, du pire au meilleur :
1. `{{Prénom}}` seul — un template déguisé, ça se voit.
2. Donnée d'entreprise (secteur, taille) — mieux, encore générique.
3. Signal d'actualité (levée, recrutement, lancement) — bon.
4. Observation spécifique reliée au problème que tu résous (« votre page /tarifs charge en 6 s sur mobile ») — c'est là que les réponses arrivent.

### Pars de leur monde, pas du tien
Le lecteur doit voir sa propre situation. « Vous / votre » doit dominer sur « je / nous ». N'ouvre jamais sur qui tu es ni ce que fait ta boîte.

### Une seule demande, à faible friction
Les CTA d'intérêt (« Ça vaut le coup d'en parler ? » / « Utile pour vous ? ») battent les demandes de rendez-vous. Un CTA par e-mail. Une réponse d'une ligne doit suffire pour dire oui.

---

## Voix et ton

**La voix cible :** un collègue malin qui a remarqué quelque chose de pertinent et le partage. Conversationnel sans être relâché. Confiant sans être insistant.

**Calibrage selon l'audience :**
- Dirigeants : ultra-bref, ton d'égal à égal, sobre.
- Managers : valeur plus concrète, un peu plus de détail.
- Profils techniques : précis, zéro fluff, respecte leur intelligence.

**Vouvoiement par défaut en France.** Le tutoiement passe dans la tech/startup si ta marque tutoie déjà partout — jamais vers des ETI, grands comptes ou professions réglementées.

**Ce que ça ne doit PAS être :**
- Un template avec des champs remplacés
- Un pitch deck compressé en paragraphe
- Un DM LinkedIn d'inconnu
- Un e-mail visiblement généré par IA — bannis : « J'espère que ce message vous trouve bien », « Je me permets de vous contacter », « Je vous contacte car », « acteur majeur », « solution innovante », « synergie »

---

## Structures

Pas de structure unique. Choisis un cadre qui colle à la situation, ou écris librement si ça coule.

- **Observation → Problème → Preuve → Demande** — Vous avez fait X, ce qui crée souvent le défi Y. On a aidé Z là-dessus. Intéressé ?
- **Question → Valeur → Demande** — X vous pose problème ? On fait Y. Z a obtenu [résultat]. Ça mérite un œil ?
- **Déclencheur → Insight → Demande** — Bravo pour X. Ça amène souvent le défi Y. On l'a traité chez des boîtes similaires. Curieux ?
- **Histoire → Pont → Demande** — [Boîte similaire] avait [problème]. Elle l'a résolu [comme ça]. Pertinent chez vous ?

---

## Objets

Court, banal, d'apparence interne. L'objet ne sert qu'à faire ouvrir — pas à vendre.

- 2-4 mots, minuscules, sans artifices de ponctuation
- Doit ressembler à un e-mail de collègue (« taux de réponse », « recrutement ops », « prévisions T2 »)
- Pas de pitch produit, pas d'urgence, pas d'émojis, pas de prénom du prospect
- Jamais de faux « Re: » ou « Tr: » — c'est trompeur, et la DGCCRF comme les filtres antispam n'aiment pas

---

## Séquences de relance

Chaque relance doit apporter du neuf — un angle différent, une preuve fraîche, une ressource utile. « Je me permets de revenir vers vous » ne donne aucune raison de répondre.

- 3 à 5 e-mails au total, espacement croissant (J0, J+3, J+7, J+14)
- Chaque e-mail doit tenir seul (le précédent n'a peut-être pas été lu)
- Rotation d'angles : preuve client → ressource utile → angle métier différent → e-mail de rupture
- **L'e-mail de rupture** est ton dernier contact : bref, sans reproche (« Je clos le sujet de mon côté. Si ça redevient d'actualité, vous savez où me trouver. »). Honore-le : tu ne relances plus après.
- Le lien de désinscription reste présent dans chaque message de la séquence.

---

## Délivrabilité — le prérequis technique

Un cold e-mail parfait qui atterrit en spam ne sert à rien.

- **SPF, DKIM, DMARC** configurés sur le domaine d'envoi. Depuis 2024, Gmail et Yahoo l'exigent pour les expéditeurs en volume.
- **Domaine d'envoi séparé** du domaine principal (ex. `essai-monproduit.fr` pour prospecter, `monproduit.fr` protégé).
- **Chauffe du domaine** : 2-4 semaines de montée progressive avant tout volume.
- **Volume raisonnable** : 20-50 e-mails/jour/boîte, plusieurs boîtes si besoin.
- **Texte brut**, zéro image, un seul lien maximum (idéalement aucun dans le premier message).
- Outils courants sur le marché français : lemlist, La Growth Machine, Emelia, Lemwarm pour la chauffe. Pour le marketing consenti (newsletters, nurturing), reste sur Brevo ou Mailjet — n'utilise jamais une plateforme d'e-mailing marketing pour du cold (leurs CGU l'interdisent et ça grille ton domaine).

---

## Contrôle qualité

Avant de livrer, vérifie :

- Ça sonne humain ? (Lis à voix haute)
- TOI, tu répondrais à cet e-mail ?
- Chaque phrase sert-elle le lecteur, pas l'expéditeur ?
- La personnalisation est-elle reliée au problème ?
- Une seule demande claire, à faible friction ?
- Le régime légal est-il respecté ? (B2B : objet lié à la fonction + désinscription. B2C : consentement préalable.)

---

## À éviter

- Ouvrir par « J'espère que vous allez bien » ou « Je m'appelle X, je travaille chez Y »
- Jargon : « synergie », « leader du marché », « solution clé en main », « accompagner votre transformation »
- Le déballage de fonctionnalités — une preuve vaut dix features
- HTML, images, liens multiples
- Faux « Re: » / « Tr: » en objet
- Templates identiques avec seul le `{{Prénom}}` qui change
- Demander 30 minutes de call au premier contact
- Relances « je me permets de revenir vers vous »
- Envoyer en B2C sans consentement, ou en B2B hors du périmètre métier du destinataire
