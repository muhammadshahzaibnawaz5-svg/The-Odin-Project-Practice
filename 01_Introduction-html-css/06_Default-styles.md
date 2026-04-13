### Why Use a CSS Reset / Normalize / Reboot?
Browsers have inconsistent default styles (margins, padding, font sizes, form elements, HTML5 semantics, etc.).  
A reset creates a **consistent baseline** so your custom styles behave predictably across browsers.

### Evolution of Approaches

| Approach              | Philosophy                                      | Key Characteristics                          | Best For |
|-----------------------|-------------------------------------------------|----------------------------------------------|----------|
| **Traditional Reset** | Strip everything to zero                        | Sets `margin:0`, `padding:0`, `border:0`, `font-size:100%` on almost all elements | Projects wanting full control from scratch |
| **Normalize.css**     | Fix only differences, preserve useful defaults  | Targeted fixes with comments, keeps sensible browser styles | Most modern projects (balanced & documented) |
| **Reboot (Bootstrap)**| Opinionated baseline on top of Normalize        | Element selectors only, adds Bootstrap-friendly defaults | Bootstrap-based sites |
| **Custom / Opinionated** | Add useful globals (e.g. `box-sizing`, font stack) | Mix of reset + enhancements                 | Personal projects & modern workflows |

### Popular Examples

**Eric Meyer’s Reset (Classic)**
```css
html, body, div, h1, h2, p, ul, li, table, th, td, article, section, ... {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
```

**Normalize.css Style (Targeted)**
- Does **not** zero out everything.
- Fixes specific issues (e.g. `abbr[title]`, headings in Firefox).
- Preserves useful defaults like link underlines and form layouts.

**Common Global Additions (Modern Practice)**
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  font-size: 100%; /* or 62.5% for easier rem calculations */
}
```

### Key Differences Summary

| Feature                  | Traditional Reset          | Normalize.css                  | Bootstrap Reboot              |
|--------------------------|----------------------------|--------------------------------|-------------------------------|
| **Scope**                | Very broad (`*` or long list) | Targeted (only inconsistencies) | Targeted + opinionated        |
| **Removes Defaults**     | Yes (aggressively)         | Minimal                        | Minimal + adds some styles    |
| **Preserves Useful Styles** | No                      | Yes                            | Yes (Bootstrap-tuned)         |
| **HTML5 Support**        | Added manually             | Built-in                       | Built-in                      |
| **Opinionated**          | Can be                         | Low                            | Medium (Bootstrap-specific)   |
| **Maintenance**          | Simple but blunt           | Well-documented                | Tied to Bootstrap             |

### Modern Recommendations
- **Start with Normalize.css** for most projects — it’s reliable, lightweight, and well-maintained.
- Use **Bootstrap Reboot** only if you’re already using Bootstrap.
- Consider **custom resets** (e.g. Josh Comeau style or sanitize.css) for opinionated defaults you love.
- Many inconsistencies have reduced in modern browsers — a full reset may not always be needed.
- Tools like **PostCSS Normalize** let you include only rules for your supported browsers (via Browserslist).
