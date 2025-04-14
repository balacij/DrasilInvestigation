```haskell
constAccel      = cic "constAccel"      constAccelDesc      "constAccel"      assumpDom

constAccelDesc :: Sentence
constAccelDesc = atStartNP (the acceleration) `S.is` S "constant" +:+.
                 fromSources [accelXZero, accelYGravity, neglectDrag, freeFlight]
```

A [[ConceptInstance]] in the [[assumption (ConceptChunk)]] domain explaining that: the [[acceleration (ConceptChunk)]] is constant (from [[accelXZero (ConceptInstance)]], [[accelYGravity (ConceptInstance)]], [[neglectDrag (ConceptInstance)]], [[freeFlight (ConceptInstance)]]).