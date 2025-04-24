```haskell
-- | For all containers, c, which contain typed expressions, e, against a
--   specific type universe, t, expose all expressions and relations that need
--   to be type-checked.
class Typed e t => RequiresChecking c e t where
  -- | All things that need type checking.
  requiredChecks :: c -> [(e, t)]
```

For all things which we have a bidirectional type system defined for (via [[Typed]]), what things does it expose which should be type-checked?