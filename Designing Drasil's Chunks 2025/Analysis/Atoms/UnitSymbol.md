```haskell
-- | When we define units, they come in three flavours:
-- SI (base) units, derived SI units (aka synonyms), and defined units.
-- The type below captures that knowledge.
data UnitSymbol =
     BaseSI USymb
   | DerivedSI USymb USymb UDefn
   | Defined USymb UDefn
```

Dependencies:
* [[USymb]]
* [[UDefn]]