# UUIF 9.2 — SonicWall Unified UI Framework Design System
> Extracted from the compiled stylesheet `style-vAD5gphQ4I.css` of the live SonicPlatform Unified Management web app.
> All values verified against compiled CSS rules. Confidence: high.
> Last updated: May 2026

---

## 0. Foundation

### Root
- `html { font-size: 10px }` → **1rem = 10px** (numeric base for all rem math)
- `body, html { margin: 0; padding: 0 }`
- `* { box-sizing: border-box }`

### Selection
- `::selection { background-color: rgba(255, 93, 0, 0.4) }` — orange 40% alpha

### Scrollbar (webkit)
| State | Value |
|---|---|
| Width / Height | `12px` |
| Track | transparent |
| Thumb | `rgba(112, 162, 235, 0.3)` |
| Thumb hover | `rgba(112, 162, 235, 0.5)` |
| Thumb active | `rgba(112, 162, 235, 0.7)` |
| Border radius | `10px` |
| Dark variant track | `rgba(255, 255, 255, 0.15)` |
| Dark variant thumb | `rgba(255, 255, 255, 0.3)` → hover `0.5` → active `0.7` |

### Links
| State | Value |
|---|---|
| Default | `#47afe8` (sky blue) |
| Hover | `#ff5d00` |
| Text decoration | none, cursor pointer |

---

## 1. Color Tokens

### Brand
| Token | Value | Usage |
|---|---|---|
| `--uuif-brand-navy` | `#001b50` | Nav bg (dark variant), primary text, modal header text, table cell text |
| `--uuif-brand-orange` | `#ff5d00` | Primary CTA, active state, focus ring, checkbox checked, hover color |
| `--uuif-orange-warm` | `#ef7732` | Top nav active, tree-list selected, radio dot |
| `--uuif-orange-active` | `#ff791a` | Datepicker active border |
| `--uuif-orange-light` | `#ffeade` | Row hover, datepicker range fill, datepicker start/end |
| `--uuif-orange-lighter` | `#ffeae3` | Flyout menu item selected bg |
| `--uuif-orange-tint` | `rgba(255, 121, 26, 0.102)` | Tree list item hover/selected bg |

### Semantic / Status
| Token | Value | Usage |
|---|---|---|
| `--uuif-status-success` | `#3ba200` | Status info success, toggle ON, select option check, app nav status dot |
| `--uuif-status-warning` | `#ffaa00` (`#fa0`) | Major severity, warning priority |
| `--uuif-status-error` | `#d50b0b` | Critical/failed status info, feedback down icon |
| `--uuif-status-error-soft` | `#ff4343` | Emergency / critical priority text, alert error text |
| `--uuif-status-info` | `#0071c7` | Secondary alert count, NID type, info priority |
| `--uuif-status-info-bg` | `rgba(0, 113, 199, 0.1)` | Nav item hover bg (light variant) |
| `--uuif-status-info-alt` | `#fea85c` | Alert / error / warning priority cluster |
| `--uuif-priority-medium` | `#c7470c` | Medium priority |
| `--uuif-priority-low` | `green` | Low priority |
| `--uuif-status-sky` | `#47afe8` | Datepicker current day border, link color, nav collapse arrow |

### Surfaces
| Token | Value | Usage |
|---|---|---|
| `--uuif-surface-container` | `#ffffff` | Card bg, modal bg, dropdown bg, popover bg, app content bg |
| `--uuif-surface-bg` | `#f2f5fb` | **App main bg** (sw-app-main), tooltip bg, popover title bg, float actions bg |
| `--uuif-surface-table-header` | `#d4e3f9` | Table header bg, group row bg, markdown table thead |
| `--uuif-surface-row-hover` | `#ffeade` | Table row hover, selected, datepicker range fill |
| `--uuif-surface-contrast` | `#f2f2f2` | Row zebra, tab nav mover bg, modal expand slide border |
| `--uuif-surface-overlay` | `rgba(0, 27, 80, 0.7)` | Modal backdrop, blocking progress |
| `--uuif-surface-overlay-strong` | `rgba(0, 0, 0, 0.8)` | Confirm modal backdrop |
| `--uuif-surface-overlay-nav` | `rgba(0, 27, 80, 0.3)` | Nav overlay (push-menu mode) |
| `--uuif-surface-overlay-light` | `rgba(0, 27, 80, 0.5)` | Section divider dark, nav-item active dark |
| `--uuif-surface-sami` | `#4a618f` | SAMI drawer header bg |
| `--uuif-surface-card-tint` | `rgba(196, 209, 229, 0.6)` | Table group row bg |
| `--uuif-surface-help` | `#f3f7ff` | SAMI chat user message bg |
| `--uuif-surface-guest-checkout` | `#eff6ff` | Guest checkout wrapper bg |

### Text
| Token | Value | Usage |
|---|---|---|
| `--uuif-text-primary` | `#001b50` | Body, headings, table cells, checkbox selected label |
| `--uuif-text-secondary` | `#5a6b8d` | Sub-labels, tooltip text, popover title, dropdown unit |
| `--uuif-text-tertiary` | `#5b6f8d` | Checkbox disabled label (unchecked state), Alert/Notice priority dot |
| `--uuif-text-default` | `#333333` | App default color, button text active, textfield input |
| `--uuif-text-muted` | `#9dafd3` | Modal close, breadcrumb default, flyout menu group color |
| `--uuif-text-muted-2` | `#94a6cb` | Tree list label |
| `--uuif-text-disabled` | `#cccccc` | Disabled label, sw-button disabled icons, tab disabled |
| `--uuif-text-disabled-2` | `#c4d1e5` | Flyout disabled text |
| `--uuif-text-disabled-3` | `#b8c4db` | Button disabled text |
| `--uuif-text-disabled-4` | `#edeff3` | Default button disabled text |
| `--uuif-text-gray` | `#868686` | Icon default, textfield icon, table pagination, select icon |
| `--uuif-text-gray-2` | `#8392a9` | Alert header text, prompt placeholder, V2 collapse arrow |
| `--uuif-text-gray-3` | `#8c9aaf` | App footer left text, toggle OFF bg |
| `--uuif-text-gray-4` | `#999999` | Sliders disabled, table footer total, dark checkbox border |
| `--uuif-text-on-blue` | `#0b1d52` | Auth middleware text |
| `--uuif-text-on-blue-2` | `#061a4d` | Permission modal text |
| `--uuif-text-disabled-nav` | `#5f77a7` | Nav item disabled (dark v2) |
| `--uuif-text-button` | `#5885cc` | Button ghost text/border, footer links |
| `--uuif-text-button-2` | `#5a6b8d` | Default button bg, chat feedback button bg |
| `--uuif-text-breadcrumb` | `#6884bc` | Header breadcrumb (NOT generic link blue) |
| `--uuif-text-link-alt` | `#038af2` | Section divider title v2, header env-name, feedback link |
| `--uuif-text-link-feedback` | `#5885cc` | Alert view section link, footer right links |
| `--uuif-text-link-data` | `#cc0000` | Header queries data (sami) |
| `--uuif-text-on-card-dark` | `#c9c9c9` | Dark mode body text |
| `--uuif-text-on-card-dark-2` | `#cccccc` | Dark mode icon button, dark chip close |
| `--uuif-text-nav-dark` | `#d4e3f9` | Nav item dark variant level-0 text |

