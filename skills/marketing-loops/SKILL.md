---
name: marketing-loops
description: "Mettre en place un flux marketing récurrent et auto-porté — une boucle répétable qu'un agent IA exécute à cadence fixe (hebdo, quotidienne, sur déclencheur) plutôt qu'une tâche ponctuelle. Déclencheurs : « boucle marketing », « workflow marketing récurrent », « automatiser mon marketing », « revue marketing hebdomadaire », « veille de positions », « alerte de chute de trafic », « surveillance du churn », « rafraîchissement de contenu », « lance ça toutes les semaines », « marketing en continu ». Sert à choisir, adapter et planifier une boucle qui orchestre les autres skills marketing. Pour des idées ponctuelles, voir marketing-ideas. Pour la boucle d'expérimentation, voir ab-testing."
metadata:
  version: 1.2.0
---

# Boucles marketing

Tu aides à monter des **boucles marketing** : des workflows répétables qu'un agent IA exécute à cadence régulière, chacun avec un déclencheur défini, des étapes bornées, une auto-vérification et une condition d'arrêt explicite. Une boucle transforme une tâche que tu ferais à la main (et que tu oublierais) en système toujours actif : la revue SEO du lundi, le contrôle de fatigue publicitaire, la veille des signaux de churn.

C'est le cousin opérationnel de `marketing-ideas`. Les idées disent *quoi essayer une fois*. Les boucles disent *quoi refaire à quelle cadence* — et câblent les autres skills marketing pour le faire.

## Comment utiliser ce skill

**Vérifie d'abord le contexte produit :** si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne demande que ce qui manque.

Ensuite :
1. **Clarifie la mission.** Quel résultat cette boucle doit-elle protéger ou faire croître ? (positions, efficacité pub, activation, rétention, revenu, parrainage, visibilité IA)
2. **Choisis une boucle** dans le catalogue ci-dessous — ou adapte la plus proche.
3. **Règle la cadence** sur la vitesse réelle du signal (voir la règle de cadence).
4. **Fixe le point de contrôle humain.** Ce que la boucle fait seule vs ce qu'elle prépare pour validation avant publication ou dépense.
5. **Planifie-la** (voir « Planifier une boucle »).

Tu montes plusieurs boucles, voire un système complet ? Commence par le tracking + une revue hebdo. Ne construis jamais dix boucles d'un coup : une seule, prouve qu'elle rapporte, puis la suivante.

## Anatomie d'une boucle

Neuf parties. Quand tu crées ou adaptes une boucle, remplis-les toutes — une boucle sans condition d'arrêt, sans auto-vérification ou sans gestion d'état est un passif, pas un actif.

| Partie | Ce qu'elle définit |
|--------|--------------------|
| **Cadence de contrôle** | À quelle fréquence la boucle *regarde* (hebdo / quotidien / sur déclencheur). |
| **Agit quand** | La condition d'action — ce qui doit être vrai pour *faire* quelque chose. La plupart des exécutions d'une bonne boucle finissent en « vérifié, rien à faire ». |
| **Objectif** | Le seul résultat que cette boucle existe pour faire bouger. |
| **Skills utilisés** | Les skills marketing orchestrés à chaque itération. |
| **Corps de boucle** | Les étapes ordonnées de chaque itération. |
| **Auto-vérification** | Le contrôle fait *avant* d'agir — pour ne pas réagir au bruit, à la saisonnalité ou à un bug de tracking. |
| **État / idempotence** | Ce que la boucle mémorise entre deux passages : marqueur de dernière exécution, clé de déduplication, fenêtre de refroidissement, liste des « déjà traités ». Sans ça, les boucles agissent en double, relancent les mêmes personnes, ré-alertent sur la même chose. Non négociable pour tout ce qui est planifié. |
| **Arrêt / débrayage** | Quand la boucle passe son tour, s'arrête, escalade à un humain ou se désactive — et ce qu'elle fait en cas d'erreur. Toute boucle en a un, y compris les boucles de surveillance (leur arrêt = « désactivation manuelle + halte sur erreur », jamais « sans objet »). |
| **Sortie** | Où vont les résultats : fichier, brouillon préparé, notification, rapport. |

La séparation **cadence de contrôle / agit quand** est capitale : une boucle churn peut *vérifier* chaque jour mais n'*agir* que quand un compte franchit un seuil de risque et n'a pas été contacté dans la fenêtre de refroidissement. Les confondre produit des boucles qui ratent la fenêtre ou qui spamment.

## La règle de cadence

Cale la cadence sur la vitesse réelle du signal — pas sur la fréquence à laquelle tu *aimerais* un rapport.

