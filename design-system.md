# Monsora Design System

**Source:** [Figma — Monsora macOS v1.1](https://www.figma.com/design/SbdesW48YocQrY6tq2E8gu/Monsora-macOS-v1.1-1008?node-id=100-18) · page "🎲 Design System"
**Version:** v0.1 (quick-reference board) / v1.0 (detailed guide) · Local variables only · Font: Manrope · Light + Dark modes

> This file documents the tokens and base components defined on the Figma "Design System" page: the English quick-reference board, the detailed Chinese design-guide frame (`Monsora · 设计规范指南 v1.0`), the icon set, and the base component set. Hex values below are read directly from Figma's resolved variables where noted "resolved"; values marked "derived" are computed by following the documented name → primitive mapping (e.g. `bg/canvas = neutral/50`) and have not been individually re-resolved.

## Scope & status

- **Already existed before v0.1:** the color palette, Manrope typeface, spacing scale, and radius scale.
- **Added in v0.1:** error-red palette, action states, control sizing, and the Button / Input / Badge / Switch component masters.
- **How to use it:** always reference the semantic variables (e.g. `bg/surface`, `text/primary`), not raw hex or primitive names. Instance properties can be edited freely — this board has no external library dependencies.
- **Scope:** this is a starter library. Existing product screens have **not** been migrated to it yet.

---

## 1. Color

Neutrals are a **warm-grey ramp** (hue shifted ~30°) — not pure neutral grey. Semantic colors carry paired Light/Dark values; switching the Color collection's mode re-skins the whole system at once.

### Primitives (neutral scale)

| Token | Hex (resolved) |
|---|---|
| `neutral/0` | `#FFFFFF` |
| `neutral/25` | `#F8F8F8` |
| `neutral/50` | `#F4F3F3` |
| `neutral/100` | `#EDECEB` |
| `neutral/200` | `#E2E2E2` |
| `neutral/300` | `#D3D1CF` |
| `neutral/400` | `#BCBAB8` |
| `neutral/500` | `#8A8784` |
| `neutral/600` | `#5C5957` |
| `neutral/700` | `#3A3836` |
| `neutral/800` | `#2A2827` |
| `neutral/900` | `#1D1C1B` |
| `neutral/950` | `#141312` |
| `neutral/1000` | `#000000` |

### Accent primitives

| Token | Hex | Role |
|---|---|---|
| `lime/200` | `#EFFFB7` | accent, light |
| `lime/600` | `#7A9410` | accent, dark |
| `sky/100` | `#DDEBF0` | accent, light |
| `sky/600` | `#4A7C8C` | accent, dark |
| `red/400` | `#E8807A` | error, dark-mode |
| `red/600` | `#C72929` | error, light-mode |

### Semantic tokens

| Token | Light | Dark | Usage |
|---|---|---|---|
| `bg/canvas` | `#F4F3F3` (derived) | `#141312` (derived) | Window base background |
| `bg/surface` | `#FFFFFF` (resolved) | `#1D1C1B` (derived) | Cards, panels, dialogs |
| `bg/subtle` | `#F8F8F8` (resolved) | `#2A2827` (derived) | Embedded/inset blocks |
| `bg/hover` | `#EDECEB` (resolved) | `#2A2827` (derived) | Hover-state fill |
| `bg/inverse` | `#1D1C1B` (resolved) | `#F8F8F8` (derived) | Inverted blocks (e.g. the Fetch button) |
| `bg/overlay` | `#000000 @ 40%` (same both modes) | `#000000 @ 40%` | Modal scrim — always pair with 40% opacity |
| `bg/glass` | — | — | Frosted-glass fill; already includes ~80% white — never stack extra layer opacity on it |
| `text/primary` | `#1D1C1B` (resolved) | `#F8F8F8` (derived) | Body copy, headings |
| `text/secondary` | `#5C5957` (resolved) | `#D3D1CF` (derived) | Descriptions, subtitles |
| `text/muted` | `#8A8784` (resolved) | `#BCBAB8` (derived) | Meta/info labels |
| `text/inverse` | `#FFFFFF` (resolved) | — | Text on inverse/dark fills |
| `text/error` | `#C72929` (derived) | `#E8807A` (derived) | Error messaging |
| `border/default` | `#E2E2E2` (derived) | `#3A3836` (derived) | Default borders |
| `border/subtle` | `#EDECEB` (resolved) | — | Hairlines, dividers |
| `border/focus` | `#1D1C1B` (derived) | `#F8F8F8` (derived) | Keyboard focus ring — never remove with `outline: none` |
| `icon/strong` | `#1D1C1B` (derived) | `#F8F8F8` (derived) | Primary icons |
| `icon/muted` | `#8A8784` (derived) | `#BCBAB8` (derived) | De-emphasized icons |
| `action/primary` | `#1D1C1B` (derived) | `#F8F8F8` (derived) | Primary button fill |

### Choosing a token

When it's unclear which token to use, ask in order:

1. Is it text? → `text/*`
2. Is it an icon? → `icon/*`
3. Is it a stroke? → `border/*`
4. Is it a clickable fill? → `action/*`
5. Otherwise → `bg/*`

---

## 2. Typography

Single type family: **Manrope**, with **PingFang SC** as the Chinese fallback. Earlier Geist / Inter / Roboto Mono usage has been fully consolidated into Manrope. `9px` and `10px` sizes are reserved for high-density areas (e.g. detail-page meta); **do not use them in primary body copy.**

| Style | Size / Line-height | Weight | Usage |
|---|---|---|---|
| `Display/M` | 40 / 48 | SemiBold (600) | Marketing-page hero title |
| `Heading/M` | 24 / 32 | SemiBold (600) | Section headings |
| `Heading/S` | 20 / 24 | Medium (500), +1.4 tracking | Card titles |
| `Title/M` | 16 / 20 | Regular (400) | Detail-page titles |
| `Body/L` | 14 / 22 | Regular (400) | Body copy |
| `Body/M` | 13 / 18 | Regular (400) | Default interface text |
| `Body/M-medium` | 13 / 18 | Medium (500) | Menu items, button labels |
| `Body/M-bold` | 13 / 18 | Bold (700) | Emphasis within interface text |
| `Caption/L` | 12 / 18 | Regular (400) | Supporting copy |
| `Caption/M` | 11 / 16 | Regular (400) | Dense information areas |
| `Caption/M-medium` | 11 / 16 | Medium (500) | Dense info, emphasized |
| `Caption/M-bold` | 11 / 16 | Bold (700) | Dense info, strong emphasis |
| `Micro/L-bold` | 10 / 14 | Bold (700) | Metadata field names |
| `Micro/S` | 9 / 12 | Regular (400) | Extremely dense info (detail pages only) |

The Figma file's text-styles panel defines **27 styles in total**; the table above covers the ones demonstrated on the design-system board plus the weight variants encountered while reading it. All styles are bound to variables (family/weight/size/line-height) — change the variable once and it propagates everywhere.

---

## 3. Spacing & radius

**Spacing** — 8pt base grid; even-number micro-adjustments are allowed in dense areas. `space/3`, `5`, `7`, `9` are legacy compatibility values — **do not use them in new designs.**

`space/4 · 8 · 12 · 16 · 20 · 24 · 32 · 40 · 48 · 64`

**Radius** — values and real usage counts, taken from an audit of the live product file (not estimates):

| Token | px | Uses | Typical components |
|---|---|---|---|
| `radius/2` | 2 | 32 | Inline link underline/markers |
| `radius/4` | 4 | 138 | `mm-block`, `member-cover`, `variant-badge` — very small elements |
| `radius/6` | 6 | 386 | `btn-view` / `btn-active` small buttons, favicons, progress indicator |
| `radius/8` | 8 | 889 | Thumbnails, `lineage-row`, Link — **highest usage in the product** |
| `radius/10` | 10 | 172 | `ref-card`, Button, `member-capsule` |
| `radius/12` | 12 | 122 | `lineage-node`, floating toolbar, `asset-card`, comment card |
| `radius/14` | 14 | 59 | Dropdown/View panel, `section-*` containers |
| `radius/16` | 16 | 77 | `InfoPanel`, `CanvasArea`, `PreviewArea`, `ThumbnailStrip` region panels |
| `radius/20` | 20 | 10 | `asset-detail-modal`, generation input |
| `radius/24` | 24 | 7 | Dropzone, search, menubar |
| `radius/28` | 28 | 5 | A few one-off frames |
| `radius/32` | 32 | 247 | Large containers — Home grid asset card (310×204), upload modal, inbox |
| `radius/999` | 999 (pill) | 286 | Pills/circles: tag, status pill, bar, back button, zoom control |

---

## 4. Elevation, blur & glass

Shadow exists **only to express hierarchy, never as decoration.** Elements at the same hierarchy level must share the exact same shadow token. In dark mode shadow contrast is weak — add a `border/default` stroke alongside shadow to keep levels distinguishable.

### Elevation (resolved drop-shadow values)

| Token | CSS box-shadow | Usage |
|---|---|---|
| `Elevation/xs` | `0 1px 2px rgba(0,0,0,0.04)` | Inputs |
| `Elevation/sm` | `0 2px 10px rgba(0,0,0,0.05)` | Card, default state |
| `Elevation/md` | `0 2px 10px rgba(0,0,0,0.10)` | Card, hover state |
| `Elevation/lg` | `0 4px 16px rgba(0,0,0,0.10)` | Dropdown menus |
| `Elevation/xl` | `0 12px 20px rgba(0,0,0,0.05)` | Modals |

### Background blur

| Token | Blur radius | Uses | Where |
|---|---|---|---|
| `Blur/xs` | 4 | 7 | Inset containers, Browser/Start page, imported sites |
| `Blur/md` | 15 | 11 | Menubar flyout, full-screen dialog scrim |
| `Blur/lg` | 40 | 5 | Search overlay, upload modal — the standard glass panel |
| `Blur/xl` | 80 | 1 | Full-screen background blur, bottom layer only |

### Glass panel recipe (search / upload modal / menubar)

```css
background: var(--mon-bg-glass); /* already ~80% white — never stack extra opacity */
backdrop-filter: blur(40px);     /* Blur/lg; use Blur/md (15) for menubar/smaller flyouts */
border-radius: 24px;             /* or 32px for the upload modal */
/* No border by default on floating overlays; menubar & browser panels add border/default */
/* No drop-shadow on glass panels — hierarchy is expressed by blur alone */
```

---

## 5. Components

| Component | Variants / states | Spec |
|---|---|---|
| **Button** | Variant × State × Size — `Primary / Secondary / Accent` × `Default / Hover / Disabled` × `Small / Medium` (18 variants total) | Small height 32, Medium height 40 |
| **Input** | `Default / Focus / Filled / Error / Disabled` | — |
| **Badge** | Tone `Neutral / Lime / Sky` | — |
| **Switch** | `Off / On / Disabled` | — |
| **Tag** | Variant `Default / Add` | Pill radius 999 · padding 5/10 · `Caption/L` 12px · height 30. `Add` variant uses a solid outline. |
| **Icon Button** | `Default / Hover` | 32×32 · radius 8 · icon 16 · hover fills `bg/hover` |
| **Menu Item** | State × Tone — `Default / Hover` × `Default / Danger` | 232×32 · padding 6/8 · radius 6 · `Body/M` 13px · no icon |
| **Meta Field** | — | 3px internal gap · field name = `Micro/L-bold` + `text/muted` · value = `Body/M` + `text/primary` |
| **Divider** | — | 1px, filled with `border/subtle` |
| **Icon set** | ~40 icons currently in the library (the written spec, from v0.1, cites 24; more have been added since) | 16×16 canvas · 1.25 stroke weight · round caps & joins |

Icon set as of this read: `arrow-left, chevron-left, chevron-right, chevron-down, plus, minus, close, check, pencil, comment, lineage, canvas, masonry, expand, play, volume, copy, link, globe, tag, bolt, warning, send, more, user, star, star-fill, search, download, loader, retry, clock, upload, file, folder, certificate, sparkle, image, search-ai, desktop`.

### Interaction state rules

- **Hover** — change fill to `bg/hover` only. Never change size, never add displacement.
- **Focus** — `border/focus` + a focus ring. Must stay visible for keyboard navigation — **never** `outline: none`.
- **Disabled** — fill `action/disabled`, text `text/disabled`; also remove any hover effect.
- **Danger** — only `text/error` / `border/error`. Destructive actions require a second confirmation step.

---

## 6. Beyond the core system

The same Figma page also holds product-specific component families that sit on top of (not inside) the token system above — useful to know about, but not yet formalized as reusable primitives:

- **Business components:** `filter`, `cli`, `menubar`, `card demo`, `search`, `back`
- **Tile components:** Hover Info (`Size=L/M`), Star Button (`Size × Starred × Hover`), Starred Mark
- **Selection Action Bar:** `Selection=Partial / All`
- **Search Bar / Result Header / Panel / Zone Header:** each split into `Size=Platform` vs `Size=Plugin`, with states spanning `Default, Focus, Typing, Filled, Loading, Image, Uploading`
- **Search AI Status:** `Idle, Searching, Empty, Error` (Platform + Plugin sizes)
- **AI Aura:** `Flowing, Edge, Empty, Error` (Platform + Plugin sizes)

These weren't speced out in detail here since they're product compositions rather than design-system tokens — pull them individually with Figma's `get_design_context` if/when one needs to be implemented.
