### Main Thesis
CSS preprocessors (like Sass, LESS, Stylus) offer many advantages, but they introduce significant drawbacks in debugging, performance, maintenance, tooling, and workflow. The author argues that many "problems" preprocessors solve can be handled with vanilla CSS + good conventions. Adding a preprocessor is easy, but removing it later is difficult.

### Disadvantages Summary Table

| # | Disadvantage                          | Explanation                                                                 | Key Impact / Drawback                                      | Author's Note / Quote |
|---|---------------------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------|-----------------------|
| 1 | **Debugging is harder**              | Compiled CSS means browser line numbers don't match source files           | Makes debugging slower and more frustrating               | "Debugging is twice as hard as programming" – Brian Kernighan |
| 2 | **Compilation slows down development** | Extra build step adds delay between saving and seeing changes              | Breaks fast feedback loop during development              | Even on fast machines and modern tools, it can feel slow |
| 3 | **Produces very large CSS files**    | Small source files often generate bloated output CSS                       | Increases file size, hurts performance                     | You lose fine control over the final CSS |
| 4 | **Maintenance & overengineering**    | Variables and mixins often provide little real value (e.g., changing a `$red` variable still requires updating both name and value) | Leads to unnecessary abstraction and complexity           | Search & replace is often sufficient |
| 5 | **Extra tooling & developer friction** | Requires additional build tools, watchers, and editor setup                | Forces team to adopt specific tools ("tail wagging the dog") | Adds complexity that must be maintained and upgraded |
| 6 | **Decisions about saving generated files** | Debate on whether to commit compiled CSS to version control                | Creates team friction and "Consensus Driven Development"  | No clear community agreement |
| 7 | **Capability & understanding gap**   | Many developers use preprocessors without fully understanding trade-offs   | Risk of introducing new problems while solving old ones   | Big difference between "using" and "using effectively" |

### Alternatives Suggested by the Author

| Preprocessor Feature       | Vanilla CSS Alternative                                      | Example |
|----------------------------|--------------------------------------------------------------|---------|
| **Variables**             | Search & replace or CSS custom properties (`--var`)         | — |
| **Mixins**                | Comma-delimited selectors for shared rules                   | `button, .btn { ... }` |
| **Nesting**               | Write fully qualified selectors (or use a naming convention) | Avoid deep nesting for better performance |
| **General maintainability**| Solid CSS architecture + conventions                         | — |

### Key Quotes from the Article
- “It’s easy to add a CSS preprocessor to the tech stack. But, it’s not easy to remove it down the line, should we so choose.”
- “Debugging is twice as hard as programming.”

### Conclusion & Advice
Before adopting a CSS preprocessor, carefully weigh the real benefits against these disadvantages. Many common CSS problems can be solved with:
- Modern native CSS features (custom properties, `calc()`, nesting in modern browsers)
- Good naming conventions and architecture
- Simple search & replace

A well-written vanilla CSS codebase is often more maintainable, debuggable, and performant than one relying heavily on a preprocessor.