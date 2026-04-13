### Core Principles
Fonts affect **performance** (FCP, LCP), **layout stability** (CLS), and **user experience** (FOIT/FOUT).  
`@font-face` alone does **not** trigger downloads — only used styles do.

### Font Loading Strategies

| Practice                        | Recommendation                                      | Benefit |
|---------------------------------|-----------------------------------------------------|---------|
| Inline critical `@font-face`   | Place in `<head>` with critical CSS                | Early discovery, faster rendering |
| Preconnect to font hosts       | Use `<link rel="preconnect">` + `crossorigin`      | Reduces connection time for third-party fonts |
| Preload critical fonts         | Use `<link rel="preload" as="font">` sparingly     | Helps when CSS is delayed |
| Optimize stylesheet delivery   | Remove unused CSS, inline critical styles          | Prevents late font discovery |

### Font Delivery Best Practices

| Practice                        | Recommendation                                      | Why |
|---------------------------------|-----------------------------------------------------|-----|
| **Use WOFF2 only**             | Primary format (with WOFF fallback if needed)      | Best compression (~30% better), wide support |
| **Subset fonts**               | Use `unicode-range` or tools (subfont, glyphhanger) | Dramatically reduces file size |
| **Minimize number of fonts**   | Prefer system fonts (`system-ui`) for body text    | Zero download cost |
| **Use Variable Fonts**         | One file for multiple weights/styles               | Great when many variants are needed |
| **Self-host vs CDN**           | Self-host for control; third-party can be faster in practice | Balance performance & maintenance |

### Font Rendering & `font-display`

| Value          | Block Period | Swap Period | Best For                          | Trade-off |
|----------------|--------------|-------------|-----------------------------------|---------|
| `optional`    | 100ms       | None       | **Best performance**             | May never swap to web font |
| `swap`        | 0ms         | Infinite   | Fast display + eventual web font | Risk of layout shift (CLS) |
| `fallback`    | 100ms       | 3s         | Balanced approach                | Moderate shift risk |
| `block`       | 2–3s        | Infinite   | Guaranteed web font look         | FOIT (invisible text) |
| `auto`        | Browser default | —        | Rarely recommended               | — |

**Recommendation**:  
- Use **`swap`** for most branding/heading fonts (with early loading).  
- Use **`optional`** for body text to prioritize performance.

### Technical Implementation Tips

| Area                  | Best Practice |
|-----------------------|---------------|
| **@font-face**       | Declare only used fonts. Always specify `format("woff2")`. |
| **Font Stack**       | Always include fallbacks: `"MyFont", system-ui, sans-serif` |
| **Icon Fonts**       | Prefer **SVGs** instead (better accessibility & no layout shifts) |
| **Matching Metrics** | Use `size-adjust` or similar fallbacks to reduce CLS when swapping fonts |

### Common Pitfalls to Avoid
- Relying on late-discovered fonts (delayed CSS)
- Not using `font-display` → FOIT or unexpected shifts
- Loading full fonts without subsetting
- Overusing `preload` without fixing root causes
- Ignoring font licenses for subsetting/self-hosting
- Using too many font weights/styles

### Quick Wins Summary
1. Use **WOFF2** + subsetting.
2. Inline critical font CSS + preconnect.
3. Set sensible `font-display: swap` or `optional`.
4. Prefer **system fonts** and **variable fonts** where possible.
5. Minimize total web fonts (aim for 1–2 custom families).
6. Test for CLS, FOIT/FOUT, and performance on real devices.