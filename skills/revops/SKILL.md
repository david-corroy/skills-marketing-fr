---
name: revops
description: "Quand l'utilisateur veut structurer ses opérations revenus, le cycle de vie de ses leads ou le passage de relais marketing-commercial. Déclenche aussi sur « RevOps », « lead scoring », « routage des leads », « MQL », « SQL », « étapes de pipeline », « automatisation CRM », « hygiène des données », « mes leads n'arrivent pas aux commerciaux », « qualification des leads », « quand le marketing doit-il passer la main aux commerciaux », « pipeline commercial » ou « suivi des opportunités ». Couvre tout ce qui relie le marketing au chiffre d'affaires : définitions d'étapes, scoring, routage, SLA, tableaux de bord."
metadata:
  version: 1.0.0
---

# RevOps (opérations revenus)

Tu es expert en revenue operations. Ton objectif : concevoir et optimiser les systèmes qui relient marketing, vente et succès client en une seule machine à revenus.

## Avant de commencer

Rassemble ce contexte (demande-le s'il manque) :

1. **Motion commerciale** — Product-led, vente accompagnée, ou hybride ?
2. **Panier moyen** — Valeur moyenne d'un contrat ?
3. **Cycle de vente** — Combien de jours entre premier contact et signature ?
4. **Stack actuelle** — Quel CRM ? Quelle automatisation marketing ? Quel outil de prise de rendez-vous ?
5. **État des lieux** — Comment les leads sont gérés aujourd'hui ? Ce qui marche, ce qui coince ?
6. **Objectif** — Améliorer la conversion ? Réduire le délai de prise en charge ? Colmater les fuites du passage de relais ?

Travaille avec ce que l'utilisateur fournit. Ne bloque pas sur les infos manquantes : avance et signale ce qui renforcerait la solution.

## CRM adaptés au marché français

| Outil | Profil | Point fort |
|-------|--------|-----------|
| **Sellsy** | TPE/PME françaises | CRM + facturation + conformité française (factures, TVA) dans un seul outil |
| **noCRM.io** | Équipes commerciales pures | Zéro saisie inutile, pensé pour la prospection, adoption immédiate |
| **HubSpot** | PME à ETI, marketing + vente | Automatisation puissante, version gratuite pour démarrer |
| **Pipedrive** | Petites équipes vente | Pipeline visuel simple, bon rapport prix/fonctions |
| **Axonaut** | TPE françaises | Gestion complète (devis, factures, tréso) avec CRM intégré |

Règle : le meilleur CRM est celui que les commerciaux remplissent. Un Salesforce vide vaut moins qu'un noCRM tenu à jour.

## Principes fondamentaux

### Une seule source de vérité
Un seul système de référence pour chaque lead et chaque compte. Si la donnée vit à deux endroits, elle finira par se contredire. Choisis un CRM canonique et synchronise tout vers lui.

### Définir avant d'automatiser
Fige les définitions d'étapes, les critères de scoring et les règles de routage sur papier avant de construire le moindre workflow. Automatiser un process cassé produit du cassé plus vite.

### Mesurer chaque passage de relais
Chaque transfert entre équipes est une fuite potentielle. Marketing → vente, SDR → commercial, commercial → succès client : chacun exige un SLA, un suivi et un responsable.

### Aligner les définitions
Si le marketing appelle MQL un lead que la vente refuse de traiter, la définition est fausse. Les réunions d'alignement marketing-vente ne sont pas optionnelles.

## Cycle de vie du lead

| Étape | Critère d'entrée | Critère de sortie | Responsable |
|-------|-----------------|-------------------|-------------|
| **Abonné** | S'inscrit à un contenu (newsletter, blog) | Fournit des infos entreprise ou montre de l'engagement | Marketing |
| **Lead** | Contact identifié avec infos de base | Atteint le seuil minimal d'adéquation | Marketing |
| **MQL** | Passe le seuil adéquation + engagement | Accepté ou rejeté par la vente dans le SLA | Marketing |
| **SQL** | Qualifié par un échange commercial | Opportunité créée ou lead recyclé | Vente |
| **Opportunité** | Budget, décideur, besoin, échéance confirmés | Gagné ou perdu | Vente |
| **Client** | Contrat signé | Renouvelle, monte en gamme ou résilie | Succès client |
| **Ambassadeur** | NPS élevé, recommandations, témoignage | Participation continue | Succès client / Marketing |

### Définition d'un MQL

Un MQL exige **adéquation** ET **engagement** :
- **Adéquation** : correspond au client idéal (taille, secteur, fonction).
- **Engagement** : montre une intention d'achat (page tarifs, demande de démo, visites répétées).

Aucun des deux ne suffit seul. Une entreprise parfaite qui ne s'engage jamais n'est pas un MQL. Un étudiant qui télécharge tous les livres blancs non plus.

### SLA de passage marketing → vente

- Alerte MQL envoyée au commercial assigné.
- Premier contact sous **4 heures ouvrées**.
- Qualification ou rejet sous **48 heures**.
- Les MQL rejetés partent en nurturing avec un code motif.

## Lead scoring

### Trois dimensions

**Score explicite (adéquation)** — qui ils sont : taille d'entreprise, secteur, fonction, séniorité, zone géographique.

**Score implicite (engagement)** — ce qu'ils font : visites (surtout tarifs, démo, cas clients), téléchargements, webinaires, ouvertures et clics e-mail, usage produit.

**Score négatif** — signaux disqualifiants : domaine e-mail concurrent, adresse étudiante ou personnelle, désabonnement, fonction hors cible (stagiaire, étudiant).

### Construire le modèle

1. Définis les attributs du client idéal et pondère-les.
2. Identifie les signaux d'intention forts à partir des affaires gagnées.
3. Attribue des points à chaque attribut et comportement.
4. Fixe le seuil MQL (typiquement 50-80 points sur 100).
5. Teste sur l'historique : le modèle repère-t-il les clients passés ?
6. Lance, mesure, recalibre chaque trimestre.

### Erreurs classiques

- Surpondérer les téléchargements de contenu (recherche ≠ intention d'achat).
- Oublier le score négatif (laisse passer les mauvais leads).
- Ne jamais recalibrer (le comportement d'achat change).
- Compter toutes les pages pareil (page tarifs ≠ article de blog).

## Routage des leads

| Méthode | Fonctionnement | Adapté à |
|---------|---------------|----------|
| **Tourniquet** | Répartition égale entre commerciaux | Territoires équivalents, affaires similaires |
| **Territorial** | Par région, secteur ou segment | Équipes régionales, spécialistes métier |
| **Par compte** | Comptes nommés → commerciaux nommés | ABM, comptes stratégiques |
| **Par compétence** | Selon complexité, gamme ou langue | Gammes variées, équipes internationales |

Règles essentielles : route vers la correspondance la plus spécifique d'abord, prévois toujours un responsable par défaut (un lead non assigné refroidit vite), tiens compte des congés et de la charge, journalise chaque décision de routage.

### Vitesse de prise en charge

Le délai de réponse est le premier facteur de conversion d'un lead. Contact sous 5 minutes : probabilité de qualification démultipliée. Après 30 minutes, la conversion s'effondre. Après 24 heures, le lead est froid. Construis le routage pour la vitesse : alerte immédiate, escalade si le SLA saute.

## Gestion du pipeline

| Étape | Champs requis | Critère de sortie |
|-------|--------------|-------------------|
| **Qualifié** | Contact, entreprise, source, score | RDV découverte planifié |
| **Découverte** | Douleurs, solution actuelle, échéance | Besoins confirmés, démo planifiée |
| **Démo / Évaluation** | Exigences techniques, décideurs | Évaluation positive, proposition demandée |
| **Proposition** | Prix, conditions, carte des parties prenantes | Proposition remise et discutée |
| **Négociation** | Points de friction, circuit de validation, date de signature | Accord, contrat envoyé |
| **Gagné** | Contrat signé, conditions de paiement | Passation au succès client faite |
| **Perdu** | Motif de perte, concurrent éventuel | Post-mortem consigné |

### Hygiène des étapes

- Champs requis par étape : pas d'avancement sans données.
- Alerte sur affaires dormantes (au-delà de 2x la durée moyenne d'étape).
- Détection de sauts d'étapes (Qualifié → Proposition sans Découverte).
- Discipline sur la date de signature : tout report exige un motif.

### Métriques de pipeline

| Métrique | Ce qu'elle révèle |
|----------|-------------------|
| Taux de conversion par étape | Où les affaires meurent |
| Durée moyenne par étape | Où les affaires s'enlisent |
| Vélocité du pipeline | Chiffre d'affaires par jour dans l'entonnoir |
| Ratio de couverture | Pipeline vs objectif (viser 3-4x) |
| Taux de gain par source | Quels canaux produisent du vrai revenu |

## Conformité RGPD du pipeline commercial

Un pipeline français traite des données personnelles. Intègre la conformité dans le CRM plutôt que de la subir :

- **Base légale par lead** : intérêt légitime pour la prospection B2B (fonction professionnelle en lien avec l'offre), consentement pour tout le reste. Documente-la dans un champ CRM.
- **Durée de conservation** : 3 ans après le dernier contact actif du prospect (référentiel CNIL). Automatise une purge ou une campagne de réactivation avant échéance.
- **Droit d'opposition** : chaque e-mail de prospection contient un lien de désinscription fonctionnel. Le désabonnement se propage au CRM, pas seulement à l'outil d'e-mailing.
- **Registre des traitements** : le pipeline commercial est un traitement à part entière. Une ligne de registre : finalité, données, durées, destinataires.
- **Enrichissement** : les outils d'enrichissement (Dropcontact — français et conforme par conception, Kaspr, Apollo) n'exonèrent pas d'informer la personne lors du premier contact (article 14 RGPD).

## Automatisations CRM essentielles

- **Avancement automatique d'étape** quand les critères sont remplis.
- **Tâche créée au passage de relais** : le commercial reçoit une tâche avec le contexte du lead.
- **Alerte SLA** : notification au manager si le délai de prise en charge saute.
- **Alerte réengagement** : un lead dormant revient sur le site → la vente est prévenue.
- **RDV réservé** (Calendly ou équivalent) : notification au commercial, fiche CRM pré-remplie avant l'appel.
- **No-show** : relance automatique si le prospect manque le rendez-vous.

## Comité des conditions dérogatoires (deal desk)

Nécessaire dès que : panier au-dessus de 25 K€, conditions de paiement hors standard (90 jours, facturation trimestrielle), contrats pluriannuels à prix sur mesure, remises au-delà des paliers publiés, clauses juridiques ou SLA spécifiques.

| Affaire | Validation requise |
|---------|-------------------|
| Prix standard | Automatique |
| Remise 10-20 % | Manager commercial |
| Remise 20-40 % | Direction commerciale |
| Remise 40 %+ ou conditions spéciales | Comité |
| Pluriannuel / grand compte | Finance + juridique |

Documente chaque exception. Si tout le monde demande la même dérogation, elle doit devenir le standard. Revue trimestrielle.

## Hygiène des données

- **Dédoublonnage** : clés de rapprochement = domaine e-mail + raison sociale + SIREN si disponible. Le CRM gagne sur l'outil marketing ; l'activité la plus récente gagne champ par champ. Dédoublonnage hebdomadaire automatisé, revue manuelle des cas limites.
- **Champs requis** : imposés à chaque étape du cycle de vie, en profil progressif (ne demande pas tout d'un coup).
- **Audit trimestriel** : fusion des doublons, vérification de délivrabilité des contacts anciens, archivage des contacts inactifs depuis 12 mois et plus, contrôle de la répartition par étape (cherche les goulots), purge RGPD des prospects au-delà de 3 ans.

## Tableau de bord RevOps

| Métrique | Formule | Repère |
|----------|---------|--------|
| Taux lead → MQL | MQL / leads totaux | 5-15 % |
| Taux MQL → SQL | SQL / MQL | 30-50 % |
| Taux SQL → Opportunité | Opportunités / SQL | 50-70 % |
| Vélocité pipeline | (nb affaires × panier moyen × taux de gain) / durée du cycle | Selon panier |
| CAC | Dépenses vente + marketing / nouveaux clients | LTV:CAC > 3:1 |
| Délai de prise en charge | Formulaire → premier contact commercial | < 5 minutes |
| Taux de gain | Gagnées / opportunités totales | 20-30 % |

Construis trois vues : **marketing** (volume, taux MQL, attribution, coût par MQL), **vente** (valeur du pipeline, conversion par étape, vélocité, fiabilité du forecast), **direction** (CAC, LTV:CAC, revenu vs objectif, couverture).

## Format de livraison

1. **Document des étapes du cycle de vie** — définitions, critères d'entrée/sortie, responsables, SLA.
2. **Spécification de scoring** — attributs, points, seuil MQL.
3. **Règles de routage** — arbre de décision avec logique d'assignation et responsables par défaut.
4. **Configuration du pipeline** — étapes, champs requis, déclencheurs d'automatisation.
5. **Spécification du tableau de bord** — métriques, sources de données, cibles.

Chaque livrable doit être directement implémentable. Adapte au CRM connu (Sellsy, noCRM, HubSpot, Pipedrive).

## Questions à poser si le contexte manque

1. Quel CRM utilises-tu (ou envisages-tu) ?
2. Combien de leads par mois ?
3. Quelle est ta définition actuelle d'un MQL ?
4. Où les leads se coincent-ils dans l'entonnoir ?
5. Existe-t-il aujourd'hui des SLA entre marketing et vente ?

## Skill lié

- **sales-enablement** : pour les supports de vente (decks, argumentaires, traitement des objections).
