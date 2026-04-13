### Main Root
| Element     | Description |
|-------------|-------------|
| `<html>`   | Root element of an HTML document. All other elements are descendants. |

### Document Metadata
| Element     | Description |
|-------------|-------------|
| `<base>`   | Specifies base URL for relative URLs in the document (only one allowed). |
| `<head>`   | Contains metadata about the document (title, scripts, styles, etc.). |
| `<link>`   | Links external resources (e.g., CSS, favicons, manifests). |
| `<meta>`   | Represents metadata not covered by other elements (charset, viewport, etc.). |
| `<style>`  | Contains CSS style rules for the document. |
| `<title>`  | Defines the document title (shown in browser tab/title bar). |

### Sectioning Root
| Element     | Description |
|-------------|-------------|
| `<body>`   | Contains the visible content of the HTML document (only one allowed). |

### Content Sectioning
| Element      | Description |
|--------------|-------------|
| `<address>` | Contact information for the author/organization. |
| `<article>` | Self-contained, independently distributable content (e.g., blog post). |
| `<aside>`   | Content indirectly related to the main content (e.g., sidebar). |
| `<footer>`  | Footer for its nearest sectioning content (author, copyright, links). |
| `<header>`  | Introductory or navigational content (logo, nav, headings). |
| `<h1>` to `<h6>` | Section headings (h1 highest level, h6 lowest). |
| `<hgroup>` | Groups a heading with secondary content (subheadings, taglines). |
| `<main>`    | Dominant/main content of the document. |
| `<nav>`     | Navigation links section. |
| `<section>` | Generic standalone section (should have a heading). |
| `<search>`  | Container for search/filter form controls. |

### Text Content
| Element       | Description |
|---------------|-------------|
| `<blockquote>`| Extended quotation (can include `cite` attribute). |
| `<dd>`        | Description/definition in a `<dl>`. |
| `<div>`       | Generic flow content container (no semantic meaning). |
| `<dl>`        | Description list (terms + descriptions). |
| `<dt>`        | Term/name in a `<dl>`. |
| `<figcaption>`| Caption for a `<figure>`. |
| `<figure>`    | Self-contained content with optional caption. |
| `<hr>`        | Thematic break (e.g., topic change). |
| `<li>`        | List item (in `<ul>`, `<ol>`, or `<menu>`). |
| `<menu>`      | Unordered list of items (semantic alternative to `<ul>`). |
| `<ol>`        | Ordered (numbered) list. |
| `<p>`         | Paragraph of content. |
| `<pre>`       | Preformatted text (preserves whitespace, monospaced). |
| `<ul>`        | Unordered (bulleted) list. |

### Inline Text Semantics (common examples)
| Element     | Description |
|-------------|-------------|
| `<a>`      | Hyperlink. |
| `<abbr>`   | Abbreviation or acronym. |
| `<b>`      | Bold text (stylistic, no semantic emphasis). |
| `<br>`     | Line break. |
| `<cite>`   | Title of a cited creative work. |
| `<code>`   | Computer code snippet. |
| `<em>`     | Emphasized text (usually italic). |
| `<i>`      | Italic text (stylistic, e.g., foreign words). |
| `<mark>`   | Highlighted/ marked text. |
| `<q>`      | Short inline quotation. |
| `<span>`   | Generic inline container. |
| `<strong>` | Strong importance (usually bold). |
| `<time>`   | Machine-readable date/time. |

### Image & Multimedia
| Element      | Description |
|--------------|-------------|
| `<audio>`   | Audio player. |
| `<img>`     | Image (use `src`, `alt`, `width`, `height`). |
| `<picture>` | Container for multiple image sources (responsive). |
| `<source>`  | Media resource for `<picture>`, `<audio>`, `<video>`. |
| `<track>`   | Text track for `<video>` or `<audio>` (subtitles). |
| `<video>`   | Video player. |

### Embedded Content / iframes / Objects
| Element     | Description |
|-------------|-------------|
| `<embed>`  | Embedded external content (plugins). |
| `<iframe>` | Inline frame (nested browsing context). |
| `<object>` | Embedded external resource (fallback content supported). |

### SVG & MathML
| Element | Description |
|---------|-------------|
| `<svg>` | Inline SVG vector image container. |
| `<math>`| MathML mathematical expressions. |

### Scripting
| Element    | Description |
|------------|-------------|
| `<canvas>`| Graphics/scriptable bitmap canvas. |
| `<noscript>`| Content shown when JavaScript is disabled. |
| `<script>`| Embedded or external JavaScript. |

### Table Content
| Element     | Description |
|-------------|-------------|
| `<caption>`| Table caption. |
| `<col>`    | Column properties. |
| `<colgroup>`| Group of columns. |
| `<table>`  | Table. |
| `<tbody>`  | Table body rows. |
| `<td>`     | Table data cell. |
| `<tfoot>`  | Table footer rows. |
| `<th>`     | Table header cell. |
| `<thead>`  | Table header rows. |
| `<tr>`     | Table row. |

### Forms
| Element       | Description |
|---------------|-------------|
| `<button>`   | Clickable button. |
| `<datalist>` | Predefined options for `<input>`. |
| `<fieldset>` | Groups form controls with legend. |
| `<form>`     | Form container for user input. |
| `<input>`    | Various input types (text, checkbox, radio, etc.). |
| `<label>`    | Label for a form control. |
| `<legend>`   | Caption for `<fieldset>`. |
| `<meter>`    | Scalar gauge (e.g., disk usage). |
| `<optgroup>` | Group of options in `<select>`. |
| `<option>`   | Option in `<select>` or `<datalist>`. |
| `<output>`   | Result of calculation or user action. |
| `<progress>` | Progress bar. |
| `<select>`   | Dropdown/select menu. |
| `<textarea>` | Multi-line text input. |

### Interactive Elements
| Element      | Description |
|--------------|-------------|
| `<details>` | Collapsible disclosure widget. |
| `<dialog>`  | Modal dialog box. |
| `<summary>` | Summary/caption for `<details>`. |

### Obsolete / Deprecated Elements (avoid in new code)
| Element     | Description / Note |
|-------------|--------------------|
| `<acronym>`| Use `<abbr>` instead. |
| `<applet>` | Use `<object>` or `<embed>`. |
| `<bgsound>`| Deprecated audio background. |
| `<big>`    | Use CSS. |
| `<center>` | Use CSS. |
| `<font>`   | Use CSS. |
| `<frame>` / `<frameset>` | Deprecated framing. |
| `<marquee>`| Use CSS animations. |
| `<nobr>`   | Use CSS `white-space`. |
| `<strike>` / `<s>` (in some contexts) | Use CSS or semantic alternatives. |

