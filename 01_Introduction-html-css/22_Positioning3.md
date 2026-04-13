### Core Comparison

| Aspect                  | `position: fixed`                                      | `position: sticky`                                      |
|-------------------------|--------------------------------------------------------|---------------------------------------------------------|
| **Reference Point**    | Viewport (browser window)                             | Normal flow until threshold, then viewport              |
| **Scrolling Behavior** | Always stays in the same place on screen              | Scrolls normally, then **sticks** at specified offset  |
| **Document Flow**      | Removed from normal flow                              | Stays in normal flow until it becomes sticky           |
| **Containing Block**   | Viewport (ignores most ancestors)                     | Limited to its **parent/container**                     |
| **When It Leaves**     | Never leaves the screen (unless overridden)           | Leaves when its parent scrolls off the page             |
| **Offset Required**    | Yes (`top`, `bottom`, etc.)                           | Yes (at least one offset like `top: 0`)                 |

### Detailed Behavior

| Feature                    | `position: fixed`                                      | `position: sticky`                                      |
|----------------------------|--------------------------------------------------------|---------------------------------------------------------|
| **Initial Position**      | Immediately positioned relative to viewport           | Behaves like `position: relative` until threshold      |
| **After Threshold**       | Always fixed                                          | Switches to fixed-like behavior                         |
| **Parent Influence**      | Minimal (can be affected by `transform` etc.)         | Strong — must stay inside parent                        |
| **Layout Impact**         | Can overlap/hide other content                        | Respects surrounding content until stuck                |
| **Mobile Considerations** | Can cover important content on small screens          | Safer as it only sticks temporarily                     |

### When to Use Each

| Use Case                          | Recommended Property | Why |
|-----------------------------------|----------------------|-----|
| Permanent floating button / chat widget | `fixed`             | Must always be visible |
| Persistent header / navbar        | `fixed`             | Should never scroll away |
| Sticky table headers              | `sticky`            | Scrolls with content then sticks |
| Section headings that stick while reading | `sticky`       | Natural reading experience |
| Sidebar that sticks after scrolling | `sticky`           | Better than fixed (respects container) |
| Navigation that appears after scroll | `sticky`           | Cleaner user experience |

### Pros & Cons

**`position: fixed`**
- **Pros**: Simple, always visible, consistent positioning.
- **Cons**: Removed from flow → may overlap content, can feel intrusive on mobile.

**`position: sticky`**
- **Pros**: More natural behavior, stays in flow initially, easier to avoid overlap issues.
- **Cons**: Limited by parent container, disappears when parent scrolls away, requires proper HTML structure.

### Quick Tips from the Article
- Use **`sticky`** when you want an element to scroll normally and then stop at a point (modern replacement for many JavaScript solutions).
- Use **`fixed`** only when the element must **always** remain visible regardless of scroll position.
- For best results with `sticky`, make sure the parent container has enough height and is the scrolling container.
- Test thoroughly on mobile — fixed elements can sometimes cause usability issues.

**Most Common Pattern**
```css
/* Sticky header */
header {
  position: sticky;
  top: 0;
  z-index: 100;
}

/* Always visible button */
.floating-btn {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```