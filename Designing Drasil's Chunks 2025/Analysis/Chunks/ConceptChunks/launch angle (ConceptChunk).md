```haskell
launAngle = cc' launchAngleNC
  (foldlSent_ [phraseNP (the angle), S "between the", phrase launcher `S.and_` S "a straight line"
             `S.fromThe` phraseNP (launcher `toThe` target)])
```

A [[ConstrConcept]] extending [[launch angle (IdeaDict)]] with a definition, "the angle between the launcher and a straight line from the launcher to the target," dependant on:
* [[launcher (ConceptChunk)]], and
* [[target (ConceptChunk)]].