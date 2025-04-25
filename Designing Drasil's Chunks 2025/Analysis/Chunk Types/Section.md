```haskell
-- | Sections have a title ('Sentence'), a list of contents ('SecCons')
-- and a shortname ('Reference').
data Section = Section
             { tle  :: Title
             , cons :: [SecCons]
             , _lab :: Reference
             }
makeLenses ''Section
```

An extension of a [[Reference]] that adds a [[Title]] and a list of [[SecCons]].

Satisfies:
* [[HasUID]]
* [[HasShortName]]
* [[Referable]]
* [[HasRefAddress]]
