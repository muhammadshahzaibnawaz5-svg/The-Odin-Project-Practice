### 1. CSS Syntax Basics

| Type              | Example |
|-------------------|---------|
| **Rule Syntax**   | `selector { property: value; property2: value2; }` |
| **External CSS**  | `<link rel="stylesheet" type="text/css" href="style.css">` |
| **Internal CSS**  | `<style> selector { property: value; } </style>` |
| **Inline CSS**    | `<tag style="property: value;">` |

### 2. Common CSS Properties

#### Box Model & Layout
| Property              | Description                          | Common Values |
|-----------------------|--------------------------------------|---------------|
| `margin`             | Outer space                          | `10px`, `20px 0`, `auto` |
| `padding`            | Inner space                          | `10px`, `1rem` |
| `border`             | Border shorthand                     | `1px solid #000` |
| `width`              | Width of element                     | `100%`, `200px`, `50vw` |
| `height`             | Height of element                    | `100px`, `auto` |
| `box-sizing`         | Box model calculation                | `content-box`, `border-box` |
| `display`            | Display behavior                     | `block`, `inline`, `inline-block`, `flex`, `grid`, `none` |
| `position`           | Positioning method                   | `static`, `relative`, `absolute`, `fixed`, `sticky` |
| `top` / `right` / `bottom` / `left` | Offset for positioned elements | `0`, `10px`, `50%` |
| `float`              | Float element                        | `left`, `right`, `none` |
| `clear`              | Clear floats                         | `left`, `right`, `both` |
| `overflow`           | Overflow handling                    | `visible`, `hidden`, `scroll`, `auto` |
| `z-index`            | Stack order                          | `1`, `10`, `-1`, `auto` |

#### Flexbox
| Property              | Description                          | Common Values |
|-----------------------|--------------------------------------|---------------|
| `display: flex`      | Enable flexbox                       | - |
| `flex-direction`     | Main axis direction                  | `row`, `column`, `row-reverse` |
| `flex-wrap`          | Wrapping                             | `wrap`, `nowrap` |
| `justify-content`    | Main axis alignment                  | `center`, `flex-start`, `space-between`, `space-around` |
| `align-items`        | Cross axis alignment                 | `center`, `stretch`, `flex-start` |
| `align-content`      | Multi-line alignment                 | `space-between`, `center` |
| `flex`               | Shorthand for grow/shrink/basis      | `1`, `0 0 auto` |

#### Text & Font
| Property              | Description                          | Common Values |
|-----------------------|--------------------------------------|---------------|
| `color`              | Text color                           | `#fff`, `rgb(0,0,0)`, `blue` |
| `font-family`        | Font stack                           | `Arial, sans-serif` |
| `font-size`          | Text size                            | `16px`, `1rem`, `1.2em` |
| `font-weight`        | Boldness                             | `400`, `700`, `bold` |
| `font-style`         | Italic/oblique                       | `italic`, `normal` |
| `text-align`         | Horizontal alignment                 | `left`, `center`, `right`, `justify` |
| `line-height`        | Vertical spacing between lines       | `1.5`, `1.8`, `20px` |
| `text-decoration`    | Underline, etc.                      | `none`, `underline`, `line-through` |
| `text-transform`     | Capitalization                       | `uppercase`, `lowercase`, `capitalize` |
| `letter-spacing`     | Space between letters                | `0.5px`, `1px` |
| `word-spacing`       | Space between words                  | `2px` |

#### Background & Borders
| Property                  | Description                          | Common Values |
|---------------------------|--------------------------------------|---------------|
| `background-color`       | Background color                     | `#f0f0f0`, `rgba(0,0,0,0.5)` |
| `background-image`       | Background image                     | `url(image.jpg)` |
| `background-size`        | Image size                           | `cover`, `contain`, `100%` |
| `background-position`    | Image position                       | `center`, `top left` |
| `background-repeat`      | Repeat behavior                      | `no-repeat`, `repeat-x` |
| `border-radius`          | Rounded corners                      | `10px`, `50%` |
| `box-shadow`             | Shadow effect                        | `0 4px 8px rgba(0,0,0,0.2)` |

#### Other Useful Properties
| Property                  | Description                          | Common Values |
|---------------------------|--------------------------------------|---------------|
| `opacity`                | Transparency                         | `0.5`, `1`, `0` |
| `cursor`                 | Mouse cursor                         | `pointer`, `default`, `grab` |
| `transition`             | Smooth property changes              | `all 0.3s ease` |
| `transform`              | Rotate, scale, translate             | `rotate(45deg)`, `scale(1.1)` |
| `filter`                 | Visual effects                       | `blur(5px)`, `grayscale(100%)` |
| `visibility`             | Show/hide (keeps space)              | `visible`, `hidden` |
| `list-style`             | List markers                         | `none`, `disc`, `decimal` |

### 3. Selectors Quick Reference

| Selector Type       | Example                  | Description |
|---------------------|--------------------------|-----------|
| Element             | `div`                    | All `<div>` elements |
| Class               | `.btn`                   | Elements with class `btn` |
| ID                  | `#header`                | Element with id `header` |
| Descendant          | `ul li`                  | `li` inside `ul` |
| Child               | `ul > li`                | Direct children |
| Pseudo-class        | `a:hover`, `input:focus` | State-based |
| Pseudo-element      | `::before`, `::after`    | Insert content |
| Attribute           | `input[type="text"]`     | By attribute |

### 4. Media Queries
```css
@media (max-width: 600px) { ... }     /* Mobile */
@media (min-width: 900px) { ... }     /* Desktop */
@media (orientation: landscape) { ... }
```