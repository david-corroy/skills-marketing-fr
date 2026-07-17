🇫🇷 Français · [🇬🇧 English](README.en.md) · [🇪🇸 Español](README.es.md)

# Skills Marketing FR

**47 skills marketing en français pour Claude Code** — copywriting, acquisition, conversion, rétention, growth. Pas une traduction : une adaptation au marché français (exemples français, Brevo/Mailjet, euros HT/TTC) et au droit français (RGPD/CNIL, pratiques commerciales trompeuses L121-2, loi influenceurs, cadre SMS), avec la couche visibilité IA (GEO) intégrée à chaque étape.

![Skills](https://img.shields.io/badge/skills-47%2F47-2ea44f) ![Licence](https://img.shields.io/badge/licence-MIT-blue) ![Langue](https://img.shields.io/badge/langue-fran%C3%A7ais-0055A4)

Vous tapez « écris-moi la page tarifs » ou « mes clients résilient » dans Claude Code : le bon skill se déclenche tout seul et travaille avec les réflexes d'un marketeur français — pas d'un template anglophone traduit à la va-vite.

## Sommaire

- [Comment les skills travaillent ensemble](#comment-les-skills-travaillent-ensemble)
- [Catalogue des 47 skills](#catalogue-des-47-skills)
  - [Stratégie & organisation](#stratégie--organisation)
  - [Contenu & copie](#contenu--copie)
  - [Acquisition](#acquisition)
  - [SEO & IA](#seo--ia)
  - [Conversion](#conversion)
  - [Rétention & growth](#rétention--growth)
  - [Mesure](#mesure)
  - [Ventes](#ventes)
- [Installation](#installation)
- [Exemples d'usage](#exemples-dusage)
- [FAQ](#faq)
- [Auteur](#auteur)

## Comment les skills travaillent ensemble

Un skill isolé rend service. Le pack complet forme un système : le plan cadre tout, chaque étage nourrit le suivant, la mesure boucle sur le plan.

```
        ┌───────────────────────────────┐
        │        marketing-plan         │
        │   le plan d'ensemble (AARRR)  │
        └───────────────┬───────────────┘
                        │
        ┌───────────────▼───────────────┐
        │           STRATÉGIE           │
        │   customer-research           │
        │   competitors                 │
        │   marketing-psychology        │
        └───────────────┬───────────────┘
                        │
        ┌───────────────▼───────────────┐
        │          ACQUISITION          │
        │   ads · cold-email · social   │
        │   content-strategy · ai-seo   │
        └───────────────┬───────────────┘
                        │
        ┌───────────────▼───────────────┐
        │          CONVERSION           │
        │   copywriting · cro · popups  │
        │   signup · pricing · offers   │
        └───────────────┬───────────────┘
                        │
        ┌───────────────▼───────────────┐
        │      RÉTENTION & GROWTH       │
        │   onboarding · emails         │
        │   churn-prevention            │
        │   referrals · marketing-loops │
        └───────────────┬───────────────┘
                        │
        ┌───────────────▼───────────────┐
        │            MESURE             │
        │    analytics · ab-testing     │
        └───────────────┬───────────────┘
                        │
                        └──▶ les enseignements nourrissent
                             le cycle suivant du plan
```

Conseil de démarrage : lancez d'abord [`product-marketing`](skills/product-marketing/SKILL.md). Il crée le document de contexte (`.agents/product-marketing.md`) que tous les autres skills lisent — vous ne répétez plus jamais qui vous êtes, ce que vous vendez et à qui.

## Catalogue des 47 skills

### Stratégie & organisation

| Skill | Description |
|---|---|
| [`marketing-plan`](skills/marketing-plan/SKILL.md) | Plan marketing 12 mois structuré AARRR, calibré sur le budget, l'équipe et le stade réels — volet visibilité IA inclus |
| [`marketing-ideas`](skills/marketing-ideas/SKILL.md) | Bibliothèque de tactiques éprouvées pour trouver les bonnes stratégies selon votre situation et vos ressources |
| [`marketing-council`](skills/marketing-council/SKILL.md) | Conseil consultatif simulé de marketeurs légendaires (Godin, Ogilvy, Dunford…) : désaccords assumés, puis synthèse |
| [`marketing-psychology`](skills/marketing-psychology/SKILL.md) | Biais cognitifs et sciences comportementales appliqués au marketing, dans les limites du droit de la consommation |
| [`customer-research`](skills/customer-research/SKILL.md) | Entretiens, enquêtes, avis, tickets : extraire ce que les clients pensent et disent vraiment — JTBD, personas |
| [`competitors`](skills/competitors/SKILL.md) | Pages comparatives et « alternative à » qui rankent, dans les clous de la publicité comparative française |
| [`competitor-profiling`](skills/competitor-profiling/SKILL.md) | Fiches concurrents structurées à partir d'URL, avec part de voix dans les réponses IA (ChatGPT/Perplexity) |
| [`product-marketing`](skills/product-marketing/SKILL.md) | Le document de contexte produit que tous les autres skills lisent : positionnement, ICP, messages — une fois pour toutes |

### Contenu & copie

| Skill | Description |
|---|---|
| [`copywriting`](skills/copywriting/SKILL.md) | Textes de pages qui convertissent — accueil, landing, tarifs, hero — en français qui sonne français |
| [`copy-editing`](skills/copy-editing/SKILL.md) | Relecture d'un texte existant par passes ciblées, sans dénaturer le message ni la voix de l'auteur |
| [`content-strategy`](skills/content-strategy/SKILL.md) | Décider quoi publier : piliers, calendrier éditorial, sujets qui visent Google ET les moteurs de réponse IA |
| [`emails`](skills/emails/SKILL.md) | Séquences et automations email (bienvenue, nurturing, réactivation) conformes RGPD — scénarios Brevo/Mailjet |
| [`video`](skills/video/SKILL.md) | Production vidéo IA et programmatique : démos, explainers, clips sociaux (Remotion, HeyGen, Veo, Sora…) |
| [`image`](skills/image/SKILL.md) | Génération, retouche et optimisation d'images marketing : OG, bannières, mockups, compression AVIF/WebP |
| [`ad-creative`](skills/ad-creative/SKILL.md) | Créations publicitaires à l'unité ou en volume : titres, accroches, angles, variations, itération sur données réelles |

### Acquisition

| Skill | Description |
|---|---|
| [`ads`](skills/ads/SKILL.md) | Campagnes payantes Google/Meta/LinkedIn/TikTok avec les contraintes réelles d'un annonceur français (budget PME, consentement) |
| [`cold-email`](skills/cold-email/SKILL.md) | Cold e-mails B2B et séquences de relance qui obtiennent des réponses, avec le cadre légal français (B2B vs B2C) |
| [`prospecting`](skills/prospecting/SKILL.md) | Constituer et qualifier des listes de prospects vérifiés et scorés — posture RGPD à chaque étape (base légale, Bloctel) |
| [`social`](skills/social/SKILL.md) | Contenu réseaux sociaux (LinkedIn, X, Instagram, TikTok…) avec les codes et plateformes qui comptent en France |
| [`sms`](skills/sms/SKILL.md) | Programmes SMS/MMS qui génèrent du chiffre en respectant le cadre français : consentement, STOP au 36111, règles opérateurs |
| [`public-relations`](skills/public-relations/SKILL.md) | Relations presse et médias gagnés : journalistes, podcasts, newsletters, PQR, newsjacking, tribunes |
| [`co-marketing`](skills/co-marketing/SKILL.md) | Identifier les bons partenaires et monter des campagnes conjointes à fort impact (webinaires, échanges de newsletters) |
| [`community-marketing`](skills/community-marketing/SKILL.md) | Créer et animer une communauté (Slack, Discord, ambassadeurs) qui produit des résultats business mesurables |
| [`directory-submissions`](skills/directory-submissions/SKILL.md) | Annuaires français (PagesJaunes, CCI, Trustpilot…) : backlinks, cohérence NAP et citations par les IA |
| [`launch`](skills/launch/SKILL.md) | Lancements de produits et annonces qui créent de l'élan : Product Hunt, bêta, liste d'attente, plan GTM |
| [`aso`](skills/aso/SKILL.md) | Audit et optimisation de fiches App Store / Google Play : métadonnées, visuels, avis — marché français d'abord |

### SEO & IA

| Skill | Description |
|---|---|
| [`ai-seo`](skills/ai-seo/SKILL.md) | GEO : être cité et recommandé par ChatGPT, Perplexity, AI Overviews, Claude, Gemini — méthode CITE complète |
| [`seo-audit`](skills/seo-audit/SKILL.md) | Diagnostic SEO priorisé par impact : indexation, on-page, Core Web Vitals, chute de trafic, erreurs de crawl |
| [`schema`](skills/schema/SKILL.md) | Données structurées JSON-LD pour les résultats enrichis et une entité mieux comprise par les moteurs et les IA |
| [`site-architecture`](skills/site-architecture/SKILL.md) | Hiérarchie des pages, navigation, URL et maillage interne pensés pour les visiteurs et les moteurs |
| [`programmatic-seo`](skills/programmatic-seo/SKILL.md) | Pages templatées à l'échelle qui rankent sans contenu fin : [métier] + [ville], intégrations, comparatifs |

### Conversion

| Skill | Description |
|---|---|
| [`cro`](skills/cro/SKILL.md) | Analyse d'une page marketing et recommandations actionnables pour augmenter son taux de conversion |
| [`popups`](skills/popups/SKILL.md) | Popups et modales qui convertissent sans exaspérer, sans casser les Core Web Vitals ni enfreindre les règles CNIL |
| [`signup`](skills/signup/SKILL.md) | Parcours d'inscription : réduire la friction et l'abandon, avec le RGPD comme contrainte de conception |
| [`pricing`](skills/pricing/SKILL.md) | Prix et grilles tarifaires dans le cadre français : HT/TTC, TVA, TJM, freemium, annuel vs mensuel |
| [`offers`](skills/offers/SKILL.md) | Construire l'offre elle-même : cadrage de valeur, bonus, garantie, rareté, nom, structure de paiement |
| [`paywalls`](skills/paywalls/SKILL.md) | Paywalls et écrans d'upgrade in-app : convertir le gratuit en payant au moment où la valeur est vécue |
| [`free-tools`](skills/free-tools/SKILL.md) | Outils gratuits « engineering as marketing » : calculateurs, graders, générateurs qui captent leads et backlinks |
| [`lead-magnets`](skills/lead-magnets/SKILL.md) | Choisir et diffuser l'aimant à leads qui capture des e-mails qualifiés, dans le respect du RGPD |

### Rétention & growth

| Skill | Description |
|---|---|
| [`onboarding`](skills/onboarding/SKILL.md) | Amener chaque nouvel utilisateur à son « moment aha » le plus vite possible : activation, checklists, time to value |
| [`churn-prevention`](skills/churn-prevention/SKILL.md) | Réduire le churn volontaire et involontaire : parcours de résiliation, offres de sauvetage, relance des impayés |
| [`referrals`](skills/referrals/SKILL.md) | Parrainage, affiliation et bouche-à-oreille dans le cadre français (CNIL, obligations de transparence) |
| [`marketing-loops`](skills/marketing-loops/SKILL.md) | Boucles marketing récurrentes qu'un agent IA exécute à cadence fixe, en orchestrant les autres skills |

### Mesure

| Skill | Description |
|---|---|
| [`analytics`](skills/analytics/SKILL.md) | Tracking GA4/Matomo/GTM qui produit des décisions — et qui tient la route face à la CNIL (exemption de consentement) |
| [`ab-testing`](skills/ab-testing/SKILL.md) | Tests A/B statistiquement valides et programme d'expérimentation : hypothèses, durée, score ICE, backlog |

### Ventes

| Skill | Description |
|---|---|
| [`revops`](skills/revops/SKILL.md) | Relier le marketing au chiffre d'affaires : lead scoring, routage, MQL/SQL, étapes de pipeline, SLA, dashboards |
| [`sales-enablement`](skills/sales-enablement/SKILL.md) | Decks, one-pagers, traitement des objections, scripts de démo et playbooks que les commerciaux utilisent vraiment |

## Installation

### Option 1 — Plugin marketplace (recommandée)

Dans Claude Code :

```
/plugin marketplace add david-corroy/skills-marketing-fr
/plugin install skills-marketing-fr@skills-marketing-fr
```

Les 47 skills sont disponibles immédiatement, et les mises à jour suivent le repo.

### Option 2 — Clone complet

```bash
git clone https://github.com/david-corroy/skills-marketing-fr.git
cp -r skills-marketing-fr/skills/* ~/.claude/skills/
```

Pour un seul projet plutôt qu'en global : copiez dans `.claude/skills/` à la racine du projet.

### Option 3 — Un seul skill (sparse checkout)

```bash
git clone --filter=blob:none --sparse https://github.com/david-corroy/skills-marketing-fr.git
cd skills-marketing-fr
git sparse-checkout set skills/copywriting
cp -r skills/copywriting ~/.claude/skills/
```

Remplacez `copywriting` par le skill de votre choix.

## Exemples d'usage

Rien à invoquer à la main : vous décrivez votre besoin, le skill correspondant se déclenche.

| Vous tapez dans Claude Code… | Skill déclenché |
|---|---|
| « Écris-moi le texte de ma page tarifs » | [`copywriting`](skills/copywriting/SKILL.md) |
| « Mes concurrents sortent dans ChatGPT et pas moi » | [`ai-seo`](skills/ai-seo/SKILL.md) |
| « Monte une séquence de bienvenue dans Brevo » | [`emails`](skills/emails/SKILL.md) |
| « Mes clients résilient, aide-moi à réduire le churn » | [`churn-prevention`](skills/churn-prevention/SKILL.md) |
| « Il me faut un plan marketing 12 mois pour ce client » | [`marketing-plan`](skills/marketing-plan/SKILL.md) |

## FAQ

**C'est gratuit ?**
Oui. Licence MIT : usage libre, y compris commercial et en agence. Voir [LICENSE](LICENSE).

**Quelle différence avec les packs de skills anglophones ?**
Trois choses. 1) Le marché : exemples français, outils utilisés en France (Brevo, Mailjet, smsmode…), prix en euros HT/TTC, TJM, usages B2B français. 2) Le droit : RGPD/CNIL, pratiques commerciales trompeuses (L121-2), publicité comparative, loi influenceurs, cadre SMS (STOP au 36111) sont intégrés comme contraintes de conception, pas ajoutés en note de bas de page. 3) La visibilité IA : la couche GEO (être cité par ChatGPT, Perplexity, AI Overviews) est câblée dans les skills concernés, pas vendue à part.

**La conformité RGPD est vraiment intégrée ?**
Les skills traitent le RGPD et la doctrine CNIL comme des contraintes de conception : base légale avant la collecte, consentement SMS/email, exemption de consentement analytics, Bloctel en prospection. Ça ne remplace pas un avis juridique — ça évite les erreurs évidentes dès le premier jet.

**Faut-il des clés API ou des outils payants ?**
Non. Les skills sont des instructions en markdown que Claude Code lit nativement. Certains skills mentionnent des outils externes (Brevo, GA4, plateformes publicitaires) parce que votre stack en a besoin — mais le pack lui-même ne requiert rien.

**Qui maintient ce pack ?**
[Bernard David Corroy](https://www.david-corroy.com/), consultant SEO & GEO. Les skills évoluent avec les plateformes (moteurs IA, règles CNIL, formats publicitaires) ; les mises à jour passent par ce repo.

## Auteur

**Bernard David Corroy** — consultant SEO & GEO. J'aide les entreprises à être visibles sur Google et citées par les IA (ChatGPT, Perplexity, AI Overviews).

- Site : [david-corroy.com](https://www.david-corroy.com/)
- Audit express de votre visibilité IA : [david-corroy.com/audit-express](https://www.david-corroy.com/audit-express/)
- Formation GEO gratuite (7 leçons par e-mail) : [david-corroy.com/formation-geo](https://www.david-corroy.com/formation-geo/)
- LinkedIn : [bernard-david-corroy](https://www.linkedin.com/in/bernard-david-corroy/)
- Wikidata : [Q140472682](https://www.wikidata.org/entity/Q140472682)

Autres repos :

- [skills-seo-geo](https://github.com/david-corroy/skills-seo-geo) — skills SEO & GEO pour Claude Code : audit, contenu, technique, netlinking, tracking IA
- [prompts-geo](https://github.com/david-corroy/prompts-geo) — panels de prompts pour mesurer la visibilité d'une marque dans les réponses IA
- [ba-avif](https://github.com/david-corroy/ba-avif) — conversion AVIF des images pour WordPress
- [html-head-seo](https://github.com/david-corroy/html-head-seo) — le `<head>` HTML de référence pour le SEO et le GEO

## Licence

[MIT](LICENSE)
