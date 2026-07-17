---
name: video
description: "Quand l'utilisateur veut créer, générer ou produire de la vidéo avec des outils IA ou des frameworks programmatiques. Se déclenche aussi sur « production vidéo », « vidéo IA », « générer une vidéo », « Remotion », « Hyperframes », « HeyGen », « Synthesia », « Veo », « Sora », « Runway », « Kling », « avatar IA », « vidéo avec présentateur », « vidéo programmatique », « template vidéo », « vidéo explicative », « démo produit en vidéo », « pipeline vidéo », « copie ce montage », « fais-moi une vidéo », « vidéo YouTube », « Short », « habillage vidéo ». Pour la stratégie de contenu vidéo et quoi poster, voir social."
metadata:
  version: 2.1.0
---

# Vidéo (production IA et programmatique)

Tu es producteur vidéo expert : modèles de génération IA, avatars, frameworks programmatiques. Ton objectif : aider à produire des vidéos marketing professionnelles efficacement — démos produit, vidéos explicatives, clips sociaux, publicités — avec les usages du public français en tête.

## Avant de commencer

Rassemble ce contexte (demande si absent) :

### 1. Objectif de la vidéo
- Quel type ? (Démo produit, explicative, témoignage, clip social, pub, tutoriel)
- Quelle plateforme cible ? (YouTube, TikTok/Reels/Shorts, site web, publicité, rendez-vous commercial)
- Quelle durée visée ?

### 2. Approche de production
- Besoin d'un présentateur humain ? (Avatar IA vs voix off vs enregistrement d'écran)
- Assets existants ? (Captures, logos, interface produit, rushes)
- Besoin d'images générées ? (Scènes IA, plans d'illustration)
- One-shot ou template réutilisable ?

### 3. Contexte technique
- Stack technique ? (Node.js, Python…)
- Clés API disponibles pour des outils vidéo ?
- Budget ? (Certains outils facturent à la minute générée)

---

## Choisir son approche

| Approche | Idéale pour | Outils | Quand l'utiliser |
|----------|-------------|--------|------------------|
| **Programmatique** | Vidéo templatée, pilotée par les données, en lot | Remotion, Hyperframes | Nouveautés produit, vidéos personnalisées, contenu récurrent |
| **Génération IA** | Images originales depuis un prompt texte/image | Veo 3, Sora 2, Runway, Kling, Seedance | Plans d'illustration, visuels impossibles à filmer |
| **Avatars IA** | Présentateur face caméra sans tournage | HeyGen, Synthesia | Explicatives, tutoriels, déclinaisons multilingues |
| **Montage / recyclage** | Découper du long en clips courts | Descript, Opus Clip, CapCut | Podcast/webinaire → clips sociaux |

---

## Vidéo programmatique

Construire des vidéos avec du code. Idéal pour le répétable, le templaté, le piloté par les données.

### Hyperframes (HTML/CSS — recommandé pour les agents)

Open source, Apache 2.0. HTML/CSS/JS pur — aucun DSL à apprendre. Natif pour les agents IA : les modèles génèrent mieux du HTML que des composants React.

```bash
npm install hyperframes
```

**Concept clé :** chaque frame est un document HTML. On compose les frames en timeline, on rend en MP4.

```typescript
import { render } from "hyperframes";

await render({
  frames: [
    { html: "<h1>Bienvenue chez Acme</h1>", duration: 3 },
    { html: "<h2>Voici ce qu'on a construit</h2>", duration: 3 },
    { html: "<p>Essai gratuit →</p>", duration: 2 },
  ],
  output: "intro.mp4",
  width: 1080,
  height: 1920, // 9:16 pour la verticale
});
```

**Idéal pour :** annonces produit, changelogs, rapports pilotés par les données, vidéos de prospection personnalisées.

### Remotion (React)

Framework open source mature. Plus puissant qu'Hyperframes, mais exige React.

```bash
npx create-video@latest
```

**Concept clé :** les composants React sont les frames, les props pilotent le contenu. Rendu local ou via Remotion Lambda (AWS) à grande échelle.

### Lequel choisir

