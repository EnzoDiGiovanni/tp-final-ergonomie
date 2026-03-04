# TP Final Ergonomie — Homepage GTA V

Reproduction de la landing page de **Grand Theft Auto V** (Rockstar Games) avec Vue 3 et Tailwind CSS v4 CSS-first.

---

## Structure

- `Header.vue` → `<header>` nav sticky + burger mobile
- `HeroSection.vue` → `<section>` bannière plein écran, logos, 2 CTA
- `SplitSection.vue` → `<section>` image + texte alternés gauche/droite
- `FeatureBlock.vue` → `<section>` image + titre + texte
- `Footer.vue` → `<footer>` liens légaux, icônes sociales

Tout le CSS est centralisé dans `src/main.css`. Aucun `<style>` dans les composants.

---

## Ergonomie

**Hiérarchie visuelle** — trois niveaux : Hero plein écran (attention immédiate), SplitSection (contenu principal), FeatureBlock (détails secondaires).

**Charge cognitive réduite** — une thématique par section, alternance gauche/droite pour créer un rythme, maximum deux CTA par écran, fond sombre uniforme sans distraction.

**Pattern de lecture** — Z sur le Hero (logo → nav → CTA), F sur les sections de contenu (titres à gauche, texte en dessous).

**CTA** — bordure blanche sur fond sombre pour un contraste maximal. Les deux boutons du Hero sont au même niveau hiérarchique car les deux actions sont équivalentes.

**Heuristiques de Nielsen** — burger animé avec `aria-expanded` (visibilité du statut), libellés en français naturel (correspondance réel/système), `type="button"` partout (prévention d'erreurs), skip link clavier (flexibilité), une police + fond noir dominant (minimalisme), tokens et focus uniform (cohérence).

---

## Accessibilité (WCAG AA)

- Texte blanc sur `#111111` → ratio ≈ 18:1 / texte `gray-300` sur fond sombre → ≈ 10:1
- Skip link `<a href="#main-content">` visible uniquement au focus (`sr-only focus:not-sr-only`)
- `@utility focus-rs` : outline blanc 2px appliqué uniformément sur tous les interactifs
- Menu mobile : `aria-expanded`, `aria-controls`, liens hors DOM visuel exclus du Tab
- Images décoratives : `alt=""` + `aria-hidden="true"` / images de contenu : `alt` descriptif
- Balises sémantiques : `<header>`, `<nav aria-label>`, `<main>`, `<section aria-labelledby>`, `<footer>`, `<h1>` unique, `<h2>` par section

---

## Tailwind CSS v4

**Tokens `@theme`**

```css
--color-rs-red: #c8102e; /* rouge Rockstar */
--color-rs-dark: #111111; /* fond header/footer */
--color-rs-surface: #121212; /* fond sections features */
--color-rs-nav: #d4d4d4; /* liens nav */
--color-rs-border: #404040; /* séparateur nav mobile */
--font-chalet: "Chalet", "Arial Black", sans-serif;
```

Seules les valeurs absentes de Tailwind sont définies ici.

**Utilities `@utility`** — `container-rs` (wrapper centré), `focus-rs` (focus visible), `nav-link-rs`, `nav-link-mobile`, `btn-rs-outline`. Chacun encapsule ses états hover et focus-visible via CSS nesting.

**Responsive** — breakpoint principal `lg` (1024px). En dessous : layout colonne, images pleine largeur, typographies réduites, CTA centrés. Au-dessus : sections split en `lg:flex-row`. Aucun `@media` dans les composants.

---

## Difficultés

- **Tokens manquants** — le code initial référençait des variables non définies. Résolu en complétant `@theme` et `@utility`.
- **Overflow image** — l'image latérale débordait entre 768px et 1024px avec `md:flex-row`. Corrigé en passant les breakpoints critiques à `lg:`.
- **`@utility` avec états** — en Tailwind v4, `&:hover` et `&:focus-visible` s'écrivent directement dans `@utility` via CSS nesting.

---

```sh
npm install && npm run dev
```
