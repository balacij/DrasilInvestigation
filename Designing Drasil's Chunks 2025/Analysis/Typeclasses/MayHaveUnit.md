```haskell
-- | Types may contain a unit ('UnitDefn').
class MayHaveUnit u where
   getUnit :: u -> Maybe UnitDefn
```

Something that might have a [[UnitDefn|unit]].