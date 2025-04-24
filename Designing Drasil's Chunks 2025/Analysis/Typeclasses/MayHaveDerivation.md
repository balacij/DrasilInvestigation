```haskell
-- | A class that might have a 'Derivation'.
class MayHaveDerivation c where
  -- | Provides a 'Lens' to a possible derivation.
  derivations :: Lens' c (Maybe Derivation)
```

For things that might have [[Derivation]]s.