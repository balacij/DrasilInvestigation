```haskell
neglectDrag     = cic "neglectDrag"     neglectDragDesc     "neglectDrag"     assumpDom

neglectDragDesc :: Sentence
neglectDragDesc = (S "Air drag" `S.is` S "neglected" !.)
```

A [[ConceptInstance]] in the [[assumption (ConceptChunk)]] explaining that: Air drag is neglected.