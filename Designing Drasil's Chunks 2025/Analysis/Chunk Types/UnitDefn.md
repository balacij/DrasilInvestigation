```haskell
-- | For defining units.
-- It has a 'ConceptChunk' (that defines what kind of unit it is),
-- a unit symbol, maybe another (when it is a synonym),
-- perhaps a definition, and a list of 'UID' of the units that make up
-- the definition.
--
-- Ex. Meter is a unit of length defined by the symbol (m).
data UnitDefn = UD { _vc :: ConceptChunk 
                   , _cas :: UnitSymbol
                   , _cu :: [UID] }
makeLenses ''UnitDefn
```

A chunk for defining units, extending a [[ConceptChunk]] with a [[UnitSymbol]] and list of dependency [[UnitDefn]]s.

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[ConceptDomain]]
* [[HasUnitSymbol]]
* [[IsUnit]]
