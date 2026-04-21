# Toastmasters FTH Homepage Generator

A Claude Code skill that generates professional, brand-compliant HTML homepages for Toastmasters clubs using the **Free Toast Host (FTH)** platform.

## What It Does

FTH is the official website platform for all Toastmasters clubs (`clubname.toastmastersclubs.org`). The homepage content area accepts raw HTML. This skill collects your club's info and generates a complete, ready-to-paste HTML page — no coding required.

## Three Visual Themes

| Theme | Style |
|---|---|
| **Classic** | White background · Loyal Blue + True Maroon · Clean & professional |
| **Accent** | Dark `#0d1117` · Frosted glass cards · Gold highlights · Fade-up animations |
| **Obsidian** | Deep black `#080808` · Grid texture hero · Gradient borders · Shimmer CTA |

Preview SVGs for each theme are in the [`assets/`](assets/) folder.

## No Claude Code? Use the Self-Contained Builder

**[`output/fth-homepage-builder.html`](output/fth-homepage-builder.html)** is a standalone web app — no Claude account needed.

**[Try the live demo →](https://4039.toastmastersclubs.org/test1.html)**

1. Open the file in any browser (or copy its source code into any `.html` file on your computer)
2. Fill in your club's details using the form UI (name, meeting time, location, contact, etc.)
3. Choose a theme and click **Generate**
4. Copy the generated HTML from the output box and paste it into FTH

This is the recommended path for Toastmasters members who don't have a Claude Code account.

## How to Use (Claude Code)

Invoke the skill in Claude Code and it will walk you through four steps:

1. **Collect club info** — name, number, tagline, meeting time/place, contact email, optional social links
2. **Choose a theme** — Claude shows visual previews; you pick A, B, or C
3. **Generate HTML** — a complete, self-contained file is written to `output/`
4. **Paste into FTH** — log in → Site Administration → Main Heading → Source → paste → Save

## Pasting Into FTH

1. Log in to your FTH admin panel
2. Go to **Site Administration**
3. Open the **Main Heading** editor and click the **Source** (`<>`) button
4. Select all existing content and delete it
5. Paste the generated HTML
6. Click **Save / Close**

## Example Output

| File | Description |
|---|---|
| [`output/fth-homepage-builder.html`](output/fth-homepage-builder.html) | **Self-contained builder UI** — open in any browser, no Claude needed |
| [`output/circlecity5170-homepage-accent.html`](output/circlecity5170-homepage-accent.html) | Circle City Toastmasters #5170 — Accent theme |
| [`output/eeclub4039-homepage.html`](output/eeclub4039-homepage.html) | Enthusiastic Embarkers Club #4039 — Classic theme |
| [`output/eeclub4039-homepage-accent.html`](output/eeclub4039-homepage-accent.html) | Enthusiastic Embarkers Club #4039 — Accent theme |
| [`output/eeclub4039-homepage-obsidian.html`](output/eeclub4039-homepage-obsidian.html) | Enthusiastic Embarkers Club #4039 — Obsidian theme |

## Brand Compliance

All generated pages follow Toastmasters International brand guidelines:

- **Colors:** Loyal Blue `#004165`, True Maroon `#772432`, Happy Yellow `#F2DF74`
- **Fonts:** Montserrat (headings) + Source Sans 3 (body) via Google Fonts
- **Logo:** Official Toastmasters International logo — no custom club logos
- **Disclaimer:** Required TM disclaimer included on every page

See [`references/brand.md`](references/brand.md) for full brand rules and [`references/fth.md`](references/fth.md) for FTH platform constraints.

## Repository Structure

```
toastmasters-fth-homepage/
├── SKILL.md                        # Claude Code skill definition
├── assets/
│   ├── homepage-template.html      # Base HTML template with placeholders
│   ├── preview-accent.svg          # Theme preview — Accent
│   ├── preview-classic.svg         # Theme preview — Classic
│   └── preview-obsidian.svg        # Theme preview — Obsidian
├── output/
│   ├── fth-homepage-builder.html   # Self-contained builder UI (no Claude needed)
│   └── ...                         # Generated homepages (one per club/theme)
└── references/
    ├── brand.md                    # Toastmasters brand guidelines
    └── fth.md                      # FTH platform constraints & how-to
```

---

*This skill is not affiliated with or endorsed by Toastmasters International.*
