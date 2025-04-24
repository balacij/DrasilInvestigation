```haskell
-- | Build a bidirectional type checker for your expression language, e, with
--   respect to a specific type universe, t.
class (Eq t, Show t) => Typed e t where
  
  -- | Given a typing context and an expression, infer a unique type or explain
  --   what went awry.
  infer :: TypingContext t -> e -> Either t TypeError

  -- | Given a typing context, an expression, and an expected type, check if the
  --   expression can satisfy the expectation.
  check :: TypingContext t -> e -> t -> Either t TypeError
```

Pretty straightforward as per comments. Depends on [[TypingContext]] and [[TypeError]].