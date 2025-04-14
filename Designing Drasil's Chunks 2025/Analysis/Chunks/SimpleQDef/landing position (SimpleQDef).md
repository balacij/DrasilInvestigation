```haskell
landPosQD :: SimpleQDef
landPosQD = mkQuantDef landPos E.landPosExpr
```

A [[SimpleQDef]] that extends [[landing position (ConstrConcept)]] with a formula dependant on:
* [[launch speed (ConstrConcept)]]
* [[launch angle (ConstrConcept)]]
* [[gravitational acceleration (ConstQDef)]]

```haskell
landPosExpr = exactDbl 2 $* square (sy launSpeed) $* sin (sy launAngle) $* cos (sy launAngle) $/ sy gravitationalAccelConst
```