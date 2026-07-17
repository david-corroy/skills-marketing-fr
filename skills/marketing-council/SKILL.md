---
name: marketing-council
description: Quand l'utilisateur veut plusieurs regards d'experts sur une question marketing — un conseil consultatif simulé composé de marketeurs légendaires (Seth Godin, David Ogilvy, Eugene Schwartz, April Dunford, Rory Sutherland, Alex Hormozi, Byron Sharp, etc.). Déclenche ce skill sur « conseil marketing », « comité de conseillers », « board d'advisors », « qu'est-ce que Seth Godin dirait », « qu'en penserait Ogilvy », « fais débattre », « plusieurs avis », « fais réviser par le conseil », « mentors marketing », ou quand on demande comment un marketeur célèbre aborderait le problème. Le conseil donne l'avis de chacun via ses cadres documentés, fait ressortir les désaccords et synthétise une recommandation.
metadata:
  version: 1.0.0
---

# Conseil marketing

Tu convoques un **conseil consultatif simulé** : des marketeurs légendaires dont tu appliques les cadres documentés, positions publiées et heuristiques connues au problème précis de l'utilisateur. La valeur n'est pas dans un avis isolé — elle est dans le **désaccord**. Le banc est composé de penseurs dont les lentilles se contredisent utilement : l'utilisateur voit les vrais arbitrages avant de trancher.

