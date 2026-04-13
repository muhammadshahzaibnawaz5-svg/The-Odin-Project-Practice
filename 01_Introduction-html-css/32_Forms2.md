### Overview
The **"The different form controls"** section in MDN's Learn Web Forms path explains all native HTML form widgets (controls). It is divided into three sub-articles:

- **Basic native form controls** — Original HTML `<input>` types (since early web days).
- **The HTML5 input types** — Newer semantic input types with built-in validation and specialized UIs.
- **Other form controls** — Non-`<input>` elements like multi-line text, dropdowns, and progress indicators.

All controls are placed inside a `<form>` element. Use `<label>`, `<fieldset>`, and `<legend>` for accessibility and grouping.

### 1. Basic Native Form Controls

| Control Type          | HTML Element                          | Purpose                                      | Key Attributes & Notes                                                                 | Example |
|-----------------------|---------------------------------------|----------------------------------------------|----------------------------------------------------------------------------------------|---------|
| **Text**             | `<input type="text">`                | Single-line text input (default)            | `placeholder`, `maxlength`, `size`, `readonly`, `disabled`, `spellcheck`              | `<input type="text" name="username">` |
| **Password**         | `<input type="password">`            | Masked password input                       | Same as text; data sent in plain text (use HTTPS)                                      | `<input type="password" name="pwd">` |
| **Hidden**           | `<input type="hidden">`              | Send data without showing to user           | Requires `name` and `value`; not visible or focusable                                  | `<input type="hidden" name="token" value="abc123">` |
| **Checkbox**         | `<input type="checkbox">`            | Toggle on/off (multiple allowed)            | `checked`; only sends value if checked; group with `<fieldset>`                        | `<input type="checkbox" name="subscribe" checked>` |
| **Radio**            | `<input type="radio">`               | Select one from a group                     | Same `name` for grouping; `checked`; only one can be selected                         | `<input type="radio" name="color" value="red">` |
| **File**             | `<input type="file">`                | File upload                                 | `accept`, `multiple`, `capture` (camera)                                               | `<input type="file" accept="image/*" multiple>` |
| **Submit**           | `<input type="submit">` or `<button type="submit">` | Send form data                              | `<button>` allows rich content and better styling                                      | `<button type="submit">Send</button>` |
| **Reset**            | `<input type="reset">` or `<button type="reset">` | Reset form to default values                | —                                                                                      | `<input type="reset" value="Clear">` |
| **Button**           | `<input type="button">` or `<button type="button">` | Custom button (no default action)           | Use JavaScript for functionality; `<button>` is preferred                             | `<button type="button">Click me</button>` |
| **Image**            | `<input type="image">`               | Submit with click coordinates               | Behaves like submit + sends `name.x` and `name.y`                                      | `<input type="image" src="submit.png" alt="Submit">` |

### 2. HTML5 Input Types

| Input Type            | Purpose                                      | Special UI / Behavior                                      | Validation & Attributes                          | Fallback / Notes |
|-----------------------|----------------------------------------------|------------------------------------------------------------|--------------------------------------------------|------------------|
| **email**            | Email address                                | @ key on mobile keyboard                                   | Built-in email format validation; supports `multiple` | Treat as text in old browsers |
| **search**           | Search queries                               | Clear button, rounded corners, search icon on Enter        | No special validation                            | Behaves like text |
| **tel**              | Telephone number                             | Numeric keypad on mobile                                   | No built-in validation (use `pattern`)           | Good for numeric input |
| **url**              | Web address                                  | URL-specific keyboard                                      | Validates URL format                             | Requires protocol (http://) |
| **number**           | Numeric value                                | Spinner (up/down arrows)                                   | `min`, `max`, `step`; only numbers allowed       | Widely supported |
| **range**            | Numeric value within range (slider)          | Horizontal slider                                          | `min`, `max`, `step`; use `<output>` to show value | Not for precise input |
| **color**            | Color selection                              | Native color picker                                        | Returns #rrggbb (hex)                            | Good support |
| **date**             | Date selection                               | Calendar picker                                            | `min`, `max`, `step`                             | Varies by browser |
| **datetime-local**   | Date + time (no timezone)                    | Calendar + time picker                                     | `min`, `max`, `step`                             | — |
| **month**            | Month & year                                 | Month picker                                               | —                                                | — |
| **time**             | Time selection                               | Time picker (24-hour)                                      | `min`, `max`, `step`                             | — |
| **week**             | Week & year                                  | Week picker                                                | —                                                | — |

### 3. Other Form Controls

| Control               | HTML Element                          | Purpose                                      | Key Attributes & Features                                                      | Example |
|-----------------------|---------------------------------------|----------------------------------------------|--------------------------------------------------------------------------------|---------|
| **Textarea**         | `<textarea>`                         | Multi-line text input                        | `rows`, `cols`, `wrap` (`soft`/`hard`/`off`), `resize` (CSS)                   | `<textarea rows="5" cols="40"></textarea>` |
| **Select**           | `<select>` + `<option>`              | Dropdown / list selection                    | `multiple`, `size`; use `<optgroup>` for grouping                              | `<select name="fruit"><option>Apple</option></select>` |
| **Datalist**         | `<input list="id">` + `<datalist>`   | Autocomplete suggestions                     | Works with most input types; provides suggestions                              | `<input list="browsers"><datalist id="browsers">…</datalist>` |
| **Meter**            | `<meter>`                            | Scalar measurement / gauge                   | `value`, `min`, `max`, `low`, `high`, `optimum` (color-coded)                  | `<meter value="75" min="0" max="100"></meter>` |
| **Progress**         | `<progress>`                         | Task completion progress bar                 | `value`, `max`                                                                 | `<progress value="50" max="100"></progress>` |

### Common Attributes (Applicable to Most Controls)

- `name` — Required for form submission data.
- `value` — Initial or submitted value.
- `id` — For associating with `<label for="id">`.
- `autofocus`, `disabled`, `readonly`, `required`, `placeholder`.
- `form` — Associate control with a form even if outside it.

### Best Practices
- Always pair controls with proper `<label>` elements.
- Group related controls using `<fieldset>` + `<legend>`.
- Client-side validation (from HTML5 types) is helpful but **not secure** — always validate on the server.
- Older browsers treat unknown input types as `type="text"`.
- Prefer `<button>` over `<input type="button">` for better styling and content support.