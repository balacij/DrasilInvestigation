```haskell
yVel = dccWDS "yVel" (yComp `of_` velocity) (atStartNP $ NP.the $ yComp `of_` velocity)
```

A [[ConceptChunk]] dependant on [[y-component (ConceptChunk)]] and [[velocity (ConceptChunk)]].