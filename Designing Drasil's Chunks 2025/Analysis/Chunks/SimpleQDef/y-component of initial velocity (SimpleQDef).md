```haskell
..., speedIYQD :: SimpleQDef
speedIYQD = mkQuantDef iyVel $ sy iSpeed $* sin (sy launAngle)
```

A [[SimpleQDef]] that extends [[y-component of initial velocity (UnitalChunk)]] with a formula dependant on [[initial speed (UnitalChunk)]] and [[launch angle (ConstrConcept)]].