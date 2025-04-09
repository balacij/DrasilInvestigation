```haskell
-- | CommonIdea is a 'NamedIdea' with the additional
-- constraint that it __must__ have an abbreviation.
class NamedIdea c => CommonIdea c where
  -- | Introduces abrv which necessarily provides an abbreviation.
  abrv :: c -> String
```

A thing that is a `CommonIdea` must also be a [[NamedIdea]] with the added restriction that it **must** have an abbreviation.