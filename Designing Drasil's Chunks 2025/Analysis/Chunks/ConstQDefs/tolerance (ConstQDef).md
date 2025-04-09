```haskell
tol :: ConstQDef
tol = mkQuantDef (vcSt "tol" (nounPhraseSP "hit tolerance") (autoStage vEpsilon) Real) (perc 2 2)
```

A [[ConstQDef]] of a transient [[QuantityDict]] ("tol" -- a [[Real]]-typed quantity with display [[Symbol]] $\epsilon$), declaring that the "tol" is precisely $\frac{2}{10^2}$ (or, $2\%$).