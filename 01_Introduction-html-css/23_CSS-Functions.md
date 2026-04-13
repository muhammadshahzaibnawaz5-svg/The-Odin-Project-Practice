### CSS Value Functions Overview
CSS **value functions** are special notations that compute or generate values for CSS properties. They start with the function name followed by parentheses `()` and can accept arguments.

**Syntax Example:**
```css
property: function-name(argument1, argument2);
```

### 1. Transform Functions
Used with the `transform` property for 2D/3D manipulations.

| Function              | Description                                      | Syntax Example                          | Primary Use |
|-----------------------|--------------------------------------------------|-----------------------------------------|-------------|
| `translate()`        | Moves element in 2D space                       | `translate(50px, 30px)`                | Positioning |
| `translateX()`       | Moves horizontally                              | `translateX(100px)`                    | Horizontal shift |
| `translateY()`       | Moves vertically                                | `translateY(50px)`                     | Vertical shift |
| `translateZ()`       | Moves along z-axis (3D)                         | `translateZ(100px)`                    | 3D depth |
| `translate3d()`      | 3D translation                                  | `translate3d(50px, 30px, 100px)`       | Full 3D move |
| `rotate()`           | Rotates in 2D plane                             | `rotate(45deg)`                        | 2D rotation |
| `rotateX()`          | Rotates around x-axis (3D)                      | `rotateX(30deg)`                       | 3D tilt |
| `rotateY()`          | Rotates around y-axis (3D)                      | `rotateY(45deg)`                       | 3D spin |
| `rotateZ()`          | Rotates around z-axis                           | `rotateZ(90deg)`                       | 2D/3D rotation |
| `rotate3d()`         | Rotates around custom axis                      | `rotate3d(1, 1, 1, 45deg)`             | Advanced 3D |
| `scale()`            | Scales in 2D                                    | `scale(1.5)` or `scale(1.2, 0.8)`      | Resize |
| `scaleX()` / `scaleY()` | Scales horizontally or vertically             | `scaleX(2)`                            | Non-uniform scale |
| `scaleZ()`           | Scales along z-axis                             | `scaleZ(1.5)`                          | 3D scale |
| `scale3d()`          | 3D scaling                                      | `scale3d(1.5, 1.5, 2)`                 | Full 3D scale |
| `skew()`             | Skews (shears) in 2D                            | `skew(20deg, 10deg)`                   | Distortion |
| `skewX()` / `skewY()`| Horizontal or vertical skew                     | `skewX(30deg)`                         | 2D shear |
| `matrix()`           | 2D transformation matrix                        | `matrix(1, 0, 0, 1, 50, 50)`           | Low-level 2D |
| `matrix3d()`         | 3D transformation matrix                        | `matrix3d(...)` (16 values)            | Advanced 3D |
| `perspective()`      | Sets 3D perspective distance                    | `perspective(500px)`                   | 3D depth effect |

### 2. Math Functions
Allow calculations inside CSS values (great for responsive design).

| Function         | Description                                              | Syntax Example                          | Primary Use |
|------------------|----------------------------------------------------------|-----------------------------------------|-------------|
| `calc()`        | Basic arithmetic calculations                           | `calc(100% - 20px)`                    | Dynamic sizes |
| `min()`         | Returns the smallest value from a list                  | `min(50vw, 400px)`                     | Responsive min |
| `max()`         | Returns the largest value from a list                   | `max(50vw, 400px)`                     | Responsive max |
| `clamp()`       | Clamps a value between min and max                      | `clamp(1rem, 2.5vw, 3rem)`             | Fluid typography |
| `round()`       | Rounds a number with different strategies               | `round(3.7)`                           | Precise values |
| `mod()`         | Modulus (remainder with sign of divisor)                | `mod(10, 3)`                           | Cyclic values |
| `rem()`         | Remainder (sign of dividend)                            | `rem(10, 3)`                           | Remainder calc |

### 3. Filter Functions
Used with the `filter` property for visual effects on images/elements.

| Function             | Description                                      | Common Example |
|----------------------|--------------------------------------------------|----------------|
| `blur()`            | Applies Gaussian blur                           | `blur(5px)` |
| `brightness()`      | Adjusts brightness                              | `brightness(1.5)` |
| `contrast()`        | Adjusts contrast                                | `contrast(120%)` |
| `grayscale()`       | Converts to grayscale                           | `grayscale(100%)` |
| `hue-rotate()`      | Rotates hue in color wheel                      | `hue-rotate(90deg)` |
| `invert()`          | Inverts colors                                  | `invert(80%)` |
| `opacity()`         | Changes transparency                            | `opacity(0.5)` |
| `saturate()`        | Adjusts saturation                              | `saturate(200%)` |
| `sepia()`           | Applies sepia tone                              | `sepia(50%)` |
| `drop-shadow()`     | Adds shadow (similar to `box-shadow`)           | `drop-shadow(4px 4px 8px rgba(0,0,0,0.5))` |

### 4. Color & Image Functions

| Function                  | Description                                      | Common Use |
|---------------------------|--------------------------------------------------|------------|
| `rgb()` / `rgba()`       | Defines colors (modern space-separated syntax)  | Colors |
| `hsl()` / `hsla()`       | Hue, saturation, lightness colors               | Colors |
| `linear-gradient()`      | Creates linear color gradients                  | Backgrounds |
| `radial-gradient()`      | Creates radial (circular) gradients             | Backgrounds |
| `conic-gradient()`       | Creates angular gradients                       | Backgrounds |
| `url()`                  | References external resources (images, fonts)   | Background-image, @font-face |

### 5. Other Notable Functions
- `attr()` – Returns attribute value
- `var()` – Uses custom properties (CSS variables)
- `counter()` / `counters()` – For generated content
- `shape()` functions – For `clip-path` and `shape-outside`

**Best Practices:**
- Combine functions: e.g., `transform: translate(50px) rotate(45deg);`
- Use `calc()`, `clamp()`, `min()`, and `max()` heavily for responsive/fluid designs.
- Prefer modern syntax (e.g., `rgb(255 0 0 / 0.5)` instead of `rgba()`).
- Always test transform functions with `transform-origin` for better control.