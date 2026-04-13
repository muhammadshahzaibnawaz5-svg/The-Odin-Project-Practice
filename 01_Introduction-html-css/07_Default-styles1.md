### Core Problem
Browsers apply inconsistent default styles (margins, fonts, line-heights, etc.). This causes cross-browser issues and forces repeated overrides.

### Main Approaches Compared

| Aspect                  | **Normalize**                                      | **Reset**                                          | **Hybrid (Recommended)** |
|-------------------------|----------------------------------------------------|----------------------------------------------------|--------------------------|
| **Goal**                | Fix inconsistencies while keeping useful defaults | Strip everything to a blank canvas                | Combine fixes + clean slate |
| **Philosophy**          | Preserve accessibility & legibility               | Full control — start from zero                     | Best of both             |
| **Browser Defaults**    | Kept & standardized                               | Removed completely                                 | Fixed + selectively removed |
| **Developer Effort**    | Lower (fewer overrides needed)                    | Higher (must restyle everything)                   | Balanced                 |
| **Accessibility**       | Strong (retains browser features)                 | Weaker (must re-add)                               | Strong + customizable    |
| **Examples**            | Normalize.css, modern-normalize                   | Eric Meyer’s Reset CSS                             | Tailwind Preflight       |

### Pros & Cons

**Normalize**
- **Pros**: Cross-browser consistency, maintains readability, less work, accessibility-friendly.
- **Cons**: Still requires some margin/padding overrides.

**Reset**
- **Pros**: No more fighting defaults, fully additive CSS.
- **Cons**: Loses semantic visuals, higher initial effort, risk of accessibility issues.

### Author’s Recommended Modern Approach (2023+)

1. **Start with `modern-normalize`**  
   - Fixes browser bugs (`-webkit-text-size-adjust`, etc.)
   - Sets `box-sizing: border-box`
   - Uses `system-ui` font stack
   - Removes `<body>` margin
   - Makes forms inherit font styles

2. **Add Lightweight Custom Reset**

```css
@import "modern-normalize";

:root {
  line-height: 1.5;           /* WCAG-friendly readability */
}

h1, h2, h3, h4, h5, figure, p, ol, ul {
  margin: 0;
}

h1, h2, h3, h4, h5 {
  font-size: inherit;
  font-weight: inherit;
}

ol[role="list"], ul[role="list"] {
  list-style: none;
  padding-inline: 0;
}

img {
  display: block;
  max-inline-size: 100%;      /* Responsive images */
}
```