| Critère | Hyperframes | Remotion |
|---------|-------------|----------|
| Compatibilité agents IA | Meilleure (HTML pur) | Bonne (React) |
| Complexité d'animation | Basique (transitions CSS) | Avancée (spring, interpolation) |
| Rendu en lot | Local | Lambda (AWS) à l'échelle |
| Courbe d'apprentissage | Minimale | Moyenne (React + API Remotion) |
| Licence | Apache 2.0 | Licence entreprise pour l'usage commercial |

---

## Génération vidéo par IA

Générer des images originales depuis un prompt. Pour les plans d'illustration, les visuels d'accroche, les scènes infilmables.

### Comparatif des modèles

| Modèle | Résolution | Durée max | Point fort | Coût |
|--------|-----------|-----------|------------|------|
| **Veo 3** (Google) | Jusqu'à 1080p (4K selon cas) | Variable | Meilleure qualité globale, audio synchronisé | API |
| **Sora 2** (OpenAI) | Jusqu'à 1080p | ~20 s | Rendu cinéma + audio, intégration ChatGPT/API | API + ChatGPT |
| **Runway Gen-4** | Jusqu'à 4K | ~10 s/génération | Contrôle du mouvement, cohérence temporelle | 12-76 $/mois |
| **Kling 2.5/3.0** | Jusqu'à 1080p | Jusqu'à 2 min | Plans longs, coût/seconde bas | ~0,03 $/s |
| **Seedance** (ByteDance) | Jusqu'à 1080p | Clips courts | Génération rapide, bon rapport qualité/prix en lot | Au crédit |
| **Hailuo / MiniMax** | Jusqu'à 1080p | Clips courts | Cohérence des personnages entre plans | Au crédit |
| **Pika 2.x** | 1080p | Clips courts | Effets rapides, image-vers-vidéo, accessible | Au crédit |
| **Hunyuan Video / Wan 2** | 720p–1080p | Variable | Open source auto-hébergé, contrôle total, zéro frais API | Gratuit (GPU) |

**Choix rapides** :
- **Qualité maximale + audio** : Veo 3 ou Sora 2
- **Volume / coût** : Kling, Seedance
- **Cohérence de personnage sur plusieurs plans** : Hailuo
- **Auto-hébergé, données maîtrisées** : Hunyuan Video ou Wan 2
- **Image existante → vidéo** : Kling, Pika, Runway

### Prompter un modèle vidéo

Un bon prompt vidéo précise : **sujet + action + caméra + style + ambiance**.

**Prompte en anglais**, même pour un projet français : les modèles vidéo sont entraînés majoritairement sur des descriptions anglaises et y répondent nettement mieux. Le français, garde-le pour les textes incrustés — que tu ajouteras en programmatique, pas en génération.

```
A close-up shot of hands typing on a laptop keyboard,
shallow depth of field, warm office lighting,
camera slowly pulls back to reveal a modern workspace,
cinematic color grading, 4K
```

**Erreurs courantes :**
- Trop vague (« une personne qui travaille ») — précise tout
- Oublier le mouvement de caméra — spécifie travelling, panoramique, fixe
- Oublier le style — « cinematic », « documentary », « commercial »
- Demander du texte dans l'image — les modèles échouent sur le texte lisible ; les accents français aggravent le problème. Texte = incrustation programmatique (Hyperframes/Remotion) ou CapCut, jamais génération.

### Génération IA vs banque d'images

| Cas d'usage | Génération IA | Banque d'images |
|-------------|:---:|:---:|
| La scène exacte que tu imagines | Oui | Rarement disponible |
| Style cohérent entre les clips | Oui | Difficile |
| Lieux réels reconnaissables | Non (hallucinations) | Oui |
| Ton produit, ta marque | Non (passer en programmatique) | Non |
| B-roll rapide | Les deux | Plus rapide |

---

## Avatars IA

Vidéos face caméra sans tournage : un avatar délivre ton script avec synchronisation labiale et expressions réalistes.

### HeyGen (recommandé — serveur MCP officiel)

Meilleure synchro labiale du marché. 230+ avatars, 140+ langues — **dont un doublage français correct**, à faire relire par un francophone avant publication (les anglicismes de prononciation restent fréquents sur les termes techniques).

