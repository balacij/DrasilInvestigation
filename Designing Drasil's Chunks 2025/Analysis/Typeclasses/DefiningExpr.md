```haskell
class DefiningExpr c e where
  -- | Provides a 'Lens' to the expression.
  --   TODO: Well, technically, `e` doesn't need to be an "expression" of any sorts.
  --         It just needs to be _something_, and it would have approximately have same meaning.
  defnExpr :: Lens' (c e) e
```

"Give me the _thing_ (usually an expression) you define something else (completely unknown and foreign to this interface) with!" This should perhaps be merged with [[Definition]] and/or [[DefinesQuantity]].