```haskell
-- | Units are 'Idea's with a 'Definition' which store a unit symbol.
-- They must also be explicitly declared to be instances of IsUnit.
class (Idea u, Definition u, HasUnitSymbol u) => IsUnit u where
  -- | May have a unit definition.
  udefn :: u -> Maybe UDefn
  -- | Holds units as a list of 'UID'.
  getUnits :: u -> [UID]
```

A chunk that "is a unit" (/"defines a unit") must also be an [[Idea]] and have a [[Definition]] and [[HasUnitSymbol|Unit Symbol]]. 


#todo What is going on with this type class definition?