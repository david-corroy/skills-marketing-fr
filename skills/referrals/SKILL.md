---
name: referrals
description: "Créer, optimiser ou analyser un programme de parrainage, un programme d'affiliation ou une stratégie de bouche-à-oreille. Déclencheurs : « parrainage », « programme de parrainage », « affiliation », « affilié », « ambassadeur », « bouche-à-oreille », « boucle virale », « parrainez un ami », « programme partenaire », « prime de parrainage », « comment obtenir des recommandations », « mes clients qui recommandent », « commission d'affiliation ». À utiliser dès que quelqu'un veut que ses clients ou partenaires amènent de nouveaux clients. Pour la viralité de lancement, voir launch."
metadata:
  version: 2.0.0
---

# Parrainage et affiliation

Tu es expert en croissance par recommandation. Objectif : concevoir et optimiser des programmes qui transforment les clients en moteur d'acquisition — dans le respect du cadre français (CNIL pour le parrainage, obligations de transparence pour l'affiliation).

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Comprends la situation :

### 1. Type de programme
- Parrainage client, affiliation, ou les deux ?
- B2B ou B2C ?
- Valeur vie client (LTV) moyenne ?
- Coût d'acquisition (CAC) actuel sur les autres canaux ?

### 2. État actuel
- Programme existant ?
- Taux de parrainage actuel (% de clients qui parrainent) ?
- Incitations déjà testées ?

### 3. Adéquation produit
- Le produit est-il partageable ? A-t-il des effets de réseau ?
- Les clients en parlent-ils spontanément ?

### 4. Ressources
- Outils envisagés ? Budget d'incitations ?

---

## Parrainage vs affiliation

### Programme de parrainage client

**Pour :**
- Des clients existants qui recommandent à leur réseau.
- Des produits à bouche-à-oreille naturel.
- Des paniers modestes ou du self-serve.

**Caractéristiques :** le parrain est client ; récompenses ponctuelles ou plafonnées ; confiance élevée, volume faible. Exemples français bien connus : les banques en ligne (primes de 80 à 150 € par filleul), les opérateurs télécom, les néobanques.

### Programme d'affiliation

**Pour :**
- Toucher des audiences que tu n'as pas (créateurs, blogueurs, médias).
- Des paniers qui justifient une commission récurrente.

**Caractéristiques :** l'affilié n'est pas forcément client ; relation de commission continue ; volume plus fort, confiance variable.

---

## Le cadre légal français — à intégrer dès la conception

### Parrainage : la règle CNIL de l'usage unique

Le mécanisme « entrez l'e-mail de votre ami » est encadré. Doctrine CNIL constante :

- L'adresse du filleul ne peut servir **qu'à envoyer l'unique message d'invitation** pour le compte du parrain, puis doit être **supprimée** si le filleul ne donne pas suite. Interdiction de la verser au fichier de prospection.
- Le message d'invitation doit **identifier le parrain** (c'est lui qui recommande, pas la marque qui prospecte) et permettre au filleul de s'opposer à toute nouvelle sollicitation.
- Pas de relances automatiques au filleul non inscrit : une invitation, point.

Alternative plus propre et plus performante : le **lien de parrainage personnel** que le parrain partage lui-même (WhatsApp, e-mail, réseaux). Aucune donnée du filleul collectée avant sa démarche volontaire — conformité par construction, et meilleure conversion car la recommandation passe par le canal personnel du parrain.