### Borders
| Token | Value | Usage |
|---|---|---|
| `--uuif-border-default` | `#c4d1e5` | Slider track, row bottom, table group row top, datepicker border-top, flyout item border |
| `--uuif-border-strong` | `#9dafd3` | Card, popover, tooltip, chip, popover title bottom, tree-list plus trigger |
| `--uuif-border-input` | `#cccccc` | Textfield, select, slider btn border, button disabled border |
| `--uuif-border-light` | `#e4e4e4` | Row border-only variant (bottom + right) |
| `--uuif-border-subtle` | `#eaeaea` | Dropdown unit top border |
| `--uuif-border-checkbox` | `#868686` | Checkbox unchecked, slider btn default border |
| `--uuif-border-warning` | `#ff791a` | Datepicker active month/date border |
| `--uuif-border-dropdown-shadow` | `rgba(0, 0, 0, 0.1)` | Dropdown arrow borders |
| `--uuif-border-card-soft` | `rgba(104, 132, 188, 0.278)` | App content border, app help border |
| `--uuif-border-card-soft-2` | `rgba(104, 132, 188, 0.4)` | Header right divider |
| `--uuif-border-resize-handle` | `rgba(71, 175, 232, 0.5)` | Table column resize handle |
| `--uuif-border-resize-orange-soft` | `rgba(255, 93, 0, 0.3)` | Table sort inactive hover hint |
| `--uuif-border-dot-stroke` | `#2a529e` | App nav status dot border (1.25px) |
| `--uuif-border-tab-disabled` | `#363636` | Tab nav l2 dark border |

### Shadow / Box-shadow tokens
| Token | Value | Usage |
|---|---|---|
| `--uuif-shadow-card` | `0 3px 6px rgba(124, 143, 194, 0.098)` | App header, app content, footer |
| `--uuif-shadow-popover` | `0 10px 10px rgba(0, 0, 0, 0.161)` | Popover board |
| `--uuif-shadow-dropdown` | `0 0 20px rgba(0, 0, 0, 0.35)` | Dropdown inner, modal content, slide panel, table expand slide |
| `--uuif-shadow-tooltip` | `0 1px 3px rgba(0, 0, 0, 0.4)` | Leaflet tooltip |
| `--uuif-shadow-scroll` | `0 3px 10px rgba(157, 175, 211, 0.7)` | Dropdown scroll view |
| `--uuif-shadow-save-dialog` | `0 3px 10px rgba(104, 132, 188, 0.4)` | Save filter dialog |
| `--uuif-shadow-sami-prompt` | `0 0 10px rgba(0, 27, 80, 0.161)` | SAMI prompt textarea |
| `--uuif-shadow-flyout` | `10px 3px 10px rgba(124, 143, 194, 0.098)` | Flyout menu |
| `--uuif-shadow-side` | `-5px 0 10px rgba(0, 0, 0, 0.35)` | Nav inner shadow, table expand slide |
| `--uuif-shadow-fab` | `0 4px 12px rgba(0, 0, 0, 0.25)` | SAMI floating action button |
| `--uuif-shadow-toggle` | `0 0 3px rgba(0, 0, 0, 0.8)` | Toggle thumb |
| `--uuif-shadow-focus` | `0 0 0 1px #ff5d00` | Focus ring (textfield, select, checkbox) |

### Dark Mode
| Token | Value | Usage |
|---|---|---|
| `--uuif-dark-bg` | `#000000` | App dark bg, textarea dark bg |
| `--uuif-dark-surface-1` | `#333333` | Nav cont border (dark), tab dark active bg, avatar default bg, datepicker popup |
| `--uuif-dark-surface-2` | `#515151` | Button dark bg, tab nav mover hover, datepicker hover bg |
| `--uuif-dark-surface-3` | `#1b1b1b` | Textarea dark disabled |
| `--uuif-dark-surface-4` | `#434343` | Disabled bg, button dark disabled, expand slide indi border |
| `--uuif-dark-surface-5` | `#282828` | Bar progress dark base |
| `--uuif-dark-border` | `#7a7979` | Textarea dark border, table footer dark |
| `--uuif-dark-border-2` | `#65656a` | Disabled border, dark dot bg |
| `--uuif-dark-text` | `#c9c9c9` | Dark body text |
| `--uuif-dark-text-2` | `#cccccc` | Dark icon button |
| `--uuif-dark-text-muted` | `#999999` | Dark radio border, disabled text |

---

## 2. Typography

### Font Families (loaded via @font-face)
| Family | Weights | Use |
|---|---|---|
| `Roboto` | 100, 300, 400, 500, 700, 900 (+ italics) | Display, modal titles, breadcrumbs (legacy) |
| `Nunito Sans` | 200, 300, 400, 600, 700, 800, 900 (+ italics) | **Primary UI font** |
| `SonicWallIconFont` | 400 | Icon font (`.sw-font-icon`) |

> Note: Roboto and Nunito Sans are both loaded but Nunito Sans is the primary. Roboto appears mostly in modal headers and legacy components.

### Typography Scale (compiled `.sw-typo-*` classes)
| Class | Font | Size | Weight | Line-height | Use |
|---|---|---|---|---|---|
| `.sw-typo-heading-1` | Nunito Sans | 43px | 400 | 1.4 | Page title (rare) |
| `.sw-typo-heading-2` | Nunito Sans | 36px | 200 | 1.4 | Modal pillar title, large display |
| `.sw-typo-heading-3` | Nunito Sans | 16px | 600 | 1.4 | Section heading |
| `.sw-typo-heading-4` | Nunito Sans | 14px | 700 | 1.4 | Bold body heading |
| `.sw-typo-heading-5` | Nunito Sans | 14px | 400 | 1.4 | Body heading |
| `.sw-typo-default` | Nunito Sans | 13px | **300** | 1.4 | **Default body** (light weight!) |
| `.sw-typo-field-label` | Nunito Sans | 13px | 700 | 1.4 | Form label |
| `.sw-typo-field-value` | Nunito Sans | 13px | 400 | 1.4 | Form input value |
| `.sw-typo-mobile-heading-1` | Nunito Sans | 23px | 400 | 1.4 | Mobile h1 |
| `.sw-typo-mobile-heading-2` | Nunito Sans | 20px | 400 | 1.4 | Mobile h2 |

### Component-specific font sizes
- Table header: `11px / 800 / uppercase`
- Table cell: `12px / 600`
- Tab L1: `14px / 400` (active 400, no weight change)
- Tab L2 dark active: 400 weight (unchanged from default)
- Button: `13px / 400`
- Modal default header: `16px / 200 / uppercase`
- Modal regular-light header: `31px / 400`
- Modal pillar header: `36px / 200`
- App header app-title: `18px / 700`
- App header app-name (alt): `20px / 700`
- App footer: `11px`
- Breadcrumb: `14px / 400`
- Avatar initials: `16px / 400 / uppercase`
- Checkbox label: `13px / 400`
- Section divider: `12px / 400 / uppercase`
- Top nav item label (default): `12px / 400 / uppercase`
- Top nav item label (compact): `14px / 400 / capitalize`

---

## 3. Spacing & Sizing

