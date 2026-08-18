# UUIF 9.2 — Color Tokens

<!-- This file contains 7 sections: Text, Surface, Border, Icon, Branding, Status/Severity, Fill Colors, Status Color Pairings, Conflict Resolution -->

> Always use `var(--uuif-*)` CSS variables. Never hardcode hex values.

---

## Text

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-text-primary` | `#191c25` | Default body copy |
| `--uuif-text-secondary` | `#4a618f` | Labels, nav links, captions |
| `--uuif-text-tertiary` | `#888888` | Tertiary/muted text |
| `--uuif-text-contrast` | `#ffffff` | Text on dark/colored surfaces |
| `--uuif-text-disabled` | `rgba(17,17,17,0.3)` | Disabled labels |
| `--uuif-text-hover` | `#ff5d00` | Hover state text |
| `--uuif-text-selected` | `#ffffff` | Selected state text |
| `--uuif-text-highlight` | `#0c2b67` | Dashboard card titles, emphasis |

---

## Surface

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-surface-container` | `#ffffff` | Default card / panel background |
| `--uuif-surface-bg` | `#fafafa` | Page-level background |
| `--uuif-surface-primary` | `#5b74a7` | Primary button fill |
| `--uuif-surface-secondary` | `#d2dff2` | Secondary surface, theme bg |
| `--uuif-surface-tertiary` | `#f6f8fe` | Subtle tinted bg, tooltip bg |
| `--uuif-surface-highlight` | `#ff5d00` | Active states, selected fills |
| `--uuif-surface-hover` | `rgba(17,17,17,0.06)` | Generic hover overlay |
| `--uuif-surface-selected` | `rgba(255,72,26,0.09)` | Selected row / active subnav link |
| `--uuif-surface-disabled` | `#e8eff9` | Disabled input/tab backgrounds |
| `--uuif-surface-contrast` | `#111315` | Dark button fill |
| `--uuif-surface-model` | `#f0f2f5` | Table headers, card headers |

---

## Border

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-border-primary` | `#ff5d00` | Active indicators, focus borders |
| `--uuif-border-secondary` | `#78a3e5` | Secondary button border, emphasis |
| `--uuif-border-tertiary` | `#cccccc` | Light dividers, outer card borders |
| `--uuif-border-transparent` | `rgba(17,17,17,0.09)` | Subtle internal dividers |
| `--uuif-border-disabled` | `#d2dff2` | Disabled field borders |
| `--uuif-border-hover` | `#ff5d00` | Hover border state |
| `--uuif-border-selected` | `#ffffff` | Selected state border |

---

## Icon

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-icon-primary` | `#5885cc` | Default icon fill |
| `--uuif-icon-secondary` | `#9dafd3` | Secondary / muted icon |
| `--uuif-icon-tertiary` | `#62686d` | Tertiary icon |
| `--uuif-icon-hover` | `#ff5d00` | Icon hover state |

---

## Branding

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-brand-navy` | `#001b50` | Left nav, top nav background |
| `--uuif-brand-blue` | `#1f3c73` | Page header, date picker header |
| `--uuif-brand-orange` | `#ff5d00` | Active nav indicator, count block icons |
| `--uuif-brand-green` | `#59a02e` | Toggle ON, wizard done step |
| `--uuif-brand-red` | `#c70f0f` | Danger actions |
| `--uuif-brand-yellow` | `#f3ac3d` | Warning semantic |
| `--uuif-theme-text-primary` | `#001b50` | Primary text on themed surfaces |
| `--uuif-theme-text-secondary` | `#5b74a7` | Secondary text on themed surfaces |
| `--uuif-theme-bg-primary` | `#001b50` | Primary themed background |
| `--uuif-theme-bg-secondary` | `#d2dff2` | Info status message background |

---

## Status / Severity (Traffic Light Scale)

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-status-normal` | `#99CC00` | Normal / healthy |
| `--uuif-status-minor` | `#FFCC00` | Minor alert |
| `--uuif-status-major` | `#FF9900` | Major alert |
| `--uuif-status-high` | `#FF0000` | High severity |
| `--uuif-status-failed` | `#CC0000` | Failed / critical |

---

## Fill Colors (Alert Backgrounds)

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-fill-blue-lightest` | `#f6f8fe` | Info alert background |
| `--uuif-fill-green-xxx-lighter` | `#e3efdc` | Success alert background |
| `--uuif-fill-yellow-xxx-lighter` | `#ffe9be` | Warning alert background |
| `--uuif-fill-red-lightest` | `#fff0f0` | Error alert background |
| `--uuif-fill-green-x-darker` | `#478234` | Success emphasis |
| `--uuif-fill-orange-x-darker` | `#c24903` | Warning emphasis |
| `--uuif-fill-red-x-darker` | `#ab0a0c` | Error emphasis |

---

## Status Color Pairings (Always Use Together)

| Status | Icon/Border Color | Background |
|---|---|---|
| Info | `--uuif-border-secondary` | `--uuif-fill-blue-lightest` |
| Success | `--uuif-brand-green` | `--uuif-fill-green-xxx-lighter` |
| Warning | `--uuif-brand-yellow` | `--uuif-fill-yellow-xxx-lighter` |
| Error/Critical | `--uuif-brand-red` | `--uuif-fill-red-lightest` |

---

## Token Conflict Resolution

> Resolved in favour of UUIF 9.2 Figma-extracted values:
> - `surface/highlight`: use `#ff5d00` (orange), not `#5885cc` (blue)
> - `border/primary`: use `#ff5d00` (orange), not `#9dafd3` (slate)
