```haskell
-- | 'IdeaDict' is the canonical dictionary associated to an 'Idea'.
-- Contains a 'UID' and a term that could have an abbreviation ('Maybe' 'String').
--
-- Ex. The project name "Double Pendulum" may have the abbreviation "DblPend".
data IdeaDict = IdeaDict {
  _uu :: UID,
  _np :: NP,
  mabbr :: Maybe String
}
```

An IdeaDict is a chunk that simply proclaims a "term" (satisfying the [[NamedIdea]] typeclass) which other chunks may assign further meaning to. An IdeaDict may also have an abbreviation (satisfying the [[Idea]] typeclass).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
