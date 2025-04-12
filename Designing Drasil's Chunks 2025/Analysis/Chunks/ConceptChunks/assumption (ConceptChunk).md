```haskell
..., assumpDom, ... :: ConceptChunk
assumpDom     = ccs (mkIdea "assumpDom"     (assumption ^. term)               $ Just "A")        EmptyS [srsDom]
```

A [[ConceptChunk]] carrying a transient [[IdeaDict]] declaring "A" as an abbreviation for [[assumption (CI)]].