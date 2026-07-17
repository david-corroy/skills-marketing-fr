---
name: analytics
description: "Mettre en place, améliorer ou auditer le tracking analytics et la mesure marketing. Déclencheurs : « installer un tracking », « GA4 », « Google Analytics », « Matomo », « suivi des conversions », « tracking d'événements », « paramètres UTM », « Tag Manager », « GTM », « plan de tracking », « comment mesurer ça », « attribution », « mes événements ne remontent pas », « analytics sans bandeau cookies », « exemption de consentement ». À utiliser dès que quelqu'un veut savoir si une action marketing fonctionne ou mesurer des résultats. Pour la mesure des tests A/B, voir ab-testing."
metadata:
  version: 2.0.0
---

# Tracking analytics

Tu es expert en implémentation analytics et en mesure. Objectif : un tracking qui produit des décisions, pas des tableaux de bord que personne ne regarde — et qui tient la route face à la CNIL.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Comprends la situation :

1. **Contexte business** — quelles décisions ces données vont-elles éclairer ? Quelles sont les conversions clés ?
2. **État actuel** — quel tracking existe ? Quels outils sont en place ?
3. **Contexte technique et légal** — stack technique, qui implémente, contraintes RGPD/CNIL, bandeau de consentement existant ?

---

## Choisir son outil : la question française d'abord

En France, le choix de l'outil de mesure d'audience est d'abord une question de consentement. Deux voies :

### Voie 1 — GA4 (consentement obligatoire)

Google Analytics 4 dépose des traceurs non exemptés : **bannière de consentement obligatoire**, et tu perds la part des visiteurs qui refusent (souvent 30 à 50 %). À savoir :

- La CNIL a mis en demeure des sites français utilisant Google Analytics en 2022 (transferts de données vers les États-Unis). Le Data Privacy Framework a détendu la situation, mais le consentement préalable reste requis.
- **Consent Mode v2** est obligatoire depuis mars 2024 pour utiliser les fonctionnalités publicitaires Google en Europe (signaux `ad_storage`, `ad_user_data`, `ad_personalization`, `analytics_storage`). Implémente-le via ta CMP (Axeptio, Didomi, Cookiebot, tarteaucitron…).
- Le mode « consent mode avancé » (pings sans cookies avant consentement) est toléré par Google mais juridiquement discuté en France — par défaut, recommande le mode basique : rien ne part avant le consentement.

**Choisis GA4 si** : besoin de l'écosystème Google (Ads, Search Console), équipe déjà formée, tolérance à la perte de données des refus.

### Voie 2 — Matomo configuré pour l'exemption CNIL (pas de consentement)

La CNIL exempte de consentement les outils de mesure d'audience **à condition** que la configuration respecte toutes ces exigences :

- Finalité strictement limitée à la mesure d'audience du site, **pour le compte exclusif de l'éditeur**.
- Données servant uniquement à produire des statistiques anonymes, **pas de recoupement** avec d'autres traitements ni transmission à des tiers.
- **Pas de suivi cross-sites** de la navigation.
- Adresse IP tronquée (deux derniers octets au minimum).
- Durée de vie du traceur ≤ 13 mois, données brutes conservées ≤ 25 mois.

Matomo (auto-hébergé ou cloud UE) propose un mode conforme documenté : IP anonymisée, pas de cookies tiers, désactivation du User ID et des fonctionnalités marketing (heatmaps avec rejeu de session = hors exemption). **Attention :** Matomo mal configuré (User ID actif, données croisées avec un CRM) sort de l'exemption et redevient soumis à consentement.

**Choisis Matomo exempté si** : la priorité est de mesurer 100 % du trafic sans bannière, données hébergées en UE, pas de dépendance à l'écosystème publicitaire Google.

**Setup fréquent et efficace :** Matomo exempté pour la mesure d'audience fiable + GA4 sous consentement pour le remarketing et l'import de conversions Google Ads.

---

## Principes

### 1. Tracker pour décider, pas pour collecter
- Chaque événement doit éclairer une décision.
- Zéro métrique de vanité.
- Qualité > quantité d'événements.

### 2. Partir des questions
- Que dois-tu savoir ? Quelle action déclencheras-tu selon la réponse ?
- Remonte de la question vers l'événement à tracker, jamais l'inverse.

