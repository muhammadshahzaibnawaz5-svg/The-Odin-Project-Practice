### Overview
**CanIUse.com** is a free, open-source website that provides up-to-date **browser support tables** for HTML5, CSS3, JavaScript APIs, and other front-end web technologies. It covers both **desktop** and **mobile** browsers.

It helps developers quickly check compatibility before using a feature, decide on fallbacks or polyfills, and make informed decisions about browser support.

### How to Use CanIUse (Quick Guide)

| Step | Action | Details |
|------|--------|---------|
| 1    | Go to the site | Visit https://caniuse.com |
| 2    | Search | Type a feature name (e.g., `flexbox`, `css-grid`, `webp`, `clamp`, `view-transitions`) |
| 3    | View results | See colored support table + global usage % |
| 4    | Customize | Click **Settings** to import your own Google Analytics stats, adjust minimum usage threshold for old browsers, or change data source |
| 5    | Explore | Use "Usage relative" button, view notes, known issues, and prefixes |
| 6    | Test live | Use the BrowserStack integration to test on real devices |

### Support Table Legend (Color Meaning)

| Color / Symbol | Meaning | Typical Implication |
|----------------|---------|---------------------|
| **Green** (Full support) | ✅ Supported | Safe to use |
| **Yellow / Partial** | ⚠️ Partial support | Works with limitations or requires prefixes |
| **Red** (No support) | ❌ Not supported | Needs polyfill, fallback, or alternative |
| **Gray** | Unknown / No data | Rare, usually very old versions |
| **Black / Strikethrough** | Not applicable or removed | Feature was removed or never existed in that browser |

**Notes section** (below the table) often includes:
- Required prefixes (`-webkit-`, `-moz-`, etc.)
- Known bugs or partial implementations
- Version-specific caveats
- Alternative features or workarounds

### Key Features of CanIUse

| Feature | Description |
|---------|-------------|
| **Search** | Fast search for features, CSS properties, HTML elements, JS APIs |
| **Index of features** | Full categorized list of all tracked features |
| **Latest features** | Shows newly added or updated support tables |
| **Most searched** | Popular features like Flexbox, CSS Grid, WebP, viewport units |
| **Browser scores** | Overall support score per browser (e.g., Chrome 147: 443 points) |
| **Usage data** | Global + country/continent usage; import your own site stats |
| **Settings** | Adjust old browser visibility (default ≥0.5% usage), relative usage view |
| **Mobile support** | Includes iOS Safari, Android Chrome, Samsung Internet, etc. |
| **Third-party tools** | Embed widget, CLI tool, linting (doiuse), "I want to use" multi-feature checker |

### Common Use Cases

| Use Case | How CanIUse Helps |
|----------|-------------------|
| **CSS Layout** | Check Flexbox, Grid, `gap`, `clamp()`, container queries |
| **Images & Media** | WebP, AVIF, lazy loading, `picture` element |
| **Modern CSS** | `:has()`, `view-transitions`, custom properties, `dvh` units |
| **JavaScript APIs** | Fetch, Intersection Observer, WebAssembly, Service Workers |
| **HTML5** | New input types, `<dialog>`, `<details>` |
| **Deciding polyfills** | See exact version support to know when a polyfill is needed |

### Pro Tips
- Click **"Show all"** to reveal very old browser versions.
- Use **"Usage relative"** mode to visually see market share impact.
- Always read the **Notes** section — many "green" cells have important caveats.
- For production sites, combine global usage % with your own audience analytics (import via Settings).
- Contribute missing data or vote for new features on GitHub.