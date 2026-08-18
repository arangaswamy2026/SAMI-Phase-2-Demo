# UUIF 9.2 — Dialogs & Overlay Components

<!-- This file contains 5 sections: Modal, Tooltip, Popover, Status Info Banner, Date Picker -->

---

## Modal

- Radius: `--uuif-radius-8` · Shadow: `--uuif-shadow-md`
- Header: 45px, `--uuif-border-transparent` bottom — title 16px regular UPPERCASE, close ✕ 16px `--uuif-text-secondary`
- Body: 20px padding
- Footer: `--uuif-border-transparent` top, 16px padding, right-aligned buttons
- Modal structure: 45px title pane + scrollable body + 69px action bar, right-aligned buttons

| Size | Width |
|---|---|
| Small | 498px |
| Medium | 736px |
| Large | 879px |

---

## Tooltip

- Background: `--uuif-surface-tertiary` · Border: `--uuif-border-secondary` · Radius: `--uuif-radius-6`
- Font: 14px `--uuif-theme-text-secondary`
- Arrow: 8px CSS triangle
- "Learn more": semibold `#038af2`

---

## Popover

- Width: 274px · Radius: `--uuif-radius-8` · Shadow: `--uuif-shadow-md`
- Header: `--uuif-surface-tertiary` bg, 13px padding, 18px bold UPPERCASE
- Body: 10px padding, 13px
- Footer: `--uuif-border-transparent` top, right-aligned buttons

---

## Status Info Banner

| Variant | Background | Border/Icon | Usage |
|---|---|---|---|
| Info | `--uuif-fill-blue-lightest` | `--uuif-border-secondary` | System messages |
| Success | `--uuif-fill-green-xxx-lighter` | `--uuif-brand-green` | Completed operations |
| Warning | `--uuif-fill-yellow-xxx-lighter` | `--uuif-brand-yellow` | Configuration review |
| Error | `--uuif-fill-red-lightest` | `--uuif-brand-red` | Failures |

- Icon: 24×24px circle, white symbol
- Title: 16px bold `--uuif-text-secondary`
- Body: 13px `--uuif-text-secondary`

---

## Date Picker

- Width: 270px · Radius: `--uuif-radius-6` · Shadow: `--uuif-shadow-sm`
- Header: `--uuif-brand-blue` bg, white text, bold 14px month label
- Grid: 7-col, 11px day text
- Today: `--uuif-surface-tertiary` bg
- Selected: `--uuif-surface-primary` bg, white text
- Footer: Cancel (secondary sm) + Apply (primary sm), right-aligned
