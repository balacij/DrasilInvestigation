```haskell
-- | A HasSymbol is anything which has a 'Symbol'.
class HasSymbol c where
  -- | Provides the 'Symbol' for a particular stage of generation.
  symbol  :: c -> Stage -> Symbol
```

A thing that has a [[Symbol]], which is dependant on the rendering [[Stage]].