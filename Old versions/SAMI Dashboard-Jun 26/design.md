# SAMI / UUIF 9.2 — Design System (`design.md`)

This document is the single source of truth for the look and feel of the SAMI
Recommendations experience. It is extracted directly from
`sami-insights- side panel embedded.html` (the `:root` token block and the
component styles). Feed this file to Claude Code — or place its contents in
`CLAUDE.md` — so every generated screen reuses the same tokens instead of
inventing new colors, spacing, or radii.

**Design language:** UUIF 9.2 (SonicWall Unified UI Framework).
**Every value below maps 1:1 to a `--uuif-*` CSS custom property.** Always
reference the token, never the raw hex.

---

## 1. How to use these tokens

- Reference a token as `var(--uuif-token-name)` in CSS.
- Never hardcode a hex value that a token already covers.
- If a needed value does not exist, add a new token here first, then use it —
  do not scatter one-off literals through the markup.

```css
/* Correct */
color: var(--uuif-text-primary);
/* Wrong */
color: #191c25;
```

---

## 2. Brand colors

These are the fixed SonicWall brand hues. Orange is the primary accent /
call-to-action color; navy anchors the primary navigation.

| Token | Value | Meaning — where and why it is used |
|---|---|---|
| `--uuif-brand-navy` | `#001b50` | Deepest brand blue. Background of the fixed left navigation rail. |
| `--uuif-brand-blue` | `#1f3c73` | Mid brand blue. Secondary structural accents and headings. |
| `--uuif-brand-orange` | `#ff5d00` | Primary action / accent. Buttons, active states, the SAMI FAB, focus rings. |
| `--uuif-brand-green` | `#59a02e` | Success / positive. Renewal and healthy-state indicators. |
| `--uuif-brand-red` | `#c70f0f` | Danger / critical. Critical severity labels and destructive hovers. |
| `--uuif-brand-yellow` | `#f3ac3d` | Warning. Medium-severity dots and warning accents. |

---

## 3. Surface colors (backgrounds)

"Surface" tokens are the fills behind content — pages, cards, panels, and
interaction states such as hover and selected.

| Token | Value | Meaning |
|---|---|---|
| `--uuif-surface-container` | `#ffffff` | Default container/card fill. Title bar, sidebars, list headers. |
| `--uuif-surface-bg` | `#fafafa` | App canvas behind everything. The page background. |
| `--uuif-surface-primary` | `#5b74a7` | Filled accent surface — for example the user avatar circle. |
| `--uuif-surface-secondary` | `#d2dff2` | Light blue surface for secondary emphasis blocks. |
| `--uuif-surface-tertiary` | `#f6f8fe` | Very light blue tint used on hover for tabs and rows. |
| `--uuif-surface-highlight` | `#ff5d00` | Orange highlight surface (mirrors brand orange). |
| `--uuif-surface-hover` | `rgba(17,17,17,0.06)` | Generic neutral hover wash over any element. |
| `--uuif-surface-selected` | `rgba(255,72,26,0.09)` | Faint orange tint marking the selected filter tab. |
| `--uuif-surface-disabled` | `#e8eff9` | Fill for disabled controls. |
| `--uuif-surface-contrast` | `#111315` | Near-black surface for maximum contrast blocks. |
| `--uuif-surface-model` | `#f0f2f5` | Neutral grey for AI/model message surfaces. |

---

## 4. Text colors

Foreground colors for type. The hierarchy runs primary → secondary → tertiary
(most to least emphasis).

| Token | Value | Meaning |
|---|---|---|
| `--uuif-text-primary` | `#191c25` | Default body and title text. Highest emphasis. |
| `--uuif-text-secondary` | `#4a618f` | Muted blue-grey for supporting text, breadcrumbs, tags. |
| `--uuif-text-tertiary` | `#888888` | Lowest emphasis — timestamps, counts, captions. |
| `--uuif-text-contrast` | `#ffffff` | White text on dark or colored surfaces. |
| `--uuif-text-disabled` | `rgba(17,17,17,0.3)` | Greyed-out text for disabled states. |
| `--uuif-text-hover` | `#ff5d00` | Text turns orange on hover (links, actions). |
| `--uuif-text-selected` | `#ffffff` | Text color inside a selected/active colored element. |
| `--uuif-text-highlight` | `#0c2b67` | Deep blue for section titles and emphasized headings. |

---

## 5. Border colors

Stroke colors for dividers, outlines, and control edges.

| Token | Value | Meaning |
|---|---|---|
| `--uuif-border-primary` | `#ff5d00` | Orange active border — left edge of the selected filter tab. |
| `--uuif-border-secondary` | `#78a3e5` | Blue border for hover/focus on secondary controls. |
| `--uuif-border-tertiary` | `#cccccc` | Neutral grey border for default inputs and buttons. |
| `--uuif-border-transparent` | `rgba(17,17,17,0.09)` | Hairline divider between sections and rows. |
| `--uuif-border-disabled` | `#d2dff2` | Border for disabled controls. |
| `--uuif-border-hover` | `#ff5d00` | Border turns orange on hover. |

---

## 6. Icon colors

Dedicated tokens so icons stay consistent independent of text color.

