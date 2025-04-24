```haskell
-- | Derivations are an ordered list of sentences and expressions.
-- They are rendered in order as paragraphs and equation blocks to display
-- the derivation.
data Derivation = Derivation Sentence [Sentence]
```

A `Derivation` contains a header (a [[Sentence]]) and a list of [[Sentence]]s that explain how a derivation works.