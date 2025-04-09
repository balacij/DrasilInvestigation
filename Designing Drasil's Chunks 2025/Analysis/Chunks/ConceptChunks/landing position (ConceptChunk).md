```haskell
landPos, ... :: ConceptChunk
landPos = cc' landingPosNC
  (foldlSent_ [phraseNP (the distance) `S.fromThe` phrase launcher `S.toThe`
            S "final", phraseNP (position `ofThe` projectile)])
```

A [[ConceptChunk]] extending [[landing position (IdeaDict)]] with a definition, "the distance from the launcher to the final position of the projectile," dependant on:
* [[distance (ConceptChunk)]],
* [[position (ConceptChunk)]], and
* [[Projectile (ConceptChunk)]].