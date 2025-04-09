```haskell
-- | Language of unit equations, to define a unit relative
-- to another.
data UDefn = USynonym USymb      -- ^ to define straight synonyms.
           | UScale Double USymb -- ^ scale, i.e. *.
           | UShift Double USymb -- ^ shift, i.e. +.
```

Dependencies:
* [[USymb]]