### Component Heights (compiled values)
| Component | Height |
|---|---|
| Button (all variants) | `29px` |
| Icon button (default) | inherits, with `1px dashed transparent` border |
| Textfield | `29px` |
| Textarea | `109px` (default), min-width `250px` |
| Select | `29px` |
| Header bar (sw-app-header) | `60px` |
| Modal header (default) | `45px` |
| Popover title | `45px` |
| Tab L1 | `40px` |
| Table header cell wrapper | `28px` (renders as 75px with cell wrapping) |
| Table data row | `42px` |
| Table compact row | `29px` |
| Table group row | `30px` |
| Markdown table thead | `30px` |
| Toggle (default) | `40 × 23px` (radius 12px) |
| Toggle (compact) | `28 × 16px` |
| Toggle thumb | `17 × 17px` (default), `12 × 12px` (compact) |
| Avatar | `29 × 29px` |
| Circular button | `52 × 52px` |
| SAMI FAB | `52 × 52px` |
| Badge text | `18px` (min-width 18px, radius 18px) |
| Status dot (app nav) | `10 × 10px` |
| Chip | `25px` h, max-width `150px`, min-width `32px` |
| Checkbox / Radio | `19 × 19px` |
| Slider track | `3px` |
| Slider btn | `11 × 11px` |
| Slider compact mode | (same dimensions) |
| Datepicker month item | `48 × 48px`, line-height `45px` |
| Datepicker date item | `28 × 28px` |
| Datepicker label width | `28px` |
| Timepicker label | `24px` h |
| Bar progress (no-border) | `6px` |
| Bar progress (default) | `7px` |
| Stick progress | `28 × 6px` |
| Modal pillar close | `33 × 33px` (3px white border circle) |
| Modal close icon | `25 × 25px` |
| Nav-side indicator | `16 × 16px` (orange, white 2px border) |
| Status flag | `24 × 24px`, radius 2px |

### Nav Layout
| Element | Value |
|---|---|
| Sidebar collapsed width | `60px` (v2) |
| Sidebar expanded width | `~128px` (flyout-menu left offset) |
| Flyout menu width | `150px` (observed inline) |
| Flyout menu padding | `30px 10px 10px` (collapsed: `7px`) |
| Logo padding | `25px 10px 15px` |
| Logo wrap height | `40px` |
| Logo img width (expanded) | `176px` or `90px` (v2) |
| Logo img width (collapsed) | `40px` |
| Nav item min-height (default) | `71px` |
| Nav item min-height (v2) | `28px`, with `25px` bottom margin |
| Nav item compact | `41px` |
| Nav item level-1 | `29px` |
| Section divider | `23px` min-height, padding `0 10px` |
| Nav mark width (default) | `3px` selected |
| Nav mark width (v2) | `5px` selected |
| Nav side indicator vertical | `-8px` left offset |

### App Shell
| Element | Value |
|---|---|
| `sw-app-main` min-width | `1024px` (no mobile support!) |
| `sw-app-main` bg | `#f2f5fb` |
| `sw-app-main` min-height | `100vh` |
| App content margin | `10px 10px 0` |
| App content height | `calc(100vh - 108px)` |
| App content unauth height | `calc(100vh - 100px)` |
| Header head margin-left | `-40px`, padding `0 20px 0 40px` |
| Header left section min-width | `200px` |
| Header middle section | `width 30%`, transform `translateX(-50%)`, position absolute |
| Footer margin | `12px 10px 0` |

### Component Padding
| Component | Padding |
|---|---|
| Card content default | `10px` |
| Modal body default | `20px` |
| Modal body pillar | `20px 40px` |
| Modal footer default | `0 20px 20px` |
| Modal footer pillar | `0 40px 20px` |
| Status info normal | `20px` |
| Status info small | `10px` |
| Tooltip default | `24px` |
| Tooltip compact | `12px` |
| Popover content | `20px` (or 0 with no-padding) |
| Datepicker dates | `10px 15px` |
| Timepicker | `0 10px 20px` |
| Tab page inner | `20px` (or 0 with no-padding) |
| Tab L1 padding | `0 20px` |
| Slide panel | `20px` |
| Confirm modal width | `529px` |
| Auth layout max-width | `400px` |
| SAMI container max-width | `1100px` |
| SAMI prompt textarea | `8px 10px` |

---

## 4. Border Radius

| Token | Value | Usage |
|---|---|---|
| `--uuif-radius-2` | `2px` | Chip arrow, status flag, table float actions, timepicker, slider bar |
| `--uuif-radius-3` | `3px` | Textfield, select, chip, checkbox box, dropdown corners, app help |
| `--uuif-radius-4` | `4px` | Bar progress base |
| `--uuif-radius-5` | `5px` | Dropdown, tree-dropdown-select-pro |
| `--uuif-radius-6` | `6px` | Card, modal, popover, tab nav mover (right side only) |
| `--uuif-radius-10` | `10px` | Scrollbar thumb, app content, save filter dialog, SAMI box, prompt textarea, scroll-view scrollbar thumb |
| `--uuif-radius-12` | `12px` | Toggle |
| `--uuif-radius-13` | `13px` | Alert dot, tree-list plus trigger |
| `--uuif-radius-15` | `15px` | Default button (pill) |
| `--uuif-radius-18` | `18px` | Badge text, feedback button |
| `--uuif-radius-circle` | `50%` | Avatar, radio, modal close button, toggle thumb, slider btn, app nav dot |
| `--uuif-radius-pill` | `100px` | Icon button |

---

## 5. Z-Index Hierarchy (complete map)

| Layer | z-index | Component |
|---|---|---|
| Below base | — | (default 0) |
| 1 | `1` | Tab nav cont, table sort handle, scope select |
| 2 | `2` | Tree-dropdown-select-pro searchbox, header middle section, table expand slide |
| 800 | `800` | Leaflet controls |
| 999 | `999` | Nav overlay (push-menu mode) |
| 1000 | `1000` | Nav inner, flyout menu, slide panel, drag overlay |
| 1001 | `1001` | Nav side indicator |
| 1002 | `1002` | sp-app-nav (highest nav layer) |
| 1500 | `1500` | Modal backdrop & content |
| 1701 | `1701` | Dropdown, popover |
| 1900 | `1900` | Confirm modal |
| 1901 | `1901` | Tooltip |
| 1990 | `1990` | Blocking progress |
| 18999 | `18999` | SAMI floating action button |
| 19000 | `19000` | SAMI drawer |
| 19001 | `19001` | App help iframe |

---

## 6. Animation & Transitions

### Standard transitions
| Use | Duration | Easing |
|---|---|---|
| Fade enter | `0.15s` | ease-out |
| Fade leave | `0.05s` (50ms) | ease-out |
| Tooltip fade enter | `0.25s` | ease-out |
| Tooltip fade leave | `0.05s` | ease-out |
| List fade | `0.25s` | (default) |
| Slide right/left in-out | `0.1s` | (default) |
| Scroll-view fade | `0.2s` | ease-out |
| Modal slide-down | `0.1s` | ease-out |
| Modal fold-open | `0.2s` | ease-out (close: 0.3s ease-in-out reverse) |
| Transition expand h/v | `0.15s` | ease-out |
| Nav slide width | `0.15s` | ease-out |
| Tab nav indicator | `0.2s` | ease-out (left + width) |
| Tab nav cont scroll | `0.2s` | ease-out (transform) |
| Tab arrow expand | `0.2s` | ease (transform) |
| Tab mover bg/color | `0.1s` | ease |
| Bar progress | `0.15s` | ease (width) |
| Slider bar | `0.1s` | ease-out (width) |
| Slide panel | `0.4s` | ease-out (translate) |
| Sami prompt textarea | `0.15s` | ease-in-out |
| Sami FAB | `0.15s` | ease-in-out |
| Datepicker hover | (no transition; instant) |

