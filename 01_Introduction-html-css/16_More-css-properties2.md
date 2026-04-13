### 1. Border Properties

| Property              | Description                                      | Common Values                                      | Initial Value          | Notes |
|-----------------------|--------------------------------------------------|----------------------------------------------------|------------------------|-------|
| `border`             | Shorthand for width, style, and color (all sides) | `1px solid #000` <br> `2px dashed red`            | `medium none currentColor` | Order doesn't matter. Invisible if style is `none` or `hidden`. |
| `border-width`       | Thickness of the border                         | `thin`, `medium`, `thick`, `1px`, `0.5em`         | `medium`              | Can be set per side (`border-top-width`, etc.) |
| `border-style`       | Style/appearance of the border                  | `none`, `hidden`, `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset` | `none` | Most important — no style = no visible border |
| `border-color`       | Color of the border                             | Any `<color>` (`#000`, `rgb()`, `currentColor`)   | `currentColor`        | Can be set per side |

**Tip**: Use `border: 1px solid #ccc;` for the most common case.

### 2. Border-Radius (Rounded Corners)

| Property             | Description                                      | Syntax & Values                                    | Initial Value | Notes |
|----------------------|--------------------------------------------------|----------------------------------------------------|---------------|-------|
| `border-radius`     | Rounds the corners of an element's border/background | `10px` <br> `20px 10px` <br> `10px / 20px` (horizontal / vertical) <br> `1px 2px 3px 4px` | `0`          | 1–4 values for corners. `/` separates horizontal and vertical radii. Negative values not allowed. |

**Common Patterns**:
- `border-radius: 8px;` → All corners same
- `border-radius: 50%;` → Perfect circle/oval
- `border-radius: 10px 20px 30px 40px;` → Different for each corner

### 3. Box-Shadow

| Property       | Description                                      | Syntax & Values                                      | Initial Value | Notes |
|----------------|--------------------------------------------------|------------------------------------------------------|---------------|-------|
| `box-shadow`  | Adds shadow effects (outer or inner)            | `none` <br> `2px 4px 8px rgba(0,0,0,0.2)` <br> `inset 5px 5px 10px #000` <br> Multiple shadows separated by commas | `none`       | Format: `offset-x offset-y blur-radius spread-radius color inset` |

**Shadow Order** (from left to right):
- `offset-x` (horizontal)
- `offset-y` (vertical)
- `blur-radius` (optional)
- `spread-radius` (optional)
- `color` (optional)
- `inset` (for inner shadow)

**Tip**: Shadows follow `border-radius` automatically.

### 4. Overflow

| Property          | Description                                              | Values                                      | Initial Value | Notes |
|-------------------|----------------------------------------------------------|---------------------------------------------|---------------|-------|
| `overflow`       | Shorthand for `overflow-x` and `overflow-y`             | `visible`, `hidden`, `clip`, `scroll`, `auto` | `visible`    | Most commonly used |
| `overflow-x`     | Controls horizontal overflow                            | Same as above                               | `visible`    | — |
| `overflow-y`     | Controls vertical overflow                              | Same as above                               | `visible`    | — |

**Value Behavior**:
- `visible` — Content spills out (default)
- `hidden` — Content clipped, no scrollbars
- `scroll` — Always shows scrollbars
- `auto` — Scrollbars only when needed (most practical)
- `clip` — Strict clipping, no scrolling allowed

### 5. Opacity

| Property    | Description                                      | Values                                      | Initial Value | Notes |
|-------------|--------------------------------------------------|---------------------------------------------|---------------|-------|
| `opacity`  | Controls transparency of the entire element     | `0` (invisible) to `1` (fully opaque) <br> or `0%` to `100%` | `1`          | Affects the whole element + children. Creates new stacking context. |

**Key Notes on Opacity**:
- `0.5` = 50% transparent
- Element remains in the document flow and can still receive clicks (even when `opacity: 0`)
- For accessibility, avoid using opacity alone to hide content
- Respect `prefers-reduced-transparency` media query

### Quick Usage Examples
```css
.card {
  border: 2px solid #ddd;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  overflow: auto;           /* or hidden / visible */
  opacity: 1;               /* default */
}
```