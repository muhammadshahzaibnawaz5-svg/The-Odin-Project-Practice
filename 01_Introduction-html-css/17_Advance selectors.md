CSS Diner is a fun interactive game to master **CSS selectors**. You select specific food items (plates, apples, pickles, etc.) on the table using correct CSS selectors.

### CSS Diner – All 32 Levels (Solved)

| Level | Task Description                          | Correct Selector                          | Selector Type                  | Explanation |
|-------|-------------------------------------------|-------------------------------------------|--------------------------------|-------------|
| 1     | Select the plates                        | `plate`                                  | Type Selector                 | Selects all `<plate>` elements |
| 2     | Select the bento boxes                   | `bento`                                  | Type Selector                 | Selects all `<bento>` elements |
| 3     | Select the fancy plate                   | `#fancy`                                 | ID Selector                   | Selects element with `id="fancy"` |
| 4     | Select the apple on the plate            | `plate apple`                            | Descendant Selector           | Apple inside a plate |
| 5     | Select the pickle on the fancy plate     | `#fancy pickle`                          | Descendant Selector           | Pickle inside `#fancy` |
| 6     | Select the small plates                  | `.small`                                 | Class Selector                | Elements with class `small` |
| 7     | Select the small orange                  | `orange.small`                           | Type + Class                  | Orange that also has class `small` |
| 8     | Select the small orange in a bento       | `bento orange.small`                     | Descendant + Class            | Orange with class `small` inside bento |
| 9     | Select all plates and bento boxes        | `plate, bento`                           | Group Selector (Comma)        | Selects both types |
| 10    | Select everything on the table           | `*`                                      | Universal Selector            | Selects all elements |
| 11    | Select everything on a plate             | `plate *`                                | Descendant Universal          | Everything inside a plate |
| 12    | Select the apple next to a plate         | `plate + apple`                          | Adjacent Sibling (+)          | Apple immediately after a plate |
| 13    | Select the pickle after a bento          | `bento ~ pickle`                         | General Sibling (~)           | All pickles after a bento |
| 14    | Select the apple directly on a plate     | `plate > apple`                          | Child Selector (>)            | Direct child apple of plate |
| 15    | Select the first orange                  | `orange:first-child`                     | Pseudo-class :first-child     | First child that is orange |
| 16    | Select the plate with only one child     | `plate :only-child`                      | :only-child                   | The only child inside plate |
| 17    | Select the last small item               | `.small:last-child`                      | :last-child                   | Last child with class small |
| 18    | Select the 3rd plate                     | `:nth-child(3)`                          | :nth-child                    | 3rd child (any type) |
| 19    | Select the 3rd from the end              | `:nth-last-child(3)`                     | :nth-last-child               | 3rd from the bottom |
| 20    | Select the first apple of its type       | `apple:first-of-type`                    | :first-of-type                | First apple among siblings |
| 21    | Select every 2nd bento                   | `bento:nth-of-type(2n)`                  | :nth-of-type                  | Every even bento |
| 22    | Select every 3rd item starting from 2nd  | `:nth-of-type(3n+2)`                     | :nth-of-type (An+B)           | Complex positioning |
| 23    | Select the only orange of its type       | `orange:only-of-type`                    | :only-of-type                 | The only orange in its group |
| 24    | Select the last bento                    | `bento:last-of-type`                     | :last-of-type                 | Last bento among siblings |
| 25    | Select empty plates                      | `plate:empty`                            | :empty                        | Plates with no children |
| 26    | Select everything except pickles         | `:not(pickle)`                           | :not()                        | Negative selector |
| 27    | Select items with a "for" attribute      | `[for]`                                  | Attribute Selector            | Any element with `for` attribute |
| 28    | Select plates with "for" attribute       | `plate[for]`                             | Type + Attribute              | Plate with `for` attribute |
| 29    | Select items with for="one"              | `[for="one"]`                            | Attribute = Value             | Exact match |
| 30    | Select items whose for starts with "t"   | `[for^="t"]`                             | Attribute ^ (starts with)     | Begins with "t" |
| 31    | Select items whose for ends with "e"     | `[for$="e"]`                             | Attribute $ (ends with)       | Ends with "e" |
| 32    | Select items whose for contains "en"     | `[for*="en"]`                            | Attribute * (contains)        | Contains "en" anywhere |

### Quick Reference of Selector Types

- **Basic**: `element`, `.class`, `#id`
- **Combinators**: Space (descendant), `>` (child), `+` (adjacent sibling), `~` (general sibling)
- **Pseudo-classes**: `:first-child`, `:last-child`, `:nth-child()`, `:only-child`, `:first-of-type`, `:empty`, `:not()`
- **Attribute Selectors**: `[attr]`, `[attr="value"]`, `[attr^="value"]`, `[attr$="value"]`, `[attr*="value"]`