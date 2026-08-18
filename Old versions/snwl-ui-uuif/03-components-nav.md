# UUIF 9.2 — Page Layout & Navigation Components

<!-- This file contains 4 sections: Page Layout Pattern, Primary Nav Rail, SubNav Panel, Top Action Bar, Icon Color Rules -->

---

## Page Layout Pattern

Every SonicWall page follows this exact structure:

```
┌─────────────────────────────────────────────┐
│ Primary Nav │  SubNav  │  Content Area       │
│    60px     │  266px   │  flex: 1            │
│  #001b50    │  white   │  #fafafa bg         │
│  [Logo]     │  [Logo]  │  [Breadcrumb]       │
│  [Icons]    │  [Title] │  [Page Title]       │
│             │  [Sects] │  [Content...]       │
└─────────────────────────────────────────────┘
```

Every page mock must include the full nav shell (60px primary rail + 266px subnav).

---

## Primary Nav Rail

- Width: 60px · Background: `--uuif-brand-navy`
- Logo area: 32×32px SonicWall swoosh SVG, always `fill="#FF5D00"`
- Nav items: 60×52px, 28px icons centered
- Selected item: `rgba(17,17,17,0.4)` bg + 2px `--uuif-brand-orange` left edge indicator
- Default icon fill: `#D2DFF2` · Selected icon fill: `#FF5D00`
- Divider: 44px wide, 1px `rgba(255,255,255,0.15)`

---

## SubNav Panel

- Width: 266px · Background: white · Right border: `--uuif-border-tertiary`
- Header: SonicWall Wordmark SVG (always `fill="#FF5D00"`) + "Unified Management" in semibold 14px `#e67f02`
- Page title: semibold 16px UPPERCASE
- Section headers: semibold 13px `--uuif-brand-navy`, 12px chevron at 60% opacity
- Sub-links: regular 12px `--uuif-text-secondary`
- Active sub-link: semibold 12px `#e67f02`, `--uuif-surface-selected` bg, 5px radius

---

## Top Action Bar

- Height: 46px · Background: `--uuif-surface-container`
- Left: breadcrumb (home icon 16px, `\` separator, path items in `--uuif-theme-text-secondary`)
- Right: icon action buttons (16px) + 20px avatar circle (`--uuif-surface-primary`)

---

## Icon Color Rules (SVG Nav Icons)

- Default: `fill="#D2DFF2"`
- Selected/Active: `fill="#FF5D00"`
- Swoosh logomark: always `fill="#FF5D00"`
- Wordmark: always `fill="#FF5D00"`

Navigation icons must be copied verbatim from the SVG registry — never substitute Font Awesome, Material Icons, or emoji.
