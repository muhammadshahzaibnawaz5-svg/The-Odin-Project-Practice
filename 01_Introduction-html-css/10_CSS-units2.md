### Quick Recommendation
- **Font sizes**: Use **`rem`** (accessibility-friendly)
- **Margins, padding, widths, heights, borders**: Use **`px`** (layout stability)
- **Avoid `em`** in most cases (inheritance issues)

### Main CSS Units Comparison

| Unit     | Type       | Relative To                          | Best For                          | Pros                                      | Cons                                      |
|----------|------------|--------------------------------------|-----------------------------------|-------------------------------------------|-------------------------------------------|
| **`px`** | Absolute   | CSS reference pixel (96 DPI)        | Spacing (margin, padding), widths, heights, borders | Predictable, consistent spacing, easy to understand | Does **not** scale with user’s browser font-size preference |
| **`em`** | Relative   | **Parent** element’s `font-size`    | Rare cases (component scaling)   | Scales with parent font size             | Compounding inheritance → unpredictable & error-prone |
| **`rem`** | Relative  | **Root** (`<html>`) `font-size`     | **Font sizes** (recommended)     | Predictable, respects user font settings, accessible | Can cause extra whitespace when text enlarges |

### Detailed Breakdown

| Aspect                  | `px`                                      | `em`                                           | `rem`                                          |
|-------------------------|-------------------------------------------|------------------------------------------------|------------------------------------------------|
| **Scales with**        | Browser zoom only                         | Parent `font-size` + zoom                      | Root `font-size` + zoom                        |
| **Inheritance**        | None                                      | Yes (compounds)                                | No (always from root)                          |
| **Accessibility**      | Moderate (zoom works)                     | Good but risky due to compounding              | **Best** – respects browser text size setting  |
| **Layout Stability**   | Excellent (fixed spacing)                 | Poor (can break layouts)                       | Good for fonts, may inflate spacing            |
| **Common Pitfall**     | Ignores user font-size preference         | "1.5em inside 1.5em" becomes much larger      | Large text can create excessive whitespace     |

### Practical Usage Guide

| Property Type              | Recommended Unit | Reason |
|----------------------------|------------------|--------|
| **Font sizes** (`font-size`) | `rem`           | Accessibility + predictability |
| **Margins & Padding**      | `px`            | Keeps consistent spacing even if user increases text size |
| **Widths & Heights**       | `px` (or `%` / `vw`) | Layout control |
| **Borders & Shadows**      | `px`            | Crisp, predictable lines |
| **Component scaling**      | `em` (rarely)   | Only when you deliberately want child elements to scale with parent |