| Token | Value | Meaning |
|---|---|---|
| `--uuif-icon-primary` | `#5885cc` | Default icon blue; also the "info" severity color. |
| `--uuif-icon-secondary` | `#9dafd3` | Lighter icon blue for secondary or inactive icons. |
| `--uuif-icon-tertiary` | `#62686d` | Neutral grey icon for low-emphasis glyphs. |

---

## 7. Fill colors (status tints)

Soft background tints that pair with a status. Used behind chips, badges, and
callouts to signal state without heavy color.

| Token | Value | Meaning |
|---|---|---|
| `--uuif-fill-blue-lightest` | `#f6f8fe` | Lightest blue tint for neutral/info blocks. |
| `--uuif-fill-green-xxx-lighter` | `#e3efdc` | Pale green behind success/renewal chips. |
| `--uuif-fill-yellow-xxx-lighter` | `#ffe9be` | Pale yellow behind warning chips. |
| `--uuif-fill-red-lightest` | `#fff0f0` | Pale red behind critical/danger callouts. |
| `--uuif-fill-green-x-darker` | `#478234` | Darker green for green text on light green fills. |

---

## 8. Shadows (elevation)

Elevation cues. `sm` is resting elevation for cards; `md` is raised elevation
for popovers and panels.

| Token | Value | Meaning |
|---|---|---|
| `--uuif-shadow-sm` | `0px 1px 6px 2px rgba(0,0,0,0.12)` | Low elevation — resting cards. |
| `--uuif-shadow-md` | `0px 4px 12px 0px rgba(0,0,0,0.16)` | Higher elevation — floating panels, menus. |

---

## 9. Radii (corner rounding)

The rounding scale. Small values for controls, large for pills.

| Token | Value | Meaning |
|---|---|---|
| `--uuif-radius-4` | `4px` | Tight rounding — inputs, small buttons, tags. |
| `--uuif-radius-6` | `6px` | Slightly softer — chips and tooltips. |
| `--uuif-radius-8` | `8px` | Standard card/box rounding. |
| `--uuif-radius-12` | `12px` | Large rounding for prominent containers. |
| `--uuif-radius-pill` | `88px` | Fully pill-shaped — count badges, pill buttons. |

---

## 10. Typography

- **Font family:** `'Nunito Sans', sans-serif` (loaded from Google Fonts). All
  text and controls use this single family.
- **Base font size:** `13px` on `body`.
- **Weight scale in use:** `500` (medium), `600` (semibold), `700` (bold),
  `800` (extra-bold headings).

| Role | Size | Weight | Notes |
|---|---|---|---|
| Body base | 13px | 400–500 | Default text. |
| Card title | 13px | 700 | `.ric-title`, list rows. |
| Card excerpt | 11.5px | 400 | Two-line clamped summary. |
| Page title | 18px | 800 | `.page-subheader-title`, in `--uuif-text-highlight`. |
| Section label | 9.5–11px | 700–800 | Uppercase, letter-spaced group labels. |
| Caption / count | 10–10.5px | 600–700 | Timestamps, count badges. |

---

## 11. Layout skeleton

Fixed structural dimensions the whole app is built around. Keep these constant
so screens line up.

| Region | Dimension | Notes |
|---|---|---|
| Primary nav rail | `60px` wide, full height, `--uuif-brand-navy` | Fixed left, `z-index: 100`. |
| Title bar | `48px` tall, offset `left: 60px` | Fixed top, `z-index: 99`. |
| Filter sidebar (col 1) | `220px` wide | White container, right hairline border. |
| Insight list (col 2) | `flex: 1` | Fills remaining width. |
| SAMI chat panel | `390px` wide | Right overlay; docks below title bar when pinned. |
| SAMI FAB | `52px` circle, bottom-right `28px` | Orange, `z-index: 9000`. |

**Motion:** primary transitions use `0.28s cubic-bezier(0.4,0,0.2,1)` for
panel slides and width reflow; smaller state changes use `0.1s–0.2s`.

---

## 12. Core component recipes

Reuse these compositions rather than restyling from scratch.

- **Card (`.rec-insight-card`):** translucent white `rgba(255,255,255,0.92)`
  with `backdrop-filter: blur(8px)`, `10px` radius, soft shadow; active state
  adds an orange outline `rgba(255,93,0,0.28)`.
- **Pill button — primary:** `--uuif-brand-orange` fill, white text,
  `--uuif-radius-pill`, `700` weight; hover darkens to `#e05300`.
- **Pill button — secondary:** white fill, `--uuif-border-secondary` border,
  `--uuif-text-secondary` text; hover switches border and text to orange.
- **Count badge (`.ft-count`):** pill, neutral `rgba(17,17,17,0.07)` fill;
  active variant uses orange tint; `.red` variant uses red tint.
- **Severity dots:** critical `#c70f0f`, warning `#f3ac3d`, info
  `--uuif-icon-primary`.

---

## 13. Note on the SAMI chat panel palette

The chat panel currently uses several hardcoded colors that are **not yet
tokenized** (for example header `#3d5a7a`, user bubble `#1a2540`, bot bubble
`#f0f2f8`, input border `#8b82f0`). To keep the system consistent, these should
be promoted to `--uuif-*` tokens (e.g. `--uuif-sami-header`,
`--uuif-sami-bubble-user`) before the panel is reused elsewhere.
