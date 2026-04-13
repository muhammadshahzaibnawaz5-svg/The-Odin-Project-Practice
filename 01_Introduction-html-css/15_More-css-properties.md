### Background Shorthand
| Property          | Description                                                                 | Syntax Highlights                          | Initial Value                  | Key Notes |
|-------------------|-----------------------------------------------------------------------------|--------------------------------------------|--------------------------------|-----------|
| `background`     | Shorthand for all background properties (color, image, position, size, repeat, origin, clip, attachment, blend-mode) | `bg-color bg-image position / size repeat attachment origin clip` (comma-separated layers) | See individual properties     | Multiple layers allowed. Color only in last layer. Most used property. |

### Individual Background Properties

| Property                    | Description                                              | Common Values                                      | Initial Value      | Applies To                  | Important Notes |
|-----------------------------|----------------------------------------------------------|----------------------------------------------------|--------------------|-----------------------------|-----------------|
| `background-color`         | Sets the background color                               | `<color>` (e.g. `#fff`, `rgb()`, `transparent`)   | `transparent`     | All elements               | Always bottom layer |
| `background-image`         | Sets one or more background images                      | `none` \| `url()` \| `linear-gradient()` etc.     | `none`            | All elements               | Images painted in order (first = top) |
| `background-position`      | Sets starting position of background image(s)           | `center`, `top left`, `50% 30%`, `10px 20px`      | `0% 0%`           | All elements               | Horizontal then vertical |
| `background-size`          | Controls size of background image(s)                    | `auto`, `cover`, `contain`, `50%`, `100px 200px`  | `auto`            | All elements               | Use after `/` in shorthand |
| `background-repeat`        | Controls how images are repeated                        | `repeat`, `no-repeat`, `repeat-x`, `repeat-y`, `space`, `round` | `repeat`       | All elements               | Can be set separately for x/y |
| `background-attachment`    | Whether image scrolls with content or viewport          | `scroll`, `fixed`, `local`                        | `scroll`          | All elements               | `fixed` = parallax effect |
| `background-origin`        | Sets the origin (starting point) of the background     | `padding-box`, `border-box`, `content-box`        | `padding-box`     | All elements               | Affects positioning |
| `background-clip`          | Defines the painting area of the background            | `border-box`, `padding-box`, `content-box`, `text` | `border-box`     | All elements               | `text` clips to text shape |
| `background-blend-mode`    | Blends background image with background color          | `normal`, `multiply`, `screen`, `overlay`, etc.   | `normal`          | All elements               | Affects how layers blend |

### Quick Usage Tips
- **Multiple backgrounds**: Separate layers with commas. Last layer can include color.
- **Shorthand order** (common):  
  `background: color image position/size repeat attachment origin clip;`
- **Best practice**: Use the shorthand `background` for most cases. Use longhands only when you need to override one value.
- **Layer order**: First declared layer is painted on top.
- **Performance**: Gradients and multiple images can impact rendering — use wisely.

### Example
```css
.hero {
  background: 
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
    url("hero.jpg") center/cover no-repeat fixed;
  background-color: #333;   /* fallback */
}
```