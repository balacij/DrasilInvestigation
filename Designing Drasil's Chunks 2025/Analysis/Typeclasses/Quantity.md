```haskell
-- | A Quantity is an 'Idea' with a 'Space' and a 'Symbol'.
-- In theory, it should also restrict to being a part of 'MayHaveUnit', but that causes
-- all sorts of import cycles (or lots of orphans).
class (Idea c, HasSpace c, HasSymbol c) => Quantity c where
```

Alias for a(n) thing that satisfies all of:
* [[Idea]]
* [[HasSpace]]
* [[HasSymbol]]
