---
assumesExistenceOfHack: "[[Values of Auxiliary Constants (Section)]]"
---

```haskell
gravAccelValue = cic "gravAccelValue" gravAccelValueDesc "gravAccelValue" assumpDom
```

A [[ConceptInstance]] that explains that "the [[acceleration (ConceptChunk)]] due to [[gravity (ConceptChunk)]] is assumed to have the [[value (IdeaDict)]] provided in the section for [[Values of Auxiliary Constants (IdeaDict)]]" (where it references the IdeaDict and contains a transient copy of the [[Values of Auxiliary Constants (Section)]] chunk).



```haskell
gravAccelValueDesc :: Sentence
gravAccelValueDesc = atStartNP (the acceleration) +:+ S "due to" +:+
  phrase gravity +:+ S "is assumed to have the" +:+ phrase value +:+ 
  S "provided in the section for" +:+. namedRef (SRS.valsOfAuxCons [] []) (titleize consVals)
```

