```haskell
launSpeed = constrained'    (uc       C.launSpeed (subStr lV "launch") Real velU  ) [gtZeroConstr] (exactDbl 100)
```

A [[ConstrConcept]] extending a transient [[UnitalChunk]] (also extending [[launch speed (ConceptChunk)]], with a display [[Symbol]], $v_\text{launch}$, type information, [[Real]], and unit information, [[velocity (UnitDefn)]]) with a [[ConstraintE]], $>0$, and a "reasonable value" of exactly $100$ ([[Expr]]).