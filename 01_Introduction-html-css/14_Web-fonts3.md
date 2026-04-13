### Typography Fundamentals
Good web typography prioritizes **readability**, respects user preferences, and ensures comfortable reading across devices and font sizes.

### Choosing Fonts

| Practice                  | Recommendation                                      | Why It Matters |
|---------------------------|-----------------------------------------------------|----------------|
| Use custom web fonts     | Define via `@font-face` with **WOFF2** format      | Matches brand while maintaining performance |
| Variable fonts           | Use when multiple weights/styles are needed        | Reduces file size (one file instead of many) |
| Limit number of fonts    | 1–2 custom families maximum                        | Prevents slow loading and poor UX |
| Font stack               | Always include fallbacks: `Roboto, system-ui, sans-serif` | Graceful degradation |

**Example:**
```css
@font-face {
  font-family: Roboto;
  src: url('/fonts/roboto-regular.woff2') format('woff2');
}
body {
  font-family: Roboto, sans-serif;
}
```

### Font Sizes & Fluid Scaling

| Approach                  | Recommended CSS                                    | Notes |
|---------------------------|----------------------------------------------------|-------|
| **Base scaling**         | Media queries on `html { font-size }`             | Adjusts root size at breakpoints |
| **Fluid typography**     | `font-size: clamp(1rem, 0.75rem + 1.5vw, 2rem);` | Smooth scaling with safe limits |
| **Avoid**                | Pure `vw` (e.g. `2.5vw`)                          | Prevents user text resizing |

**Tip**: Combine `rem` + `vw` with `clamp()` or `calc()` for responsive yet resizable text.

### Line Length (Measure) & Spacing

| Property                  | Recommended Value / Practice                       | Reason |
|---------------------------|----------------------------------------------------|--------|
| **Line length**          | `max-inline-size: 66ch;` (ideal 45–75 characters) | Optimal for comfortable reading |
| **Longer content**       | 45–50ch for multi-column or quotes                | Prevents eye fatigue |
| **Line height**          | Unitless value: `1.5` – `1.65` (body), `2` (quotes) | Scales with font size |
| **Avoid**                | Fixed `px` / `rem` for `line-height` or `max-width` | Breaks when user changes font size |

**Best Practice:**
```css
article {
  max-inline-size: 66ch;
  line-height: 1.65;
}
```

### Hierarchy & Readability
- Establish a clear **typographic scale** (e.g., Material Design Type Scale).
- Use heading levels (`h1`–`h6`) consistently to guide users through content.
- Prioritize contrast, spacing, and alignment for better flow.

### Performance & Loading

| Technique                 | Recommendation                                      | Benefit |
|---------------------------|-----------------------------------------------------|---------|
| Font format              | **WOFF2** primary                                  | Best compression |
| Preloading               | `<link rel="preload" as="font" ... crossorigin>`   | Faster font discovery |
| Font display             | `font-display: swap` (most common) or `fallback`   | Avoids invisible text (FOIT) |
| Self-hosting             | Preferred over third-party when possible           | Better control and speed |

### Accessibility & User Experience
- Respect browser/user font size preferences (use relative units + `clamp()`).
- Allow text to resize without breaking layout.
- Test with increased text size and screen readers.
- Use `font-display: swap` to prevent blank text while fonts load.

### Common Mistakes to Avoid
- Using fixed `px` for line length or line height.
- Pure `vw` for font sizes (breaks zooming/resizing).
- Loading too many font files/weights.
- No fallback font stack.
- Ignoring layout shifts when custom fonts load.

### Quick Wins Summary
1. Set base `font-size` with fluid `clamp()` + media queries.
2. Control line length with `66ch` (`max-inline-size`).
3. Use unitless `line-height`.
4. Preload + `font-display: swap` for custom fonts.
5. Limit to 1–2 font families and prefer variable fonts.
6. Always test on real devices with user text size increased.