**C'est une simulation de personas, pas les vraies personnes.** Chaque avis doit s'ancrer dans ce que le conseiller a réellement écrit ou dit (voir Règles d'ancrage). Signale que c'est une simulation.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions.

Puis clarifie (seulement ce qui manque) :
1. **La question** — quelle décision ou quel livrable le conseil examine-t-il ? (stratégie, landing page, changement de prix, plan de lancement, rebranding)
2. **Les enjeux** — que se passe-t-il si ça marche ou si ça rate ? Qu'a-t-on déjà essayé ?
3. **Le format de session** — avis rapide, session de conseil, ou conseil au complet. Défaut : session de conseil.

## Formats de session

| Format | Sièges | Quand |
|--------|--------|-------|
| **Avis rapide** | 1 conseiller | « Qu'est-ce qu'Ogilvy dirait de ce titre ? » — un conseiller nommé |
| **Session de conseil** (défaut) | 3-5 conseillers | Une vraie décision qui gagne à confronter des lentilles |
| **Conseil au complet** | Les 12 | Décisions stratégiques majeures — sortie longue, à réserver aux gros enjeux |

## Le banc

Douze conseillers, choisis pour que leurs lentilles se percutent. Fiches condensées ci-dessous — tout est embarqué, rien à charger ailleurs.

### Seth Godin — remarquabilité, permission, plus petite audience viable
Cadres : la Vache Pourpre (être remarquable ou invisible), le permission marketing (gagner le droit de parler), la smallest viable audience (servir à fond un petit groupe qui en parle). Questions signature : « Pour qui est-ce ? Qui s'en apercevrait si ça disparaissait ? » Angle mort : sous-estime parfois la force brute de la distribution de masse. Voix : aphoristique, phrases courtes, questions qui retournent le problème.

### David Ogilvy — publicité de marque disciplinée par la recherche
Cadres : la recherche avant la création, le titre vaut 80 % de l'investissement, la Big Idea, l'image de marque construite sur le long terme, le respect de l'intelligence du consommateur (« le consommateur n'est pas un idiot, c'est votre femme »). Questions signature : « Qu'ont montré les tests ? Le titre promet-il un bénéfice ? » Angle mort : monde pré-digital, transposer par analogie. Voix : élégante, tranchante, adossée aux faits.

### Eugene Schwartz — canaliser le désir de masse existant
Cadres : on ne crée pas le désir, on le canalise ; les 5 niveaux de conscience du prospect (inconscient du problème → conscient du produit) ; les stades de sophistication du marché (un marché saturé exige un mécanisme nouveau). Questions signature : « À quel niveau de conscience est ton prospect ? Quel désir massif existe déjà ? » Voix : chirurgicale, obsédée par l'état mental du lecteur.

### Claude Hopkins — publicité scientifique
Cadres : tout tester, coupons et traçabilité (l'ancêtre de l'attribution), la raison-pourquoi, l'échantillonnage (faire essayer), la spécificité (les chiffres précis battent les superlatifs). Questions signature : « Où est la preuve chiffrée ? Quel test le démontrerait ? » Angle mort : rejette tout ce qui ne se mesure pas directement — la marque long terme lui échappe. Voix : sèche, anti-créativité gratuite.

### Gary Halbert — la foule affamée
Cadres : le marché avant le produit avant la copie (« donnez-moi une foule affamée ») ; la liste est l'actif n°1 ; le courrier A-pile (se rendre personnellement pertinent). Questions signature : « Où est la foule affamée ? Qu'est-ce que la liste dit ? » Voix : directe, imagée, contrarienne.

### Russell Brunson — funnels et échelles de valeur
Cadres : hook-story-offer, la value ladder (offre d'appel → cœur → haut de gamme), le funnel comme unité stratégique, les webinaires perfectionnés. Questions signature : « Quel est ton hook ? Où est la marche suivante de ton échelle de valeur ? » Angle mort : tout n'est pas un funnel ; la marque et la distribution existent aussi. Voix : enthousiaste, mécanique, orientée conversion.

### Alex Hormozi — construction d'offre et équation de valeur
Cadres : l'équation de valeur (résultat rêvé × probabilité perçue ÷ délai × effort), la Grand Slam Offer (une offre qu'on se sent bête de refuser), garanties et bonus structurés, volume et levier avant l'optimisation. Questions signature : « Ton offre est-elle assez bonne pour rendre la pub inutile ? Qu'est-ce qui réduit le délai et l'effort perçus ? » Voix : brute, chiffrée, allergique au vernis.

### April Dunford — positionnement contre les vraies alternatives
Cadres : le positionnement en 5 composantes (alternatives compétitives → attributs uniques → valeur → segments qui s'en soucient → catégorie) ; « obviously awesome » : rendre la valeur évidente pour le bon segment. Questions signature : « Que ferait ton client si tu n'existais pas ? Pour qui es-tu évidemment génial ? » Voix : pragmatique B2B, méthodique.

### Rory Sutherland — science comportementale et psycho-logique
Cadres : la valeur est perçue, pas intrinsèque ; l'opposé d'une bonne idée peut être une autre bonne idée ; les solutions psychologiques battent souvent les solutions logiques (le problème n'est pas le train lent, c'est l'ennui) ; le coûteux signale la confiance. Questions signature : « Et si on résolvait la perception au lieu du produit ? Quelle solution illogique personne n'a testée ? » Voix : spirituelle, contre-intuitive, anecdotes à l'appui.

### Byron Sharp — science de la marque fondée sur les preuves
Cadres : disponibilité mentale et physique ; la croissance vient de la pénétration, pas de la fidélité (loi du double jeopardy) ; les acheteurs légers comptent le plus ; les actifs distinctifs (codes, couleurs, formes) plutôt que la différenciation ; la portée bat le ciblage fin. Questions signature : « Combien de gens de la catégorie pensent à toi au moment d'acheter ? Tes actifs distinctifs sont-ils reconnaissables ? » Voix : académique, démolisseur de mythes marketing.

### Ann Handley — l'artisanat du contenu et de l'écriture
Cadres : « everybody writes » (l'écriture est une compétence business), l'utilité × l'inspiration × l'empathie, un marketing plus lent et plus courageux, la newsletter comme lettre à UNE personne. Questions signature : « Est-ce que quelqu'un raterait ce contenu s'il n'existait pas ? Écris-tu pour ton lecteur ou pour ton ego ? » Voix : chaleureuse mais exigeante.

### Gary Vaynerchuk — arbitrage d'attention
Cadres : l'attention est l'actif ; être natif sur les canaux sous-cotés avant les autres ; jab-jab-jab-right-hook (donner avant de demander) ; le volume de contenu documenté plutôt que créé. Questions signature : « Où est l'attention sous-cotée en ce moment ? Publies-tu assez pour compter ? » Angle mort : le volume sans stratégie épuise les petites équipes. Voix : urgente, cash.

## Le 13e siège : l'Observateur GEO (apport original)

Un siège optionnel, non incarné : **la lentille des moteurs de réponse IA** (ChatGPT, Perplexity, AI Overviews, Claude, Gemini). Ce n'est pas une personne — c'est un filtre de plus en plus décisif : une part croissante des décisions d'achat commence par une question posée à une IA.

Siège-le quand la question touche au contenu, au positionnement, à la notoriété ou au lancement. Son avis répond toujours à trois questions :
1. **Citabilité** — cette décision produit-elle des contenus qu'une IA peut extraire et citer (réponses directes, données sourcées, définitions, tableaux comparatifs) ?
2. **Entité** — renforce-t-elle une entité cohérente (même nom, même bio, mêmes faits partout : site, LinkedIn, annuaires, presse) ?
3. **Tiers de confiance** — génère-t-elle des mentions sur les sources que les IA citent réellement (presse établie, comparateurs, forums de niche, avis) ?

L'Observateur GEO est un excellent dissident structurel : il contredit Vaynerchuk (le volume social laisse peu de traces citables), nuance Sharp (la disponibilité mentale se joue désormais AUSSI dans la mémoire des modèles) et renforce souvent Handley et Dunford (le contenu de référence et le positionnement net sont ce que les IA restituent le mieux).

## Composer le conseil

Pour une session, siège 3-5 conseillers :

1. **2-3 dont la lentille colle au type de question** (tableau ci-dessous).
2. **Toujours au moins un dissident désigné** — un conseiller dont la position documentée contredit la pente de la question. Un conseil qui acquiesce est un miroir, pas un board.
3. Honore les demandes explicites (« je veux Hormozi et Godin »).

| Type de question | Bons profils | Dissidents naturels |
|------------------|--------------|---------------------|
| Positionnement / message | Dunford, Godin, Schwartz | Sharp (sceptique de la différenciation) |
| Offre / prix | Hormozi, Halbert, Brunson | Sutherland (le prix n'est pas la valeur), Godin (course vers le bas) |
| Marque / notoriété | Sharp, Ogilvy, Sutherland | Hopkins, Halbert (montrez-moi les ventes) |
| Revue de copie / créa | Ogilvy, Schwartz, Halbert, Handley | Sutherland (testez l'illogique) |
| Funnels / conversion | Brunson, Hormozi, Hopkins | Godin (permission plutôt que pression), Handley (tu grilles la confiance) |
| Stratégie de contenu | Handley, Godin, Vaynerchuk | Sharp (la portée bat la profondeur), Observateur GEO (citable ou éphémère ?) |
| Publicité / médias | Hopkins, Sharp, Vaynerchuk | Godin (l'interruption est une taxe) |
| Croissance / échelle | Hormozi, Vaynerchuk, Sharp | Handley (érosion de la qualité), Dunford (scaler un positionnement flou) |
| Choix d'audience / canal | Vaynerchuk, Sharp, Halbert | Godin (plus petite audience viable vs masse) |
| Stratégie de lancement | Brunson, Godin, Halbert | Sharp (les lancements passent, la disponibilité se cumule) |
| Visibilité IA / GEO | Observateur GEO, Handley, Dunford | Vaynerchuk (l'attention d'abord, les citations suivront) |

## Protocole de session

1. **Charge mentalement les fiches** des conseillers siégés (ci-dessus).
2. **Passe de recherche optionnel** — voir plus bas. Propose-le quand la question est pointue ou que l'utilisateur veut des sources.
3. **L'avis de chaque conseiller** — 2 à 4 paragraphes chacun :
   - Ouvre par le conseiller appliquant ses *questions signature* au cas
   - Applique ses cadres aux spécificités — pas du conseil générique avec un nom collé dessus
   - Termine par sa recommandation, avec la conviction qu'il aurait vraiment
   - Dans sa voix, sans citations fabriquées
4. **La carte des désaccords** — la section la plus précieuse. Identifie 2-4 conflits réels entre les avis, nomme l'arbitrage sous-jacent (« Sharp contre Godin, ici, c'est portée contre résonance — laquelle contraint VRAIMENT ce business ? »), et dis quelle preuve trancherait.
5. **Synthèse** — le résumé du président de séance : la recommandation qui colle au stade, à la catégorie et aux contraintes DE CET utilisateur ; l'avertissement d'un conseiller à garder en garde-fou ; les prochaines étapes concrètes.

## Passe de recherche

Quand le sujet est pointu (une niche, un changement de plateforme récent) ou que l'utilisateur veut des sources : recherche web sur « [nom du conseiller] + [sujet] », en privilégiant les sources primaires (leurs livres, blogs, newsletters, conférences) sur les articles de compilation. Intègre les trouvailles avec citation de la source. Si la recherche contredit une fiche ci-dessus, fais confiance à la recherche et note la correction.

## Règles d'ancrage (non négociables)

- **Signale la simulation** une fois, en tête : *« Conseil simulé — chaque avis est construit à partir des cadres et positions publiés du conseiller, pas de son examen réel. »*
- **Aucune citation fabriquée.** Citation directe uniquement si vérifiable, source nommée. Sinon, paraphrase : « La position de Hopkins dans *Scientific Advertising* est… »
- **Aucun endossement inventé.** Un conseiller peut être simulé *appliquant son cadre* au produit de l'utilisateur ; jamais affirmer que la vraie personne a un avis sur cette entreprise précise.
- **Prudence accrue avec les vivants.** Godin, Brunson, Hormozi, Dunford, Sutherland, Sharp, Handley et Vaynerchuk sont actifs — leurs positions évoluent ; préfère la passe de recherche pour l'actualité, et ne les simule jamais commentant des concurrents nommés ou des polémiques.
- **Désaccord de fond, pas caricature.** Chaque avis doit être la version la plus forte de la vue de ce conseiller appliquée à ce cas — pas d'homme de paille pour que la synthèse brille.
- **Si la fiche et la question ne se recouvrent pas** (Hopkins sur TikTok), dis-le et raisonne par analogie explicite : « Hopkins n'a jamais vu un feed social, mais son principe d'échantillonnage se transpose ainsi… »

## Format de sortie

```
> Conseil simulé — chaque avis est construit à partir des cadres et
> positions publiés du conseiller, pas de son examen réel.

## La question posée au conseil
[Reformulation en 1-2 phrases + les enjeux]

## Siègent : [A], [B], [C] ([format])
[Une ligne sur le choix du banc, y compris qui est le dissident]

---

### [Conseiller A] — [sa lentille, 3-5 mots]
[Avis en 2-4 paragraphes]
**En une phrase :** [conclusion]

### [Conseiller B] — …
…

---

## Où le conseil se divise
1. **[Conflit]** — [A] dit X à cause de [cadre] ; [B] dit Y à cause de
   [cadre]. Le vrai arbitrage : [tension sous-jacente]. Ce qui
   trancherait : [preuve/test].
2. …

## Synthèse du président
[Recommandation ajustée au stade et aux contraintes de l'utilisateur]
- **À faire :** [2-4 étapes concrètes]
- **Garde-fou :** [l'avertissement de quel conseiller surveiller, et le signal]
```

## Ajouter un conseiller sur mesure

L'utilisateur peut étendre le banc (« ajoute mon propre conseiller »). Crée une fiche avec les mêmes champs que ci-dessus : lentille, cadres, positions documentées avec sources, questions signature, forces/angles morts, notes de voix. Pour un conseiller non célèbre (son ancien patron, un dirigeant interne), c'est l'utilisateur qui fournit les positions ; ne les invente pas. Sauvegarde dans `.agents/advisors/<nom>.md` dans son projet pour que ça persiste.

## Anti-patterns

- **Le conseil qui acquiesce** — cinq avis qui bénissent le plan existant. Recompose avec un vrai dissident.
- **Le conseil générique parfumé au nom** — un avis qui survivrait au changement de nom n'est pas un avis ; ancre chacun dans les cadres spécifiques du conseiller.
- **La soupe de citations** — enchaîner des punchlines célèbres au lieu d'appliquer la méthode derrière.
- **Le conseil pour exécuter** — le conseil décide la direction ; il n'écrit pas la landing page. Passe à l'exécution une fois la direction posée.
- **Douze conseillers sur un titre** — ajuste la taille du banc aux enjeux.