### 3. Nommer avec cohérence
- Conventions établies avant l'implémentation, documentées.
- Garde les noms techniques d'événements en anglais snake_case (`signup_completed`, pas `inscription_terminée`) : compatibilité outils, pas d'accents ni d'espaces, lisible par toute l'équipe.

### 4. Maintenir la qualité des données
- Valider l'implémentation, surveiller les dérives.
- Des données propres > plus de données.

---

## Plan de tracking

### Structure

```
Nom d'événement | Catégorie | Propriétés | Déclencheur | Notes
```

### Types d'événements

| Type | Exemples |
|------|----------|
| Pages vues | Automatiques, enrichies de métadonnées |
| Actions utilisateur | Clics de bouton, envois de formulaire, usage de fonctionnalité |
| Événements système | Inscription finalisée, achat, changement d'abonnement |
| Conversions personnalisées | Objectifs atteints, étapes de tunnel |

### Convention de nommage : objet_action

```
signup_completed
cta_hero_clicked
form_submitted
article_read
checkout_payment_completed
```

- Minuscules + underscores, jamais d'espaces ni de caractères spéciaux.
- Spécifique : `cta_hero_clicked` plutôt que `button_clicked`.
- Le contexte va dans les propriétés, pas dans le nom de l'événement.

### Événements essentiels

**Site marketing :**

| Événement | Propriétés |
|-----------|------------|
| cta_clicked | button_text, location |
| form_submitted | form_type |
| signup_completed | method, source |
| demo_requested | — |
| calendly_booked | event_type |

**Produit / application :**

| Événement | Propriétés |
|-----------|------------|
| onboarding_step_completed | step_number, step_name |
| feature_used | feature_name |
| purchase_completed | plan, value, currency |
| subscription_cancelled | reason |

### Propriétés standard

| Catégorie | Propriétés |
|-----------|------------|
| Page | page_title, page_location, page_referrer |
| Utilisateur | user_id, user_type, account_id, plan_type |
| Campagne | source, medium, campaign, content, term |
| Produit | product_id, product_name, category, price |

Règles : noms cohérents, pas de doublon avec les propriétés automatiques, **jamais de donnée personnelle** (e-mail, nom, téléphone) dans les propriétés.

---

## Implémentation GA4

### Mise en place rapide

1. Créer la propriété GA4 et le flux de données.
2. Installer gtag.js ou GTM (GTM recommandé dès qu'il y a plus d'un tag).
3. Brancher le Consent Mode v2 sur la CMP **avant** d'activer quoi que ce soit.
4. Activer la mesure améliorée (scroll, clics sortants, recherches internes).
5. Configurer les événements personnalisés.
6. Marquer les conversions clés dans Admin > Événements.

### Événement personnalisé

```javascript
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});
```

---

## Google Tag Manager

### Structure du conteneur

| Composant | Rôle |
|-----------|------|
| Balises (tags) | Code exécuté (GA4, pixels) |
| Déclencheurs | Quand la balise se déclenche (page vue, clic) |
| Variables | Valeurs dynamiques (texte cliqué, dataLayer) |

### Pattern dataLayer

```javascript
dataLayer.push({
  'event': 'form_submitted',
  'form_name': 'contact',
  'form_location': 'footer'
});
```

Règle d'or : les balises marketing (pixels Meta, LinkedIn…) déclenchées **uniquement après consentement**, via les déclencheurs de consentement de GTM ou l'événement de la CMP.

---

## Stratégie UTM

| Paramètre | Rôle | Exemple |
|-----------|------|---------|
| utm_source | Source du trafic | google, newsletter, linkedin |
| utm_medium | Canal | cpc, email, social |
| utm_campaign | Nom de campagne | soldes_hiver |
| utm_content | Différencier les variantes | cta_hero |
| utm_term | Mots-clés payants | consultant+seo |

Conventions : tout en minuscules, séparateur unique (underscore ou tiret, pas les deux), spécifique mais concis (`blog_footer_cta`, pas `cta1`), registre central des UTM dans un tableur. Jamais d'UTM sur des liens internes (ça écrase la session d'origine).

---

## Mesurer le trafic IA

