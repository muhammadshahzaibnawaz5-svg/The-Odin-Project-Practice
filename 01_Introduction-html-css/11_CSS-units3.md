### Overview
Viewport units are relative to the **browser viewport** (window size), not the parent element (unlike `%`).  
They enable fluid, responsive designs that adapt to screen size.

**Formula**:  
`1vw = 1% of viewport width`  
`1vh = 1% of viewport height`

### Core Viewport Units

| Unit   | Full Name                  | Definition                                      | Best Use Cases                              | Notes / Quirks |
|--------|----------------------------|-------------------------------------------------|---------------------------------------------|----------------|
| `vw`   | Viewport Width            | 1% of viewport **width**                       | Fluid typography, full-width sections      | Scales aggressively if used alone for fonts |
| `vh`   | Viewport Height           | 1% of viewport **height**                      | Hero sections, full-height layouts, sticky footers | On mobile (iOS Safari), `100vh` often includes browser UI → content may overflow |
| `vmin` | Viewport Minimum          | 1% of the **smaller** dimension (width or height) | Responsive text/icons that adapt to orientation | Great for portrait/landscape safety |
| `vmax` | Viewport Maximum          | 1% of the **larger** dimension (width or height) | Scaling based on dominant screen side      | Poor support (no IE/Edge) – use cautiously |

### Practical Examples

| Use Case                        | Recommended Code                                      | Why It Works |
|---------------------------------|-------------------------------------------------------|--------------|
| **Fluid Body Font Size**       | `font-size: calc(16px + 1vw);`                       | Combines fixed base + viewport scaling. Preserves browser zoom. |
| **Full Viewport Height**       | `min-height: 100vh;`                                 | Perfect for hero or single-page sections. |
| **Sticky Footer**              | `body { min-height: 100vh; }`                        | Footer stays at bottom when content is short. |
| **Responsive Typography**      | `h1 { font-size: calc(2rem + 3vw); }`                | Grows nicely with screen size. |
| **Fluid Video Aspect Ratio**   | `height: calc(100vw * 9 / 16);` (for 16:9)           | Maintains ratio based on width. |
| **Break Out of Container**     | `margin-left: calc(50% - 50vw); margin-right: calc(50% - 50vw);` | Makes element full viewport width despite parent constraints. |
| **Orientation-Safe Scaling**   | `font-size: 4vmin;`                                  | Uses smallest dimension – safe for mobile. |

### Common Issues & Fixes

| Issue                                      | Solution / Tip |
|--------------------------------------------|----------------|
| Text becomes too small or too large        | Always use `calc()` with a fixed base (`px` or `rem`) |
| Pure `vw`/`vh` breaks browser text zoom    | Combine with `calc()` or `rem` to preserve accessibility |
| `100vh` cuts off content on iOS Safari     | Use `min-height: 100vh` or JavaScript to adjust dynamically |
| `vmax` not supported in older Edge/IE      | Provide fallback with `vh` or `vw` |
| Overly aggressive scaling                  | Add media queries to cap sizes (`@media (min-width: 50em) { ... }`) |
