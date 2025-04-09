
Things that instantiate this have an axiomatic description and can be rendered as such.

```haskell
-- | Data that can be expressed using 'ModelExpr'.
class Express c where
  express :: c -> ModelExpr

instance Express Literal where
  express = Lit

-- | Rewriting 'Expr's using the 'ModelExpr' language.
instance Express Expr where
  express = expr

-- | No change, it's already a 'ModelExpr'.
instance Express ModelExpr where
  express = id
```