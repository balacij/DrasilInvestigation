```haskell
speed = dccWDS "speed" (cn' "speed")
  (S "magnitude" `S.the_ofThe` phrase velocity +:+ S "vector")
```

A [[ConceptChunk]] that defines "speed", dependant on [[velocity (ConceptChunk)]].