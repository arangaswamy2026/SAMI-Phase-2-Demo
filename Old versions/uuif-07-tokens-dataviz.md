# UUIF 9.2 — Data Visualization Tokens & Patterns

<!-- This file contains 6 sections: Viz Color Palette, Severity Mapping, Chart Spacing, Stacked Bar Pattern, Sparkline Pattern, Donut Pattern -->

> **Design System Version:** UUIF 9.2
> **Canonical variable prefix:** `--viz-*`
> **Scope:** All chart, graph, and data visualization components
> **Rule:** Never use brand UI tokens (`--uuif-brand-*`, `--uuif-status-*`) directly in charts. Always use `--viz-*` tokens.

---

## 1. Viz Color Palette

Desaturated ~35% from brand tokens to reduce visual noise inside dense dashboards.

| CSS Variable      | Hex Value | Derived From              | Usage                          |
|---|---|---|---|
| `--viz-red`       | `#a03535` | `--uuif-status-failed`    | Critical severity, infected, not mitigated |
| `--viz-green`     | `#668c50` | `--uuif-brand-green`      | Healthy, mitigated, online, success |
| `--viz-orange`    | `#c48a3a` | `--uuif-status-major`     | High severity, warning, out of sync |
| `--viz-blue`      | `#7a94ba` | `--uuif-icon-primary`     | Info, benign, Windows OS, low severity |
| `--viz-yellow`    | `#c0a25c` | `--uuif-brand-yellow`     | Medium severity, pending |
| `--viz-grey`      | `#8a9aaa` | `--uuif-text-tertiary`    | Offline, neutral, decommissioned |
| `--viz-other`     | `#90a8cc` | `--uuif-border-secondary` | Catch-all 7th segment, "Other" |

### CSS Declaration (include in every file that uses charts)

```css
:root {
  --viz-red:    #a03535;
  --viz-green:  #668c50;
  --viz-orange: #c48a3a;
  --viz-blue:   #7a94ba;
  --viz-yellow: #c0a25c;
  --viz-grey:   #8a9aaa;
  --viz-other:  #90a8cc;
}
```

---

## 2. Severity Mapping Table

Always use this mapping — never infer severity colors from context.

| Severity Level | Token          | Hex       | Text Pair |
|---|---|---|---|
| Critical       | `--viz-red`    | `#a03535` | `#fff` (white) |
| High           | `--viz-orange` | `#c48a3a` | `#fff` (white) |
| Medium         | `--viz-yellow` | `#c0a25c` | `#fff` (white) |
| Low            | `--viz-blue`   | `#7a94ba` | `#fff` (white) |
| Info / Benign  | `--viz-blue`   | `#7a94ba` | `#fff` (white) |
| Healthy / OK   | `--viz-green`  | `#668c50` | `#fff` (white) |
| Neutral / N/A  | `--viz-grey`   | `#8a9aaa` | `#fff` (white) |

All segment text is always `color: #ffffff`. Minimum contrast 3:1 guaranteed at these values.

---

## 3. Chart Spacing Tokens

| Property              | Value  | Notes |
|---|---|---|
| Chart card padding    | `12px` | Inner padding for all chart card bodies |
| Legend gap            | `8px`  | Gap between legend items (row or column) |
| Section gap           | `12px` | Gap between chart sections within one card |
| Chart title margin-bottom | `6px` | Below title, above chart |
| Label font size       | `9px`  | All axis, segment, and legend labels |
| Label font weight     | `700`  | All axis, segment, and legend labels |
| Label letter-spacing  | `0.05em` | All uppercase labels |

---

## 4. Stacked Bar Pattern

### Anatomy

```
┌─────────────────────────────────────────────────────┐
│  SECTION TITLE                           TOTAL: 18  │  ← 9px / 700 / uppercase
│ ┌──────────┬──────────────────┬────────┬──────────┐ │
│ │  2       │        5         │   7    │    4     │ │  ← height: 24px, radius: 4px
│ └──────────┴──────────────────┴────────┴──────────┘ │
│  11.1%      27.8%              38.9%    22.2%        │  ← 9px labels below
│  Critical   High               Medium   Low          │
└─────────────────────────────────────────────────────┘
```

