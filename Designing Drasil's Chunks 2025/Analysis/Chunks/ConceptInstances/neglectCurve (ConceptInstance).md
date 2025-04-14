```haskell
neglectCurv = cic "neglectCurv" neglectCurvDesc "neglectCurv" assumpDom


neglectCurvDesc :: Sentence
neglectCurvDesc = atStartNP (the distance) `S.is` S "small enough that" +:+.
                  (S "curvature" `S.the_ofThe` S "celestial body can be neglected")
```

A [[ConceptInstance]] that explains that: the [[distance (ConceptChunk)]] is small enough that the curvature of the celestial body can be neglected.