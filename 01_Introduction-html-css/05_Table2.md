### Learning Goals
- Build a well-structured, accessible HTML table
- Use semantic elements (`<thead>`, `<tbody>`, `<caption>`, `<colgroup>`)
- Properly associate headers with data using `scope`
- Handle grouped data with `rowspan` and `colspan`

### Recommended Table Structure

| Element / Attribute       | Purpose                                      | Usage Example |
|---------------------------|----------------------------------------------|---------------|
| `<table>`                | Main table container                        | Root element |
| `<caption>`              | Table title or description                  | First child of `<table>` |
| `<colgroup>` + `<col>`   | Group and style columns                     | Add borders or styles to specific columns |
| `<thead>`                | Table header section                        | Contains column titles |
| `<tbody>`                | Main data body                              | Contains all planet rows |
| `<th scope="col">`       | Column header                               | Top headers (Name, Mass, etc.) |
| `<th scope="row">`       | Row header (planet name)                    | Identifies each planet |
| `<th scope="rowgroup">`  | Group header (e.g. Terrestrial planets)     | Spans multiple rows |
| `rowspan`                | Merge cells vertically                      | Group labels spanning rows |
| `colspan`                | Merge cells horizontally                    | Empty top-left cell or group labels |
| `scope`                  | Improves screen reader support              | `"col"`, `"row"`, `"rowgroup"` |

### Key Best Practices
- Always include a `<caption>` for context.
- Use `<th>` for all headers (never `<td>` for headings).
- Add `scope="col"` for column headers and `scope="row"` for row headers.
- Use `scope="rowgroup"` for category groups (Terrestrial / Jovian planets).
- Use `<colgroup>` to apply CSS to entire columns (e.g., vertical border).
- Keep data in `<td>` elements only.

### Quick CSS Tips (from the tutorial)
- `border-collapse: collapse;` for clean borders
- Style the `.column-border` class to add a vertical separator after the planet name
- Add zebra striping with `nth-child(odd)` for better readability
- Use padding on `th` and `td` for comfortable spacing

### Complete Example Structure (Summary)
```html
<table>
  <caption>Data about the planets of our solar system...</caption>
  <colgroup>
    <col span="2" />
    <col class="column-border" />
    <col span="9" />
  </colgroup>
  <thead>
    <tr>
      <td colspan="2"></td>
      <th scope="col">Name</th>
      <!-- other column headers -->
    </tr>
  </thead>
  <tbody>
    <!-- Terrestrial planets group with rowspan -->
    <!-- Jovian planets (Gas giants + Ice giants) -->
    <!-- Dwarf planets -->
  </tbody>
</table>
``