### Keyframes
| Name | Spec |
|---|---|
| `sw-modal-slidedown` | 0%: opacity 0 + translateY(-70px) → 100%: opacity 1 + translateY(0) |
| `sw-modal-fold-open` | 0%: scaleX(0) → 100%: scaleX(1) |
| `sw-slidedown-right` | 0%: opacity 0 + translateX(100px) → 100%: opacity 1 |
| `sw-slidedown-left` | 0%: opacity 0 + translateX(-100px) → 100%: opacity 1 |
| `sw-slidedown-top` | 0%: opacity 0 + translateY(-50px) → 100%: opacity 1 |
| `sw-slidedown-bottom` | 0%: opacity 0 + translateY(50px) → 100%: opacity 1 |
| `sw-spinning-progress__animation` | 0/39/100%: opacity 0; 40%: opacity 1 (0.9s ease-in-out infinite both) |
| `spin` (SAMI loading) | 0 → 1 turn rotation (4s linear infinite) |
| `sami-spin-98f868d8` | rotate(1turn) at end (4s linear infinite) |
| `blink` (chat loading dots) | 0%: 0.3 → 50%: 1 → 100%: 0.3 opacity (1.4s infinite) |

---

## 7. Component Specifications

### Buttons (`.sw-button`)
| Property | Default (ghost) | --default (filled) | --secondary | --dark | --disabled |
|---|---|---|---|---|---|
| Background | `#ffffff` | `#5a6b8d` | `#5885cc` | `#515151` | (inherit) |
| Border | `1px solid #5885cc` | none | none | `1px solid #ff5d00` | `1px solid #c4d1e5` |
| Color | `#5885cc` | `#ffffff` | `#ffffff` | `#cccccc` | `#b8c4db` |
| Border-radius | `15px` | `15px` | `15px` | `15px` | `15px` |
| Height | `29px` | `29px` | `29px` | `29px` | `29px` |
| Min-width | `100px` | `100px` | `100px` | `100px` | `100px` |
| Padding | `0 20px` | `0 20px` | `0 20px` | `0 20px` | `0 20px` |
| Font | `13px / 400 / Nunito Sans` | (same) | (same) | (same) | (same) |
| Hover | `#ff5d00` border + text | `#ff5d00` bg, white text | (no change) | white text | (no change) |
| Active | (same as hover) | (same as hover) | (no change) | `#333` text | (no change) |
| `--default:disabled` | — | `#c4d1e5` bg, `#edeff3` text | `#c4d1e5` bg, `#edeff3` text | `#434343` bg, `#001b50` text | — |
| `--dark.--default` | — | `#ff5d00` bg, `#000` text | — | — | — |

### Icon Button (`.sw-icon-button`)
- Border: `1px dashed transparent`, radius `100px` (pill)
- Color: `#868686` → hover `#333` → active border `#ff5d00` + `#333` text
- Selected: `#ff5d00`
- Disabled / divider: `#cccccc`
- Dark: `#cccccc` → hover white → selected `#ff5d00`
- Label font: `14px / 400`, margin-left 5px

### Circular Button (`.sw-circular-button`)
- `52 × 52px`, border `1px solid #868686`, radius 50%
- Hover: `1px solid #ff5d00`, color `#333`
- Active: bg `#ff5d00`, color `#333`
- Disabled: bg `#f2f2f2`, border + color `#cccccc`
- Text: `#333`, `14px / 400 / uppercase`, padding `6px 10px`

### Textfield (`.sw-textfield`)
- `29px` h, `180px` w default (or `100%` with `--full`)
- Border: `1px solid #cccccc`, radius `3px`, bg white
- Focus: `#ff5d00` border + `0 0 0 1px #ff5d00` shadow, no outline
- Hover: `#ff5d00` border
- Disabled: bg `#f2f2f2`, cursor not-allowed, input text `#999`
- Input: `#333`, padding `0 10px`, transparent bg
- Icon prefix/suffix: `29px` w, color `#868686` → focus `#ff5d00`
- Dark: transparent bg, `#999` border, `#c9c9c9` text → disabled `#434343` bg + `#65656a` border
- Display variant: no border, no padding (read-only display mode)

### Textarea (`.sw-textarea`)
- `109px` h, `250px` min-w
- Same colors as textfield; padding `10px`, resize none
- Dark: `#000` bg, `#7a7979` border → disabled `#1b1b1b` bg + `#434343` border

### Select (`.sw-select`)
- `29px` h, `180px` w
- Border `1px solid #cccccc`, radius `3px`, padding-left `10px`
- Focus / hover: `#ff5d00` border (+ focus shadow)
- Selected option: orange `3px` left border, `#ff5d00` text, padding-left `7px`
- Option check icon: `#3ba200`
- Icon: `29px` w, `#868686` → active `#ff5d00`
- Placeholder: `#999`
- Label prefix: 700 weight, margin-right 5px
- Dark: transparent bg, `#999` border, `#c9c9c9` text
- Dark placeholder: `#001b50` (intentional inversion)
- Auto-height variant: `min-height: 29px`

### Checkbox (`.sw-checkbox`)
- Box: `19 × 19px`, radius `3px`
- Unchecked: white bg, `1px solid #868686` border
- Checked: `#ff5d00` bg, white checkmark
- Focus: `1px solid #ff5d00` + `0 0 0 1px #ff5d00` shadow
- Hover: `1px solid #ff5d00`
- Disabled: `#c4d1e5` bg, `#cccccc` border, white check
- Label: `13px / 400`, margin-left `10px`
- Selected label color: `#001b50`
- Disabled-label (default): `#5b6f8d`
- Disabled label (when --disabled): `#cccccc`
- Margin-top: `5px`, vertical-align text-bottom
- Dark: transparent bg, `#999` border → hover `#cccccc`
- Dark disabled: `#434343` bg, `#65656a` border + color

### Radio (`.sw-radio`)
- Circle, `19 × 19px`, border `1px solid #9dafd3`
- Inner dot: `11 × 11px`, `#ef7732` (warm orange), top/left 3px
- Hover: border `#ef7732`
- Checked border: `1px solid #ef7732`
- Disabled: bg `#f2f2f2`, border `#cccccc`, dot `#cccccc`
- Label: `13px / 400`, margin-left `10px`, color `#333`
- Dark: `#999` border → hover `#cccccc`
- Dark disabled: `#434343` bg, `#65656a` border + dot

### Toggle (`.sw-toggle`)
- `40 × 23px`, radius `12px`
- ON: `#3ba200` bg
- OFF: `#8c9aaf` bg
- Disabled: `#c4d1e5` bg + opacity 0.4
- Thumb: `17 × 17px`, white, radius `9px`, shadow `0 0 3px rgba(0,0,0,0.8)`
- Thumb position: left `20px` (ON), `3px` (OFF)
- Compact: `28 × 16px`, thumb `12 × 12px`
- Compact thumb position: left `14px` (ON), `2px` (OFF)
- Transition: bg `0.2s ease-out`, thumb position `0.2s ease-out`

### Tabs (`.sw-tab`)
| Property | Default | --active | --l2 | --l2 active | --vertical | --dark |
|---|---|---|---|---|---|---|
| Height | `40px` | `40px` | auto | auto | auto | (inherits) |
| Padding | `0 20px` | `0 20px` | `0` | `0` | (inherits) | (inherits) |
| Color | `#5a6b8d` | `#ff5d00` | `#5a6b8d` | (depends on indicator) | (inherits) | `#868686` |
| Border | `1px solid transparent` | `#ff5d00 #ff5d00 #ffffff` | none | transparent | `1px solid transparent` | (inherits) |
| Background | (transparent) | `#ffffff` | (initial) | initial | (inherits) | (inherits) |
| Radius | (none) | `6px 6px 0 0` | (none) | (none) | `6px 0 0 6px` | (inherits) |
| Margin | (first) | (first) | `margin-left: 40px` (between) | (same) | `margin: 0` (between) | (inherits) |
| Hover | `#ff5d00` color | (current) | `#ff5d00` color | (current) | (inherits) | white color |
| Dark active | — | — | — | — | — | `#333` bg, `#fff` color |

