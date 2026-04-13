### Quick Summary
Custom properties (declared with `--name: value;`) are **inherited** by default from the parent element, just like many CSS properties. They participate in the cascade.  
Defining them on `:root` makes them **globally available** to all descendants.

Unlike traditional programming variables, their values are resolved at the point of use via `var()`.

### Inheritance Comparison Table

| Aspect                        | Custom Properties (`--var`)                          | Regular CSS Properties                          | Key Difference |
|-------------------------------|------------------------------------------------------|-------------------------------------------------|---------------|
| **Inheritance**              | Always inherit from parent (by default)             | Inherit only if the property is "inherited" type | Custom props always inherit unless controlled |
| **Scope**                    | Scoped to the element + descendants                 | Depends on the property                        | Custom props are highly flexible for theming |
| **Global Definition**        | Best practice: declare on `:root`                   | Not typically done this way                    | `:root` acts as the highest ancestor |
| **Control Inheritance**      | Use `@property` with `inherits: false`             | Cannot disable inheritance for inherited props | `@property` gives extra control |
| **Value Resolution**         | Computed where used (`var()`)                       | Computed immediately                           | Dynamic & context-dependent |
| **Case Sensitivity**         | Yes (`--color` ≠ `--Color`)                         | No                                             | Important for naming |

### Core Rules

- **Default Behavior**: A custom property not set on an element inherits the value from its nearest ancestor that defines it.
- **:root Usage**: Placing variables on `:root` makes them available everywhere (global scope).
  ```css
  :root {
    --main-bg-color: teal;
  }
  ```
- **Local Scoping**: Variables set on a specific class or element only affect that element and its descendants.
- **Invalid Values**: If a custom property resolves to an invalid value in context, the declaration is ignored, and the property falls back to its initial or inherited value.

### Practical Examples Table

| Example Type                  | CSS Code                                                                 | HTML Structure Summary                          | Result / Explanation |
|-------------------------------|--------------------------------------------------------------------------|-------------------------------------------------|----------------------|
| **Basic Inheritance**        | `div { background-color: var(--box-color); }`<br>`.two { --box-color: teal; }`<br>`.three { --box-color: pink; }` | `.one > .two > (.three, .four)`                | `.one`: invalid (default)<br>`.two`: teal<br>`.three`: pink<br>`.four`: teal (inherits from `.two`) |
| **Global with :root**        | `:root { --main-bg-color: teal; }`                                      | Any element                                     | All descendants can use `var(--main-bg-color)` unless overridden |
| **Disable Inheritance**      | `@property --box-color { syntax: "<color>"; inherits: false; initial-value: teal; }`<br>`.parent { --box-color: green; }` | `.parent > .child`                             | `.child` gets `teal` (initial-value), **not** `green` from parent |
| **Fallback in var()**        | `color: var(--text-color, black);`                                      | Any element                                     | Uses `--text-color` if defined; otherwise `black` |

### Key Notes & Tips
- **@property At-Rule** — Allows advanced control:
  - `syntax`: Type constraint (e.g., `"<color>"`, `"<length>"`)
  - `inherits`: `true` or `false`
  - `initial-value`: Default when no value is set or inherited
- **Fallback Values**:
  - In `var(--name, fallback-value)`
  - Via `@property` `initial-value`
- Custom properties are **not** like Sass/Less variables — they are live in the CSS cascade and can be changed dynamically with JavaScript.
- They work great for **theming**, **component styling**, and **reducing repetition**.
- Values are **computed at use time**, not stored globally like in programming languages.