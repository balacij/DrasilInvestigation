```haskell
data CI = CI { _nc' :: IdeaDict, _ab :: String, cdom' :: [UID]}
```

A CI is an [[IdeaDict]] that belongs to a [[ConceptDomain|concept domain]] and is required to have an abbreviation (via type classes [[Idea]] (**maybe has** an abbreviation) and [[CommonIdea]] (**must have** an abbreviation)).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[CommonIdea]]
* [[ConceptDomain]]