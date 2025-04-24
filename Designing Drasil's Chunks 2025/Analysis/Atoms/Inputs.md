```haskell
type Input = (QuantityDict, Maybe (RealInterval Expr Expr))
```

Used for our theories (TMs, GDs, IMs, and DDs), this indicate a restriction on an input variable (a [[Quantity]] restricted by _maybe_ a [[RealInterval]]]).