| Signal | Cadence réaliste | Pourquoi |
|--------|------------------|----------|
| Positions, backlinks, autorité | Hebdomadaire | Bouge lentement ; en quotidien, c'est du bruit |
| Fatigue créa, dérive du CPA | Tous les 2-3 jours | Les boucles de feedback Meta/Google se comptent en jours |
| Tunnel d'activation / onboarding | Hebdomadaire | Il faut assez d'inscriptions pour que ce soit significatif |
| Signaux de churn | Quotidien ou sur déclencheur | La fenêtre d'intervention est courte |
| Érosion de contenu / copie | Mensuelle | La décrue de trafic est graduelle |
| Changements concurrents | Hebdomadaire | Les virages prix/positionnement sont rares mais lourds |
| Mentions / écoute sociale | Quotidien | Les fenêtres d'engagement se ferment vite |
| Visibilité IA (citations, part de voix) | Mensuelle | Les réponses des moteurs IA évoluent lentement et varient d'un tirage à l'autre |

La sur-fréquence est le mode d'échec n°1 : elle génère du travail inutile, brûle du budget et t'entraîne à ignorer les sorties.

## Quand NE PAS boucler

Tout ne s'automatise pas à cadence fixe. Renonce à la boucle — ou impose un point de contrôle humain — quand :

- **La stratégie ou la direction créative est le vrai travail.** Les boucles entretiennent et optimisent ; elles ne définissent pas un positionnement, n'inventent pas une campagne, ne tranchent pas une question de marque.
- **L'action publie ou dépense sans relecture.** *Rédiger* automatiquement un e-mail, une pub, un post : oui. *Publier* ou *déplacer du budget* automatiquement : point de contrôle humain obligatoire, sauf autorisation explicite avec garde-fous (plafonds, listes blanches).
- **Le signal est trop maigre pour être significatif.** Une boucle de taux de conversion hebdo sur 40 visiteurs/semaine mesure du bruit.
- **C'est une boucle de vanité.** Si personne n'agit sur la sortie, supprime la boucle. Un rapport que personne ne lit est pire que rien.

## Garde-fous — envoi, dépense, données personnelles

Pour toute boucle qui envoie, dépense, publie ou touche des données personnelles :

- **Deux niveaux d'action** : autonome-sans-risque (lire, analyser, rédiger un brouillon, alerter) vs sous validation (envoyer, publier, dépenser, modifier des enchères). Chaque étape du corps de boucle est classée dans l'un des deux.
- **Plafonds** : budget max par itération, volume d'envois max par jour, jamais dépassables par la boucle elle-même.
- **RGPD/CNIL** : une boucle qui envoie des e-mails respecte le régime applicable (B2B : intérêt légitime + objet lié à la fonction + désinscription ; B2C : consentement préalable). Une boucle qui relance des prospects mémorise les oppositions — définitivement. Données de prospects : durée de conservation définie (repère CNIL : 3 ans après le dernier contact).
- **Liste d'escalade systématique** : plainte ou demande d'un client, anomalie de tracking, écart budgétaire, tout contenu sensible → humain, toujours.
- **Interrupteur d'arrêt** : un moyen en une action de suspendre la boucle, documenté à la création.

## Planifier une boucle

Le *corps* d'une boucle fonctionne dans n'importe quel agent. La *planification* dépend de ton environnement :

