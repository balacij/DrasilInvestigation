```haskell
speedIXQD, ... :: SimpleQDef
speedIXQD = mkQuantDef ixVel $ sy iSpeed $* cos (sy launAngle)
```

A [[SimpleQDef]] that extends [[x-component of initial velocity (UnitalChunk)]] with a formula dependant on [[initial speed (UnitalChunk)]] and [[launch angle (ConstrConcept)]].