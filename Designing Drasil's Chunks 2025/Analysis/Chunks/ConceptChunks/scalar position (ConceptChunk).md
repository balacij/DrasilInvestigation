```haskell
scalarPos = dccWDS "scalarPos" (cn' "scalar position")
  (S "magnitude" `S.the_ofThe` phrase position +:+ S "vector")
```

A [[ConceptChunk]] defining "scalar position," dependant on [[position (ConceptChunk)]].