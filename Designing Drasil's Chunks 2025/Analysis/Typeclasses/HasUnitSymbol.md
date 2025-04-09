```haskell
-- | Some chunks store a unit symbol.
class HasUnitSymbol u where
  -- | Provides the ability to hold a unit symbol ('USymb').
  usymb :: u -> USymb
```

Intended only for unit-defining chunks to expose what [[USymb]] they define.