---
name: snwl-ui-uuif
description: "Consult this skill before generating any SonicWall mockup, component, or prototype. Contains enforcement rules and routes to UUIF 9.2 design system reference files. Trigger whenever a PM requests a screen, flow, component, or UI artifact for any SonicWall product (UM, NSM, WNM, CMC, MSW, CSE, Capture Client, SAMI)."
---

# SonicWall UI Prototyping — Index & Enforcement Rules

> **Design System Version:** UUIF 9.2
> **Canonical variable prefix:** `--uuif-*`
> **Font:** Nunito Sans (always loaded from Google Fonts)

<!-- This file contains 5 sections: Routing, Pre-Generation Checklist, MUST Rules, Gap Protocol, Output Structure -->

---

## How to Use This Skill (Routing)

This skill is split into one index (this file) plus five reference files. Read the files needed for the task — never assume content; always read.

| Task involves... | Read this file |
|---|---|
| Color tokens, status colors, alert fills | `01-tokens-color.md` |
| Spacing, radius, shadow, typography | `02-tokens-foundation.md` |
| Page layout, primary nav, subnav, top bar | `03-components-nav.md` |
| Buttons, inputs, checkboxes, toggles, tabs, wizards, sliders | `04-components-forms.md` |
| Modals, tooltips, popovers, banners, date pickers | `05-components-overlays.md` |
| Dashboard cards, count blocks, data tables, chips, pagination, spinners | `06-components-data.md` |

For a full-page prototype, read all six files. For a single-component task (e.g., a button), read the index plus the one relevant file.

---

## Pre-Generation Checklist

Before producing any output, confirm:

1. This index file has been read in full
2. All relevant reference files (per routing table above) have been read in full
3. The design system version (UUIF 9.2) is noted in the output header block
4. The request can be fulfilled using existing components — if not, follow the Gap Protocol

---

## MUST Rules — Non-Negotiable

### Design System as Source of Truth

- The reference files are the single source of truth — no exceptions
- Never invent tokens, components, or patterns

### Color

- Adhere strictly to the color palette in `01-tokens-color.md`
- Never introduce colors outside the defined tokens — not even for hover states, shadows, or overlays
- Always use `var(--uuif-*)` CSS variables — never hardcode hex values inline
- If a token does not exist for a use case, flag it to the PM rather than inventing one

### Typography

- Use only the typography scale, weights, and line heights in `02-tokens-foundation.md`
- Font family is always `'Nunito Sans', sans-serif` — never default to system fonts
- Include the Google Fonts `<link>` in every HTML file (see `02-tokens-foundation.md`)

### Spacing & Layout

- Apply spacing exactly per `02-tokens-foundation.md`
- Every spacing value must use one of the defined steps: 2, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64 px
- Do not approximate or interpolate between steps

### Component Naming

- Use semantic class names: `uuif-btn`, `uuif-input`, `uuif-modal`, `uuif-chip`, etc.
- Use component names, variants, and states exactly as named in the reference files

### Icon Discipline

- Navigation icons must be copied verbatim from the SVG registry — never substitute Font Awesome, Material Icons, or emoji
- The SonicWall Swoosh logomark always uses `fill="#FF5D00"`
- The SonicWall Wordmark SVG always appears in the SubNav header — never substitute with plain text

---

## Design System Gap Protocol

When a PM's request cannot be fulfilled using existing components, respond with:

> "This pattern does not exist in the current UUIF 9.2 design system. Here are the closest available components: [list them]. Would you like to flag this as a design system gap?"

Never invent new components — surface the gap instead.

---

## Required Output Structure

Every prototype artifact must include a comment header block at the top:

```
/*
  Design System Version: UUIF 9.2
  Reference Files Read: [list which reference files were consulted]
  Component Tokens Used: [list all --uuif-* tokens referenced]
  Components Used: [list all uuif-* components referenced]
  Gaps Flagged: [any patterns that fell outside the system, or "None"]
*/
```

---

## Verification

After reading any reference file, confirm you have received its complete content by checking the section count noted in the file header comment. If sections appear missing, re-read using `view_range` to fetch the dropped portion.
