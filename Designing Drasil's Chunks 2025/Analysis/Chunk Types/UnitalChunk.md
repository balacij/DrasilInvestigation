```haskell
-- | Similar to a `DefinedQuantityDict`, UnitalChunks are concepts
-- with quantities that must have a unit definition.
-- Contains 'DefinedQuantityDict's and a 'UnitDefn'.
--
-- Ex. A pendulum arm is a tangible object with a symbol (l) and units (cm, m, etc.).
data UnitalChunk = UC { _defq' :: DefinedQuantityDict
                      , _uni :: UnitDefn
                      }
```

A `UnitalChunk` extends a [[DefinedQuantityDict]] with it's own [[UnitDefn]], which now means that the [[DefinedQuantityDict]] _must_ have one.