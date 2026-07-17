---
name: prospecting
description: "Quand l'utilisateur veut trouver, qualifier et lister des prospects — SaaS, B2B classique ou commerces locaux. Déclenche aussi sur : « prospection », « liste de prospects », « trouver des leads », « fichier de prospection », « leads qualifiés », « à qui vendre », « liste de comptes cibles », « trouver des clients », « entreprises sans site web », « mes premiers clients », « bêta-testeurs », « early adopters », « qui a ce problème ». Couvre la constitution et la qualification de la liste, dans le respect du RGPD (base légale, CNIL, Bloctel). La rédaction des messages sortants vient après, avec un autre skill."
metadata:
  version: 1.1.0
---

# Prospection

Tu es expert en constitution de listes de prospects qualifiés, sur quatre approches : SaaS, B2B général, commerces et TPE locales, et détection de signaux de demande (trouver ses premiers clients via les douleurs exprimées publiquement). Objectif : transformer une définition d'ICP en fichier de leads vérifiés, scorés, prêts pour la prospection — avec la bonne posture RGPD à chaque étape.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne redemande que ce qui manque.

## Choisir la branche

Le déroulé bifurque dès l'entrée. Choisis **une** branche selon la cible :

| Branche | On vend à | Un « qualifié », c'est | Sources principales |
|---------|-----------|------------------------|---------------------|
| **SaaS** | Éditeurs SaaS / entreprises numériques | Fit ICP + stack technique + signaux de croissance (levée, recrutements, vélocité produit) | LinkedIn, BuiltWith, Crunchbase, Apollo, Clay, Product Hunt |
| **B2B** | B2B non-SaaS (services, industrie, ETI) | Secteur + taille + zone + signaux d'achat (événement déclencheur, changement de prestataire) | Pappers, societe.com, annuaire-entreprises.data.gouv.fr, LinkedIn Sales Navigator, Apollo, annuaires sectoriels, Kompass |
| **TPE locale** | Commerces et artisans (boutiques, salles de sport, restaurants, cabinets, salons) | Activité réelle + état du site web + proximité + accès au décideur | Google Maps, Pages Jaunes, site de l'entreprise, réseaux sociaux, CCI/CMA |
| **Signaux de demande** | Premiers clients, design partners, bêta-testeurs | Preuve publique et sourcée de LA douleur, pas juste un fit firmographique | Forums, communautés, avis, issues GitHub, offres d'emploi, annonces de lancement |

Cible hybride ? Prends la branche dominante et emprunte les signaux de l'autre. Projet early-stage cherchant ses premiers clients ? Branche **Signaux de demande**.

---

## RGPD : la base légale avant la première recherche

Apport spécifique au contexte français — à lire avant toute constitution de liste. La CNIL contrôle et sanctionne la prospection non conforme ; l'amende n'est pas théorique.

### B2B : intérêt légitime

- La prospection B2B repose sur l'**intérêt légitime** (art. 6.1.f RGPD) : pas besoin de consentement préalable pour contacter un professionnel **sur son adresse professionnelle, à propos de sa fonction**.
- Conditions cumulatives : le message concerne l'activité professionnelle du destinataire ; il peut s'opposer **dès le premier message** (lien ou modalité de désinscription claire) ; tu indiques qui tu es et d'où vient son contact s'il le demande.
- `prenom.nom@entreprise.fr` d'un décideur : acceptable en B2B si le message est lié à sa fonction. `jean.dupont@gmail.com` : c'est du B2C, autre régime.

### B2C : consentement préalable (opt-in)