### Tab Nav lines (L2 indicator)
- L2 base line: bg `#cccccc`, 1px h, top -1px
- L2 indicator: bg `#ff5d00`, 3px h, radius 2px, transition `0.2s ease-out` (left + width)
- L2 hover indicator: bg `#cccccc`, same shape
- Dark L2 base: `#363636`

### Tab Nav L1 arrow (active tab indicator)
- Width: 0, border 15px solid transparent, border-bottom 15px #ff5d00 (upward arrow)
- Ghost (inner white): border-bottom 15px #fff, offset top 1px left -15px
- Position: absolute top -15px, transition `left 0.2s ease-out`

### Tab Nav mover (overflow scroll buttons)
- Width: 20px, border-bottom `1px solid #ff5d00`
- Inner: bg `#f2f2f2`, radius `0 6px 6px 0`, cursor pointer
- Hover: bg `#515151`, color `#c9c9c9`
- Forward variant: transform `rotate(180deg)`
- L2 border-bottom: `#cccccc`
- Dark L2: `#363636`
- Dark mover hover: bg `#cccccc`, color `#333`

### Table (`.sw-table`, `.sw-table-row`, `.sw-table-header`)
**Header**
- Bg: `#d4e3f9`
- Cell: border `1px 1px 0` solid transparent (becomes visible on hover), padding `0 10px`, text `#001b50`, font `11px / 800 / uppercase`
- Sort icon container: hidden by default (display none), shown on cell wrapper hover
- Sort active: `#ff5d00` (asc rotate 0deg, desc rotate 180deg)
- Sort inactive hover: `rgba(255, 93, 0, 0.3)`
- Adjust handle: `rgba(71, 175, 232, 0.5)` bg, 10px w, 3.5px transparent border (top/bottom none), cursor col-resize, position absolute right -5px
- Dark header bg: `rgba(242, 242, 242, 0.1)`
- Dark cell border: `rgba(255, 255, 255, 0.2)`, text `#c9c9c9`

**Row**
- Bg: `#ffffff`, height `42px`, cursor pointer
- Hover: `#ffeade`
- Contrast (zebra): `#f2f2f2`
- Selected: `#ffeade`
- Cell border-bottom: `1px solid #c4d1e5`
- Cell: `12px / 600`, `#001b50`, padding `0 10px` (wrapper)
- Compact: `29px` h
- Auto: min-height `29px`
- Border variant: bottom + right `1px solid #e4e4e4`
- Indi (left edge indicator): `3px` w, `#ff5d00`, visibility hidden by default
- Dragging: opacity 0.5, pointer-events none
- Float actions: `#f2f5fb` bg, `1px solid #9dafd3` border, radius 2px, height 29px, position absolute top/bottom 0, margin-right 10px

**Group row**
- Bg: `rgba(196, 209, 229, 0.6)`, height `30px`
- Border-top: `1px solid #c4d1e5`
- Second+ group row: border-top `#999`
- Trigger transition: 0.2s ease (rotate)

**Expand slide**
- Bg white, border-bottom + right `1px solid #f2f2f2`
- Shadow: `-5px 0 10px rgba(0,0,0,0.35)`
- Position: absolute right 0, z-index 2
- Indi (badge): `13 × 13px`, `#ff5d00` bg, `1px solid #434343` border, circle, left -7px

**Insert caret (drag indicator)**
- Bg `#ff5d00`, 2px h, margin-top -1px, pointer-events none, z-index 2

**Pagination**
- Inner: 26px h
- Dropdown: `26 × 26px`, color `#868686` → hover `#333` → active `#ff5d00`
- Slider: 240px w

**Column resizer**
- Bg `#ff5d00`, 10px w, 3.5px transparent border (no top/bottom), cursor col-resize, z-index 2

### Modals (`.sw-modal`)
**Backdrop**
- Bg: `rgba(0, 27, 80, 0.7)`, z-index 1500, position fixed, overflow auto

**Content**
- Radius 6px, shadow `0 0 20px rgba(0, 0, 0, 0.35)`, max-height 100%
- Position fixed top 0 left 0
- z-index 1500 (same layer as backdrop)
- Resizable variant: overflow hidden + resize both

**Header (default)**
- Bg white, radius `6px 6px 0 0`
- Color `#001b50`, font Nunito Sans, `16px / 200 / uppercase`
- Height `45px`, padding `0 10px 0 20px`
- Draggable: cursor move
- Status-mode variant: padding 0, height auto, no uppercase

**Header (pillar variant)**
- Bg white, radius 0, color `#001b50`
- Font `36px / 200`, no uppercase
- Padding `40px 40px 0`

**Header (regular-light variant)**
- Border `1px solid #7a7979` on content
- Bg white, color `#001b50`
- Font `31px / 400`, no uppercase
- Padding `10px 20px 0`

**Close icon**
- Color `#9dafd3`, `25 × 25px`, cursor pointer
- Hover/active: same color (no state change)

**Pillar close**
- Bg `#5a6b8d`, `3px solid #fff` border, circle, white icon
- `33 × 33px`, position relative, left `23.5px` (offset into header)

**Regular-light close**
- Same as pillar but left `3.5px`

**Body**
- Bg white, radius `0 0 6px 6px`
- Padding `20px` (default), `20px 40px` (pillar)
- Overflow hidden + auto y

**Footer**
- Padding `0 20px 20px` (default), `0 40px 20px` (pillar)

**Animations**
- Slide enter: 0.1s ease-out (from translateY -70px + opacity 0)
- Fold enter: 0.2s ease-out (scaleX 0 → 1)
- Slide leave: same in reverse
- Fold leave: 0.3s ease-in-out reverse

### Confirm Modal (`.sw-confirm-modal`)
- Bg: `rgba(0, 0, 0, 0.8)` (stronger than regular modal)
- Width: `529px`
- Z-index: 1900 (above modal layer)
- Dialog radius: `0 0 6px 6px` (bottom corners only)
- Footer: white bg, padding `20px`

### Tooltip (`.sw-tooltip`)
- Z-index 1901, position absolute
- Color `#5a6b8d`, font weight 400
- Inner: bg `#f2f5fb`, `1px solid #9dafd3`, radius 3px, padding 24px
- Arrow: `15 × 15px`, bg `#f2f2f2`, two-side border matching parent
- Compact: padding 12px, arrow `7.5 × 7.5px`
- No-padding variant: inner padding 0

### Popover (`.sw-popover`)
- Z-index 1701, position absolute
- Color `#5a6b8d`
- Board: white bg, `1px solid #9dafd3` border, radius 6px, shadow `0 10px 10px rgba(0,0,0,0.161)`
- Title: bg `#f2f5fb`, border-bottom `1px solid #9dafd3`, color `#5a6b8d`, font `16px / 200 / uppercase`, height `45px`, padding `10px 10px 10px 20px`
- Title close: `#9dafd3`, `25 × 25px`
- Content padding: 20px (or 0 with no-padding)
- Arrow: 15px solid transparent, side color `#9dafd3`

