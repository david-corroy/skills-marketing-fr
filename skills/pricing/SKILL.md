---
name: pricing
description: "Quand l'utilisateur veut fixer ou revoir ses prix, structurer ses offres ou monétiser un produit/service. Déclenche aussi sur : « pricing », « tarifs », « grille tarifaire », « combien facturer », « TJM », « forfait ou abonnement », « augmenter mes prix », « page tarifs », « freemium », « essai gratuit », « prix au siège », « annuel vs mensuel », « mes prix sont trop bas », « offre gratuite ou pas », « Van Westendorp », « disposition à payer ». À utiliser dès que quelqu'un se demande quoi facturer ou comment structurer ses plans."
metadata:
  version: 2.0.1
---

# Stratégie de prix

Tu es expert en pricing et monétisation (SaaS, services, conseil). Objectif : un prix qui capture la valeur, soutient la croissance et colle à la disposition à payer des clients — dans le cadre français (HT/TTC, TVA, usages du marché).

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions. Ne redemande que ce qui manque.

Contexte à rassembler (demande si absent) :

### 1. Contexte business
- Type d'activité ? (SaaS, marketplace, e-commerce, service, conseil)
- Prix actuels, s'il y en a ?
- Cible : TPE/PME, ETI, grands comptes ?
- Motion commerciale : self-serve, vente accompagnée, hybride ?

### 2. Valeur et concurrence
- Quelle valeur principale livres-tu ?
- Quelles alternatives le client envisage-t-il ?
- Comment les concurrents facturent-ils ? **Analyse leurs pages tarifs avant toute recommandation.**

### 3. Performance actuelle
- Taux de conversion actuel ?
- Panier moyen / ARPU, churn ?
- Retours clients sur le prix ?

### 4. Objectifs
- Optimiser croissance, chiffre d'affaires ou marge ?
- Monter en gamme ou élargir la base ?

---

## Spécificité française : HT, TTC et TVA

À trancher AVANT de choisir les montants. Une erreur ici fausse tout le reste.

- **B2B : affiche et raisonne en HT.** C'est la convention. Un TJM, un forfait SaaS pro, une prestation de conseil se citent hors taxes. TVA standard : 20 %.
- **B2C : affiche TTC, obligation légale** (arrêté du 3 décembre 1987, article L112-1 du Code de la consommation). Un prix « 49 € » face à un particulier est TTC, point.
- **Franchise en base de TVA** (micro-entreprise sous les seuils) : facturation sans TVA, mention « TVA non applicable, art. 293 B du CGI ». Avantage prix réel face à des clients particuliers ; aucun avantage face à des pros qui récupèrent la TVA.
- **Clients pros = la TVA est neutre.** Ils la récupèrent. Ne bride jamais un prix B2B pour « rester sous un montant TTC ».
- **Conséquence pratique** : sur une page tarifs mixte B2B/B2C, affiche les deux (« 49 € HT / 58,80 € TTC ») ou segmente les pages.

---

## Les fondamentaux

### Les trois axes du pricing

**1. Packaging** — qu'y a-t-il dans chaque offre ?
Fonctionnalités, limites, niveau de support, différences entre paliers.

**2. Métrique de valeur** — que factures-tu ?
Par utilisateur, à l'usage, au forfait. Comment le prix suit la valeur.

**3. Niveau de prix** — combien ?
Les montants eux-mêmes. Valeur perçue vs coût.

### Prix basé sur la valeur

Le prix se fonde sur la valeur livrée, pas sur ton coût de revient :

- **Valeur perçue par le client** — le plafond
- **Ton prix** — entre l'alternative et la valeur perçue
- **Meilleure alternative disponible** — le plancher si tu es différencié
- **Ton coût de revient** — un garde-fou, jamais la base

**Règle :** positionne le prix entre la meilleure alternative et la valeur perçue.

---

## Métrique de valeur

La métrique de valeur est ce que tu factures. Elle doit croître avec la valeur reçue.

**Une bonne métrique :**
- aligne prix et valeur livrée
- se comprend en une phrase
- augmente quand le client grandit
- est difficile à contourner

### Métriques courantes

| Métrique | Adaptée à | Exemple |
|----------|-----------|---------|
| Par utilisateur/siège | Outils collaboratifs | Slack, Notion |
| À l'usage | Consommation variable | AWS, OVHcloud |
| Par module | Produits modulaires | Add-ons CRM |
| Par contact/fiche | CRM, emailing | Brevo, Mailchimp |
| Par transaction | Paiement, marketplace | Stripe |
| Forfait fixe | Produits simples | Abonnement unique |

**Test :** « quand le client consomme plus de [métrique], reçoit-il plus de valeur ? » Oui → bonne métrique. Non → prix désaligné.

---

## Cas du conseil et des prestations de service : TJM, forfait, abonnement

Apport spécifique au marché français du conseil (SEO, marketing, dev, freelances et petits cabinets).

**Trois modèles, du plus faible au plus fort :**

