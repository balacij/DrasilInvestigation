```haskell
xVel = dccWDS "xVel" (xComp `of_` velocity) (atStartNP $ NP.the $ xComp `of_` velocity)
```

A [[ConceptChunk]] dependant on [[x-component (ConceptChunk)]] and [[velocity (ConceptChunk)]].