### Overview
HTML5 **Constraint Validation** lets browsers automatically validate form inputs using HTML attributes (no JavaScript needed for basic checks). The **Constraint Validation API** provides JavaScript control for custom logic, error messages, and styling.  

**Key Rule**: Client-side validation improves UX but is **not secure** — always validate on the server.

### 1. Validation Methods Comparison

| Method                        | Description                                      | Pros                                      | Cons / When to Use |
|-------------------------------|--------------------------------------------------|-------------------------------------------|--------------------|
| **Built-in (Declarative)**   | HTML attributes (`required`, `pattern`, `type`, etc.) | No JS, fast, accessible defaults         | Limited customization, default messages |
| **Constraint Validation API** | JavaScript (`checkValidity()`, `setCustomValidity()`) | Custom messages, complex logic, async checks | More code required |
| **Custom JS (Manual)**       | Full manual checks + `preventDefault()`          | Complete control                         | Harder to maintain, accessibility challenges |

### 2. Core HTML Validation Attributes

| Attribute          | Applies To                  | Purpose                                      | Example |
|--------------------|-----------------------------|----------------------------------------------|---------|
| `required`        | Most inputs                | Field must not be empty                     | `<input type="text" required>` |
| `minlength` / `maxlength` | Text, textarea            | Minimum/maximum character length            | `minlength="3" maxlength="20"` |
| `min` / `max`     | number, range, date, etc.  | Numeric or date range                       | `min="1" max="100"` |
| `step`            | number, range              | Allowed increment                           | `step="0.5"` |
| `type`            | `<input>`                  | Built-in format validation (email, url, number, tel, etc.) | `type="email"` |
| `pattern`         | Text inputs                | Regex pattern matching                      | `pattern="[A-Z]+"` |
| `novalidate`      | `<form>`                   | Disable browser auto-validation             | `<form novalidate>` |
| `formnovalidate`  | Submit button              | Disable validation for this submit only     | `<button formnovalidate>` |

### 3. Constraint Validation API – Properties & Methods

| Item                          | Type       | Description |
|-------------------------------|------------|-------------|
| `input.validity`             | Object    | `ValidityState` object with detailed flags |
| `input.validity.valid`       | Boolean   | `true` if all constraints passed |
| `input.validity.valueMissing`| Boolean   | `required` but empty |
| `input.validity.typeMismatch`| Boolean   | Wrong format (e.g., bad email) |
| `input.validity.patternMismatch` | Boolean | Doesn't match `pattern` |
| `input.validity.tooShort` / `tooLong` | Boolean | Length violation |
| `input.validity.rangeUnderflow` / `rangeOverflow` | Boolean | Outside `min`/`max` |
| `input.validity.stepMismatch`| Boolean   | Not a multiple of `step` |
| `input.validity.customError` | Boolean   | Custom message set via JS |
| `input.validationMessage`    | String    | Current error message (localized) |
| `input.checkValidity()`      | Method    | Returns `true/false`; triggers `invalid` event |
| `input.reportValidity()`     | Method    | Checks + shows browser error bubble |
| `input.setCustomValidity(msg)` | Method  | Set custom error (`""` to clear) |

### 4. CSS Pseudo-Classes for Styling

| Pseudo-class          | When It Applies                          | Common Use |
|-----------------------|------------------------------------------|----------|
| `:valid`             | Element passes all constraints          | Green border |
| `:invalid`           | Fails at least one constraint           | Red border |
| `:user-invalid`      | Invalid after user interaction (Firefox) | Show errors only after typing |
| `:required`          | Has `required` attribute                | Add asterisk style |
| `:optional`          | No `required`                           | — |
| `:in-range` / `:out-of-range` | Numeric/date within/outside bounds | Visual range feedback |

**Tip**: Combine with `.invalid .help { display: block; }` for custom error messages.

### 5. UX & Accessibility Best Practices

| Practice                              | Recommendation |
|---------------------------------------|----------------|
| **Error Placement**                  | Show errors **near the specific input**, not in one central list |
| **Submit Button**                    | Keep enabled — allow click to reveal all errors |
| **Error Messages**                   | Use clear, human-readable language (no jargon) |
| **Visual Cues**                      | Add exclamation icon + color for colorblind users |
| **Prevention > Correction**          | Show password rules upfront |
| **Positive Feedback**                | Show success states too |
| **Timing**                           | Validate on `blur` / `input` / `submit` (not too aggressively) |
| **Accessibility**                    | Use `aria-live` for dynamic errors; ensure labels and focus management |

### 6. Common Patterns & Examples

**Basic HTML Validation**
```html
<form>
  <input type="email" required>
  <input type="password" minlength="8" pattern="(?=.*\d).{8,}">
  <button type="submit">Submit</button>
</form>
```

**Custom Validation with JS**
```javascript
const email = document.getElementById('email');

email.addEventListener('input', () => {
  email.setCustomValidity(''); // Clear previous

  if (email.validity.typeMismatch) {
    email.setCustomValidity('Please enter a valid email address.');
  } else if (!email.value.endsWith('@company.com')) {
    email.setCustomValidity('Only @company.com emails allowed.');
  }
});
```

**Prevent Default + Custom UI**
```javascript
form.addEventListener('submit', (e) => {
  if (!form.checkValidity()) {
    e.preventDefault();
    // Show custom error messages near fields
  }
});
```

### 7. Limitations & Important Notes
- Custom error bubbles cannot be fully styled (browser-controlled).
- Complex logic (password match, async username check) requires JavaScript.
- Older browsers fall back gracefully (`type="text"`).
- Never trust client-side validation for security.