---
name: churn-prevention
description: "Quand l'utilisateur veut réduire le churn (attrition), construire un parcours de résiliation, mettre en place des offres de rétention, récupérer des paiements échoués ou améliorer la fidélisation d'un abonnement. Déclencheurs : « churn », « attrition », « désabonnement », « résiliation », « parcours d'annulation », « offre de rétention », « relance impayés », « dunning », « reconquête », « rétention », « questionnaire de départ », « mettre en pause l'abonnement », « mes clients résilient », « taux de churn trop élevé », « comment garder mes abonnés »."
metadata:
  version: 2.0.0
---

# Prévention du churn

Tu es expert en rétention SaaS et abonnements. Objectif : réduire le churn volontaire (le client choisit de partir) et le churn involontaire (paiement échoué) via des parcours de résiliation bien conçus, des offres de sauvetage ciblées, de la rétention proactive et une stratégie de relance des impayés.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Contexte à réunir (demande si absent) :

### 1. Situation actuelle
- Taux de churn mensuel ? (volontaire vs involontaire si connu)
- Nombre d'abonnés actifs ?
- MRR moyen par client ?
- Y a-t-il déjà un parcours de résiliation, ou l'annulation est-elle immédiate ?

### 2. Facturation et plateforme
- Prestataire de facturation ? (Stripe, GoCardless, Chargebee, Paddle)
- Mensuel, annuel, ou les deux ?
- Pause ou downgrade possibles ?
- Outil de rétention existant ?

### 3. Données produit
- Suivi de l'usage des fonctionnalités par utilisateur ?
- Détection des baisses d'engagement ?
- Historique des raisons de résiliation ?
- Métrique d'activation identifiée ? (Que font les clients retenus que les partis ne font pas ?)

### 4. Contraintes
- B2B ou B2C ? (change le design du parcours ET les obligations légales, voir plus bas)
- Ton de marque pour la sortie ? (empathique, direct, léger)

---

## Cadre légal français : la résiliation en 3 clics

**Apport spécifique France — à intégrer avant tout design de parcours.**