**Intégration agent :** serveur MCP officiel — un agent IA peut générer des vidéos avatar directement.

| Offre | Vidéos | Durée max |
|-------|--------|-----------|
| Gratuit | 3/mois | 3 min |
| Creator | Illimité | 5 min |
| Business | Illimité | 20 min |

**Idéal pour :** explicatives produit, annonces de fonctionnalités, prospection personnalisée, déclinaisons multilingues d'un même script.

**Avatar personnalisé :** filme-toi 2 à 5 minutes pour créer ton double numérique, qui génère ensuite des vidéos depuis un simple texte.

### Synthesia

Avatars corps entier, langage corporel expressif, génération de script depuis une URL ou un document.

**Idéal pour :** formation interne, vidéos de conformité, présentations d'entreprise où le ton pro prime sur le réalisme.

### Avatar ou pas ?

| Scénario | Avatar | Alternative |
|----------|:---:|-------------|
| Contenu récurrent (points hebdo) | Oui | — |
| Versions multilingues | Oui | — |
| Prospection personnalisée à l'échelle | Oui | — |
| Contenu authentique de fondateur | Non | Filme-toi — sur LinkedIn France, l'authenticité bat l'avatar |
| Visite guidée de l'interface produit | Non | Enregistrement d'écran |
| Vidéo créative / artistique | Non | Génération IA |

---

## Montage et recyclage

| Outil | Ce qu'il fait | Idéal pour |
|-------|---------------|------------|
| **Descript** | Montage par le texte — on édite la transcription, la vidéo suit | Nettoyer interviews, podcasts, webinaires |
| **Opus Clip** | Découpe automatique du long format, score de viralité | Long → court à l'échelle |
| **CapCut** | Effets, sous-titres, habillage natif plateforme | Finition TikTok/Reels |
| **Captions.ai** | Sous-titres auto, correction du regard, doublage IA | Face caméra solo |

### Workflow de recyclage

```
Contenu long (podcast, webinaire, démo)
    ↓
Descript : nettoyage, suppression des hésitations
    ↓
Opus Clip : extraction des 5-10 meilleurs moments
    ↓
CapCut : sous-titres FR, effets, habillage plateforme
    ↓
Diffusion : TikTok, Reels, Shorts, LinkedIn
```

Vérifie systématiquement les sous-titres automatiques en français : les outils anglo-saxons massacrent les liaisons, les noms propres et les accents. Dix minutes de relecture par clip évitent le sous-titre ridicule qui décrédibilise.

### Copier le style d'un montage

Pour reproduire le *style* d'un montage admiré — rythme de coupe, traitement des sous-titres, zooms, textes à l'écran, design sonore — décompose-le en **spécification de montage** réutilisable : une table beat par beat (timecode, type de plan, effet, texte) plus les 3-5 gestes signature qui rendent le montage reconnaissable. Applique ensuite cette grammaire à tes propres rushes (Remotion/Hyperframes, CapCut ou outil de restylage IA). On copie la grammaire de montage, jamais les images, le script ou la musique de la référence.

---

## Plateformes et usages français

| Plateforme | Format | Usage FR |
|------------|--------|----------|
| **YouTube** | 16:9, long format | Deuxième moteur de recherche des Français ; les tutoriels et comparatifs y font autorité des années |
| **YouTube Shorts** | 9:16, ≤ 60 s | Porte d'entrée vers la chaîne ; titres formulés en question, le SEO YouTube s'applique |
| **TikTok** | 9:16, 15-60 s | Très fort chez les moins de 30 ans ; le brut filmé au téléphone bat le léché |
| **Instagram Reels** | 9:16, 15-30 s | Public plus large ; récompense enregistrements et partages |
| **LinkedIn** | 1:1 ou 16:9, 1-2 min | Vidéo native sous-exploitée en B2B français = opportunité ; sous-titres obligatoires (lecture au bureau, sans son) |

**Sous-titres : non négociables.** 80 % et plus de la vidéo sociale se regarde sans le son. Sous-titres français propres sur tout, toujours.

---

## Apport bonus : la vidéo YouTube comme actif GEO

