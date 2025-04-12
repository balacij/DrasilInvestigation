```haskell
-- | Members of this class have the ability to be referenced.
class (HasUID s, HasRefAddress s) => Referable s where
  -- | The referencing address (what we're linking to).
  -- Only visible in the source (tex/html).
  refAdd    :: s -> String 
  -- | Alternate form of reference.
  renderRef :: s -> LblType
```

