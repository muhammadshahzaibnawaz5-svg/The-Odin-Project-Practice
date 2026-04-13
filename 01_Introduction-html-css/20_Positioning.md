### Overview
The `position` property specifies how an element is positioned in the document. It works together with the offset properties: **`top`**, **`right`**, **`bottom`**, and **`left`**.

### Core `position` Values

| Value          | Description                                                                 | Offset Properties (`top/right/bottom/left`) | Removes from Normal Flow? | Common Use Cases |
|----------------|-----------------------------------------------------------------------------|---------------------------------------------|---------------------------|------------------|
| **`static`**   | **Default** value. Follows normal document flow.                           | Ignored                                    | No                        | Default layout (most elements) |
| **`relative`** | Positioned relative to its **normal position**.                           | Yes (offsets from its original spot)       | No                        | Fine-tuning position, creating positioning context for children |
| **`absolute`** | Positioned relative to the **nearest positioned ancestor** (or initial containing block). | Yes                                        | **Yes**                   | Tooltips, modals, dropdowns, overlays |
| **`fixed`**    | Positioned relative to the **viewport** (browser window). Stays in place during scroll. | Yes                                        | **Yes**                   | Sticky headers, floating action buttons, chat widgets |
| **`sticky`**   | Hybrid: scrolls normally until it reaches a threshold, then behaves like `fixed`. | Yes                                        | No (until threshold)      | Sticky navigation, table headers, sidebars |

### Offset Properties (Work with `relative`, `absolute`, `fixed`, `sticky`)

| Property     | Description                                      | Common Values                  | Notes |
|--------------|--------------------------------------------------|--------------------------------|-------|
| `top`       | Distance from the top edge                      | `0`, `10px`, `20%`, `auto`    | — |
| `right`     | Distance from the right edge                    | `0`, `10px`, `20%`, `auto`    | — |
| `bottom`    | Distance from the bottom edge                   | `0`, `10px`, `20%`, `auto`    | — |
| `left`      | Distance from the left edge                     | `0`, `10px`, `20%`, `auto`    | — |

### Positioning Context & Behavior

| Position Value | Containing Block (Reference Point)                  | Stacking Context | Z-index Effect | Flow Impact |
|----------------|-----------------------------------------------------|------------------|----------------|-------------|
| `static`      | Normal document flow                                | No               | No             | Normal flow |
| `relative`    | Its own normal position                             | No               | Yes            | Still occupies space |
| `absolute`    | Nearest ancestor with `position` ≠ `static`         | Yes              | Yes            | Removed from flow |
| `fixed`       | Viewport (browser window)                           | Yes              | Yes            | Removed from flow |
| `sticky`      | Nearest scrolling ancestor (until threshold)        | No (until stuck) | Yes            | Stays in flow until sticky |

### Practical Examples

| Goal                              | Recommended CSS |
|-----------------------------------|-----------------|
| **Sticky Header**                | `position: sticky; top: 0;` |
| **Modal / Popup**                | `position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);` |
| **Floating Button**              | `position: fixed; bottom: 20px; right: 20px;` |
| **Slightly move an element**     | `position: relative; top: -10px;` |
| **Tooltip**                      | `position: absolute;` on child + `position: relative;` on parent |

### Key Best Practices
- Use `position: relative` as the parent when you need to position children with `absolute`.
- Always test `sticky` carefully — it requires a scrolling parent.
- For centering with `absolute`: Use `top: 50%; left: 50%;` + `transform: translate(-50%, -50%);`
- `z-index` only works on positioned elements (`relative`, `absolute`, `fixed`, `sticky`).
- Avoid overusing `fixed` and `absolute` — they can break document flow and accessibility.

### Quick Tip
```css
/* Most common modern pattern */
.parent {
  position: relative;     /* Creates positioning context */
}

.child {
  position: absolute;
  top: 0;
  right: 0;
}
```