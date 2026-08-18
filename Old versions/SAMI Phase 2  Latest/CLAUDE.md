# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **UI prototyping workspace** for **SAMI Phase 2** — SonicWall's AI-assisted management intelligence layer for the Unified Manager (UM) platform. All files are standalone HTML prototypes; there is no build system, package manager, or server. Open any `.html` file directly in a browser to preview it.

The primary design deliverable is `sami-page1-dashboard-uuif.html`, which represents the canonical northstar for the SAMI Dashboard Overview page.

## Design System: UUIF 9.2

**All prototypes must conform to UUIF 9.2.** The design system is defined in `snwl-ui-uuif/`:

| File | Contents |
|---|---|
| `SKILL.md` | Routing index + enforcement rules — read first |
| `01-tokens-color.md` | Color tokens, status colors, alert fills |
| `02-tokens-foundation.md` | Spacing, radius, shadow, typography |
| `03-components-nav.md` | Page layout, nav rail, subnav, top bar |
| `04-components-forms.md` | Buttons, inputs, checkboxes, tabs, wizards |
| `05-components-overlays.md` | Modals, tooltips, popovers, banners, date pickers |
| `06-components-data.md` | Cards, count blocks, tables, chips, spinners |

**Non-negotiable rules (from `snwl-ui-uuif/SKILL.md`):**
- Always use `var(--uuif-*)` CSS variables — never hardcode hex values
- Font is always `'Nunito Sans', sans-serif` loaded from Google Fonts
- Spacing must use only the defined steps: 2, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64 px
- Use semantic class names (`uuif-btn`, `uuif-chip`, `uuif-card`, etc.) matching the reference files exactly
- If a required pattern does not exist in the design system, surface it as a gap — do not invent tokens or components

**Before generating any prototype:** read `snwl-ui-uuif/SKILL.md` to confirm which reference files apply to the task, then read those files. For a full-page prototype, read all six reference files.

## Page Layout Architecture

The canonical shell (from `sami-page1-dashboard-uuif.html`) uses a fixed three-panel chrome:

- **Nav Rail** (60 px, fixed left, `z-index: 200`) — primary product navigation, `background: var(--uuif-brand-navy)`
- **SubNav** (266 px, fixed at `left: 60px`, `z-index: 190`) — section navigation and SAMI AI links
- **Top Bar** (46 px, fixed at `left: 326px`, `z-index: 180`) — breadcrumb, tenant selector, icons
- **Page content** (`margin-left: 326px`, `padding-top: 46px`) — scrollable body

All page prototypes must use this exact geometry. Do not alter the fixed widths.

## Prototype File Naming Convention

Active/versioned prototypes follow the pattern:
`sami-page{N}-{screen-name}-{version}-{YYYY-MM-DD}.html`

Files prefixed with `sami-page*` and dated are the working iteration files. Older numbered variants (`01_overview_v*.html`, `02_dashboard_v*.html`) are superseded explorations. The `Finalized folder/` contains locked deliverables.

## Product Context

The EPIC driving this work is defined in `EPIC_UM-MSW_SAMI-Alert-Triage.md`. Key points:

- **Audience:** MSP partners managing 25–75+ tenants on the SonicWall Unified Manager
- **Core feature:** SAMI AI surfaces prioritized alert triage recommendations, sorted by confidence score (High → Medium → Low)
- **Role gating:** SAMI triage panel is MSP-only and feature-flag controlled
- **Data model:** Each alert carries: Alert ID, SAMI confidence score (0.0–1.0), recommended action (Acknowledge / Escalate / Dismiss), triage actor, timestamp, and Tenant ID

The SAMI callout pattern (orange left border on `--uuif-fill-orange-lighter` background) is the visual convention for all AI-generated content across prototypes. It is a design system gap extrapolated from existing tokens — flag if the PM requests variations.

## Data Visualization Tokens

A separate token file `uuif-07-tokens-dataviz.md` covers chart/graph color tokens. Reference it for any prototype containing charts, Sankey diagrams, or data visualizations (e.g., `device-ai-alert-sankey.html`, `uuif-dataviz-test.html`).
