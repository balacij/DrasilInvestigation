```haskell
twoDMotion      = cic "twoDMotion"      twoDMotionDesc      "twoDMotion"      assumpDom

twoDMotionDesc :: Sentence
twoDMotionDesc = atStartNP (NP.the (projMotion `is` twoD)) +:+. sParen (getAcc twoD)
```

A [[ConceptInstance]] explaining that: the [[projectile motion (IdeaDict)]] is [[two-dimensional (CI)]] (2D).