### Spec

| Property          | Value                        |
|---|---|
| Bar height        | `24px`                       |
| Bar border-radius | `var(--uuif-radius-4)` = 4px |
| Segment min-width | `8%`                         |
| Segment text      | `10px`, `700`, `color: #fff` |
| Label font size   | `9px`                        |
| Label font weight | `700` for %, `400` for name  |
| Background track  | `var(--uuif-surface-model)`  |
| Segment gap       | `0` (flush, no gap)          |

### HTML Structure

```html
<div class="uuif-stk-title">
  Section Label
  <span class="uuif-stk-total">18</span>
</div>
<div class="uuif-stk-bar">
  <div class="uuif-stk-seg" style="width:11.1%; background:var(--viz-red);">2</div>
  <div class="uuif-stk-seg" style="width:27.8%; background:var(--viz-orange);">5</div>
  <div class="uuif-stk-seg" style="width:38.9%; background:var(--viz-yellow);">7</div>
  <div class="uuif-stk-seg" style="width:22.2%; background:var(--viz-blue);">4</div>
</div>
<div class="uuif-stk-labels">
  <div class="uuif-stk-lbl" style="width:11.1%;"><span class="pct">11.1%</span><span class="name" style="color:var(--viz-red);">Critical</span></div>
  <div class="uuif-stk-lbl" style="width:27.8%;"><span class="pct">27.8%</span><span class="name" style="color:var(--viz-orange);">High</span></div>
  <div class="uuif-stk-lbl" style="width:38.9%;"><span class="pct">38.9%</span><span class="name" style="color:var(--viz-yellow);">Medium</span></div>
  <div class="uuif-stk-lbl" style="width:22.2%;"><span class="pct">22.2%</span><span class="name" style="color:var(--viz-blue);">Low</span></div>
</div>
```

### CSS Classes

```css
.uuif-stk-title {
  font-size: 9px; font-weight: 700; text-transform: uppercase;
  letter-spacing: 0.05em; color: var(--uuif-text-tertiary);
  display: flex; justify-content: space-between; margin-bottom: 6px;
}
.uuif-stk-total {
  font-family: 'Nunito', sans-serif; font-size: 15px; font-weight: 700;
  color: var(--uuif-text-highlight); line-height: 1;
}
.uuif-stk-bar {
  width: 100%; height: 24px; border-radius: var(--uuif-radius-4);
  overflow: hidden; display: flex; background: var(--uuif-surface-model);
}
.uuif-stk-seg {
  height: 100%; min-width: 8%; display: flex; align-items: center;
  justify-content: center; font-size: 10px; font-weight: 700;
  color: #ffffff; overflow: hidden; white-space: nowrap;
}
.uuif-stk-labels {
  display: flex; width: 100%; margin-top: 4px;
}
.uuif-stk-lbl {
  display: flex; flex-direction: column; align-items: center;
  font-size: 9px; min-width: 0;
}
.uuif-stk-lbl .pct  { font-weight: 700; color: var(--uuif-text-secondary); }
.uuif-stk-lbl .name { font-weight: 400; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; max-width: 100%; }
```

---

## 5. Sparkline Pattern

### Spec

| Property           | Value                              |
|---|---|
| SVG height         | `80px`                             |
| SVG width          | `100%` (fluid)                     |
| Viewbox            | `0 0 220 80`                       |
| Stroke width       | `2px`                              |
| Data point dot radius | `3px` (default), `3.5px` (peak) |
| Dot stroke         | `#ffffff`, `stroke-width: 1.5`     |
| Area fill          | Gradient from `color @ 20%` to `color @ 0%` |
| Grid line color    | `rgba(17,17,17,0.06)`              |
| Grid line width    | `1px`                              |
| Axis label font    | `7px`, `fill: rgba(17,17,17,0.3)`, `font-family: Nunito Sans` |
| Dashed line style  | `stroke-dasharray: 4 3`            |

