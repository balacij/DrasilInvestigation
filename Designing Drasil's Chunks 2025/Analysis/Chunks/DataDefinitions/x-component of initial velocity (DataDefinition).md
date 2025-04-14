```haskell
speedIX, speedIY :: DataDefinition
speedIX = ddENoRefs speedIXQD Nothing "speedIX" [speedRef, figRef]
```

A [[DataDefinition]] that extends [[x-component of initial velocity (SimpleQDef)]] and contains two notes:
* [[initial speed (UnitalChunk)]] is from the [[speed (DataDefinition)]], and
* [[launch angle (ConstrConcept)]] is shown in the [[launch (LabelledContent)]] figure.
