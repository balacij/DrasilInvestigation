```haskell
-- | An 'Idea' is the combination of a 'NamedIdea' and a 'CommonIdea'.
-- In other words, it /may/ have an acronym/abbreviation.
class NamedIdea c => Idea c where
  -- | Gets the acronym/abbreviation.
  getA :: c -> Maybe String
```
Note: you can ignore the "CommonIdea" part of the above code comment.

An `Idea` must also be a [[NamedIdea]].