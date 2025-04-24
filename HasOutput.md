```haskell
-- | Members of this class may have outputs.
class HasOutput c where
  -- | Provides a 'Getter' that holds a 'QuantityDict' for output.
  output :: Getter c QuantityDict
  -- | Provides a 'Getter' that holds constraints on the output.
  out_constraints :: Getter c [RealInterval Expr Expr]
```

