```haskell
acceleration, ... :: UnitalChunk
acceleration           = uc CP.acceleration           (Concat [vec lA, label "(", lT, label ")"]) (Vect Real) accelU
```

A [[UnitalChunk]] extending [[acceleration (ConceptChunk)]] with a display [[Symbol]] ($\vec{a}(t)$), type information ($\mathbb{R}^n$), and a unit: [[acceleration (UnitDefn)]].