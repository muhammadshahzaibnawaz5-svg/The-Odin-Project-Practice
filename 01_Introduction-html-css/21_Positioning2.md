### Main Comparison

| Position Value   | Relative To                              | Removed from Normal Flow? | Keeps Original Space? | Creates Positioning Context? | z-index Works? | Common Use Cases |
|------------------|------------------------------------------|---------------------------|-----------------------|------------------------------|----------------|------------------|
| **`static`**    | Normal document flow (default)          | No                        | Yes                   | No                           | No             | Standard layout (rarely set explicitly) |
| **`relative`**  | Its own normal position                 | No                        | Yes                   | Yes                          | Yes            | Fine-tuning position, creating container for absolute children |
| **`absolute`**  | Nearest positioned ancestor (or `<html>`) | **Yes**                   | No                    | Yes                          | Yes            | Tooltips, modals, overlays, precise placement |
| **`fixed`**     | Viewport (browser window)               | **Yes**                   | No                    | Yes                          | Yes            | Sticky headers, floating buttons, persistent UI |
| **`sticky`**    | Normal flow until threshold, then viewport | No (until stuck)          | Yes (until stuck)     | No                           | Yes            | Sticky navigation, table headers, sidebars |

### Detailed Behavior

| Value          | How It Behaves                                                                 | Offset Properties (`top`/`right`/`bottom`/`left`) | Key Notes & Gotchas |
|----------------|--------------------------------------------------------------------------------|---------------------------------------------------|---------------------|
| **`static`**   | Flows normally into the page like any block/inline element                    | Ignored                                           | Default value. Only use to override inherited positioning. |
| **`relative`** | Shifts from its normal position when offsets are added. Without offsets, acts like `static`. | Works (shifts from original spot)                | Does **not** affect layout of surrounding elements. Great parent for `absolute` children. |
| **`absolute`** | Completely removed from flow. Positioned using offsets.                       | Works                                             | Looks for nearest `relative`/`absolute` parent. If none found, uses viewport. Overuse reduces flexibility. |
| **`fixed`**    | Stays fixed in the same screen position even when scrolling.                  | Works                                             | Always relative to viewport. Can overlap content — add padding/margin to avoid hiding text. |
| **`sticky`**   | Scrolls normally until it hits the threshold (e.g. `top: 0`), then sticks like `fixed`. | Works (activates sticking)                       | Needs a scrolling parent with enough height. Hybrid behavior. |

### Quick Practical Examples

| Goal                            | Recommended CSS Code |
|---------------------------------|----------------------|
| Fine-tune an element            | `position: relative; top: 10px;` |
| Create positioning context      | `position: relative;` (on parent) |
| Tooltip / Overlay               | `position: absolute; top: 100%; left: 0;` |
| Floating Action Button          | `position: fixed; bottom: 20px; right: 20px;` |
| Sticky Navigation               | `position: sticky; top: 0;` |

### Important Takeaways
- **`relative`** is safe and keeps the element in flow — ideal for small adjustments and as a container.
- **`absolute`** breaks out of flow — powerful but requires a positioned parent.
- **`fixed`** ignores scrolling — use for persistent UI elements.
- **`sticky`** is the smart hybrid — great for modern interfaces.
- Only positioned elements (`relative`, `absolute`, `fixed`, `sticky`) respond to `z-index`.
- Mixing `position` with `float` can cause unexpected behavior.