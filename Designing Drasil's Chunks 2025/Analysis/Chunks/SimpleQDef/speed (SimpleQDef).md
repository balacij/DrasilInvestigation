```haskell
vecMagQD :: SimpleQDef
vecMagQD = mkQuantDef QP.speed speedEqn

...
speedEqn = norm (sy QP.velocity)
```

A [[SimpleQDef]] that extends [[speed (UnitalChunk)]] with a formula dependant on [[velocity (UnitalChunk)]].