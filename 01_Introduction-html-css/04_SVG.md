
### What is SVG?
**Scalable Vector Graphics** — a text-based (XML) image format that defines shapes mathematically instead of pixels.

**Key Advantages**:
- Scales infinitely without losing quality
- Fully editable with CSS and JavaScript
- Supports animations and interactivity
- Perfect for icons, illustrations, logos, and charts
- Lightweight and accessible

**Best Practice**: Use **inline SVG** in HTML for full styling and scripting power.

### Basic SVG Boilerplate
```html
<svg width="200" height="200" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Shapes and elements go here -->
</svg>
```

### Core SVG Elements

| Element       | Purpose                              | Key Attributes |
|---------------|--------------------------------------|----------------|
| `<rect>`     | Rectangle / Square                  | `x`, `y`, `width`, `height`, `rx`, `ry` (rounded corners) |
| `<circle>`   | Circle                              | `cx`, `cy`, `r` |
| `<ellipse>`  | Oval                                | `cx`, `cy`, `rx`, `ry` |
| `<line>`     | Straight line                       | `x1`, `y1`, `x2`, `y2` |
| `<polyline>` | Open connected lines                | `points="x1,y1 x2,y2 ..."` |
| `<polygon>`  | Closed shape                        | `points="x1,y1 x2,y2 ..."` |
| `<path>`     | Most powerful – complex curves      | `d="M ... L ... C ..."` |
| `<text>`     | Text inside SVG                     | `x`, `y`, `font-size` |

### Essential Attributes

| Category          | Attribute              | Description & Common Values |
|-------------------|------------------------|-----------------------------|
| **Size**         | `width`, `height`     | Outer size (px, %, etc.) |
| **Scaling**      | `viewBox="x y w h"`   | Internal coordinate system (e.g. `0 0 100 100`) – enables responsive scaling |
| **Fill**         | `fill`                | Inside color (`hotpink`, `#ff69b4`, `none`) |
| **Stroke**       | `stroke`              | Outline color |
| **Stroke**       | `stroke-width`        | Thickness of outline |
| **Stroke**       | `stroke-linecap`      | `butt`, `round`, `square` |
| **Stroke**       | `stroke-dasharray`    | Dash pattern (e.g. `10, 5`) |
| **Position**     | `x`, `y` / `cx`, `cy` | Location of element |

### Coordinate System
- (0, 0) is at the **top-left**
- Positive X goes right, positive Y goes **down**
- Use `viewBox="0 0 100 100"` for clean, responsive designs (recommended)

**Responsive Tip**:
```html
<svg width="100%" height="auto" viewBox="0 0 200 200">
```

### Quick Examples

**Simple Circle**
```html
<svg width="120" height="120" viewBox="0 0 120 120">
  <circle cx="60" cy="60" r="40" fill="#ff69b4" stroke="#333" stroke-width="8"/>
</svg>
```

**Rounded Rectangle**
```html
<rect x="10" y="10" width="100" height="60" rx="10" fill="#4facfe"/>
```

### Styling & Animation Tips
- Most attributes (`fill`, `stroke`, `stroke-width`, etc.) can be styled with **CSS**
- Use CSS `transition` and `animation` on SVG properties
- Popular trick: **Stroke-dasharray + stroke-dashoffset** for "draw-on-load" animations