# UUIF 9.2 — Foundation Tokens (Spacing, Radius, Shadow, Typography)

<!-- This file contains 5 sections: Font Loading, Spacing Scale, Radius, Shadow, Typography Scale -->

---

## Font Loading (Include in Every HTML File)

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Nunito+Sans:ital,opsz,wght@0,6..12,200..1000;1,6..12,200..1000&display=swap" rel="stylesheet">
```

All text uses `font-family: 'Nunito Sans', sans-serif`. No system font fallbacks in UI elements.

---

## Spacing Scale

| Step | px | CSS Variable |
|---|---|---|
| 0 | 0px | — |
| 1 | 2px | `--uuif-sp-1` |
| 2 | 4px | `--uuif-sp-2` |
| 3 | 8px | `--uuif-sp-3` |
| 4 | 12px | `--uuif-sp-4` |
| 5 | 16px | `--uuif-sp-5` |
| 6 | 20px | `--uuif-sp-6` |
| 7 | 24px | `--uuif-sp-7` |
| 8 | 32px | `--uuif-sp-8` |
| 9 | 40px | `--uuif-sp-9` |
| 10 | 48px | `--uuif-sp-10` |
| 12 | 64px | `--uuif-sp-12` |

Do not approximate between steps.

---

## Border Radius

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-radius-4` | `4px` | Chips, small badges |
| `--uuif-radius-6` | `6px` | Inputs, dropdowns, cards, modals |
| `--uuif-radius-8` | `8px` | Outer card wrappers, popovers, modals |
| `--uuif-radius-12` | `12px` | Cards (large) |
| `--uuif-radius-22` | `22px` | Icon buttons |
| `--uuif-radius-pill` | `88px` | Buttons, toggles, sliders |

---

## Shadow

| CSS Variable | Value | Usage |
|---|---|---|
| `--uuif-shadow-sm` | `0px 1px 6px 2px rgba(0,0,0,0.12)` | Dropdowns, date picker |
| `--uuif-shadow-md` | `0px 4px 12px 0px rgba(0,0,0,0.16)` | Modals, popovers |

---

## Typography Scale

All text: `font-family: 'Nunito Sans', sans-serif`. Line-height: 1. Letter-spacing: 0.

| CSS Variable | Weight | Size | Usage |
|---|---|---|---|
| `--uuif-font-bold-16` | 700 | 16px | Modal titles, card headings |
| `--uuif-font-semibold-14` | 600 | 14px | Form labels, alert titles |
| `--uuif-font-semibold-13` | 600 | 13px | Nav section headers |
| `--uuif-font-semibold-12` | 600 | 12px | Active sub-links, small badges |
| `--uuif-font-regular-16` | 400 | 16px | Title pane text |
| `--uuif-font-regular-14` | 400 | 14px | Body text default |
| `--uuif-font-regular-13` | 400 | 13px | Buttons, form controls, table cells |
| `--uuif-font-regular-12` | 400 | 12px | Captions, sub-nav links |

### Hierarchy Quick Reference

- Page title: 26px bold white (on dark header)
- Panel title: 18px light, sentence case
- Card/modal title: 14–16px bold, UPPERCASE
- Body / form: 13px regular
- Caption / label: 11–12px, often UPPERCASE + letter-spacing 0.07em
