### Overview
`min()`, `max()`, and `clamp()` are CSS math functions that enable responsive sizing, spacing, and typography without media queries. They work with lengths, percentages, and other units, and support nesting or combining with `calc()`.

They are supported in all modern browsers.

### Comparison Table

| Function     | Purpose                          | Syntax                              | Behavior                                                                 | Equivalent Expression                  |
|--------------|----------------------------------|-------------------------------------|--------------------------------------------------------------------------|----------------------------------------|
| **min()**   | Select the **smallest** value   | `min(value1, value2, ...)`         | Returns the smallest value from the list                                 | N/A                                    |
| **max()**   | Select the **largest** value    | `max(value1, value2, ...)`         | Returns the largest value from the list                                  | N/A                                    |
| **clamp()** | Constrain a value between min & max | `clamp(min, ideal, max)`          | Uses `ideal` if within range; otherwise returns `min` or `max`           | `min(max(ideal, min), max)`            |

### Detailed Breakdown

**1. min() – Sets an upper limit (maximum possible value)**  
- Picks the **smallest** of the provided values.  
- Common use: Prevent elements from getting too wide.  

**Example:**
```css
width: min(75ch, 50%);        /* Never wider than 75 characters */
```

**2. max() – Sets a lower limit (minimum possible value)**  
- Picks the **largest** of the provided values.  
- Common use: Ensure minimum width, padding, or size for readability.  

**Example:**
```css
width: max(45ch, 50%);        /* At least 45 characters wide */
```

**3. clamp() – Perfect for fluid/responsive values**  
- Takes three arguments: minimum, preferred (ideal), maximum.  
- The value scales with the "ideal" but stays within bounds.  

**Example:**
```css
width: clamp(45ch, 50%, 75ch);
/* 
  - Uses 50% normally
  - Never smaller than 45ch
  - Never larger than 75ch
*/
```

### Common Use Cases & Examples

| Use Case                  | CSS Code                                                                 | Explanation |
|---------------------------|--------------------------------------------------------------------------|-----------|
| **Ideal Text Width**     | `width: clamp(45ch, 50%, 75ch);`                                        | Keeps line length readable (45–75 characters) |
| **Max Width Only**       | `width: min(75ch, 100%);`                                               | Caps width at 75ch |
| **Min Width Only**       | `width: max(45ch, 50%);`                                                | Ensures minimum readable width |
| **Fluid Typography**     | `font-size: clamp(1.5rem, 5vw, 3rem);`                                  | Font scales with viewport but stays between 1.5rem and 3rem |
| **Minimum Padding**      | `padding: max(2rem, 50vw - var(--contentWidth) / 2);`                   | Keeps padding from collapsing on small screens |
| **Nested Example**       | `font-size: max(min(0.5vw, 1em), 2rem);`                                | Combines min + max for complex constraints |

### Key Tips
- Use **`ch`** unit for text-related sizing (1ch ≈ width of the "0" character).
- `clamp()` is excellent for **fluid typography** and responsive containers.
- You can nest functions: `max(min(...), ...)`.
- Combine with `calc()` for more complex math.
- `clamp(min, ideal, max)` is mathematically identical to `min(max(ideal, min), max)`.

