```haskell
-- TODO: conceptual typeclass?
-- Temporary hack to avoid loss of information
-- | Records any additional notes needed to avoid losing information
class HasAdditionalNotes c where
  -- | Provides a 'Lens' to the notes.
  getNotes :: Lens' c [Sentence]
```

For things that have extra "notes" ([[Sentence]]s).