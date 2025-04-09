#todo: This is a very odd atom -- what do we actually use it for? I don't see any real usage?

```haskell
-- UName for the base cases, otherwise build up.
-- Probably a 7-vector would be better (less error-prone!)
-- | Language of units (how to build them up into a unit symbol).
-- Of the form ('Symbol' ^ 'Integer'). The 'Integer' may be negative, but should not be zero.
newtype USymb = US [(Symbol, Integer)] -- can be negative, should not be 0
  deriving (Eq)
```
