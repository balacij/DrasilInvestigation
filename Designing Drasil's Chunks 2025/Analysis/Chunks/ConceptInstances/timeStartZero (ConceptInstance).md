```haskell
timeStartZero = cic "timeStartZero" timeStartZeroDesc "timeStartZero" assumpDom

timeStartZeroDesc :: Sentence
timeStartZeroDesc = atStart time +:+. S "starts at zero"
```

A [[ConceptInstance]] in the [[assumption (ConceptChunk)]] domain explaining that "[[time (ConceptChunk)]] starts at zero."