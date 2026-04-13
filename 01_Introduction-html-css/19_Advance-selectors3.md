### CSS Selectors Skill Test – Solved Cheat Sheet

| Section       | Task Description                                                                 | Correct CSS Selector                          | Style Applied                                      | Selector Type |
|---------------|----------------------------------------------------------------------------------|-----------------------------------------------|----------------------------------------------------|---------------|
| **Selectors 1** | Make all `<h1>` headings blue                                                   | `h1`                                         | `color: blue;`                                    | Element (Type) |
| **Selectors 1** | Give all `<h2>` headings a blue background and white text                       | `h2`                                         | `background-color: blue; color: white;`           | Element (Type) |
| **Selectors 1** | Make text inside `<span>` 200% font size                                        | `span`                                       | `font-size: 200%;`                                | Element (Type) |
| **Selectors 2** | Give the element with `id="special"` a yellow background                        | `#special`                                   | `background-color: yellow;`                       | ID Selector |
| **Selectors 2** | Give elements with class `alert` a 2px solid grey border                        | `.alert`                                     | `border: 2px solid grey;`                         | Class Selector |
| **Selectors 2** | If an element has both `alert` and `stop` classes, make background red          | `.alert.stop`                                | `background-color: red;`                          | Multiple Classes |
| **Selectors 2** | If an element has both `alert` and `go` classes, make background green          | `.alert.go`                                  | `background-color: green;`                        | Multiple Classes |
| **Selectors 3** | Make unvisited links orange                                                     | `a:link`                                     | `color: orange;`                                  | Pseudo-class |
| **Selectors 3** | Make visited links green                                                        | `a:visited`                                  | `color: green;`                                   | Pseudo-class |
| **Selectors 3** | Remove underline from links on hover                                            | `a:hover`                                    | `text-decoration: none;`                          | Pseudo-class |
| **Selectors 3** | Make the first paragraph inside `.container` 150% font size                     | `.container p:first-child`                   | `font-size: 150%;`                                | Pseudo-class + Descendant |
| **Selectors 3** | Make the first line of that paragraph red                                       | `.container p:first-child::first-line`       | `color: red;`                                     | Pseudo-element |
| **Selectors 3** | Stripe every other table row with dark background and white text                | `tr:nth-child(even)`                         | `background-color: #333; color: white;`           | Pseudo-class (:nth-child) |
| **Selectors 4** | Make any paragraph that immediately follows an `<h2>` red                       | `h2 + p`                                     | `color: red;`                                     | Adjacent Sibling (+) |
| **Selectors 4** | Remove bullets and add 1px grey bottom border to direct child `<li>` of `.list` | `ul.list > li`                               | `list-style: none; border-bottom: 1px solid grey;` | Child Combinator (>) |
| **Selectors 5** | Give any `<a>` with a `title` attribute a pink border                           | `a[title]`                                   | `border-color: pink;`                             | Attribute Selector |
| **Selectors 5** | Give `<a>` whose `href` contains "contact" an orange border                     | `a[href*="contact"]`                         | `border-color: orange;`                           | Attribute (*= contains) |
| **Selectors 5** | Give `<a>` whose `href` starts with "https" a green border                      | `a[href^="https"]`                           | `border-color: green;`                            | Attribute (^= starts with) |

### Quick Reference – Selector Types Covered

| Selector Type              | Example                     | Purpose |
|----------------------------|-----------------------------|---------|
| **Element / Type**        | `h1`, `span`               | Target by tag name |
| **ID**                    | `#special`                 | Unique identifier |
| **Class**                 | `.alert`                   | Reusable style group |
| **Multiple Classes**      | `.alert.stop`              | Element must have both classes |
| **Pseudo-class**          | `:hover`, `:first-child`, `:nth-child(even)` | Style based on state or position |
| **Pseudo-element**        | `::first-line`             | Style specific part of an element |
| **Adjacent Sibling**      | `h2 + p`                   | Next sibling immediately after |
| **Child Combinator**      | `ul > li`                  | Direct children only |
| **Attribute**             | `[title]`, `[href*="contact"]` | Based on HTML attributes |

**Key Takeaways from the MDN Assessment**:
- Only edit the CSS (never change the HTML).
- Combine selectors when needed (e.g., class + pseudo-class, descendant + pseudo-class).
- Use `:nth-child(even)` for table striping.
- Attribute selectors are powerful for targeting links based on `href` or presence of attributes.
- `+` selects only the immediate next sibling, while space selects any descendant.