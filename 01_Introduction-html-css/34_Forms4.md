### Tutorial Overview
This practical tutorial teaches how to build a complete speaker submission form using semantic HTML and clean CSS. It emphasizes **mobile-first** design, proper labeling for accessibility, form submission basics, and the challenges of styling form controls. The focus is on the frontend (HTML + CSS) — backend processing is out of scope.

**Key Concepts**:
- Forms collect user input (e.g., contact, registration, e-commerce).
- Use `<form>` with `action` (destination URL) and `method` (`get` or `post`).
- Always associate `<label>` with inputs using `for` and `id`.
- `name` attributes determine the data keys sent to the server.
- Browser provides basic validation (e.g., `type="email"`, `required`).
- Styling forms is tricky due to inconsistent browser defaults.

### Form Structure & Attributes

| Element / Attribute          | Purpose                                      | Common Usage & Notes |
|-----------------------------|----------------------------------------------|----------------------|
| `<form action="" method="get">` | Container for all inputs                     | `action`: URL to send data<br>`method`: `get` (URL params) or `post` (body) |
| `<div class="form-row">`    | Wrapper for label + control (for layout)    | Helps with flexbox styling |
| `<label for="id">`          | Text label linked to input                   | Required for accessibility |
| `id` / `name`               | `id` for label association<br>`name` for submitted data | Use matching `id` and `name` |

### Core Form Controls

| Control Type                | HTML Code Example                                                                 | Key Attributes & Notes |
|-----------------------------|-----------------------------------------------------------------------------------|------------------------|
| **Text Input**             | `<input id="full-name" name="full-name" type="text">`                           | Single-line text |
| **Email Input**            | `<input id="email" name="email" type="email" placeholder="joe@example.com">`   | Built-in validation + mobile keyboard |
| **Radio Buttons**          | `<input type="radio" name="talk-type" value="workshop" checked>` + `<label>`   | Same `name` for grouping<br>Use `<fieldset>` + `<legend>` |
| **Select (Dropdown)**      | `<select name="t-shirt"><option value="m">Medium</option></select>`             | Hardest to style consistently |
| **Textarea**               | `<textarea name="abstract">Default text here</textarea>`                        | Multi-line input<br>Content between tags = default value |
| **Checkbox**               | `<input type="checkbox" name="available" value="is-available">`                 | Multiple allowed<br>Often wrapped in `<label>` |
| **Submit Button**          | `<button type="submit">Submit</button>`                                         | Triggers validation + submission |

### Important Attributes

| Attribute       | Applies To          | Purpose |
|-----------------|---------------------|---------|
| `placeholder`  | Text/email inputs  | Hint text inside field |
| `required`     | Most inputs        | Browser validation |
| `checked`      | Radio / Checkbox   | Pre-select |
| `value`        | Inputs / Options   | Data sent to server |
| `minlength` / `maxlength` | Text inputs     | Length validation |
| `pattern`      | Text inputs        | Regex validation |

### Styling Tips & Techniques

| Aspect                     | Recommendation                                                                 | Notes |
|----------------------------|--------------------------------------------------------------------------------|-------|
| **Mobile-First Layout**   | Base styles: `flex-direction: column`<br>Media query (`min-width: 700px`): switch to row | Labels on left on desktop |
| **Form Container**        | Background, border, padding, max-width                                         | Match header style |
| **Input Styling**         | Use attribute selectors: `input[type="text"]`, `input[type="email"]`           | Consistent padding, borders, focus states |
| **Validation Feedback**   | `:valid`, `:invalid`, `:focus` pseudo-classes                                  | Visual cues for users |
| **Radio / Checkbox**      | Use `.legacy-form-row` with floats (flexbox support is limited on fieldset)   | Custom classes for alignment |
| **Select Dropdown**       | `-webkit-appearance: none;` as a hack                                          | Cross-browser inconsistencies remain |
| **Textarea**              | `resize: none;` to disable user resizing                                       | Add instructions below |
| **Button**                | Style like other elements + `:hover`, `:active` states                        | Full control possible |

### Form Submission Behavior
- Clicking **Submit** triggers browser validation.
- With `method="get"`, data appears in the URL as query parameters:  
  `?full-name=Rick&email=rick%40example.com&talk-type=workshop`
- Real-world use requires a backend (or AJAX) to process the data.

### Summary of Covered Elements
- `<input type="text">`
- `<input type="email">`
- `<input type="radio">`
- `<input type="checkbox">`
- `<select>` + `<option>`
- `<textarea>`
- `<button type="submit">`
- `<fieldset>` + `<legend>` (for grouping)

### Best Practices Highlighted
- Always use semantic markup (`<label>`, `<fieldset>`, `<legend>`).
- Scope CSS with classes (`.form-row`) instead of global selectors.
- Test on mobile and desktop.
- Forms are critical for user interaction — invest in good UX and accessibility.
- Styling forms requires patience due to browser differences.