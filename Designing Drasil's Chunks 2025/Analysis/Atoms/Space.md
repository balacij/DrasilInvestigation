```haskell
-- | The difference kinds of spaces that may exist. This type holds numerical
-- spaces (such as the set of integers, rationals, etc.), a space for booleans,
-- a space for characters, dimensional spaces (vectors, arrays, etc.), a space
-- for Actors, discrete sets (both for numbers and strings), and a void space.
data Space =
    Integer
  | Rational
  | Real
  | Natural
  | Boolean
  | Char
  | String
  | Vect Space -- TODO: Length for vectors?
  | Set Space
  | Matrix Int Int Space
  | Array Space
  | Actor String 
  | Function (NE.NonEmpty Primitive) Primitive
  | Void
  deriving (Eq, Show)
```

All variables should have a type. Currently, Space is (ab)used for code-related contexts and pure mathematical contexts.