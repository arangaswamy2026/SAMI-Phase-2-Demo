# snwl-ui-uuif Skill Package

**SonicWall UI Prototyping skill — restructured to prevent silent truncation.**

## What is in this package

- `SKILL.md` — index + enforcement rules (entry point)
- `01-tokens-color.md` — color tokens, status colors, alert fills
- `02-tokens-foundation.md` — spacing, radius, shadow, typography
- `03-components-nav.md` — page layout, primary nav, subnav, top bar
- `04-components-forms.md` — buttons, inputs, checkboxes, tabs, wizard
- `05-components-overlays.md` — modals, tooltips, popovers, banners, date picker
- `06-components-data.md` — dashboard cards, tables, chips, spinners, mock rules

## How to upload

### Option A: Replace the old skill (recommended)

1. Delete the old `sonicwall-ui-prototyping` skill from `/mnt/skills/user/`
2. Create a new folder named `snwl-ui-uuif` in `/mnt/skills/user/`
3. Upload **all seven files** into that folder
4. Keep them as separate files — do not merge or zip

### Option B: Keep both side by side (testing)

1. Leave the old `sonicwall-ui-prototyping` skill in place
2. Create the new `snwl-ui-uuif` folder
3. Upload all seven files
4. Test the new skill on a real prototype task
5. Once validated, delete the old skill

## Important — Upload as separate files

- **Do NOT upload a zip** — Claude cannot read inside zip archives at skill-load time
- **Do NOT concatenate the files** — that recreates the truncation problem
- Each file must sit independently in the skill folder
- The folder structure must look like:

```
/mnt/skills/user/snwl-ui-uuif/
├── SKILL.md
├── 01-tokens-color.md
├── 02-tokens-foundation.md
├── 03-components-nav.md
├── 04-components-forms.md
├── 05-components-overlays.md
└── 06-components-data.md
```

## File sizes (all under truncation threshold)

| File | Characters |
|---|---|
| SKILL.md | 4,495 |
| 01-tokens-color.md | 4,874 |
| 02-tokens-foundation.md | 2,686 |
| 03-components-nav.md | 2,408 |
| 04-components-forms.md | 3,760 |
| 05-components-overlays.md | 2,009 |
| 06-components-data.md | 3,367 |

Truncation threshold is ~16,000 characters. Every file is well under one-third of that limit.

## How to verify the skill works after upload

1. Start a new chat
2. Ask: "What sections does the snwl-ui-uuif skill contain?"
3. Claude should reference the routing table in `SKILL.md` and list the six reference files
4. Ask Claude to build a simple component (e.g., a primary button) — it should read `SKILL.md` plus `04-components-forms.md` and produce token-compliant code
