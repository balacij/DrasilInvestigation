```haskell
magNote :: Sentence
magNote = foldlSent [S "For a given", phrase QP.velocity, S "vector", ch QP.velocity `sC`
  S "the magnitude of the vector", sParen (eS speedEqn) `S.isThe`
  S "scalar called", phrase QP.speed]

vecMag :: DataDefinition
vecMag = ddENoRefs vecMagQD Nothing "vecMag" [magNote]
```

A [[DataDefinition]] that extends [[speed (SimpleQDef)]] with a note: For a given [[velocity (UnitalChunk)]], the magnitude of the vector, $||v||$ is the scalar called [[speed (UnitalChunk)]].