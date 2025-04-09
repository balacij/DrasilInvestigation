```haskell
offset    = constrainedNRV' (uc       C.offset    (subStr lD "offset") Real metre ) [physRange $ UpFrom (Exc, neg $ sy targPos)]
```

A [[ConceptChunk]] extending a transient [[UnitalChunk]] (extending [[offset (ConceptChunk)]] with a display [[Symbol]], $d_\text{offset}$, type information, [[Real]], and [[Metre (UnitDefn)]] units) with a [[ConstraintE]], $> - p_\text{target}$, dependant on [[target position (ConstrConcept)]].