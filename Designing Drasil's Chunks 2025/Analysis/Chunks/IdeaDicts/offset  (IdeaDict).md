```haskell
offsetNC     = nc "offset"   (nounPhraseSent $ S "distance between the" +:+ phraseNP (targetPosNC `andThe` landingPosNC))
```

An [[IdeaDict]] dependant on [[target position (IdeaDict)]] and [[landing position (IdeaDict)]].