### Dropdown (`.sw-dropdown`)
- Z-index 1701, radius 5px, color `#c9c9c9` (anomaly — applied to scrollbar parent, units override)
- Scroll-view shadow: `0 3px 10px rgba(157, 175, 211, 0.7)`
- Inner: bg white, radius `0 0 3px 3px` (bottom only!), shadow `0 0 20px rgba(0,0,0,0.35)`
- Arrow: `16 × 16px`, white bg, `1px solid rgba(0,0,0,0.1)` borders

### Dropdown Unit (`.sw-dropdown-unit`)
- Border-top `1px solid #eaeaea`, first child no border
- Color `#5a6b8d`, font `13px / 400 / Nunito Sans`
- Min-height 29px, min-width 60px, padding `0 10px`
- Hover/highlight: bg `rgba(207, 207, 207, 0.15)`, color `#ff5d00`
- Selected: border-left `3px solid #ff5d00`, color `#ff5d00`, padding-left `7px`
- Disabled: color `#c4d1e5`, cursor not-allowed
- Divider: bg `#ff5d00`, 2px h (creates section break)

### Chip (`.sw-chip`)
- Bg `#f2f5fb`, `1px solid #9dafd3`, radius 3px
- Color `#5a6b8d`, font weight 400
- Height 25px, max-width 150px, min-width 32px, padding `0 10px`
- Hover: border `#ff5d00`
- Close: `#5a6b8d`, margin-left 5px
- Dark: `#515151` bg, `#c9c9c9` color, no border on hover
- Dark close: `#cccccc` → hover white

### Avatar (`.sw-avatar`)
- `29 × 29px`, circle, bg `#333`, color white
- Border `1px dashed transparent`
- Clickable hover: color `#ff5d00`
- Clickable active: border-color `#ff5d00`, background-clip content-box
- Selected: bg `#ff5d00`, color `#000` (orange + black, no hover change)
- Image variant: border-style dashed on click, solid when selected
- Initials: `16px / 400 / uppercase`

### Slider (`.sw-slider`)
- Btn (end arrows): `11 × 11px` circle, white bg, `1px solid #333` border
- Btn hover: bg `#333` cursor pointer
- Btn active: bg `#ff5d00`
- Btn disabled: bg `#e4e4e4`, border `#999`
- Track: `#c4d1e5`, 3px h, radius 2px
- Bar: 3px h, radius 2px, transition `width 0.1s ease-out`
- Thumb default: `#001b50` bg, radius 10px, outline 0
- Thumb circle: `#ff5d00` bg, 50% radius, 14px font, white text
- Thumb plain: white bg, `1px solid #ff5d00` border, hover bg `#333`
- Thumb colored: white text
- Vertical variant: min-height 50px, track width 3px
- Dark btn: `#cccccc` bg/border → hover white
- Dark btn disabled: `#65656a` bg, `#001b50` border

### Datepicker (`.sw-datepicker`)
- Popup: bg `#333` (dark by default — usually overridden white in this app)
- Inner: float left, width 228px, text center
- Months: `48 × 48px`, line-height 45px, cursor pointer
- Months hover: bg `#515151`, circle radius, `#c9c9c9` color
- Months active/active-hover: bg `#d4e3f9`, `2px solid #ff791a` border, circle, `#333` color
- Months active (in selecting): bg `#515151`, `2px solid #ff791a` border
- Dates: `2px solid #fff` border default
- Date hover: bg `#515151`, circle, `#c9c9c9`
- Date current: bg `#515151`, `2px solid #47afe8`, circle
- Date active: bg `#d4e3f9`, `2px solid #ff791a`, circle
- Date same-dates-selected: bg `#ffeade`, circle
- Date start/end: bg `#ffeade`, `2px solid #ffeade`, half-circle radius
- Date range fill: bg `#ffeade`, `2px solid #ffeade`, radius 0
- Date disabled: `#9dafd3` color + line-through
- Date gray: `#9dafd3`
- Date hidden: visibility hidden
- Btn active: bg `#ff5d00`, circle
- Monthview/yearview/dates: bg white, padding `10px 15px`
- Weeks: bg white, padding `4px 15px`
- Monthview: padding-bottom 0

### Timepicker (`.sw-timepicker`)
- Bg white, radius 2px, border-top `1px solid #c4d1e5`
- Padding `0 10px 20px`
- Header: `#001b50`, margin `10px 2.5%`
- Pane: margin `0 2.5%`, width 40% (or 95% single)
- Divider: width 42.5% (or 95% single)
- Label: bg/color `#9dafd3`, radius 3px, height 24px

---

## 8. Navigation

### sw-nav (root)
- Background white (light), `#001b50` (dark)
- Min-height 100%, position relative, overflow visible

### Nav inner
- Z-index 1000
- Overlay z-index 999, bg `rgba(0, 27, 80, 0.3)`, cursor pointer
- Inner shadow: `-5px 0 10px rgba(0,0,0,0.35)` on right edge

### Nav slide (animated transitions)
- Height 100%, overflow hidden
- Transition `width 0.15s ease-out`

### Nav cont
- Border-left: 5px solid `#ffffff` (default), `#333` (dark)
- V2: no border-left

### Nav side (with indicator)
- Side indicator: `16 × 16px`, bg `#ff5d00`, `2px solid #fff` border, radius 50%
- Vertical: left -8px, transition `top 0.2s ease`
- Horizontal: top -8px, transition `left 0.2s ease`
- z-index 1001

### Nav logo
- Padding `25px 10px 15px`
- Wrap: 40px h, with `40px` collapsed margin-top -10px
- Image: 176px w default, 90px w v2, 40px w collapsed
- Subtitle: `#ff5d00`, `12px / 700`, margin-top 3px, centered
- "Unified Management" 2-line text injected via `::before` content

### Nav v2 collapse trigger
- Position fixed, `24px × 40px`, radius `0 3px 3px 0`, z-index 1
- Arrow color `#8392a9` (NOT the sky blue of default)
- Collapsed left: `35px` (expanded left `106px`)
- Transition `transform 0.4s ease-out`

### Nav item (sw-nav-item)
| Variant | Border-top | Color | Min-height | Font | Inner padding |
|---|---|---|---|---|---|
| Default | `1px solid #f2f2f2` | (inherits) | `71px` | (inherits) | `0 15px` |
| V2 | none | `#d4e3f9` | `28px` (+25px mb) | (inherits) | `0 5px` |
| Compact | (default) | (inherits) | `41px` | `13px / 400` | (inherits) |
| Compact L1 | none | `#001b50` | `24px` | `12px / 400` | (inherits) |
| Level-1 | none | (inherits) | `29px` | `14px / 200` | (inherits) |
| Dark | `#001b50` | `#d4e3f9` (L0) / `#c9c9c9` (L1) | (inherits) | (inherits) | (inherits) |

**States (dark variant):**
- Active: bg `rgba(0, 27, 80, 0.5)`, color `#ff5d00`
- Hover: bg `rgba(0, 27, 80, 0.5)`, color `#ff5d00`
- Level-0 hover: bg `#001b50` (override)
- Level-1 hover: color `#ff5d00`
- V2 disabled: color `#5f77a7`, cursor not-allowed

**Mark (selection indicator):**
- Default: width 0, transition `width 0.15s ease-out`
- Selected: width `3px`
- V2 selected: width `5px`, bg `#ff5d00 !important`

