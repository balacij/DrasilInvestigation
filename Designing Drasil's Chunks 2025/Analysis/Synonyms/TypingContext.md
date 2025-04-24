```haskell
-- | We can only type check 'UID's within a type context relating 'UID's to
--   types since they don't carry any type information.
type TypingContext t = M.Map UID t
```