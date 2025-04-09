```haskell
-- | ConstrConcepts are conceptual symbolic quantities ('DefinedQuantityDict')
-- with 'Constraint's and maybe a reasonable value (no units!).
-- Similar to 'ConstrainedChunk' but includes a definition and domain. 
--
-- Ex. Measuring the length of a pendulum arm could be a concept that has some reasonable value
-- (between 1 cm and 2 m) and the constraint that the length cannot be a negative value.
data ConstrConcept = ConstrConcept { _defq    :: DefinedQuantityDict
                                   , _constr' :: [ConstraintE]
                                   , _reasV'  :: Maybe Expr
                                   }
```

A `ConstrConcept` extends a [[DefinedQuantityDict]] with a list of constraints ([[ConstraintE]], indicating usability in code generation) and _maybe_ a "reasonable (expectable) value" for the quantity to be (via [[Expr]]).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[HasSpace]]
* [[HasSymbol]]
* [[Quantity]]
* [[Definition]]
* [[ConceptDomain]]
* [[Constrained]]
* [[HasReasVal]]
* [[MayHaveUnit]]
* [[Express]]
