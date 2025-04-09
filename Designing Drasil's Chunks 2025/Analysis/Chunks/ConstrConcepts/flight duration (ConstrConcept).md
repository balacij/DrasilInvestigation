```haskell
flightDur, ... :: ConstrConcept
flightDur = constrainedNRV' (uc       C.flightDur (subStr lT "flight") Real second) [gtZeroConstr]
```

A [[ConstrConcept]] extending a transient [[UnitalChunk]] (also extending another chunk; [[flight duration (ConceptChunk)]], with a display [[Symbol]] ($t_\text{flight}$), type information ([[Real]]), and [[Second (UnitDefn)]] units) with a $> 0$ [[ConstraintE]].