```haskell
-- | Members must have a reference address.
class HasRefAddress b where
  -- | Provides the ability to hold a reference address.
  getRefAdd :: b -> LblType
```

Some things can be referable in the generated [[Generic Document Language]]-based documents via [[LblType]].