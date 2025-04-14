```haskell
targetXAxis = cic "targetXAxis" targetXAxisDesc "targetXAxis" assumpDom

targetXAxisDesc :: Sentence
targetXAxisDesc = atStartNP (the target) +:+ S "lies on the" +:+ phrase xAxis +:+. fromSource neglectCurv
```

A [[ConceptInstance]] explaining that: the [[target (ConceptChunk)]] lies on the [[x-axis (ConceptChunk)]] (from [[neglectCurve (ConceptInstance)]]).