Pense aussi : conditions générales du programme (plafonds, exclusions, anti-fraude) publiées, et fiscalité des primes (au-delà d'un usage ponctuel, les gains de parrainage peuvent devenir des revenus imposables pour le parrain — signale-le dans la FAQ du programme).

### Affiliation : transparence obligatoire

- **Loi du 9 juin 2023 sur l'influence commerciale** : tout contenu d'influenceur rémunéré (commission comprise) doit afficher clairement « publicité » ou « collaboration commerciale ». Impose-le contractuellement à tes affiliés — le manquement expose l'affilié ET l'annonceur.
- Les liens affiliés dans les contenus (blogs, comparatifs, newsletters) doivent être signalés comme tels (pratiques commerciales trompeuses sinon — DGCCRF).
- Les affiliés réguliers facturent : statut requis côté affilié (micro-entrepreneur au minimum). Prévois le circuit de facturation dans le programme.
- RGPD du tracking d'affiliation : les cookies d'attribution ne sont pas exemptés de consentement — l'attribution doit survivre au refus via des mécanismes server-side ou des codes promo nominatifs.

---

## Concevoir le programme de parrainage

### La boucle de parrainage

```
Moment déclencheur → Partage → Conversion du filleul → Récompense → (Boucle)
```

### Étape 1 : identifier les moments déclencheurs

**Moments à forte intention :**
- Juste après le premier moment « aha ».
- Après un jalon atteint (objectif, niveau, résultat).
- Après une interaction support exceptionnelle.
- Après un renouvellement ou un upgrade.
- Après une note élevée (NPS 9-10, avis 5 étoiles) — c'est LE moment de demander.

### Étape 2 : concevoir le mécanisme de partage

**Par efficacité décroissante :**
1. Partage in-app (meilleure conversion)
2. Lien personnalisé
3. Invitation par e-mail (attention à la règle CNIL de l'usage unique)
4. Partage social
5. Code de parrainage (fonctionne aussi hors ligne)

### Étape 3 : choisir la structure d'incitation

**Récompense simple** (parrain seul) : plus simple, adaptée aux produits à forte valeur.

**Récompense double** (parrain + filleul) : meilleure conversion, cadrage gagnant-gagnant. C'est le standard du marché français (banques en ligne, box, telco).

**Récompenses par paliers** : gamifie le parrainage, augmente l'engagement des gros parrains (3 filleuls = bonus, 10 = statut ambassadeur).

**Calibrage** : la récompense double se finance sur le CAC économisé. Si ton CAC payant est de 120 €, une prime de 30 € au parrain + 30 € au filleul reste très rentable. Récompense en crédit produit > cash quand c'est possible (rétention + coût réel inférieur).

---

## Optimiser le programme

### Améliorer le taux de parrainage

**Si peu de clients parrainent :**
- Demander à de meilleurs moments (voir les déclencheurs).
- Simplifier le partage (un clic, lien pré-rempli).
- Tester d'autres types d'incitations.
- Rendre le parrainage visible dans le produit.

**Si les parrainages ne convertissent pas :**
- Améliorer la page d'atterrissage du filleul (la recommandation du parrain doit y être visible : « Marie vous offre 30 € »).
- Renforcer l'incitation côté filleul.

### Tests A/B à mener

- **Incitation** : montant, nature (cash, crédit, cadeau), simple vs double, timing du versement.
- **Message** : description du programme, copie du CTA, page d'atterrissage.
- **Emplacement** : où et quand l'invitation à parrainer apparaît.

### Problèmes courants et correctifs

| Problème | Correctif |
|----------|-----------|
| Programme méconnu | Invitations in-app visibles, e-mail dédié |
| Faible taux de partage | Réduire à un clic, lien pré-rempli |
| Faible conversion filleul | Optimiser l'expérience d'atterrissage, nom du parrain visible |
| Fraude / abus | Vérification (KYC léger, délai de versement), plafonds, exclusion des auto-parrainages |
| Parrains one-shot | Paliers et gamification |

---

## Mesurer le succès

### Métriques clés

**Santé du programme :**
- Parrains actifs (ont parrainé dans les 30 derniers jours)
- Taux de conversion des parrainages
- Récompenses attribuées / versées

**Impact business :**
- % des nouveaux clients issus du parrainage
- CAC parrainage vs autres canaux
- LTV des clients parrainés
- ROI du programme

### Constats habituels

- Les clients parrainés ont une LTV supérieure de 16 à 25 %.
- Ils churnent 18 à 37 % de moins.
- Ils parrainent eux-mêmes 2 à 3 fois plus.

---

## Checklist de lancement

### Avant
- [ ] Objectifs et métriques de succès définis
- [ ] Structure d'incitation calibrée sur le CAC
- [ ] Outil de parrainage configuré
- [ ] Page d'atterrissage du programme
- [ ] Tracking et attribution en place (résistants au refus de cookies)
- [ ] Règles anti-fraude définies
- [ ] Conditions générales du programme rédigées (plafonds, exclusions, fiscalité)
- [ ] Circuit CNIL validé : lien personnel privilégié ; si invitation par e-mail, usage unique + suppression
- [ ] Parcours complet testé de bout en bout

### Lancement
- [ ] Annonce aux clients existants
- [ ] Invitations in-app aux moments déclencheurs
- [ ] Page programme sur le site
- [ ] Équipe support briefée

### Après (30 premiers jours)
- [ ] Revue du tunnel de conversion
- [ ] Identification des meilleurs parrains
- [ ] Recueil de feedback
- [ ] Correction des frictions
- [ ] Rappel aux non-parrains (tes clients, pas les filleuls)

---

## Séquences e-mail

### Annonce du programme

```
Objet : Gagnez [récompense] en partageant [Produit]

Notre programme de parrainage est lancé.

Partagez [Produit] autour de vous : [récompense] pour vous
à chaque inscription, [récompense filleul] pour eux.

[Votre lien de parrainage personnel]

1. Partagez votre lien
2. Votre filleul s'inscrit
3. Vous êtes récompensés tous les deux
```

### Séquence d'entretien (à tes clients, jamais aux filleuls)

- J+7 : rappel du programme.
- J+30 : « Quelqu'un autour de vous en aurait l'usage ? »
- J+60 : histoire d'un client + invitation à parrainer.
- Après un jalon : « Vous venez d'atteindre [X] — qui d'autre en profiterait ? »

---

## Programmes d'affiliation

### Structure de commission

| Modèle | Fonctionnement | Adapté à |
|--------|----------------|----------|
| % récurrent | 20-30 % des mensualités, à vie ou 12 mois | SaaS par abonnement |
| Montant fixe | X € par vente ou par lead qualifié | Paniers uniques, services |
| Par paliers | Commission qui monte avec le volume | Motiver les gros affiliés |

Points de conception : durée du cookie d'attribution (30-90 jours), seuil de paiement minimal, délai de versement (aligné sur la période de rétractation/remboursement), attribution au dernier clic par défaut.

### Recruter des affiliés

1. **Tes clients enthousiastes d'abord** — ils connaissent le produit, leur promotion sonne juste.
2. **Créateurs de contenu du secteur** — blogs, newsletters, YouTube ; vérifie l'adéquation d'audience avant le volume.
3. **Comparateurs et sites d'avis** — souvent les mêmes sources que citent les moteurs IA : double dividende.
4. Fournis un kit : liens propres, visuels, arguments, exemples de mentions conformes (« collaboration commerciale »).

### Gérer le programme

- Contrat d'affiliation écrit : obligations de transparence, interdictions (enchères sur ta marque en SEA, spam, fausses promesses), conditions de résiliation.
- Suivi qualité mensuel : d'où vient le trafic de chaque affilié, taux de remboursement de leurs ventes.
- Paie vite et juste : la réputation d'un programme circule entre affiliés.

Outils courants : Rewardful ou Tolt (SaaS avec Stripe), Affilae (acteur français), impact.com ou Awin (retail à volume), Dub.co (tracking de liens).

---

## Questions à poser

1. Parrainage, affiliation, ou les deux ?
2. Quelle LTV client et quel CAC actuel ?
3. Programme existant ou création ?
4. Quels outils envisages-tu ?
5. Quel budget de récompenses/commissions ?
6. Le produit se partage-t-il naturellement ? Tes clients en parlent-ils déjà ?
