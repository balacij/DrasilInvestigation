```haskell
-- | Members of this class must have 'RawContent'.
class HasContents c where
  -- | Provides a 'Lens' to the 'RawContent'.
  accessContents :: Lens' c RawContent
```

Some things expose [[RawContent]]s.