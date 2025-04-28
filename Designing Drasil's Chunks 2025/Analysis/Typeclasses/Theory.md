```haskell
-- | Theories are the basis for building models with context,
-- spaces, quantities, operations, invariants, etc.
class Theory t where
  valid_context :: Lens' t [TheoryModel]
  spaces        :: Lens' t [SpaceDefn]
  quantities    :: Lens' t [QuantityDict]
  operations    :: Lens' t [ConceptChunk] -- FIXME: Should not be Concept
  defined_quant :: Lens' t [ModelQDef]
  invariants    :: Lens' t [ModelExpr]
  defined_fun   :: Lens' t [ModelQDef]
```

A typeclass that indicates something is a "theory," which means that it has:
* "a valid context" (a list of [[TheoryModel]]s)
* "spaces" (types; a list of [[SpaceDefn]]s)
* "quantities" (symbols; a list of [[QuantityDict]]s)
* "operations" (operators; a list of [[ConceptChunk]]s)
* "defined quantities" (a list of [[ModelQDef]]s)
* "invariants" (a list of [[ModelExpr]]s)
* "defined functions" (a list of [[ModelQDef]]s)