### Line Types

| Series Type     | Stroke         | Area Fill | Dash |
|---|---|---|---|
| Primary (solid) | `var(--viz-*)` | Yes (gradient) | No |
| Secondary       | `var(--viz-*)` | Yes (gradient) | No |
| Tertiary/Benign | `var(--viz-*)` | No             | Yes (`4 3`) |

### SVG Template

```html
<svg width="100%" height="80" viewBox="0 0 220 80" preserveAspectRatio="none">
  <defs>
    <linearGradient id="grad-red" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%"   stop-color="#a03535" stop-opacity="0.25"/>
      <stop offset="100%" stop-color="#a03535" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <!-- Grid lines at y: 8, 26, 44, 62 (4 levels), baseline at y:70 -->
  <line x1="18" y1="8"  x2="220" y2="8"  stroke="rgba(17,17,17,.06)" stroke-width="1"/>
  <line x1="18" y1="70" x2="220" y2="70" stroke="rgba(17,17,17,.08)" stroke-width="1"/>
  <!-- Area fill polygon (close to baseline y=70) -->
  <polygon points="18,Y1 46,Y2 ... 220,70 18,70" fill="url(#grad-red)"/>
  <!-- Line -->
  <polyline points="18,Y1 46,Y2 ..." fill="none" stroke="#a03535" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
  <!-- Dots at notable points -->
  <circle cx="46" cy="Y2" r="3" fill="#a03535" stroke="#fff" stroke-width="1.5"/>
  <!-- X axis labels -->
  <text x="18" y="80" font-size="7" fill="rgba(17,17,17,.3)" font-family="Nunito Sans,sans-serif" text-anchor="middle">M</text>
</svg>
```

### Y-axis Calculation

```
Scale: y=70 (value=0), y=8 (value=max). Range = 62px.
y = 70 - (value / max) * 62
```

---

## 6. Donut Chart Pattern

### Spec

| Property           | Value              |
|---|---|
| SVG size           | `100px × 100px` (compact), `160px × 160px` (standard) |
| Viewbox            | `0 0 100 100`      |
| Outer radius       | `46px`             |
| Inner radius (hole)| `28px` (donut) or `0` (pie) |
| Centre label font  | `14px`, `700`, `font-family: Nunito` |
| Centre label color | `var(--uuif-text-highlight)` |
| Legend layout      | Vertical column, gap `8px` |
| Legend dot size    | `8px × 8px`, `border-radius: 2px` |
| Legend font size   | `9px`              |
| Legend value       | `margin-left: auto`, `font-weight: 700`, `9px` |

### Legend HTML

```html
<div class="uuif-donut-legend">
  <div class="uuif-leg-row">
    <span class="uuif-leg-dot" style="background:var(--viz-red);"></span>
    Critical
    <span class="uuif-leg-val">2</span>
  </div>
</div>
```

### CSS Classes

```css
.uuif-donut-legend { display: flex; flex-direction: column; gap: 8px; flex: 1; }
.uuif-leg-row      { display: flex; align-items: center; gap: 6px; font-size: 9px; color: var(--uuif-text-secondary); }
.uuif-leg-dot      { width: 8px; height: 8px; border-radius: 2px; flex-shrink: 0; }
.uuif-leg-val      { margin-left: auto; font-weight: 700; font-size: 9px; color: var(--uuif-text-highlight); }
```

---

## Gap Protocol for Data Viz

If a chart type is not defined above, do NOT invent tokens. Report:

> "This chart pattern (e.g., heatmap, area chart, scatter plot) is not defined in UUIF 9.2 §07. Closest available: [stacked bar / sparkline / donut]. Flag as design system gap?"