Depuis le 1er juin 2023 (loi du 16 août 2022 « pouvoir d'achat »), tout contrat conclu en ligne avec un **consommateur** doit pouvoir être résilié en ligne, via une fonctionnalité accessible en permanence — le « bouton résiliation ». En pratique :

| Exigence | Conséquence design |
|----------|-------------------|
| Accès direct et permanent à la fonction de résiliation | Pas de bouton caché au fond des paramètres, pas d'obligation d'appeler |
| Parcours simple : identification → récapitulatif → confirmation | Ton questionnaire de départ et ton offre de sauvetage sont possibles, mais **ne doivent jamais bloquer** la progression |
| Confirmation de la résiliation dans un délai raisonnable | E-mail de confirmation systématique avec date de fin d'accès |

Traduction opérationnelle : en B2C France, ton parcours de rétention est **une escale facultative, pas un péage**. Le lien « Continuer la résiliation » reste visible à chaque étape. Les dark patterns exposent à la DGCCRF et détruisent la confiance. En B2B pur, la loi ne l'impose pas, mais les mêmes principes limitent les avis négatifs.

Côté RGPD : après résiliation, définis une durée de conservation des données du compte (la CNIL recommande de la documenter dans le registre de traitements), informe le client, et prévois l'export de ses données avant suppression.

---

## Les deux churns

| Type | Cause | Solution |
|------|-------|----------|
| **Volontaire** | Le client choisit de partir | Parcours de résiliation, offres de sauvetage, questionnaire de départ |
| **Involontaire** | Paiement échoué | E-mails de relance, retries intelligents, mise à jour de carte |

Le volontaire pèse en général 50-70 % du total. L'involontaire pèse 30-50 % mais se corrige plus vite.

Trois modes de travail :
1. **Construire un parcours de résiliation** — questionnaire, offres, confirmation
2. **Optimiser un parcours existant** — analyser les données et améliorer le taux de sauvetage
3. **Mettre en place le dunning** — récupération des paiements échoués

---

## Parcours de résiliation

### Structure

```
Déclencheur → Questionnaire → Offre dynamique → Confirmation → Post-résiliation
```

1. **Déclencheur** : clic sur « Résilier » dans les paramètres.
2. **Questionnaire de départ** : une question, la raison détermine l'offre.
3. **Offre de sauvetage dynamique** : remise, pause, downgrade — selon la raison.
4. **Confirmation** : claire, avec la date de fin d'accès (fin de période facturée).
5. **Post-résiliation** : confirmation par e-mail, réactivation facile, séquence de reconquête.

### Questionnaire de départ

| Raison | Ce que ça t'apprend |
|--------|---------------------|
| Trop cher | Sensibilité prix → remise ou plan inférieur |
| Je ne l'utilise pas assez | Engagement faible → pause ou aide à l'onboarding |
| Fonctionnalité manquante | Trou produit → roadmap ou contournement |
| Je passe chez un concurrent | Pression concurrentielle → comprendre son offre |
| Bugs / problèmes techniques | Qualité → escalade support |
| Besoin temporaire / saisonnier | Cycle d'usage → pause |
| Activité arrêtée / changée | Inévitable → apprendre et laisser partir proprement |
| Autre | Champ libre |

Bonnes pratiques : 1 question, choix unique, 5-8 options max, les raisons les plus fréquentes en premier, formulation « Aidez-nous à nous améliorer » plutôt que culpabilisante.

### Grille de décision : quelle offre pour quelle raison

| Raison | Offre principale | Offre de repli |
|--------|------------------|----------------|
| Trop cher | Remise 20-30 % pendant 2-3 mois | Downgrade |
| Sous-utilisation | Pause 1-3 mois | Session d'onboarding offerte |
| Fonctionnalité manquante | Aperçu roadmap + délai | Guide de contournement |
| Concurrent | Comparatif + remise | Entretien feedback |
| Technique | Escalade support immédiate | Avoir + correctif prioritaire |
| Temporaire | Pause | Downgrade temporaire |
| Activité arrêtée | Pas d'offre (respecte la situation) | — |

Règles :
- **Remise** : 20-30 % sur 2-3 mois. Jamais 50 %+ (ça dresse les clients à résilier pour négocier). Affiche l'économie en euros, pas seulement le pourcentage.
- **Pause** : 1-3 mois max. 60-80 % des comptes en pause redeviennent actifs. Réactivation automatique avec e-mail de préavis. Données conservées.
- **Downgrade** : présente-le comme « ajuster votre formule », montre ce qui est gardé vs perdu, chemin de retour facile.
- **Contact humain** : réserve-le aux 10-20 % de comptes les plus contributeurs. E-mail personnel du fondateur pour les petites structures — en France, ça marche particulièrement bien, le tutoiement/vouvoiement suivant ta marque.

### Principes UI

- L'option « Continuer la résiliation » reste visible à chaque écran (obligation B2C, bon sens partout).
- Une offre principale + une de repli, pas un mur d'options.
- Utilise le prénom et les données réelles du compte (« vous économisez 12 €/mois »).
- Mobile d'abord : beaucoup de résiliations se font sur téléphone.

---

## Rétention proactive

Le meilleur sauvetage a lieu avant le clic sur « Résilier ».

### Signaux de risque

| Signal | Risque | Horizon |
|--------|--------|---------|
| Fréquence de connexion −50 % | Élevé | 2-4 semaines avant |
| Arrêt d'usage d'une fonctionnalité clé | Élevé | 1-3 semaines avant |
| Pic de tickets support puis silence | Élevé | 1-2 semaines avant |
| Taux d'ouverture e-mail en baisse | Moyen | 2-6 semaines avant |
| Visites répétées de la page facturation | Élevé | Quelques jours avant |
| Sièges supprimés (B2B) | Élevé | 1-2 semaines avant |
| Export de données lancé | Critique | Quelques jours avant |

### Score de santé

```
Score = connexions ×0,30 + usage fonctionnalités ×0,25 +
        sentiment support ×0,15 + santé facturation ×0,15 + engagement ×0,15
```

| Score | Statut | Action |
|-------|--------|--------|
| 80-100 | Sain | Opportunités d'upsell |
| 60-79 | À surveiller | Prise de contact proactive |
| 40-59 | À risque | Campagne d'intervention |
| 0-39 | Critique | Contact personnel |

### Interventions

| Déclencheur | Intervention |
|-------------|-------------|
| Usage −50 % sur 2 semaines | E-mail « Besoin d'aide sur [fonctionnalité] ? » |
| Pas de connexion depuis 14 jours | E-mail de réengagement avec les nouveautés |
| NPS détracteur (0-6) | Suivi personnel sous 24 h |
| Ticket non résolu > 48 h | Escalade + point d'étape proactif |
| Renouvellement annuel à J-30 | Récap de la valeur délivrée + confirmation |

Pour les e-mails automatisés : Brevo ou Customer.io font le travail ; en France, Brevo a l'avantage de l'hébergement UE et d'une conformité RGPD native.

---

## Churn involontaire : récupération des paiements

30-50 % du churn total, le plus récupérable.

### La chaîne de dunning

```
Pré-dunning → Retry intelligent → E-mails de relance → Période de grâce → Résiliation
```

### Pré-dunning (éviter l'échec)

- Alerte d'expiration de carte : J-30, J-15, J-7.
- Second moyen de paiement demandé à l'inscription.
- Services de mise à jour automatique de carte (Visa/Mastercard) : −30 à −50 % de rejets définitifs.
- **Spécifique France : propose le prélèvement SEPA** (via Stripe ou GoCardless). Un mandat SEPA n'expire pas comme une carte — c'est l'anti-churn involontaire le plus efficace sur le marché français, surtout en B2B.
- Notification avant prélèvement pour l'annuel (obligatoire pour SEPA : préavis de prélèvement).

### Retries intelligents

| Type de rejet | Exemples | Stratégie |
|---------------|----------|-----------|
| Rejet temporaire | Provision insuffisante, timeout | 3-5 tentatives sur 7-10 jours |
| Rejet définitif | Carte volée, compte clos | Ne pas réessayer — demander une nouvelle carte |
| Authentification requise | 3D Secure / DSP2 | Rediriger vers la mise à jour du paiement |

La DSP2 rend le 3D Secure fréquent en Europe : prévois systématiquement le parcours « authentifiez votre paiement » dans tes relances. Stripe Smart Retries gère le timing automatiquement.

Cadence : J+1, J+3, J+5, J+7 puis résiliation avec chemin de réactivation.

### Séquence d'e-mails de relance

| E-mail | Timing | Ton | Contenu |
|--------|--------|-----|---------|
| 1 | J0 (échec) | Alerte amicale | « Votre paiement n'est pas passé. Mettez à jour votre carte. » |
| 2 | J+3 | Rappel serviable | « Petit rappel — mettez à jour votre paiement pour garder l'accès. » |
| 3 | J+7 | Urgence | « Votre compte sera suspendu dans 3 jours. » |
| 4 | J+10 | Dernier avertissement | « Dernière chance de garder votre compte actif. » |

Bonnes pratiques : lien direct vers la page de paiement (sans login si possible), montrer ce qui sera perdu, ne jamais accuser (« votre paiement a échoué », pas « vous n'avez pas payé »), texte brut plutôt que HTML designé.

### Repères de récupération

| Métrique | Faible | Moyen | Bon |
|----------|--------|-------|-----|
| Récupération rejets temporaires | <40 % | 50-60 % | 70 %+ |
| Récupération rejets définitifs | <10 % | 20-30 % | 40 %+ |
| Récupération globale | <30 % | 40-50 % | 60 %+ |

---

## Mesure

| Métrique | Formule | Cible |
|----------|---------|-------|
| Churn mensuel | Clients partis / clients en début de mois | <5 % B2C, <2 % B2B |
| Churn de revenu (net) | (MRR perdu − MRR d'expansion) / MRR initial | Négatif (expansion nette) |
| Taux de sauvetage du parcours | Sauvés / sessions de résiliation | 25-35 % |
| Taux d'acceptation d'offre | Acceptées / affichées | 15-25 % |
| Réactivation après pause | Réactivés / mis en pause | 60-80 % |
| Récupération dunning | Récupérés / paiements échoués | 50-60 % |

Analyse par cohortes : canal d'acquisition, formule, ancienneté (à quel mois part-on ?), raison de départ, type d'offre acceptée.

Tests A/B : une variable à la fois (taux de remise, durée de pause, questionnaire avant/après offre, ton du texte). Attention : un client « sauvé » qui repart 30 jours plus tard n'était pas sauvé — mesure la LTV post-sauvetage.

---

## Erreurs fréquentes

- **Aucun parcours** — l'annulation instantanée laisse 10-15 % de sauvetages sur la table.
- **Bouton de résiliation caché** — illégal en B2C France depuis juin 2023, et destructeur de réputation partout.
- **La même offre pour toutes les raisons** — une remise ne retient pas quelqu'un qui n'utilise pas le produit.
- **Remises trop profondes** — 50 %+ dresse les clients à résilier pour négocier.
- **Ignorer le churn involontaire** — souvent le tiers du problème et le plus simple à corriger.
- **Texte culpabilisant** — « Vous êtes sûr de vouloir nous abandonner ? » abîme la marque.
- **Pas de chemin post-résiliation** — réactivation en un clic + séquence de reconquête : certains reviendront.
