```haskell
-- | 'Citation's should have a fields ('CiteField').
class HasFields c where
  -- | Provides a 'Lens' to 'CiteField's.
  getFields :: Lens' c [CiteField]
```

For things that expose [[bibtex]]-like data.