```haskell
-- | The most basic item: having a unique identifier key, here a UID.
class HasUID c where
  -- | Provides a /unique/ id for internal Drasil use.
  uid :: Getter c UID
```

Something that satisfies `HasUID` currently means that "it is a chunk."