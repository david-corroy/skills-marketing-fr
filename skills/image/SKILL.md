---
name: image
description: Quand l'utilisateur veut créer, générer, retoucher ou optimiser des images marketing — visuels d'articles de blog, graphiques réseaux sociaux, mockups produit, bannières de profil, images OG, assets de marque. Déclenche ce skill sur « génère une image », « crée un visuel », « image d'illustration », « bannière », « photo de couverture », « mockup », « image OG », « optimise mes images », « compresse les images », « WebP », « AVIF », « Midjourney », « Flux », « DALL-E », « Ideogram », « Nano Banana », « Canva », « Figma ». Pour la création et l'optimisation d'images marketing en général.
metadata:
  version: 2.0.1
---

# Image

Tu es expert en production visuelle marketing : génération d'images par IA, outils de design, optimisation web. Objectif : produire des visuels professionnels efficacement — du visuel d'article au mockup produit en passant par la bannière LinkedIn.

## Avant de commencer

**Vérifie d'abord le contexte produit :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`), lis-le avant de poser des questions.

Rassemble ce contexte (demande si absent) :

### 1. Objectif de l'image
- Quel type ? (visuel d'article, graphique social, mockup, bannière, asset de marque, image OG)
- Quel emplacement ? (site, réseaux sociaux, annuaire, e-mail)
- Quelles dimensions ?

### 2. Approche de production
- Assets de marque existants ? (logo, couleurs, typos, charte)
- Photoréaliste ou illustratif ?
- Ponctuel ou template réutilisable ?

### 3. Contexte technique
- Clés API disponibles ? (Gemini, Replicate/Flux, Ideogram)
- Contrainte budget ? (certains outils facturent à l'image)
- Optimisation web nécessaire ?

---

## Choisir son approche

| Approche | Idéal pour | Outils | Quand |
|----------|-----------|--------|-------|
| **Génération IA** | Images originales depuis un prompt | Gemini/Nano Banana, Flux, Ideogram | Visuels d'articles, graphiques sociaux, scènes lifestyle |
| **Retouche IA** | Modifier une image existante | Gemini, Flux Kontext | Détourage, changement de style, variantes |
| **Outils de design** | Assets templatés cohérents avec la marque | Canva, Figma | Bannières, templates sociaux, présentations |
| **Capture + habillage** | Montrer une vraie interface | Screenshot + overlay HTML/CSS | Mockups produit, annonces de fonctionnalités |
| **Banques d'images** | Scènes génériques | Unsplash, Pexels | Quand la vitesse prime sur l'unicité |

---

## Génération d'images par IA

### Comparatif des modèles

| Modèle | Idéal pour | Texte dans l'image | API |
|--------|-----------|:---:|-----|
| **Gemini Image** (Google, « Nano Banana ») | Polyvalent, retouche, multi-références, rendu de texte | Bon | Gemini API |
| **Flux** (Black Forest Labs — Pro 1.1, Kontext, Dev, Schnell) | Photoréalisme, cohérence de marque, volume ; Kontext pour la retouche | Limité | BFL, Replicate, fal.ai |
| **Ideogram 3.0** | Typographie, visuels avec texte précis | Le meilleur | Ideogram API |
| **ChatGPT Images / GPT Image** (OpenAI) | Usage général, retouche native | Bon | OpenAI API |
| **Midjourney v7** | Direction artistique, esthétique poussée | Correct | Pas d'API officielle |
| **Recraft V3** | Vectoriel + illustrations cohérentes | Fort | Recraft API |
| **Stable Diffusion 3.5 / SDXL** | Auto-hébergé, personnalisable | Variable | Open source |

**Attention au texte français** : les modèles ajoutent facilement des fautes ou des accents cassés. Pour un titre en français dans l'image, utilise Ideogram, ou mieux : génère l'image sans texte et pose le texte en overlay HTML/CSS ou dans Canva. Vérifie toujours les accents (é, è, à, ç) avant publication.

### Quel modèle pour quel besoin

```
Besoin de texte/titres dans l'image ?
├── Oui → Ideogram 3.0 (meilleur), Gemini (bon) — ou texte en overlay
└── Non ↓

Cohérence produit/marque sur une série d'images ?
├── Oui → Flux (multi-références), Gemini Nano Banana Pro, Recraft V3
└── Non ↓

Retoucher une image existante ?
├── Oui → Gemini (retouche native), Flux Kontext, ChatGPT Images
└── Non ↓

Assets vectoriels / illustratifs ?
├── Oui → Recraft V3
└── Non ↓

Qualité visuelle maximale / direction artistique ?
├── Oui → Flux Pro 1.1, Midjourney v7
└── Non ↓

Volume à bas coût ?
└── Flux Schnell, Gemini Flash, Stable Diffusion auto-hébergé
```

### Bases du prompting

Un bon prompt image suit : **Sujet + Décor + Style + Lumière + Composition + Technique**

```
Un ordinateur portable sur un bureau blanc minimaliste affichant un tableau de bord,
lumière douce venant de la gauche, faible profondeur de champ,
style photographie commerciale épurée, ratio 16:9, 4K
```

**Erreurs courantes :**
- Trop vague (« une image business ») — ajoute des détails concrets
- Oublier le ratio — précise toujours les dimensions
- Demander du texte complexe — passe par un overlay
- Aucune direction de style — « photoréaliste », « illustration flat », « rendu 3D » changent tout

---

## Outils de design

### Canva
Pour les non-designers qui veulent un rendu propre, vite.
- **Forces** : bibliothèque de templates, kit de marque, redimensionnement magique (un design → tous les formats)
- **Limites** : rendu parfois générique, moins de contrôle que Figma

### Figma
Pour les équipes avec un design system ou un besoin de précision.
- **Forces** : composants, auto layout, templates OG, plugins
- **Limites** : courbe d'apprentissage

### Design vs génération IA

| Scénario | Outil de design | Génération IA |
|----------|:---:|:---:|
| Charte graphique stricte à respecter | Oui | Peut-être (avec images de référence) |
| 20 déclinaisons de formats d'un même visuel | Oui (Canva) | Non |
| Visuel unique pour un article de blog | Non | Oui |
| Template social récurrent | Oui | Non |
| Mockup produit avec vraie interface | Non (capture d'écran) | Non (l'IA hallucine les UI) |
| Visuel abstrait/créatif | Non | Oui |

---

## Workflows marketing

### Visuels d'articles de blog

1. **Définir le concept** — quelle métaphore visuelle pour le sujet ?
2. **Générer** — Flux ou Gemini pour le photoréaliste, Ideogram si texte
3. **Format 1200x630** (sert aussi d'image OG) ou 1920x1080 en pleine largeur
4. **Optimiser** — moins de 200 Ko, AVIF ou WebP

### Graphiques réseaux sociaux

| Plateforme | Format principal | Ratio |
|-----------|-----------------|:---:|
| Twitter/X | 1200x675 | 16:9 |
| LinkedIn | 1200x627 | 1.91:1 |
| Instagram feed | 1080x1080 (ou 1080x1350) | 1:1 (4:5) |
| Instagram Stories | 1080x1920 | 9:16 |
| Facebook | 1200x630 | 1.91:1 |

Workflow : créer le concept à la résolution la plus haute, décliner par plateforme (Canva), poser le texte en overlay, exporter aux dimensions exactes.

### Mockups produit et captures

Les modèles IA hallucinent les interfaces — jamais d'IA pour montrer TON produit.

1. **Capturer de vraies captures d'écran** en résolution 2x
2. **Encadrer** dans un mockup (navigateur, laptop, mobile)
3. **Contextualiser** — flèches, labels, avant/après
4. **Annoter en code** — overlay HTML/CSS programmable pour la série

### Bannières de profil

| Plateforme | Format | Note |
|-----------|--------|------|
| Couverture LinkedIn perso | 1584x396 | zone sûre au centre |
| Couverture LinkedIn entreprise | 1128x191 | |
| En-tête Twitter/X | 1500x500 | partiellement masqué par l'avatar |
| Aperçu social GitHub | 1280x640 | |

Bonnes pratiques : texte minimal (vu petit sur mobile), contenu critique centré, montrer le produit réel, cohérence de marque.

### Assets de marque

| Asset | Génération IA | Outil de design |
|-------|:---:|:---:|
| Logo | Mauvais (pas vectoriel, incohérent) | Oui (Figma) |
| Icône d'app | Point de départ correct | Oui pour finaliser |
| Illustrations | Bon pour explorer un style | Selon le cas |
| Favicons | Non | Oui (dérivé du logo) |

---

## Optimisation des images

Chaque image affecte la vitesse de page, donc le SEO et la conversion.

### Guide des formats

| Format | Idéal pour | Compression | Support navigateur |
|--------|-----------|-------------|:---:|
| **AVIF** | Compression maximale — le choix par défaut en 2026 | Meilleure que WebP | ~95 % |
| **WebP** | Photos, graphiques — fallback moderne | Avec/sans perte | ~97 % |
| **JPEG** | Fallback universel | Avec perte | Universel |
| **PNG** | Transparence, captures | Sans perte | Universel |
| **SVG** | Logos, icônes, schémas | Vectoriel | Universel |

### Pipeline AVIF pour WordPress (apport terrain)

Recette éprouvée pour un thème WordPress rapide :

1. **Générer les diagrammes en SVG**, puis les rasteriser en AVIF haute résolution (2x la taille d'affichage) — un schéma AVIF de 1600px pèse souvent moins de 60 Ko.
2. **Convertir en lot** :
```bash
# ImageMagick ≥ 7
magick input.png -quality 55 output.avif
# ou avifenc (libavif), meilleur contrôle
avifenc --min 20 --max 32 -j all input.png output.avif
```
3. **Servir avec fallback** via `<picture>` :
```html
<picture>
  <source srcset="/img/schema.avif" type="image/avif">
  <source srcset="/img/schema.webp" type="image/webp">
  <img src="/img/schema.jpg" alt="…" width="1200" height="675" loading="lazy">
</picture>
```
4. **Visionneuse au clic** : sur les diagrammes denses, ajoute une lightbox (l'image s'ouvre en plein écran au clic). Un schéma lisible à 375px ET zoomable au clic transforme une page de texte triste en page de référence. Laisse le diagramme déborder légèrement de la colonne de texte sur desktop : ça attire l'œil.
5. **Vérifier sur mobile d'abord** : chaque visuel doit rester lisible à 375px de large avant validation.

Note : WordPress 6.5+ accepte l'upload AVIF nativement ; vérifie que le serveur (souvent une question de version d'ImageMagick/GD chez l'hébergeur mutualisé) génère bien les miniatures.

### Checklist d'optimisation

- [ ] **Servir AVIF/WebP** avec fallback JPEG/PNG (`<picture>` ou CDN auto-format)
- [ ] **Redimensionner à la taille d'affichage** — pas de 4000px dans un conteneur de 800px
- [ ] **Compresser** — qualité 75-85 % pour les photos
- [ ] **Lazy loading** sous la ligne de flottaison (`loading="lazy"`)
- [ ] **Dimensions explicites** — attributs `width` et `height` contre le CLS
- [ ] **Attribut alt** — descriptif, pertinent, sans bourrage de mots-clés (accessibilité + SEO + lisibilité par les IA)

---

## Images OG et aperçus sociaux

L'image affichée quand ton URL est partagée (réseaux sociaux, Slack, WhatsApp).

### Balises requises

```html
<meta property="og:image" content="https://tonsite.fr/og/nom-page.jpg" />
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:image" content="https://tonsite.fr/og/nom-page.jpg" />
```

Attention : la plupart des plateformes ne lisent pas l'AVIF en image OG. Garde du JPEG ou PNG pour l'OG.

### Images OG dynamiques

Pour générer une image OG unique par page (articles, profils) :
- **Vercel OG** (`@vercel/og`) — génération à la volée en JSX
- **Satori** — HTML/CSS vers SVG
- **Cloudinary** — overlay de texte par URL sur un template
- Sous WordPress : un template + les champs du post suffisent souvent (titre + visuel + logo).

---

## Erreurs courantes

1. **IA pour des captures produit** — les modèles hallucinent les interfaces ; capture le vrai écran
2. **Zapper l'optimisation** — les images non optimisées sont le tueur n°1 de vitesse
3. **Pas d'image OG** — un lien partagé sans aperçu paraît cassé
4. **Mauvais ratio** — vérifie les specs de la plateforme avant de générer
5. **Texte français généré par IA sans relecture** — fautes et accents cassés garantis
6. **Aucune direction de style dans le prompt**
7. **Visuels incohérents avec la marque** — multi-références Flux ou templates
8. **Images énormes sur les landing pages** — compresse, redimensionne, lazy load

---

## Questions à poser

1. Quel type d'image ? (visuel d'article, graphique social, mockup, bannière, asset)
2. Quelle plateforme ? (ça fixe les dimensions)
3. Assets de marque à respecter ?
4. Ponctuel ou template ?
5. Clés API disponibles ?
6. Optimisation web nécessaire ?
