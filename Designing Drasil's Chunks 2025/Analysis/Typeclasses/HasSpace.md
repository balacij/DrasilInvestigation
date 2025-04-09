```haskell
-- | HasSpace is anything which has a 'Space'.
class HasSpace c where
  -- | Provides a 'Getter' to the 'Space'.
  typ      :: Getter c Space
```