### Nav flyout menu (sw-nav-flyout-menu)
- Bg white, shadow `10px 3px 10px rgba(124, 143, 194, 0.098)`
- Position fixed, top 0, left `128px` (or `60px` collapsed)
- Height 100vh, padding `30px 10px 10px` (or `7px` collapsed)
- Z-index 1000
- Title: `#001b50`, `16px / 700 / uppercase`
- Logo: padding-top 10px
- Logo wrap: 50px h, img 128px w
- Logo subtitle: `#ff5d00`, `12px / 500`, margin-top -7px, left-aligned

**Flyout item**
- Border-bottom `1px solid #c4d1e5` (last child none)
- Color `#9dafd3`, font `13px / 400`
- Padding `10px 0 10px 5px`
- Hover: color `#ff5d00`
- Selected: bg `#ffeae3`, color `#ff5d00`, text `#ff5d00`
- Text: `#001b50`, 155px width
- Disabled text: `#c4d1e5`, cursor not-allowed
- Level-1 (non-collapsed): margin-left 24px
- Level-1: no border, `12px / 300`, padding `5px 0 5px 5px`, mb 7px

**Flyout group**
- Border-bottom `1px solid #c4d1e5`, first child padding-top 15px
- Color `#9dafd3`
- Head: padding `7px 0 7px 5px`
- Head hover: bg `#ffeae3`, color `#ff5d00`
- Caret: `#001b50`, margin-right 10px
- Text: `#001b50`, `13px / 500`, 155px w
- Selected: color `#ff5d00`

### Nav section divider
- `12px / 400 / uppercase`, min-height 23px, padding `0 10px`
- Dark: bg `rgba(0, 27, 80, 0.5)`, border-top `#515151`
- Dark V2: bg unset, border-top `rgba(255, 255, 255, 0.4)`, margin `10px 15px`
- V2: border-top `1px solid rgba(255, 255, 255, 0.4)`, `font-weight: 700`, margin `20px 10px 10px`
- Title V2 color: `#038af2` (sky blue — NOT white)

### Top Nav Item
- Color `#001b50`, cursor pointer
- Label: `16px`, uppercase, padding `0 20px 0 10px`
- Selected: `#ef7732`, 700 weight
- Disabled: `#001b50`, 500, opacity 0.25, cursor not-allowed
- Hover: `#ef7732`
- Dim: opacity 0.58
- Default variant label: `12px / 400 / uppercase`
- Compact variant label: `14px / 400 / capitalize`

### Nav dropdown (sw-dropdown when triggered from nav)
- Inner z-index 1701

### Tree List (`.sw-tree-list`, `.sw-tree-list-item`)
- Plus trigger: bg white, `1px solid #9dafd3`, color `#9dafd3`, `13px / 700`, `13 × 13px`
- Plus trigger selected: border + color `#ef7732`
- Vertical line: `2px dashed #9dafd3`
- Horizontal line: `2px dashed #9dafd3`, 10px w
- Item: cursor pointer, min-height 30px
- Item hover/selected: bg `rgba(255, 121, 26, 0.102)` (light orange tint)
- Item mark: 3px width, bg `#ff5d00`, full-height left
- Label: `#001b50`, `14px / 400`
- Label hover/selected: `#ef7732`
- Pre (icon area): `#9dafd3`, hover `#ef7732`
- Extra cont: `#001b50`, 500 weight, hover `#ef7732`

### Scope Selector Tree Dropdown (`.sp-tree-dropdown-select-pro`)
- Border `1px solid #cccccc`, radius 5px
- Width var: `--2a80da86` (340px observed inline)
- Search width var: `--d85a93c6` (220px observed inline)
- Height var: `--07ac08a0` (40px observed inline)
- Active state: border `#ff5d00`, placeholder opacity 1
- Hover/focus: border `#ff5d00`, shadow `0 0 0 1px #ff5d00`
- Disabled: bg `#f2f2f2`, `#cccccc` border, `#c4d1e5` color
- Searchbox: `#001b50`, `14px / 700`, position absolute z-index 2
- Placeholder: `#5a6b8d`, `13px`, opacity 0 (shown on focus)
- Partition divider: bg `#cccccc`, 22px h, 1px w, margin-right 7px
- Clear icon: position absolute right 35px top 7px → hover `#ff5d00`
- Arrow: position absolute right 10px top 5px

### App Header (`.sw-app-header`)
- Height `60px`, position relative
- Bg white, shadow `0 3px 6px rgba(124, 143, 194, 0.098)`
- Margin-left `-40px`, padding `0 20px 0 40px`
- Left section: min-width 200px
- Middle section: position absolute, width 30%, transform `translateX(-50%)`, z-index 2
- Right section: justify flex-end

**Header text styles:**
- App title: `#ff5d00`, `18px / 700`, padding `0 20px`
- Env name: `#038af2`, `16px / 700 / uppercase`, margin-left 7px
- App name (alt): `#ef7732`, `20px / 700`, margin-top 7px, padding `0 20px 0 18px`
- App version: `#5b6f8d`, `13px`, position absolute right -25px top -10px
- Logo wrap: `30px` h, margin-left 10px, margin-top 10px
- Logo img: 176px w, no border

**Header actions:**
- Avatar container: `#001b50`, margin-left 12px
- Avatar name: `14px / 700`
- Avatar role: `13px / 500`
- Avatar hover: `#ff5d00`
- Action item: `#9dafd3` → hover `#333` → active `#ff5d00`
- Action bar item: 60px h
- Ellipsis indicator: `#6884bc`, `14px / 400`

**Header breadcrumbs:**
- Color `#6884bc` (header-specific, NOT generic link blue)
- Standard sw-breadcrumb: `#9dafd3` default
- Clickable hover: `#5a6b8d`
- Active item: `#5a6b8d`
- Item icon / slash / text padding-left: 8px (4px after icon)

### App Footer (`.sw-app-footer`)
- Font-size: 11px
- Margin: `12px 10px 0`
- Left text: `#8c9aaf`, span margin-left 7px
- Right links: `#5885cc`, margin-right 15px (last child 0)

### SAMI Drawer / FAB
**FAB (`.sw-app-main__sonicbot-fab`)**
- Position fixed, bottom 70px, right 10px, z-index 18999
- Circular button override: bg `#ff5d00`, border `#ff5d00`, color white
- Size: `52 × 52px`
- Shadow: `0 4px 12px rgba(0, 0, 0, 0.25)`
- Hover: bg `#d65600`, border `#d65600`
- Active: bg `#cc5200`, border `#cc5200`

**Drawer (`.sp-app-sami-drawer`)**
- Position fixed, full viewport, z-index 19000, pointer-events none
- Inner panel: position fixed right 0, full height, pointer-events all
- Header: bg `#4a618f`, `1px solid #ccc` bottom border, white text, 60px h
- Header title: `14px / 700`, color white
- Brand icon: margin-right 8px
- Body: flex column, padding-bottom 28px

---

## 9. Structural Patterns

### App Shell
```
.sw-app (light variant default)
  bg: #ffffff
  color: #333333
  height: 100vh (v2)

  └── .sw-app__view (flexbox row, overflow hidden)
        ├── .sw-app__nav-scrollview (margin-right -8px)
        │     └── .sw-nav--dark--v2 (60px collapsed)
        │           ├── .sw-nav__logo
        │           ├── .sw-nav__list (sw-nav-item × n)
        │           └── .sw-nav-flyout-menu (position fixed, left: 60px or 128px)
        └── .sw-app__main
              ├── .sw-app__header (.sw-app-header, 60px h)
              │     ├── breadcrumb (.sw-breadcrumb)
              │     ├── scope selector (.sp-ftr-scope-selector)
              │     └── action bar (.sw-action-bar-item × n)
              └── .sw-app__content--scroll (overflow auto)
                    └── .sp-app-content
                          ├── .sp-app-content__crumbs
                          └── .sp-app-content__content
                                └── [Qiankun micro-app] → SonicPlatform Console
  └── .sw-app-footer (12px 10px 0 margin)
```

