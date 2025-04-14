```haskell
messageQD :: SimpleQDef
messageQD = mkQuantDef message E.message

...
message :: PExpr
message = completeCase [case1, case2, case3]
  where case1 = (str "The target was hit.",        abs_ (sy offset $/ sy targPos) $< sy tol)
        case2 = (str "The projectile fell short.", sy offset $< exactDbl 0)
        case3 = (str "The projectile went long.",  sy offset $> exactDbl 0)
```

A [[SimpleQDef]] that extends [[message (QuantityDict)]] with a formula dependant on:
* [[offset (ConstrConcept)]],
* [[target position (ConstrConcept)]],
* [[tolerance (ConstQDef)]]
