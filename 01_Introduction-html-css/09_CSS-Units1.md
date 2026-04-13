### Core Concepts
- Every CSS property accepts specific **value types**.
- Values can be **keywords**, **numbers**, **dimensions** (number + unit), **functions**, or combinations.
- **Absolute** units are fixed; **relative** units scale with context (preferred for responsive design).
- Always check a property’s syntax on MDN for allowed values.

### Main Value Types

| Value Type          | Description                                      | Syntax Example                  | Common Use |
|---------------------|--------------------------------------------------|---------------------------------|------------|
| **<integer>**      | Whole numbers (positive or negative)            | `2`, `-5`                      | `z-index`, `column-count` |
| **<number>**       | Decimal numbers (unitless)                      | `0.75`, `1.5`, `-0.2`          | `opacity`, `flex-grow` |
| **<percentage>**   | Relative to parent or reference value           | `50%`, `100%`                  | `width`, `font-size` |
| **<length>**       | Dimension for size/spacing                      | `20px`, `2em`, `5vh`           | `margin`, `padding`, `width` |
| **<time>**         | Duration for animations/transitions             | `2s`, `500ms`                  | `transition-duration` |
| **<angle>**        | Rotation or direction                           | `45deg`, `0.5turn`, `1rad`     | `transform: rotate()` |
| **<color>**        | Color values                                    | `#ff0000`, `rgb(255 0 0)`      | `color`, `background-color` |
| **<image>**        | Images or gradients                             | `url(image.jpg)`, `linear-gradient()` | `background-image` |
| **<position>**     | 2D position (x, y)                              | `center`, `top left`, `50% 20px` | `background-position` |

### Length Units

#### Absolute Lengths (Fixed size)
| Unit | Name              | Equivalent          | Best For          |
|------|-------------------|---------------------|-------------------|
| `px` | Pixels           | Base unit           | Screens (most common) |
| `cm` | Centimeters      | ~37.8px             | Print             |
| `mm` | Millimeters      | 0.1cm               | Print             |
| `in` | Inches           | 96px                | Print             |
| `pt` | Points           | 1/72 inch           | Print             |
| `pc` | Picas            | 12pt                | Print             |

#### Relative Lengths (Scalable – Recommended)
| Unit   | Relative To                          | Example                     | Notes |
|--------|--------------------------------------|-----------------------------|-------|
| `em`   | Parent element’s font-size          | `1.5em`                    | Compounds in nesting |
| `rem`  | Root (`<html>`) font-size           | `1.2rem`                   | Consistent, preferred |
| `vw`   | 1% of viewport width                | `50vw`                     | Responsive |
| `vh`   | 1% of viewport height               | `100vh`                    | Full height |
| `%`    | Parent/container value              | `80%`                      | Very common |

### Colors

| Format          | Syntax Example                              | Notes |
|-----------------|---------------------------------------------|-------|
| **Keyword**    | `red`, `hotpink`, `transparent`            | Easy to read |
| **Hex**        | `#ff0000`, `#f00` (shorthand)              | Most common |
| **RGB**        | `rgb(255 0 0)`, `rgb(100% 0% 0%)`          | Modern space-separated |
| **RGBA**       | `rgb(255 0 0 / 0.5)`                       | Alpha with `/` |
| **HSL**        | `hsl(0 100% 50%)`                          | Intuitive for adjustments |
| **HSLA**       | `hsl(0 100% 50% / 0.5)`                    | With alpha |

### Functions (Dynamic Values)

| Function       | Purpose                              | Example |
|----------------|--------------------------------------|---------|
| `calc()`      | Math calculations                   | `calc(100% - 20px)` |
| `min()` / `max()` | Choose smallest/largest value      | `min(50vw, 600px)` |
| `clamp()`     | Value between min and max           | `clamp(1rem, 2.5vw, 3rem)` |
| `rgb()` / `hsl()` | Color creation                     | See Colors section |
| `url()`       | Reference external resources        | `url("image.jpg")` |
