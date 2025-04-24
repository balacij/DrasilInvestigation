```haskell
-- | A class that contains a list of decorated references ('DecRef's).
class HasDecRef c where
  -- | Provides a 'Lens' to the 'DecRef's.
  getDecRefs :: Lens' c [DecRef]
```

Something might have [[DecRef]]s! Really, this is about having [[Reference]]s with specific content to be referred to (i.e., [[RefInfo]]).