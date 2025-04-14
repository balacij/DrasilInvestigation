```haskell
freeFlight      = cic "freeFlight"      freeFlightDesc      "freeFlight"      assumpDom

freeFlightDesc :: Sentence
freeFlightDesc = S "The flight" `S.is` S "free; there" `S.are` S "no" +:+ plural collision +:+
                 S "during" +:+. (S "trajectory" `S.the_ofThe` phrase projectile)
```

A [[ConceptInstance]] in the [[assumption (ConceptChunk)]] domain explaining that: the flight is free; there [[collision (ConceptChunk)]]s during the trajectory of the [[Projectile (ConceptChunk)]].