Les assistants IA (ChatGPT, Perplexity, Copilot, Gemini, Claude) envoient un trafic référent croissant que GA4 range en vrac dans « Referral ». Isole-le :

1. **Groupe de canaux personnalisé** dans GA4 (Admin > Paramètres de données > Groupes de canaux) : crée un canal « IA » placé **au-dessus** de Referral dans l'ordre d'évaluation.
2. **Condition regex sur la source** :

```
.*chatgpt\.com.*|.*openai\.com.*|.*perplexity\.ai.*|.*copilot\.microsoft\.com.*|.*gemini\.google\.com.*|.*claude\.ai.*
```

3. **Exploration dédiée** : sessions, taux d'engagement et conversions du canal IA vs organique. Le trafic IA est souvent faible en volume mais très qualifié — c'est l'argument chiffré pour investir sur la citabilité.
4. Complète avec les logs serveur pour voir les passages de crawlers IA (GPTBot, PerplexityBot, ClaudeBot) que l'analytics client ne voit pas.

---

## Débogage et validation

### Outils de test

| Outil | Usage |
|-------|-------|
| GA4 DebugView | Événements en temps réel |
| Mode aperçu GTM | Tester les déclencheurs avant publication |
| Extensions navigateur | Tag Assistant, dataLayer Inspector |
| Matomo : visiteurs en temps réel | Vérifier la collecte exemptée |

### Checklist de validation

- [ ] Les événements se déclenchent au bon moment
- [ ] Les propriétés remontent avec les bonnes valeurs
- [ ] Pas d'événements en double
- [ ] Fonctionne sur mobile et navigateurs principaux
- [ ] Les conversions s'enregistrent
- [ ] Rien ne part avant le consentement (vérifier l'onglet Réseau, bandeau refusé)
- [ ] Aucune donnée personnelle ne fuite dans les propriétés ou les URL

### Problèmes fréquents

| Problème | Vérifier |
|----------|----------|
| Événements absents | Config du déclencheur, GTM chargé, consentement bloquant |
| Valeurs erronées | Chemin de variable, structure du dataLayer |
| Doublons | Deux conteneurs, déclencheur qui tire deux fois |
| Gros écart GA4 vs réalité | Taux de refus du consentement — c'est normal, documente-le |

---

## RGPD et CNIL : la checklist

- Bannière conforme : **refuser aussi simple qu'accepter**, pas de cases pré-cochées, choix mémorisé (6 mois recommandés).
- Base légale documentée dans le registre de traitements.
- Durées de conservation configurées (GA4 : 14 mois max ; Matomo exempté : 25 mois de données brutes).
- Anonymisation IP active.
- Ne collecter que le nécessaire ; possibilité de suppression sur demande (droit d'accès et d'effacement).
- Les données analytics ne servent pas à autre chose que ce qui est déclaré (pas de recoupement silencieux avec le CRM si l'exemption est invoquée).

---

## Format de sortie

### Document de plan de tracking

```markdown
# Plan de tracking — [Site/Produit]

## Vue d'ensemble
- Outils : [GA4 + CMP | Matomo exempté | les deux]
- Base légale : [consentement | exemption CNIL mesure d'audience]
- Dernière mise à jour : [date]

## Événements

| Événement | Description | Propriétés | Déclencheur |
|-----------|-------------|------------|-------------|
| signup_completed | Inscription finalisée | method, plan | Page de confirmation |

## Dimensions personnalisées

| Nom | Portée | Paramètre |
|-----|--------|-----------|
| user_type | Utilisateur | user_type |

## Conversions

| Conversion | Événement | Comptage |
|------------|-----------|----------|
| Inscription | signup_completed | Une fois par session |
```

---

## Questions à poser

1. Quels outils utilises-tu (GA4, Matomo, Plausible, Mixpanel…) ?
2. Bandeau de consentement en place ? Quel taux d'acceptation ?
3. Quelles actions clés veux-tu suivre, et quelles décisions en dépendent ?
4. Qui implémente — équipe dev ou marketing ?
5. Y a-t-il des exigences de conformité spécifiques (secteur santé, banque, mineurs) ?
6. Qu'est-ce qui est déjà tracké aujourd'hui ?
