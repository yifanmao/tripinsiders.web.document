# JavaScript Style Guide
------
## JavaScript Language Rules
### var
Declarations with var: `Always`

> When you fail to specify var, the variable gets placed in the global context, potentially clobbering existing values. Also, if there's no declaration, it's hard to tell in what scope a variable lives (e.g., it could be in the Document or Window just as easily as in the local scope). So always declare with var.

### Constants
> * Use `NAMES_LIKE_THIS` for constant values.
> * Use `@const` to indicate a constant (non-overwritable) pointer (a variable or property).
> * Never use the `const` keyword as it's not supported in Internet Explorer.