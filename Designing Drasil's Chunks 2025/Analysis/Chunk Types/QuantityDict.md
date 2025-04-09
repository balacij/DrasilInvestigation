```haskell
-- | QuantityDict is a combination of an 'IdeaDict' with a quantity.
-- Contains an 'IdeaDict', 'Space', a function from 
-- 'Stage' -> 'Symbol', and 'Maybe' a 'UnitDefn'.
--
-- Ex. A pendulum arm does not necessarily have to be defined as a concept before
-- we assign a space (Real numbers), a symbol (l), or units (cm, m, etc.).
data QuantityDict = QD { _id' :: IdeaDict
                       , _typ' :: Space
                       , _symb' :: Stage -> Symbol
                       , _unit' :: Maybe UnitDefn
                       }
```

A chunk that extends an [[IdeaDict]] that assigns "mathematical meaning" to a term, proclaiming that the term denotes a quantity, with atoms:
* A [[Space]] (i.e., a "type").
* A [[Symbol]], guarded by a rendering [[Stage]].
And:
* Maybe a [[UnitDefn]] (i.e., the unit of the quantity).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[HasSpace]]
* [[HasSymbol]]
* [[Quantity]]
* [[MayHaveUnit]]
* [[Express]]
