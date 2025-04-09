```haskell
-- | ConstrainedChunks are symbolic quantities ('QuantityDict')
-- with 'Constraint's and maybe a typical value ('Maybe' 'Expr').
--
-- Ex. Measuring the length of a pendulum would have some reasonable value (between 1 cm and 2 m)
-- and the constraint that the length cannot be a negative value.
data ConstrainedChunk = ConstrainedChunk { _qd     :: QuantityDict
                                         , _constr :: [ConstraintE]
                                         , _reasV  :: Maybe Expr
                                         }
```

A `ConstrainedChunk` extends a [[QuantityDict]] with constraints ([[ConstraintE]], indicating usability in code generation) and _maybe_ a reasonable value for the quantity to be (via [[Expr]]). This is almost identical to a [[ConstrConcept]] except that the [[ConstrConcept]] is only defined for a [[DefinedQuantityDict]], indicating that the [[ConstrConcept]] is presumed to be for a quantity with a corresponding formula (via a [[QDefinition]]).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[HasSpace]]
* [[HasSymbol]]
* [[Quantity]]
* [[Constrained]]
* [[HasReasVal]]
* [[MayHaveUnit]]