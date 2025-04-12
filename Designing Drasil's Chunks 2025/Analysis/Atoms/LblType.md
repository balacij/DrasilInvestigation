```haskell
-- | Applying different pieces of information for a reference.
-- An RP is a decorated internal reference.
-- Citation is a citation.
-- URI is for URLs and other external links.
data LblType =
    RP IRefProg String
  | Citation String
  | URI String
```

(Sorry, I can't write about this again... see https://github.com/JacquesCarette/Drasil/pull/4022 and referenced PRs and issues ).

May contain an [[IRefProg]].
