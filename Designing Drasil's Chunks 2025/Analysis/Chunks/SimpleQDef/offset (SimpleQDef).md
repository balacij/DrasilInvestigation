```haskell
offsetQD :: SimpleQDef
offsetQD = mkQuantDef offset E.offset'
```

A [[SimpleQDef]] extending [[offset (ConstrConcept)]] with an expression (l - r) based on:
* [[landing position (ConstrConcept)]] and
* [[target position (ConstrConcept)]].
