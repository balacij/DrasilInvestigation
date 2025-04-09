```haskell
data QDefinition e where
  QD :: DefinedQuantityDict -> [UID] -> e -> QDefinition e
```

A `QDefinition` is a chunk that extends a [[DefinedQuantityDict]] with a formula (encoded normally with either [[Expr]], [[ModelExpr]], or [[Literal]]). For "function quantities," the "input variables" are given as [[UID]]s

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[DefinesQuantity]]
* [[HasSpace]]
* [[HasSymbol]]
* [[Definition]]
* [[Quantity]]
* [[DefiningExpr]]
* [[Express]]
