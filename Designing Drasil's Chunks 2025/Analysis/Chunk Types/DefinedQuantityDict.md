
```haskell
-- | DefinedQuantityDict is the combination of a 'Concept' and a 'Quantity'.
-- Contains a 'ConceptChunk', a 'Symbol' dependent on 'Stage', a 'Space', and maybe a 'UnitDefn'.
-- Used when we want to assign a quantity to a concept. Includes the space, symbol, and units for that quantity.
--
-- Ex. A pendulum arm can be defined as a concept with a symbol (l), space (Real numbers), and units (cm, m, etc.).
data DefinedQuantityDict = DQD { _con :: ConceptChunk
                               , _symb :: Stage -> Symbol
                               , _spa :: Space
                               , _unit' :: Maybe UnitDefn
                               }
```

A `DefinedQuantityDict` (DQD) is very similar to a [[QuantityDict]]. In fact, it's almost a duplicate! The only explicit major difference is that it extends a [[ConceptChunk]] rather than an [[IdeaDict]]. This means that the DQD also comes with a _description_ of the term defined with this DQD.