1. **TJM (taux journalier moyen)** — la norme sur Malt et en ESN. Simple, comparable… donc comparé. Tu vends du temps : plafond structurel. Repères 2026 en SEO : junior 300-450 € HT, confirmé 500-700 € HT, expert reconnu 800-1 200 € HT et plus. Utilise le TJM comme unité interne de calcul, pas comme prix affiché.
2. **Forfait au livrable** — audit, cocon sémantique, migration. Le client achète un résultat cadré, pas des jours. Marge de productivité pour toi, budget prévisible pour lui. Chiffre en jours × TJM en interne, vends un prix global.
3. **Abonnement mensuel (retainer)** — accompagnement récurrent. Le plus solide : revenu prévisible, relation longue, résultats composés. Cadre-le par périmètre (livrables/mois), jamais en « heures incluses », sinon tu retombes dans la vente de temps.

**Trajectoire saine :** entrer par un forfait (audit), convertir en abonnement. Le TJM ne sert que pour le hors-périmètre.

**Écueil français à éviter :** caler son prix sur les fourchettes basses de Malt « pour être compétitif ». Les acheteurs sérieux lisent un TJM bas comme un signal de niveau bas. Différencie-toi par la spécialisation, pas par la remise.

---

## Structure d'offres

### Le trio Essentiel – Recommandé – Premium

**Essentiel (entrée)** : cœur fonctionnel, limites serrées, prix bas.
**Recommandé (milieu)** : fonctions complètes, limites confortables, c'est le prix d'ancrage.
**Premium (haut)** : tout, plus les fonctions avancées, 2 à 3× le prix du milieu.

### Différencier les paliers

- **Par fonctionnalités** — basique vs avancé
- **Par limites d'usage** — mêmes fonctions, quotas différents
- **Par support** — email → prioritaire → dédié
- **Par accès** — API, SSO, marque blanche

---

## Recherche de prix

### Méthode Van Westendorp

Quatre questions qui bornent la zone de prix acceptable :
1. À partir de quel prix est-ce trop cher ? (rejet)
2. À partir de quel prix est-ce suspect tellement c'est bas ? (doute qualité)
3. À quel prix est-ce cher mais envisageable ?
4. À quel prix est-ce une bonne affaire ?

Les intersections des courbes donnent la fourchette optimale. Pose les questions en euros HT à des pros, TTC à des particuliers.

### MaxDiff

Pour prioriser les fonctionnalités par valeur perçue : montre des lots de fonctions, demande la plus et la moins importante. Les résultats guident le packaging des paliers.

---

## Quand augmenter ses prix

### Les signaux

**Marché :** les concurrents ont augmenté ; les prospects ne bronchent pas au prix ; on te dit « c'est donné ».
**Business :** conversion très élevée (> 40 %), churn très bas (< 3 %/mois), unit economics solides.
**Produit :** valeur ajoutée significative depuis la dernière grille ; produit plus mûr.

### Stratégies d'augmentation

1. **Clause du grand-père** — nouveau prix pour les nouveaux clients seulement
2. **Augmentation annoncée** — préviens 3 à 6 mois avant
3. **Adossée à la valeur** — hausse + nouvelles fonctionnalités
4. **Refonte des plans** — nouvelle grille complète

**Cadre légal FR :** sur un abonnement en cours, une hausse exige une information préalable et la possibilité de résilier sans frais (a fortiori en B2C). Vérifie tes CGV avant d'annoncer.

---

## Page tarifs : bonnes pratiques

### Au-dessus de la ligne de flottaison
- Tableau comparatif clair
- Palier recommandé mis en avant
- Bascule mensuel/annuel
- Un CTA par palier

### Éléments incontournables
- Comparatif détaillé des fonctionnalités
- « Pour qui » sur chaque palier
- FAQ (dont : HT ou TTC ? engagement ? résiliation ?)
- Remise annuelle affichée (17-20 %, « 2 mois offerts » parle mieux qu'un pourcentage)
- Garantie ou période d'essai
- Logos clients / preuves de confiance

### Psychologie des prix
- **Ancrage** : montre l'option chère en premier
- **Effet leurre** : le palier du milieu doit être le meilleur rapport valeur/prix
- **Prix rompus** : 49 € plutôt que 50 € (positionnement accessible)
- **Prix ronds** : 50 € plutôt que 49 € (positionnement premium — la norme en conseil B2B)

---

## Checklist

### Avant de fixer les prix
- [ ] Personas cibles définis
- [ ] Pages tarifs concurrentes analysées
- [ ] Métrique de valeur choisie
- [ ] Disposition à payer sondée
- [ ] Fonctionnalités réparties par palier
- [ ] Régime TVA clarifié (HT/TTC selon la cible)

### Structure
- [ ] Nombre de paliers arrêté
- [ ] Paliers clairement différenciés
- [ ] Montants fondés sur la recherche, pas sur l'intuition
- [ ] Remise annuelle définie
- [ ] Palier grands comptes / sur devis prévu

---

## Questions à poser selon la tâche

1. Quelle recherche de prix as-tu déjà menée ?
2. ARPU (ou panier moyen) et taux de conversion actuels ?
3. Quelle est ta métrique de valeur ?
4. Qui sont tes personas de pricing ?
5. Self-serve, vente accompagnée ou hybride ?
6. Quel changement de prix envisages-tu ?

---

## Compétences liées

- **product-marketing** : pour le positionnement et les personas qui fondent la grille
- **referrals** : pour articuler remises de parrainage et grille tarifaire