- **Claude Code** — `/loop` (auto-cadencé, jusqu'à une condition), tâches planifiées type cron pour les cadences fixes.
- **N'importe quel agent + cron** — encapsule le corps de boucle dans un prompt/script planifié (`0 9 * * 1` pour le lundi 9 h).
- **Cadence manuelle** — pour les boucles à fort jugement, « dérouler ce skill chaque lundi » est une excellente boucle. La valeur est dans le *corps* répétable, pas dans l'automatisation.

Par défaut : cron à heure fixe pour les boucles de revue (revue hebdo, veille de positions) ; cadence dynamique pour les boucles de surveillance jusqu'à seuil (churn, jour de lancement).

## Le catalogue

Douze boucles prêtes à adapter. Choisis la plus proche, puis remplis les neuf parties de l'anatomie pour le produit, le stade et l'outillage de l'utilisateur.

| Boucle | Cadence | Agit quand | Skills orchestrés |
|--------|---------|------------|-------------------|
| **Revue SEO hebdo** | Lundi | Toujours (revue) | seo-audit, analytics |
| **Veille positions & GSC** | Hebdo | Chute > 20 % de clics sur une page money | seo-audit |
| **Fraîcheur de contenu** | Mensuelle | Article > 12 mois avec trafic en baisse 3 mois d'affilée | content-strategy, copywriting |
| **Fatigue publicitaire** | Tous les 3 jours | Fréquence > 3 ou CPA en hausse > 25 % sur 7 jours | ads, ad-creative |
| **Veille concurrents** | Hebdo | Changement de prix, de positionnement ou nouvelle page vs | competitors, competitor-profiling |
| **Surveillance churn** | Quotidienne | Compte franchit le seuil de risque, hors fenêtre de refroidissement | churn-prevention, emails |
| **Suivi des avis** | Quotidienne | Nouvel avis ≤ 3 étoiles ou pic de volume | seo-local (si local), customer-research |
| **Relance des inscrits inactifs** | Hebdo | Inscrit sans activation depuis 7 jours, jamais relancé | onboarding, emails |
| **Recyclage social** | Hebdo | Un contenu pilier a > 30 jours et n'a pas été redistribué | social |
| **Revue de tunnel d'activation** | Hebdo | Étape du tunnel sous la moyenne mobile 4 semaines | signup, onboarding, analytics |
| **Contrôle délivrabilité e-mail** | Mensuelle | Taux d'ouverture < moyenne - 2 écarts-types ou plainte > 0,1 % | emails, cold-email |
| **Boucle GEO mensuelle** | Mensuelle | Toujours (mesure), actions si dégradation | ai-seo, competitors |

## Exemple complet : la boucle GEO mensuelle

Les réponses des moteurs IA (ChatGPT, Perplexity, AI Overviews) évoluent chaque mois — et personne ne pense à revérifier. Boucle type, les neuf parties remplies :

| Partie | Valeur |
|--------|--------|
| **Cadence de contrôle** | Mensuelle (1er lundi du mois) |
| **Agit quand** | Toujours pour la mesure ; actions correctives si taux de citation en baisse, nouvelle inexactitude, ou nouveau concurrent recommandé |
| **Objectif** | Maintenir et faire croître la part de voix de la marque dans les réponses IA |
| **Skills utilisés** | ai-seo (mesure et correctifs), competitors (audit « qui est cité à votre place ») |
| **Corps de boucle** | 1. Rejouer le panel de prompts acheteurs sur ChatGPT, Perplexity, AI Overviews. 2. Consigner : cité ? exact ? qui d'autre ? quelles sources ? 3. Calculer taux de citation, exactitude, part de voix ; comparer au mois précédent. 4. Si inexactitude : préparer le correctif (page, entité, profil tiers). 5. Si concurrent monte : identifier ses sources et préparer le plan d'entrée. 6. Rédiger le rapport mensuel. |
| **Auto-vérification** | Les réponses IA varient d'un tirage à l'autre : rejouer 2 fois chaque prompt sensible avant de conclure à un changement ; ignorer toute variation < 10 % de part de voix |
| **État / idempotence** | Tableur historique (panel figé + résultats datés) ; liste des correctifs déjà engagés pour ne pas les recréer |
| **Arrêt / débrayage** | Halte + alerte humaine si un moteur devient inaccessible ou si le panel renvoie des réponses vides ; désactivation manuelle possible à tout moment |
| **Sortie** | Rapport mensuel (tendances + 3 actions max) + brouillons de correctifs prêts à valider |

## Créer une nouvelle boucle

Quand rien dans le catalogue ne colle, pars de l'anatomie : remplis les neuf parties, dans l'ordre. Si tu ne peux pas répondre concrètement à l'auto-vérification, à l'état/idempotence et à l'arrêt/débrayage, la boucle n'est pas prête à tourner. Vérifie avant de livrer :

- [ ] Les neuf parties remplies, sans « sans objet »
- [ ] Cadence justifiée par la vitesse du signal
- [ ] Condition d'action distincte de la cadence de contrôle
- [ ] Actions classées autonomes vs sous validation
- [ ] Plafonds et interrupteur d'arrêt définis si la boucle envoie ou dépense
- [ ] Un destinataire nommé qui agira sur la sortie

## Anti-patterns

- Boucler sans condition d'arrêt → dépense incontrôlée ou relances infinies.
- La même cadence pour toutes les boucles → la plupart tournent trop souvent et finissent ignorées.
- Pas d'auto-vérification → la boucle réagit au bruit, à la saisonnalité ou à un bug de tracking.
- Pas de point de contrôle humain sur les actions qui publient ou dépensent.
- Dix boucles d'un coup → une seule, qui prouve sa valeur, puis la suivante.

## Vocabulaire interdit

À bannir : « pilote automatique », « marketing 100 % autonome », « l'IA s'occupe de tout », « machine à croissance », « growth hacking en roue libre ». Les boucles sont des systèmes disciplinés avec des points de contrôle, pas de la magie. Décris-les honnêtement.
