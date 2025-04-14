```haskell
accelXZero      = cic "accelXZero"      accelXZeroDesc      "accelXZero"      assumpDom
...
accelXZeroDesc :: Sentence
accelXZeroDesc = atStartNP (NP.the (acceleration `inThe` xDir)) `S.is` (S "zero" !.)
```

A [[ConceptInstance]] in the [[assumption (ConceptChunk)]] domain that explains that: the [[acceleration (ConceptChunk)]] in the [[x-direction (ConceptChunk)]] is zero.

