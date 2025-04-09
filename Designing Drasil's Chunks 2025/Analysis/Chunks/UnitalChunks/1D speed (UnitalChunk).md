```haskell
projSpeed :: UnitalChunk
projSpeed = uc C.projSpeed (Concat [lV, label "(", lT, label ")"]) Real velU
```

A [[UnitalChunk]] extending [[1D speed (ConceptChunk)]] with a display [[Symbol]] ($v(t)$) and information that it is a [[Real]]-typed variable with unit: [[velocity (UnitDefn)]] (effectively: $m/s$).