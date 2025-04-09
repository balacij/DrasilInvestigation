```haskell
-- | Defines a chunk.
class Definition c where
  -- | Provides (a 'Lens' to) the definition for a chunk.
  defn :: Lens' c Sentence
```

A chunk that satisfies `Definition` means that it has a human-readable definition for _something_.