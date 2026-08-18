# UUIF 9.2 — Dashboard, Table & Feedback Components

<!-- This file contains 8 sections: Dashboard Card, Count Block, Data Table, Chip, Severity Icon, Pagination, Spinner, Progress Bar, Mock Generation Rules -->

---

## Dashboard Card

- Background: `--uuif-surface-container` · Border: `--uuif-border-tertiary` · Radius: `--uuif-radius-6`
- Header: `--uuif-surface-model` bg, `--uuif-border-transparent` bottom — title 14px bold `--uuif-text-highlight` UPPERCASE
- Body: 10px padding
- Footer: `--uuif-border-transparent` top, right-aligned actions

---

## Count Block

- Background: `--uuif-surface-container` · Border: `--uuif-border-secondary` · Radius: `--uuif-radius-8` · Padding: 12px
- Icon: 24×24px `--uuif-brand-orange` fill, `--uuif-radius-6`
- Label: 14px semibold `--uuif-text-secondary` UPPERCASE
- Value: 20px bold `--uuif-text-primary`

---

## Data Table

- Header: `--uuif-surface-model` bg, `--uuif-border-primary` bottom, 11px bold `--uuif-text-secondary` UPPERCASE
- Rows: alternating white / `--uuif-fill-blue-lightest`
- Cell: 13px `--uuif-text-primary`, 7px/12px padding
- Row hover: `--uuif-surface-tertiary`
- Checkbox: 16×16px, checked fill `--uuif-brand-orange`

---

## Chip (Status Badge)

| Variant | Background | Border | Text |
|---|---|---|---|
| Default | `--uuif-surface-tertiary` | `--uuif-border-secondary` | `--uuif-text-secondary` |
| Success | `--uuif-fill-green-xxx-lighter` | `--uuif-brand-green` | `--uuif-brand-green` |
| Warning | `--uuif-fill-yellow-xxx-lighter` | `--uuif-brand-yellow` | `--uuif-brand-yellow` |
| Error | `--uuif-fill-red-lightest` | `--uuif-brand-red` | `--uuif-brand-red` |
| Label/New | `--uuif-brand-green` | none | white, 12px bold, UPPERCASE |

- Height: 22px · Radius: `--uuif-radius-4` · Padding: `2px 7px`

---

## Severity Icon

| Level | Color |
|---|---|
| Normal | `--uuif-status-normal` |
| Minor | `--uuif-status-minor` |
| Major | `--uuif-status-major` |
| High | `--uuif-status-high` |
| Failed | `--uuif-status-failed` |

Size: 16×16px · Radius: `--uuif-radius-4`

---

## Pagination

- Layout: space-between · Padding: `8px 10px`
- Info text: 13px `--uuif-text-primary`

---

## Spinner

- Large: 64×64px, 6px border
- Small: 32×32px, 4px border
- Track: `--uuif-border-secondary` · Spin color: `--uuif-surface-primary`
- Animation: 1s linear infinite

---

## Progress Bar

- Small: 6px tall · Large: 12px tall · Radius: `--uuif-radius-pill`
- Track: `--uuif-border-disabled` · Fill: `--uuif-surface-primary`

---

## Mock Generation Rules (Mandatory)

1. Always use `var(--uuif-*)` CSS variables — never hardcode hex values inline
2. Use semantic class names: `uuif-btn`, `uuif-input`, `uuif-modal`, `uuif-chip`, etc.
3. Every page mock must include the full nav shell (60px primary rail + 266px subnav)
4. Navigation icons must be copied verbatim from the SVG registry — never substitute Font Awesome, Material Icons, or emoji
5. Buttons are always pill-shaped (`--uuif-radius-pill`). Never rectangular
6. Form layouts use 150px right-aligned labels with 20px gap to control
7. Modal dialogs: 45px title pane + scrollable body + 69px action bar, right-aligned buttons
8. The SonicWall Swoosh logomark always uses `fill="#FF5D00"` in the primary nav
9. The SonicWall Wordmark SVG always appears in the SubNav header — never substitute with plain text
