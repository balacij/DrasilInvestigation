```haskell
offset    = constrainedNRV' (uc       C.offset    (subStr lD "offset") Real metre ) [physRange $ UpFrom (Exc, neg $ sy targPos)]
```

A [[ConstrConcept]] extending a transient [[UnitalChunk]] (also extending [[offset (ConceptChunk)]] with a display [[Symbol]], $d_\text{offset}$, type information, [[Real]], and unit information: [[Metre (UnitDefn)]]) with a [[ConstraintE]]: $> - p_\text{target}$, dependant on [[target position (ConstrConcept)]].