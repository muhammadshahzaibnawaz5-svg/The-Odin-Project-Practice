### Core Concepts

| Concept              | Description |
|----------------------|-------------|
| **Web Fonts**       | Custom fonts downloaded from the web, allowing typography beyond system (web-safe) fonts. |
| **Web-safe Fonts**  | Fonts guaranteed to exist on most devices (e.g., Arial, Verdana, Georgia). Always provide as fallback. |
| **@font-face**      | CSS at-rule used to define and load a custom font family. |
| **Font Stack**      | Comma-separated list of fonts in `font-family` (custom → system → generic). |

### Font Formats (Recommended Order)

| Format   | Pros                              | Cons                          | Support Notes |
|----------|-----------------------------------|-------------------------------|---------------|
| **WOFF2** | Best compression, modern features | Limited old browser support   | Preferred primary format |
| **WOFF** | Good compression, wide support    | Larger than WOFF2             | Fallback for older browsers |
| **TTF/OTF** | Broad compatibility              | No compression, large files   | Legacy support |
| **EOT**  | Old IE support                    | Obsolete, inefficient         | Rarely needed now |
| **SVG**  | Legacy mobile support             | Large files, poor performance | Almost never used today |

**Tip**: Always list **WOFF2 first**, then **WOFF**.

### @font-face Syntax & Descriptors

| Descriptor          | Purpose                                      | Common Values / Example |
|---------------------|----------------------------------------------|-------------------------|
| `font-family`      | Name to reference the font in CSS           | `"MyCustomFont"` |
| `src`              | URL(s) to font file(s) + optional format    | `url("fonts/myfont.woff2") format("woff2")` |
| `font-weight`      | Defines weight(s) this file provides        | `normal`, `bold`, `400`, `700` |
| `font-style`       | Defines style this file provides            | `normal`, `italic` |
| `font-display`     | Controls rendering while font loads         | **`swap`** (recommended), `block`, `fallback`, `optional` |
| `unicode-range`    | Limits download to specific characters      | `U+0000-00FF` (Latin) |
| `font-stretch`     | For condensed/expanded variants             | `normal`, `condensed` |

### Recommended @font-face Example
```css
@font-face {
  font-family: "MyFont";
  src: url("fonts/myfont.woff2") format("woff2"),
       url("fonts/myfont.woff") format("woff");
  font-weight: normal;
  font-style: normal;
  font-display: swap;   /* Prevents invisible text (FOIT) */
}
```

### Usage in CSS
```css
body {
  font-family: "MyFont", system-ui, sans-serif;
}

h1 {
  font-family: "MyFont", sans-serif;
  font-weight: 700;   /* Uses the bold variant if defined */
}
```

### Font Loading Strategies

| Strategy                  | Recommendation                          | Benefit |
|---------------------------|-----------------------------------------|---------|
| `font-display: swap`     | Almost always use this                 | Shows fallback text immediately |
| Preload critical fonts   | `<link rel="preload" as="font" ...>`   | Faster loading of important fonts |
| Limit number of fonts    | 2–3 font families maximum              | Better performance |
| Self-host fonts          | Preferred over third-party services    | Faster, more control |
| Use Google Fonts / similar | Easy for quick projects                | Hosted + optimized |

### Best Practices & Tips
- **Always** include a full font stack with system fonts and a generic family (`serif`, `sans-serif`, `monospace`).
- Use **WOFF2 + WOFF** for modern + broad support.
- Respect **font licenses** — many require payment or specific usage rights.
- Define **different `@font-face`** blocks for each weight/style instead of relying on browser fake bold/italic.
- Test on real devices and with increased text size.
- Minimize HTTP requests by self-hosting fonts.

### Common Pitfalls
- Incorrect file paths in `url()`.
- Forgetting fallback formats.
- No `font-display` → Flash of Invisible Text (FOIT).
- Overusing custom fonts → slow loading and poor accessibility.
- Not testing with screen readers or high-contrast mode.