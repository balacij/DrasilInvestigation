```haskell
-- | A 'Quantity' that could have a reasonable value.
class HasReasVal c where
  -- | Provides a 'Lens' to the possible reasonable value.
  reasVal     :: Lens' c (Maybe Expr)
```

A _thing_ (hopefully only a quantity-defining chunk) _might_ have a known reasonable value.