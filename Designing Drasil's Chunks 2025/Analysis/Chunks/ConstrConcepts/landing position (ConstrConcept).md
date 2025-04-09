```haskell
landPos   = constrainedNRV' (uc       C.landPos   (subStr lP "land"  ) Real metre ) [gtZeroConstr]
```

A [[ConstrConcept]] extending a transient [[ConstrConcept]] (also extending another chunk; [[landing position (ConceptChunk)]], with a display [[Symbol]], $p_\text{land}$, type information, [[Real]], and unit information, [[Metre (UnitDefn)]]) with a [[ConstraintE]], $>0$.