```haskell
-- | The Constrained class is a 'Quantity' that has value constraints.
-- It does not enforce 'Quantity' at this point.
class Constrained c where
  -- | Provides a 'Lens' to the 'Constraint's.
  constraints :: Lens' c [ConstraintE]
```

Something that has [[ConstraintE]]s.