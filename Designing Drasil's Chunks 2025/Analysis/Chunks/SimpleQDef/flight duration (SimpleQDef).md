```haskell
timeQD :: SimpleQDef 
timeQD = mkQuantDef flightDur E.flightDur'
```

A [[SimpleQDef]] that extends [[flight duration (ConstrConcept)]] with a formula (an [[Expr]]): $\frac{2v_\mathit{launch}\theta}{g}$.
