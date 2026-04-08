# Design System Reference for Stilla

> Use this file as a reference for AI agents (Claude, Cursor, Stitch) to generate UI that looks like Stilla's design language.
> Based on the structure from [awesome-design-md](https://github.com/VoltAgent/awesome-design-md), adapted to Stilla's brand from the stilla/stilla monorepo.

---

## 1. Visual Theme & Atmosphere

Stilla's design is built on controlled restraint and precision — a professional tool that respects the user's attention. Light mode is clean and airy with a white/near-white palette, while dark mode leans into deep neutrals (not pure black) with blue brand accents. The feeling: a confident, capable product that doesn't shout.

The typography duality defines the brand: **GT Pressura Extended Bold** for marketing headlines creates structural authority, while **Inter Variable** handles all UI text with precision. The brand color — rich blue (`#2176ef` / `#3795fa`) — appears selectively: primary buttons, interactive states, links, and a lavender-blue icon tint (`#646d9b`). Everything else is neutral.

What makes Stilla distinctive: 0.5px borders on retina displays, blue-tinted card shadows (`oklch(0.5525 0.085 207.66 / 0.1)`), a compact 15px body base, and primary buttons rendered as a gradient from `main-700 → main-600` — never flat. Active interactions have a subtle press effect (`translate-y-[0.5px]`, `scale-[99%]`).

**Key Characteristics:**
- Light: `#ffffff` / `#fafafa`; Dark: `#1d1d1d` / `#2b2b2b` — deep neutral, never pure black
- GT Pressura Extended Bold for marketing display; Inter Variable for all UI
- Blue brand accent (`#2176ef` light / `#3795fa` dark) — used selectively, not everywhere
- Lavender-blue icon tinting (`#646d9b`) — icons feel intentional, not generic gray
- Blue-tinted card shadow (`oklch(0.5525 0.085 207.66 / 0.1)`)
- Gradient primary buttons (main-700 → main-600, `to top`)
- Subtle press effect on interaction: `translate-y-[0.5px] scale-[99%]`
- 15px body base — intentionally compact, not the standard 16px
- Retina-aware: 1px borders collapse to 0.5px on high-density displays
- Icons from Central Icons (`centralicons.com`) — Lucide is deprecated

---

## 2. Color Palette & Roles

### Brand Blue Scale (same in light and dark)

| Token | Hex | Role |
|---|---|---|
| `--main-50` | `#f8f9fe` | Lightest tint, hover bg |
| `--main-100` | `#daeeff` | Subtle brand surfaces |
| `--main-200` | `#bee2ff` | Light brand fill |
| `--main-300` | `#91d0ff` | Medium brand tint |
| `--main-400` | `#5db5fd` | Active state fill |
| `--main-500` | `#3795fa` | **Primary (dark mode)** |
| `--main-600` | `#2176ef` | **Primary (light mode)** |
| `--main-700` | `#1c65e5` | Gradient start on buttons |
| `--main-800` | `#1b4db2` | Deep brand |
| `--main-900` | `#1c448c` | Darkest brand |
| `--main-950` | `#162a55` | Near-black brand |

### Semantic Tokens — Light Mode

| Token | Value | Role |
|---|---|---|
| `--background-100` | `#ffffff` | Cards, primary surface |
| `--background-200` | `#fafafa` | Page background |
| `--background-250` | `#ebebeb` | Section dividers |
| `--background-300` | `rgba(0,0,0,0.1)` | Hover states |
| `--foreground` | `#222222` | Primary text |
| `--foreground-secondary` | `#6a6a6a` | Secondary text |
| `--foreground-subtle` | `#9a9a9a` | Placeholder, muted |
| `--foreground-placeholder` | `#dddddd` | Empty state indicators |
| `--foreground-peak` | `#000000` | Maximum contrast |
| `--border-color` | `rgba(0,0,0,0.14)` | Default borders |
| `--primary` | `#2176ef` | Brand CTA |
| `--primary-foreground` | `#f8fafc` | Text on primary |
| `--success` | `#3eb33c` | Positive states |
| `--success-subtle` | bg `#ebfceb` / fg `#2a8028` | Success tint |
| `--destructive` | `#ef4444` | Error, delete |
| `--destructive-subtle` | bg `#fdebec` / fg `#cd3c3a` | Error tint |
| `--warning-subtle` | bg `#fef3e2` / fg `#b45309` | Warning tint |
| `--icon-stroke` | `#646d9b` | Icon default (lavender-blue) |
| `--icon-stroke-bg` | `#e8eaf5` | Icon bg tint |
| `--icon-stroke-active` | `#050a30` | Icon active state |

### Semantic Tokens — Dark Mode

| Token | Value | Role |
|---|---|---|
| `--background-100` | `#1d1d1d` | Cards, primary surface |
| `--background-200` | `#2b2b2b` | Page background |
| `--background-250` | `#2a2a28` | Subtle separation |
| `--background-300` | `#414141` | Hover states |
| `--foreground` | `#efefef` | Primary text |
| `--foreground-secondary` | `#8b8b8b` | Secondary text |
| `--foreground-subtle` | `#555555` | Muted text |
| `--foreground-peak` | `#ffffff` | Maximum contrast |
| `--border-color` | `rgba(255,255,255,0.14)` | Default borders |
| `--primary` | `#3795fa` | Brand CTA |
| `--success-subtle` | bg `#243424` / fg `#4ade80` | Success tint |
| `--destructive-subtle` | bg `#362422` / fg `#de5550` | Error tint |
| `--warning-subtle` | bg `#362d1e` / fg `#fbbf24` | Warning tint |
| `--icon-stroke` | `#9b9b9a` | Icon default (neutral gray) |
| `--icon-stroke-active` | `#d5dbdf` | Icon active |

---

## 3. Typography Rules

### Font Families

- **Display / Headlines (marketing)**: GT Pressura Extended Bold (700) — `--font-gt-pressura-ext-bold` / `'GT Ext Bold'`
- **Subheadings (marketing)**: GT Pressura Extended Medium (500) — `--font-gt-pressura-ext-medium` / `'GT Ext Medium'`
- **Body copy (marketing)**: GT Pressura Standard Text (400) — `--font-gt-pressura` / `'GT Text'`
- **UI / App**: Inter Variable (`InterVariable`) — all interface text, with `font-optical-sizing: auto`
- **Monospace**: `ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas`

### App Typography Scale (base 15px — custom Tailwind)

| Class | Size | Line Height | Typical Weight | Use |
|---|---|---|---|---|
| `text-xxs` | 11px | 1.5 | 500 | Micro labels |
| `text-xs` | 12px | 1.5 | 400-500 | Captions, timestamps |
| `text-sm` | 13px | 1.5 | 500 | Tags, badges, code |
| `text-base` | 15px | 1.6 | 400 | **Standard UI text** |
| `text-lg` | 17px | 1.5rem | 400 | Intro text |
| `text-xl` | 19px | 1.75rem | 500 | Card titles |
| `text-2xl` | 22px | 1.85rem | 600 | Section headings |
| `text-3xl` | 24px | 2rem | 700 | Panel headings |
| `text-4xl` | 30px | 2.5rem | 700 | Major headings |
| `text-5xl` | 36px | 2.75rem | 700 | Hero (app) |

### Marketing Typography (GT Pressura)

| Role | Font | Weight | Notes |
|---|---|---|---|
| Hero H1 | GT Pressura Extended Bold | 700 | Large display headings, taglines |
| Section H2 | GT Pressura Extended Bold | 700 | Section headings |
| Subheading H3 | GT Pressura Extended Medium | 500 | Section subheadings |
| Body | GT Pressura Standard Text | 400 | Marketing copy, descriptions |

### Custom Weight Utilities

- `font-semimedium`: weight 450 — softer emphasis between regular and medium
- `font-semiregular`: weight 450 (landing only)

### Principles

- **GT Pressura Extended Bold is the brand voice** — marketing headlines only, never app UI
- **Inter Variable is the product voice** — clean, neutral, precise for all app UI
- **15px base is non-negotiable** — the entire Tailwind scale shifts down from standard 16px
- **Semimedium (450) for soft emphasis** — avoids the bluntness of 500

---

## 4. Component Stylings

### Buttons

**Primary (Gradient Blue)**
- Background: `linear-gradient(to top, #1c65e5, #2176ef)` (main-700 to main-600)
- Text: `#f8fafc` (primary-foreground), 15px Inter weight 500
- Shadow: `ui-btn-shadow` — layered inset + drop shadows using the button's shadow-color
- Active state: `translate-y-[0.5px] scale-[99%]` — subtle tactile press
- Disabled: `opacity-45`
- Radius: 8px

**Secondary**
- Background: white (light) / dark bg (dark)
- Border: `1px solid rgba(foreground, 0.15)`
- Shadow: `0 3px 6px -2px rgba(0,0,0,0.022), 0 1px 1px 0 rgba(0,0,0,0.044)`
- Radius: 8px

**Destructive**
- Background: `#ef4444` / Text: white
- Same structure as primary

**Ghost**
- No border, no shadow
- Hover: shows `bg-accent`

**Link**
- Text: `#2176ef` (light) / `#3795fa` (dark)
- Underline on hover

**Sizes**

| Size | Height |
|---|---|
| `xxs` | 20px (h-5) |
| `xs` | 24px (h-6) |
| `sm` | 32px (h-8) |
| `md` | 40px (h-10) — default |
| `lg` | 44px (h-11) |

### Cards & Containers
- Background: `--background-100` (`#ffffff` light / `#1d1d1d` dark)
- Border: `1px solid var(--border-color)`
- Shadow: `0 1px 2px 0 oklch(0.5525 0.085 207.66 / 0.1)` — blue-tinted
- Radius: 8px-12px
- Hover: subtle background shift to `--background-200`

### Inputs & Forms
- Background: `--background-100`
- Border: `1px solid var(--border-color)`
- Focus ring: primary color
- Height: 32px (sm) / 40px (md)
- Radius: 8px

### Navigation (App Topbar)
- Fixed height: 40px
- Background: `--background-100`
- Border-bottom: `1px solid var(--border-color)`
- Nav text: Inter 13px-15px weight 500, color `--foreground-secondary`
- Active: `--foreground-peak`, `--icon-stroke-active`
- Icons: `--icon-stroke` (`#646d9b` light)

### Badges
- Background: semantic tint (e.g., `--success-subtle`, `--destructive-subtle`)
- Text: semantic foreground
- Radius: 9999px (pill)
- Padding: 2px 8px
- Font: 12px Inter weight 500

### Icons
- Source: **Central Icons** (`centralicons.com`) — `<Icon name="IconEmail2" />` from `@stilla/ui`
- **Lucide is deprecated and prohibited**
- Default tint: `--icon-stroke` (`#646d9b` light / `#9b9b9a` dark)
- Active tint: `--icon-stroke-active` (`#050a30` light / `#d5dbdf` dark)
- Background accent: `--icon-stroke-bg` (`#e8eaf5`)

---

## 5. Layout Principles

### Spacing System
- Base unit: 4px
- Standard scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64px
- Topbar height: 40px

### Grid & Container (Landing)
- Max-widths: `64rem`, `80rem`, `96rem`
- Custom breakpoints: `xs: 30rem`, `2xl: 88.75rem`, `3xl: 96rem`
- Centered layout with generous margins

### Whitespace Philosophy
- **Compact but breathable**: 15px base keeps the app dense without feeling cramped
- **Structure through spacing**: hierarchy via spacing and subtle borders, not heavy shadows
- **Dark mode: deep, not black**: `#2b2b2b` feels focused; `#000000` is too harsh

### Border Radius Scale

| Size | Value | Use |
|---|---|---|
| Minimal | 2px | Inline elements |
| Standard | 8px | Cards, inputs, buttons (app) |
| Medium | 10px | Landing page components |
| Large | 12px-16px | Panels, dialogs |
| XL | 20px-24px | Modals, sheets |
| Pill | 9999px | Badges, tags |

---

## 6. Depth & Elevation

| Level | Treatment | Use |
|---|---|---|
| Flat | No shadow | Page background, text blocks |
| Card | `0 1px 2px 0 oklch(0.5525 0.085 207.66 / 0.1)` | Standard card elevation — blue-tinted |
| Border-shadow | `0 0 0 1px rgba(0,0,0,0.06)` | Shadow-as-border |
| Button | `ui-btn-shadow` layered inset + drop | Interactive button lift |
| Image | `0 0 0 1px rgba(0,0,0,0.06), inset 0 0 0 1px rgba(0,0,0,0.04), 0 1px 2px rgba(0,0,0,0.05)` | Product screenshots |
| Focus | Primary blue ring | Keyboard focus accessibility |

**Shadow Philosophy**: Stilla uses a **blue-tinted shadow system** — even the default card shadow uses oklch hue 207.66. Shadows are subtle and purposeful, never decorative.

---

## 7. Do's and Don'ts

### Do
- Use **GT Pressura Extended Bold** for marketing headlines
- Use **Inter Variable** for all app UI
- Apply gradient on primary buttons — `linear-gradient(to top, #1c65e5, #2176ef)` — never flat blue
- Use lavender-blue (`#646d9b`) for icon tinting in light mode
- Use **blue-tinted shadows** (`oklch(0.5525 0.085 207.66 / 0.1)`) on cards
- Apply the **press effect** on buttons: `translate-y-[0.5px] scale-[99%]`
- Use deep neutrals (`#1d1d1d`, `#2b2b2b`) for dark mode backgrounds
- Use 0.5px borders on retina displays
- Source icons from **Central Icons** (centralicons.com)
- Use `font-semimedium` (450) for soft emphasis

### Don't
- **Don't use Lucide icons** — deprecated and prohibited
- **Don't use flat color on primary buttons** — gradient is non-negotiable
- **Don't use `#000000` as dark mode background** — use `#1d1d1d`
- **Don't use GT Pressura in app UI** — marketing/landing only
- **Don't use heavy shadows** (>0.15 opacity)
- **Don't use warm-tinted shadows** — palette is cool and blue-tinted
- **Don't set font-size base to 16px in app** — scale starts at 15px
- **Don't use arbitrary brand colors** outside the `--main-*` scale
- **Don't omit dark mode** — every component needs both token sets

---

## 8. Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
|---|---|---|
| xs | 30rem (480px) | Small phones |
| sm | 640px | Standard |
| md | 768px | Tablet |
| lg | 1024px | Desktop threshold |
| xl | 1280px | Wide desktop |
| 2xl | 88.75rem (1420px) | Large screens (custom) |
| 3xl | 96rem (1536px) | Ultra-wide (custom) |

### Dark Mode Implementation
- **App**: `[data-theme="dark"]` data attribute on root
- **Landing**: `.dark` CSS class
- Not based on `prefers-color-scheme` by default — user-controlled

### Collapsing Strategy
- App: sidebar collapses to icon-only or bottom nav
- Landing: multi-column grids to single column
- Topbar: maintains 40px height at all breakpoints

---

## 9. Agent Prompt Guide

### Quick Color Reference

| | Light | Dark |
|---|---|---|
| Page bg | `#fafafa` | `#2b2b2b` |
| Card bg | `#ffffff` | `#1d1d1d` |
| Primary text | `#222222` | `#efefef` |
| Secondary text | `#6a6a6a` | `#8b8b8b` |
| Border | `rgba(0,0,0,0.14)` | `rgba(255,255,255,0.14)` |
| Brand blue | `#2176ef` | `#3795fa` |
| Icon tint | `#646d9b` | `#9b9b9a` |
| Card shadow | `oklch(0.5525 0.085 207.66 / 0.1)` | same |

### Example Component Prompts

- **Primary button**: `Background: linear-gradient(to top, #1c65e5, #2176ef). Height 40px. Radius 8px. Text: #f8fafc, 15px Inter weight 500. Active: translate-y-[0.5px] scale-[99%]. Disabled: opacity-45.`

- **Card**: `Background #ffffff (light) or #1d1d1d (dark). Border: 1px solid rgba(0,0,0,0.14). Shadow: 0 1px 2px 0 oklch(0.5525 0.085 207.66 / 0.1). Radius 8px.`

- **Topbar**: `Height 40px. Background var(--background-100). Border-bottom: 1px solid var(--border-color). Nav text: 13px Inter weight 500, color #6a6a6a. Icon tint: #646d9b.`

- **Badge (success)**: `Pill (9999px). Background #ebfceb. Text #2a8028. 12px Inter weight 500. Padding 2px 8px.`

- **Marketing hero**: `Headline: GT Pressura Extended Bold weight 700. Subheading: GT Pressura Extended Medium weight 500. Body: GT Pressura Standard Text weight 400. CTA: gradient blue primary.`

- **Input**: `Background var(--background-100). Border: 1px solid rgba(0,0,0,0.14). Radius 8px. Height 40px. 15px Inter weight 400. Focus ring: #2176ef.`

- **Dark mode section**: `Background #1d1d1d. Text #efefef. Secondary text #8b8b8b. Border rgba(255,255,255,0.14). Primary blue #3795fa.`

### Iteration Guide

1. **Start neutral** — `#fafafa` light, `#2b2b2b` dark. Brand color via CTAs, not backgrounds.
2. **Blue selectively** — primary buttons, active states, focus rings, links. Not decorative.
3. **Gradient for CTAs** — `linear-gradient(to top, #1c65e5, #2176ef)` — direction matters.
4. **Lavender-blue icons** — `#646d9b` distinguishes from generic gray-icon UIs.
5. **Blue-tinted card shadow** — `oklch(0.5525 0.085 207.66 / 0.1)` — elevation carries brand character.
6. **8px radius** — not pill, not sharp. Refined default.
7. **Press state** — `translate-y-[0.5px] scale-[99%]` on active gives premium tactile feel.
8. **Always do dark mode** — every component needs `[data-theme="dark"]` variants.