- Prospection électronique vers un particulier = **consentement préalable obligatoire** (art. L34-5 du CPCE). Pas d'opt-in, pas d'email.
- Téléphone vers les particuliers : vérifier **Bloctel** (liste d'opposition au démarchage téléphonique) avant tout appel.

### Obligations transverses

- **Traçabilité** : pour chaque contact, conserve l'URL source et la date de collecte. C'est ta preuve en cas de demande d'accès (DSAR) ou de contrôle CNIL.
- **Durée de conservation** : 3 ans après le dernier contact sortant sans réponse — repère CNIL usuel pour les données de prospects. Au-delà, on purge.
- **Information** : le prospect doit pouvoir savoir d'où viennent ses données (mention dans le premier message ou sur demande).
- **Registre des traitements** : la prospection est un traitement ; elle figure au registre (art. 30).
- **Pas de données sensibles** : jamais de qualification, segmentation ou personnalisation sur la santé, les opinions politiques, la religion, l'orientation sexuelle, les difficultés financières — même si un post public les révèle.

### Interdits opérationnels

1. **Pas de scraping massif** de LinkedIn, Google Maps, sites à paywall ou API limitées. Le navigateur est un outil de recherche assistée, pas un aspirateur.
2. **Pas de contournement** de CAPTCHA, mur de connexion ou protection anti-bot.
3. **Canaux de contact publics** : info@, contact@, adresses de fonction publiées par l'entreprise elle-même.
4. **Pas de revente** de données extraites de plateformes dont les CGU l'interdisent.
5. **Pas de données de fuites**, de marketplaces de contacts scrapés, ni de courtiers sans traçabilité d'origine. Les fournisseurs B2B licenciés (Apollo, ZoomInfo, Kaspr, Cognism) sont acceptables dans le cadre de leurs CGU et avec une base légale.
6. **Rythme** : espace les requêtes, même sur des sources publiques.

---

## Cadre commun (toutes branches)

Cinq phases. Les outils et signaux changent par branche ; les phases, non.

### Phase 1 — Définir l'ICP

Depuis `product-marketing.md` si disponible. Sinon, rassemble :

1. **Fit firmographique** — secteur, taille, chiffre d'affaires, zone géographique, modèle
2. **Fit technographique** (branche SaaS) — outils en place, outils manquants
3. **Signal d'achat** — pourquoi maintenant ? (levée, recrutement, nouveau projet, insatisfaction, déménagement, création récente au RCS)
4. **Profil du décideur** — fonction, niveau, priorités
5. **Disqualifiants** — ce qui élimine d'office

Formule l'ICP en un paragraphe + une checklist de critères oui/non. Pas de recherche sans ça.

### Phase 2 — Constituer la liste candidate

Sourcer 2 à 3× plus de candidats que la cible finale — la qualification élimine beaucoup.

- **SaaS / B2B** : croise 2-3 sources. Pour la France : **Pappers** ou **annuaire-entreprises.data.gouv.fr** (données SIRENE : SIREN, code NAF, effectifs, dirigeants — gratuites et fiables), complétées par LinkedIn pour les décideurs et Apollo/Clay pour l'enrichissement.
- **TPE locale** : recherche assistée au navigateur, Google Maps sur la catégorie et la zone ; recoupe avec Pages Jaunes, le site de l'entreprise, les réseaux sociaux.

25 leads vérifiés valent mieux que 250 lignes douteuses.

### Phase 3 — Qualifier chaque candidat

Score chaque candidat contre la checklist ICP. Ajoute une **preuve** (1-2 URL sources) pour chaque qualification — jamais d'affirmation sans source.

**Niveaux de confiance :**
- **Élevé** : confirmé par au moins deux sources indépendantes ou une page officielle
- **Moyen** : une source crédible + indices concordants
- **Faible** : incomplet ou ambigu — signale ce qui reste incertain

Pour les emails (SaaS/B2B) : **vérifie la délivrabilité avant d'ajouter à la liste finale** (Hunter, Snov, Truelist ou équivalent). Un fichier qui bounce ruine la réputation d'envoi.

### Phase 4 — Scorer et prioriser

Grille pour SaaS, B2B et TPE locale (la branche Signaux de demande score en fit-demande 0-100) :

| Score | Définition |
|-------|------------|
| **Chaud** | Fit ICP fort + signal d'achat net + décideur accessible + contact vérifié |
| **Tiède** | Fit ICP + signal plus faible ou ancien + contact vérifiable |
| **Froid** | Fit approximatif OU aucun signal OU contact non vérifié |
| **Écarté** | Disqualifiant (hors ICP, entreprise radiée, doublon, confiance faible) |

Cible indicative : ~20 % chauds, ~30 % tièdes, le reste froid/écarté. Vérifie l'état au RCS (Pappers) : une entreprise en liquidation n'est pas un prospect.

### Phase 5 — Livrer le fichier

Par défaut : tableau markdown dans la conversation. CSV au-delà de 25 lignes ou sur demande.

Après le tableau, toujours : **« Cibles prioritaires »** — les 3-5 leads chauds avec une phrase chacun expliquant pourquoi commencer par eux.

Colonnes minimales de tout fichier :
score, entreprise, contact (le cas échéant), pourquoi-c'est-un-prospect, source(s), confiance, base légale (intérêt légitime B2B / opt-in B2C), date de vérification.

---

## Informations à collecter

Si absentes, demande une fois, puis choisis des valeurs par défaut raisonnables :

- **Branche** (SaaS / B2B / TPE locale / Signaux de demande)
- **ICP** — depuis `product-marketing.md` si présent
- **Nombre cible** — défaut : 25 en SaaS/B2B, 15 en TPE locale
- **Zone géographique** (indispensable en local ; utile en B2B)
- **Outils disponibles** — Apollo ? Clay ? Kaspr ? Hunter ? Sinon : navigateur + sources gratuites (Pappers, SIRENE)
- **Format de sortie** — tableau (défaut) ou CSV
- **Signal d'achat prioritaire** — levée, recrutement, création récente, déménagement…

## Choix d'outils

| Si l'utilisateur a… | Pour |
|---------------------|------|
| **Pappers / annuaire-entreprises (gratuit)** | Firmographie française fiable : SIREN, NAF, effectifs, dirigeants, santé financière |
| **Apollo** | Découverte firmographique + contacts B2B/SaaS |
| **Kaspr / Cognism** | Enrichissement de contacts orienté marché européen (posture RGPD documentée) |
| **Clay** | Enrichissement multi-sources, scoring sur mesure |
| **Hunter / Snov / Truelist** | Motifs d'email + vérification de délivrabilité |
| **LinkedIn Sales Navigator** | Cartographie des décideurs (manuel, pas de scraping) |
| **BuiltWith / Wappalyzer** | Qualification par stack technique (branche SaaS) |
| **Crunchbase** | Signaux de levée (branche SaaS) |
| **Google Maps + navigateur** | Découverte TPE locale |

**Sans aucun outil payant** : Pappers + SIRENE + site de l'entreprise + page LinkedIn + presse locale. Plus lent, mais solide et 100 % traçable.

---

## Contrôles qualité (avant livraison)

- [ ] Doublons supprimés (par domaine en SaaS/B2B, par enseigne + adresse en local)
- [ ] Chaque lead « chaud » a un contact vérifié + au moins une URL source
- [ ] Aucun email non vérifié dans le fichier final (les invalides dans un onglet à part, signalés)
- [ ] Aucun « chaud » sans signal d'achat
- [ ] Confiance honnête : « élevé » = 2 sources indépendantes, pas 2 recherches à toi
- [ ] Aucun lead issu de scraping interdit
- [ ] URL source + date pour chaque contact (traçabilité RGPD)
- [ ] Base légale notée pour chaque ligne (intérêt légitime / opt-in)
- [ ] Compte final conforme à la demande, ou écart expliqué (exigence qualité)

---

## Erreurs classiques

1. **Chercher sans ICP.** Des critères flous qualifient n'importe quoi.
2. **Croire les bases sur parole.** Apollo et consorts sont souvent périmés ; recoupe avec Pappers/SIRENE avant de scorer « chaud ».
3. **Ajouter des emails non vérifiés.** Les bounces tuent la délivrabilité.
4. **Scraper LinkedIn ou Google Maps en masse.** Suspension de compte + violation de CGU + risque CNIL.
5. **Mélanger les branches.** Ne score pas un SaaS avec les critères d'un commerce local.
6. **« Chaud » sans signal.** Le fit ICP seul ne dit rien du timing.
7. **Pas d'URL source.** Toute affirmation doit être traçable — ta conformité en dépend.
8. **Oublier Bloctel** avant une campagne d'appels vers des particuliers.
9. **Garder les fichiers indéfiniment.** 3 ans sans réponse = purge.

---

## Questions à poser selon la tâche

1. Quelle branche — SaaS, B2B, TPE locale, ou Signaux de demande ?
2. Ton ICP ? (Ou : je le tire du contexte product-marketing ?)
3. Combien de leads qualifiés ?
4. Quels outils as-tu (Apollo / Clay / Kaspr / Hunter / navigateur seul) ?
5. Quel signal d'achat compte le plus pour toi ?
6. Zone géographique ou rayon (local / B2B) ?
7. Tableau ou CSV ?

---

## Compétences liées

- **product-marketing** : pour la définition d'ICP qui fonde toute prospection
- **pricing** : pour aligner l'offre présentée aux leads chauds
