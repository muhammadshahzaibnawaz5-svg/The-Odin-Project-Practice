### Table Structure Overview
Use semantic sections for better accessibility and styling:

| Element       | Purpose                                      | Placement Notes |
|---------------|----------------------------------------------|-----------------|
| `<table>`    | Container for tabular data                  | Root element |
| `<caption>`  | Table title/description                     | First child of `<table>` (optional) |
| `<thead>`    | Header rows (column titles)                 | Top section |
| `<tbody>`    | Main data rows                              | Required for data |
| `<tfoot>`    | Footer rows (summaries, totals)             | Can come after `<tbody>` in HTML5 |
| `<tr>`       | Table row                                   | Inside thead/tbody/tfoot |
| `<th>`       | Header cell                                 | Use for column/row headers |
| `<td>`       | Data cell                                   | Regular content cells |
| `<col>`      | Defines column styles (empty element)       | Inside `<colgroup>` |
| `<colgroup>` | Groups one or more columns                  | Before `<thead>` |

### Important Attributes

| Attribute     | Applies To       | Description & Usage |
|---------------|------------------|---------------------|
| `colspan`    | `<th>`, `<td>`  | Merge cells horizontally (e.g. `colspan="3"`) |
| `rowspan`    | `<th>`, `<td>`  | Merge cells vertically (e.g. `rowspan="2"`) |
| `scope`      | `<th>`          | Improves accessibility (`row`, `col`, `rowgroup`, `colgroup`) |
| `headers`    | `<td>`          | Links cell to specific header IDs (advanced accessibility) |
| `span`       | `<col>`         | Makes the column apply to multiple columns |

**Deprecated (Avoid):**
`align`, `valign`, `bgcolor`, `cellpadding`, `cellspacing`, `border`, `width`, `summary` — use **CSS** instead.

### Basic Table Example
```html
<table>
  <caption>Monthly Sales Report</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>January</td>
      <td>$12,450</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">Total</th>
      <td>$45,200</td>
    </tr>
  </tfoot>
</table>
```

### Essential CSS for Tables

| Property                  | Recommended Value / Usage                  | Purpose |
|---------------------------|--------------------------------------------|---------|
| `border-collapse`        | `collapse`                                 | Removes double borders (most common) |
| `border-spacing`         | `0` or `0.5rem` (when separate)            | Controls space between cells |
| `width`                  | `100%`                                     | Makes table fill container |
| `table-layout`           | `fixed` or `auto`                          | `fixed` = faster & predictable widths |
| `padding`                | `0.5rem 1rem` (on `th`, `td`)              | Cell spacing |
| `text-align`             | `left` / `center` / `right`                | Horizontal alignment |
| `vertical-align`         | `top` / `middle` / `bottom`                | Vertical alignment |
| `white-space`            | `nowrap`                                   | Prevents text wrapping |

**Zebra Striping (Readability):**
```css
tbody tr:nth-child(odd) {
  background-color: #f8f8f8;
}
```