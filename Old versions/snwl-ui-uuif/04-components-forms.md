# UUIF 9.2 — Form Components

<!-- This file contains 10 sections: Button, Input, Checkbox, Radio, Toggle, Drop Menu, Slider, Icon Sizes, Tab Bar, Title Pane, Accordion, Wizard -->

---

## Button

- Shape: pill (`--uuif-radius-pill`) · Font: regular 13px · Padding: `5.5px 20px` · Small: `3px 14px`
- Hover: border and text change to `--uuif-brand-orange`
- Buttons are always pill-shaped. Never rectangular.

| Variant | Background | Border | Text |
|---|---|---|---|
| Secondary (default) | `--uuif-surface-container` | `--uuif-border-secondary` | `--uuif-text-secondary` |
| Primary | `--uuif-surface-primary` | none | `--uuif-text-contrast` |
| Danger | `--uuif-brand-red` | none | `--uuif-text-contrast` |
| Disabled | `--uuif-surface-disabled` | `--uuif-border-disabled` | `--uuif-text-disabled` |

Footer action order (right-aligned): `[Cancel]` `[Save]` `[Save As]`

---

## Input / Text Field

- Height: 29px · Padding: `0 12px` · Radius: `--uuif-radius-6`
- Background: `--uuif-surface-container` · Border: `--uuif-border-tertiary`
- Focus: border → `--uuif-border-secondary` · Error: border → `--uuif-brand-red`
- Label: 150px wide, right-aligned, semibold 13px, 20px gap to control
- Required asterisk: `#d53326` · Chevron (dropdown): `--uuif-text-secondary`, 10px

---

## Checkbox

- Size: 19×19px · Radius: `--uuif-radius-4`
- Checked: `--uuif-brand-orange` fill, white ✓
- Unchecked: white fill, `--uuif-border-secondary` border

---

## Radio Button

- Size: 19×19px circle
- Selected: `--uuif-brand-orange` dot + 1.5px border
- Default: white fill, `--uuif-border-secondary` border

---

## Toggle

- Track: 34×20px, `--uuif-radius-pill` · Knob: 16×16px white circle
- ON: `#a2cd8d` track · OFF: `#8f9aad` track

---

## Drop Menu

- Width: 240px · Border: `--uuif-border-tertiary` · Radius: `--uuif-radius-6` · Shadow: `--uuif-shadow-sm`
- Row height: 36px · Font: 13px
- Default row: `--uuif-surface-container` bg, `--uuif-theme-text-secondary` text
- Selected row: `--uuif-surface-selected` bg, `--uuif-text-hover` text, ✓ tick
- Divider: 0.5px `--uuif-border-transparent`

---

## Slider

- Track: 4px tall, `#c6d1e3` bg, `--uuif-radius-pill` · Fill: `--uuif-border-hover`
- End caps: 12×12px circle
- Value pill: `--uuif-brand-blue` bg, white text, `--uuif-radius-pill`

---

## Icon Sizes

`12 / 16 / 18 / 20 / 24 / 28 / 32 / 48 px` — use closest size, do not interpolate

---

## Tab Bar (Text Tabs)

- Container: `--uuif-surface-container` bg, `--uuif-border-primary` bottom, 20px horizontal padding
- Tab height: 40px · Font: 14px

| State | Style |
|---|---|
| Selected | Bold, `--uuif-text-hover`, top/left/right border `--uuif-border-primary`, `--uuif-radius-6` top corners |
| Default | Regular, `--uuif-theme-text-secondary` |
| Disabled | Regular, `rgba(17,17,17,0.3)`, `cursor: not-allowed` |

---

## Title Pane Variants

| Variant | Size | Weight | Case | Height |
|---|---|---|---|---|
| Section | 14px | 700 | UPPERCASE | 31px |
| Sub | 13px | 700 | UPPERCASE | 32px |
| Card | 14px | 700 | UPPERCASE | 35px |
| Modal | 16px | 700 | UPPERCASE | 45px |
| Panel | 18px | 300 | Sentence case | 51px |
| Popup | 18px | 600 | Sentence case | 46px |

All use `--uuif-text-primary`.

---

## Accordion

- Border: `--uuif-border-primary` top only
- Header: 8px padding, chevron rotates 90° on expand
- Title: 18px weight 300 `--uuif-text-primary`
- Body: 13px `--uuif-text-secondary`

---

## Wizard / Step Indicator

| State | Fill | Label |
|---|---|---|
| Done | `--uuif-brand-green` | ✓ |
| Active | `--uuif-surface-primary` | Step number |
| Pending | `--uuif-border-secondary` | Step number |

- Circle: 28×28px · Connector: 40px wide, 2px tall · Label: 12px `--uuif-text-secondary`
