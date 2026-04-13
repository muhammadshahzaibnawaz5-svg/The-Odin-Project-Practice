### 1. Combinators

| Selector Pattern          | Syntax Example               | What It Selects                                      | Use Case / Description |
|---------------------------|------------------------------|------------------------------------------------------|------------------------|
| **Descendant**           | `article h2`                | All `h2` elements inside `article` (any nesting level) | Style nested content deeply |
| **Direct Child**         | `article > p`               | Only `p` elements that are **direct** children of `article` | Target immediate children only |
| **General Sibling**      | `h2 ~ p`                    | All `p` elements that follow an `h2` (same parent)  | Style all following siblings |
| **Adjacent Sibling**     | `h2 + p`                    | The `p` element that **immediately** follows an `h2` (same parent) | Style the very next sibling |

### 2. Attribute Selectors

| Selector Pattern                  | Syntax Example                      | What It Selects                                      | Use Case |
|-----------------------------------|-------------------------------------|------------------------------------------------------|----------|
| **Attribute Present**            | `a[target]`                        | Any `<a>` with a `target` attribute                 | Style links that open in new tab |
| **Attribute Equals**             | `a[href="https://example.com"]`    | `<a>` with exact `href` value                       | Target specific links |
| **Attribute Contains**           | `a[href*="example"]`               | `<a>` where `href` contains "example"               | Partial URL matching |
| **Attribute Begins With**        | `a[href^="https://"]`              | `<a>` where `href` starts with "https://"           | Style secure (HTTPS) links |
| **Attribute Ends With**          | `a[href$=".pdf"]`                  | `<a>` where `href` ends with ".pdf"                 | Style PDF download links |
| **Attribute Word (Spaced)**      | `a[rel~="tag"]`                    | `rel` attribute contains the word "tag" (space-separated) | Style tags in `rel` attribute |
| **Attribute Hyphenated**         | `a[lang|="en"]`                   | `lang` starts with "en" (e.g., en-US, en-GB)        | Style language-specific content |

### 3. Pseudo-classes

| Category                     | Selector                  | Syntax Example          | What It Selects                                      | Common Use |
|------------------------------|---------------------------|-------------------------|------------------------------------------------------|------------|
| **Link State**              | `:link`                  | `a:link`               | Unvisited links                                     | Default link styling |
| **Link State**              | `:visited`               | `a:visited`            | Visited links                                       | Style visited links |
| **User Action**             | `:hover`                 | `a:hover`              | Mouse over element                                  | Hover effects |
| **User Action**             | `:active`                | `a:active`             | Element being clicked/activated                     | Click feedback |
| **User Action**             | `:focus`                 | `a:focus`              | Element has keyboard focus                          | Accessibility focus styles |
| **Form State**              | `:enabled`               | `input:enabled`        | Enabled form controls                               | Form styling |
| **Form State**              | `:disabled`              | `input:disabled`       | Disabled form controls                              | Show disabled state |
| **Form State**              | `:checked`               | `input:checked`        | Checked checkboxes/radio buttons                    | Style selected options |
| **Form State**              | `:indeterminate`         | `input:indeterminate`  | Indeterminate form controls                         | Special checkbox states |

### Quick Reference Summary

| Type                  | Most Useful For                              | Example |
|-----------------------|----------------------------------------------|---------|
| **Combinators**      | Controlling nesting and sibling relationships | `nav > ul > li` |
| **Attribute Selectors** | Targeting based on HTML attributes          | `a[href$=".pdf"]` |
| **Pseudo-classes**   | Styling based on state or user interaction  | `button:hover, input:focus` |

**Best Practices from the Article**:
- Combine selectors wisely (e.g., `article > p:first-child`).
- Keep selectors as simple as possible for better performance.
- Use child (`>`) and adjacent sibling (`+`) when you want to be more specific.
- Attribute selectors are powerful for styling links based on `href`, `target`, `rel`, etc.
- Always test `:hover`, `:focus`, and `:active` for good user experience and accessibility.