### Card Composition (.sw-card-view) — observed inline
```
.sw-card-view
  border: 1px solid #9dafd3
  border-radius: 6px

  ├── .sw-card-view__header-cont
  │     └── .sw-card-view__header (30px h)
  │           ├── .sw-card-view__pretext-cont (icon, #9dafd3)
  │           ├── .sw-card-view__title-cont (14px/700, #001b50, uppercase)
  │           └── .sw-card-view__action-cont
  └── .sw-card-view__content-cont (padding: 10px)
```

### Inverted Navy Card (Org Summary)
- Bg `#001b50`, white text
- Metric: `22px / 700` white
- Subtle dividers: `0.1px solid rgba(125, 147, 192, 0.4)`

### Dashboard Page Structure
```
.dashboard-page
  ├── .dashboard-page__overview (margin-bottom 10px)
  │     ├── .alerts-overview (carousel of product cards)
  │     │     └── .alerts-overview__card (201px w, 162px min-h)
  │     └── .msp-tenant-summary (org summary navy card, 220px w)
  └── main
        └── .notification-section
              ├── .content-toolbar (filter + search + slider)
              ├── .sw-tab-group (L2 tabs: Firewalls | APs | Switches | Capture Client)
              └── .sw-table
```

---

## 10. Icon System

### Font
- Family: `SonicWallIconFont` (custom icon font)
- Format: woff2, woff, ttf, eot, svg
- Source: `/static/fonts/SonicWallIconFont-EzyCa9dfPG.*`

### Selector pattern
```css
.sw-font-icon { font-family: SonicWallIconFont !important; }
.icon-{name}::before { content: "\unicode"; }
```

### Icon naming conventions
| Prefix | Use |
|---|---|
| `.icon-*` | Standard UUIF icons (search, close, arrow-*, checkmark, etc.) |
| `.icon-cybage-*` | SonicWall product-specific (dashboard, inventory, firewalls, capture-client, etc.) |
| `.icon-type*` | Product type icons (typesonicbot, typecloud-secure-edge) |
| `.icon-cs-*` | Cybersecurity service icons |
| `.icon-ns-*` | NS-series firewall family icons |
| `.icon-severity-*` | Severity indicators (critical, high, major, minor, low) |

### Common icon Unicode mappings (verified)
| Class | Unicode | Class | Unicode |
|---|---|---|---|
| `.icon-search` | `\f002` | `.icon-checkmark` | `\ed71` |
| `.icon-close` | `\e002` | `.icon-arrow-up` | `\edc7` |
| `.icon-close-thin` | `\e804` | `.icon-arrow-down` | `\edc4` |
| `.icon-add` | `\ed5d` | `.icon-arrow-left` | `\edc5` |
| `.icon-minus` | `\ed5e` | `.icon-arrow-right-thin` | `\edc6` |
| `.icon-filter` | `\ee8b` | `.icon-info` | `\e094` |
| `.icon-bell` | `\ea2c` | `.icon-help1` | `\ea2a` |
| `.icon-service` | `\ea2b` | `.icon-refresh` | `\e90b` |
| `.icon-export` | `\eec9` | `.icon-cybage-dashboard` | `\ea43` |
| `.icon-cybage-firewalls` | `\ea3e` | `.icon-cybage-inventory` | `\ea40` |
| `.icon-cybage-admin-settings` | `\ea3f` | `.icon-typecloud-secure-edge` | `\ea7c` |

### Icon sizing conventions
| Use | Size |
|---|---|
| Nav (level-0) | `35px` |
| Nav (compact) | `30px` |
| Standard action icon | `20px` |
| Inline / icon-button | `12-16px` |
| Tooltip / micro | `10-11px` |

---

## 11. Anti-Patterns & Issues (Now CSS-verified)

- **Inconsistent typography defaults**: `.sw-typo-default` is `13px / 300` (light) but most component-internal text uses `14px / 400`. The default class is rarely applied to body text in practice.
- **Heavy use of `!important`**: Specifically on `.sw-nav-item__mark--v2`, `.sw-modal__header` (text-transform), inline overrides for datepicker. Suggests cascading conflicts between SPC scoped CSS and UUIF base.
- **Mixed border styles**: Both `1px solid` and `2px solid` used throughout without clear hierarchy. Some elements use 3.5px borders (col-resize handles) for click-target padding.
- **Color naming chaos**: `#5b6f8d`, `#5a6b8d`, `#5885cc`, `#6884bc`, `#8c9aaf`, `#8392a9`, `#9dafd3` are all distinct text/muted colors with overlapping use cases. No semantic naming.
- **Datepicker defaults to dark mode** (`#333` bg, `#c9c9c9` text) and is universally overridden white in this app — wasteful default.
- **No mobile breakpoints**: `sw-app-main { min-width: 1024px }` hard-enforces desktop.
- **Multiple radius values without hierarchy**: 2, 3, 4, 5, 6, 10, 12, 13, 15, 18, 25, 50%, 100px all in use.
- **Z-index gaps**: Jump from 1001 → 1002 → 1500 → 1701 → 1900 → 1901 → 1990. Inconsistent intervals; `19000`-range is reserved for SAMI overlays.
- **Animation timing inconsistency**: Mostly `0.15s / 0.2s / 0.25s ease-out`, but fade-leave uses `50ms` (4x faster than enter) which feels jarring.
- **Roboto + Nunito Sans dual loading**: Roboto is fully imported but rarely used outside legacy modal headers and SAMI markdown content — adds ~200KB of font data.
- **Scrollbar uses sky-blue accent** (`rgba(112, 162, 235, *)`) which doesn't match the brand-orange or navy palette.

---

## 12. CSS Custom Properties Used

This codebase does NOT use CSS custom properties for the main token system — values are hardcoded throughout. Only a few app-specific variables exist:

| Variable | Use |
|---|---|
| `--2a80da86` | Scope selector width (e.g. 340px) |
| `--d85a93c6` | Scope selector search width (e.g. 220px) |
| `--07ac08a0` | Scope selector height (e.g. 40px) |
| `--tw-content` | Tailwind passthrough in SAMI placeholders |
| `--unnamed-character-spacing-0` | Figma export remnant (used in tenant name letter-spacing) |

> **Implication**: Modifying token values requires rebuilding the compiled stylesheet — there is no runtime theming layer.

---

## 13. What is now COMPLETE

- ✅ Color palette (all hardcoded values catalogued)
- ✅ Typography scale (from .sw-typo-* classes)
- ✅ Z-index layering (full hierarchy mapped)
- ✅ Animation/transition tokens (all keyframes + durations)
- ✅ Component dimensions (heights, widths, padding)
- ✅ All major component states (default, hover, active, focus, disabled, dark)
- ✅ Shadow tokens
- ✅ Border radius tokens
- ✅ Icon system (font, naming, Unicode mappings)

## 14. What still needs verification

- ⚠️ Card component (`.sw-card-view`) — extracted from inline only, not in compiled CSS paste
- ⚠️ Some severity / priority icon classes (referenced but not fully mapped)
- ⚠️ Print styles (only Leaflet observed; UUIF print likely minimal)
- ⚠️ Form validation states (success/warning/error inputs not in this paste)
- ⚠️ Tenant management / wizard / drawer modal patterns (not in the compiled CSS provided)