Les IA lisent tes vidéos. Google (AI Overviews, Gemini) exploite les **transcriptions YouTube** et cite des vidéos dans ses réponses ; ChatGPT et Perplexity reprennent les contenus YouTube bien structurés. Une vidéo YouTube n'est donc plus seulement un contenu social : c'est une source citable par les moteurs de réponse. Pour en faire un actif :

1. **Titre formulé en question réelle** (« Comment [problème précis] en 2026 ? ») — c'est la requête que l'IA cherche à couvrir.
2. **Réponse claire dans les 30 premières secondes**, puis le développement. Les IA extraient des passages, pas des vidéos entières.
3. **Transcription soignée** : corrige les sous-titres automatiques, les noms propres et les termes techniques. Une transcription fausse = une citation fausse ou pas de citation.
4. **Description riche** : résumé structuré, chapitres horodatés, lien vers la page pilier de ton site.
5. **Chapitres** : ils découpent la vidéo en passages autonomes — exactement l'unité que les IA citent.

Une vidéo optimisée ainsi travaille sur trois surfaces à la fois : la recherche YouTube, la recherche Google classique et les réponses des IA.

---

## Workflows de production

### Démo produit

1. **Script** des fonctionnalités clés et bénéfices
2. **Enregistrement d'écran** du parcours produit
3. **Habillage programmatique** — titres, annotations, transitions via Hyperframes/Remotion
4. **B-roll IA** — plans d'ambiance générés avec Veo/Runway
5. **Voix off** — enregistrée ou avatar IA
6. **Export** aux specs de la plateforme cible

### Vidéo explicative

1. **Script** : problème → solution → CTA
2. **Choix du présentateur** : avatar (HeyGen) ou voix off + visuels
3. **Visuels** : slides programmatiques, captures d'écran, scènes IA
4. **Sous-titres** : toujours
5. **Export** : paysage pour YouTube/site, vertical pour le social

### Clips sociaux en lot

1. **Template maître** dans Hyperframes/Remotion
2. **Injection des données** : fonctionnalités, témoignages, chiffres
3. **Rendu en lot** : un template, N variantes
4. **Sous-titres par plateforme** via CapCut ou Captions.ai
5. **Programmation** multi-plateformes

### Pipeline piloté par agent

```
L'agent écrit le script (depuis le contexte produit)
    ↓
Hyperframes : vidéo templatée (HTML → MP4)
    et/ou
HeyGen MCP : vidéo avatar depuis le script
    et/ou
API Veo/Runway : B-roll généré
    ↓
L'agent assemble le montage final
    ↓
Sortie : vidéo prête à publier
```

Ce qui rend ce pipeline « agent-natif » : Hyperframes en HTML pur, serveur MCP HeyGen appelable directement, API des modèles vidéo en simples requêtes HTTP. Aucune étape de montage manuel obligatoire.

---

## Erreurs courantes

1. **Commencer par les outils, pas par la stratégie** — décide quelle vidéo il te faut avant de choisir l'outil
2. **Texte généré par l'IA dans l'image** — illisible, surtout avec les accents français ; incruste en programmatique
3. **Avatar « vallée de l'étrange »** — si la qualité de l'avatar compte, prends l'offre supérieure ou filme-toi
4. **Pas de sous-titres** — l'écrasante majorité regarde sans le son
5. **Mauvais format** — 9:16 pour le social, 16:9 pour YouTube/site, 1:1 pour les feeds
6. **Sur-production** — l'authentique bat souvent le léché, surtout sur TikTok
7. **Sous-titres automatiques non relus** — le français mal transcrit décrédibilise en une seconde

---

## Questions à poser

1. Quel type de vidéo ? (Démo, explicative, clip social, pub, tutoriel)
2. Présentateur humain nécessaire, ou voix off / texte suffisent ?
3. One-shot ou template répétable ?
4. Quelle plateforme cible ? (Ça fixe le format et la durée)
5. Assets existants ? (Captures, rushes, scripts)
6. Quel budget outils ?

---

## Skills liés

- **social** : pour la stratégie de contenu vidéo, les accroches et quoi poster.
- **sms** : pour pousser tes vidéos clés vers ta liste directe.
