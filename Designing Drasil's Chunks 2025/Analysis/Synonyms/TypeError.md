```haskell
-- TODO: Rather than using a flat String, it would be better to a
--       ``breadcrumb''-style error data type that can provide a traceable path
--       to issues in an expression. The breadcrumbs could then be formatted
--       into a flat String, such as it is now, or into alternative AST views
--       that show exactly where typing went awry.
type TypeError = String
```

A synonym for a `String`!