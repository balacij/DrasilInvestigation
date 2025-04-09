```haskell
targPos   = constrained'    (uc       C.targPos   (subStr lP "target") Real metre ) [gtZeroConstr] (exactDbl 1000)
```

A [[ConstrConcept]] that extends a transient [[UnitalChunk]] (also extending another chunk: [[target position (ConceptChunk)]], with information that it's display symbol is $p_\text{target}$ and is a [[Real]]-typed variable with [[Metre (UnitDefn)]] units.) with information that it must be $> 0$ (via [[ConstraintE]]) and a reasonable value is 1000 (interestingly, with no units!).