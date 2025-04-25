```haskell
-- | Models can be of different kinds:
--     * 'EquationalModel's represent quantities that are calculated via a single definition/'QDefinition'.
data ModelKinds e where
  ...
  EquationalModel       :: QDefinition e     -> ModelKinds e
  ...
```

An [[EquationalModel]] is a variant of [[ModelKind(s)]] that wraps a [[QDefinition]].