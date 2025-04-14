```haskell
cartSyst = cic "cartSyst" cartSystDesc "cartSyst" assumpDom

cartSystDesc :: Sentence
cartSystDesc = atStartNP (a_ cartesian) `S.is` S "used" +:+. fromSource neglectCurv
```

A [[ConceptInstance]] in the [[assumption (ConceptChunk)]] domain explaining that: a [[Cartesian coordinate system (ConceptChunk)]] is used (from [[neglectCurve (ConceptInstance)]]).