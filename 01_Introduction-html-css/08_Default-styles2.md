### Philosophy
A short, modern, and intentional reset that removes inconsistencies, improves defaults, and creates a predictable foundation without being overly opinionated about design. It evolves with modern CSS features and focuses on better developer and user experience.

### Full Reset Code (Copy-Paste Ready)
```css
/*
  Josh's Custom CSS Reset
  https://www.joshwcomeau.com/css/custom-css-reset/
*/

*, *::before, *::after {
  box-sizing: border-box;
}

*:not(dialog) {
  margin: 0;
}

@media (prefers-reduced-motion: no-preference) {
  html {
    interpolate-size: allow-keywords;
  }
}

body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}

img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}

input, button, textarea, select {
  font: inherit;
}

p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}

p {
  text-wrap: pretty;
}
h1, h2, h3, h4, h5, h6 {
  text-wrap: balance;
}

#root, # {
  isolation: isolate;
}
```

### Rules Breakdown

| Rule / Selector                          | Purpose                                                                 | Why It's Useful |
|------------------------------------------|-------------------------------------------------------------------------|-----------------|
| `*, *::before, *::after { box-sizing: border-box; }` | Makes width/height include padding and border                          | Prevents unexpected layout shifts and overflow issues |
| `*:not(dialog) { margin: 0; }`          | Removes default margins from all elements (except dialog)              | Gives full control over spacing; keeps dialog centering |
| `@media (prefers-reduced-motion: no-preference) { html { interpolate-size: allow-keywords; } }` | Enables smooth animations between sizes like `0` and `auto`           | Modern animation improvement (with user preference respect) |
| `body { line-height: 1.5; }`            | Sets more readable default line spacing                                | Improves legibility, especially for dyslexia |
| `body { -webkit-font-smoothing: antialiased; }` | Improves text rendering on macOS/high-DPI screens                      | Cleaner, sharper text appearance |
| `img, picture, video, canvas, svg { display: block; max-width: 100%; }` | Makes media block-level and responsive                                 | Eliminates unwanted gaps and prevents overflow |
| `input, button, textarea, select { font: inherit; }` | Forces form controls to inherit font styles from parent                | Consistent typography and prevents mobile zoom issues |
| `p, h1–h6 { overflow-wrap: break-word; }` | Allows long words to break to prevent overflow                         | Avoids horizontal scrollbars on narrow containers |
| `p { text-wrap: pretty; }`              | Better paragraph wrapping (avoids orphan words)                        | More aesthetically pleasing body text |
| `h1–h6 { text-wrap: balance; }`         | Balances heading line lengths                                          | Cleaner, more professional multi-line headings |
| `#root, # { isolation: isolate; }`      | Creates a new stacking context at the app root                         | Helps manage z-index/modals/overlays without conflicts (React-friendly) |

### Key Benefits
- Very lightweight (only ~12 declarations)
- Modern CSS features (text-wrap, interpolate-size)
- Respects user preferences (`prefers-reduced-motion`)
- Improves accessibility and readability
- Easy to customize and extend
