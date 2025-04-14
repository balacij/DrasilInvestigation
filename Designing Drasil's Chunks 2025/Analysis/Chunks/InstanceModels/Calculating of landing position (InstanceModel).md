```haskell
landPosIM :: InstanceModel
landPosIM = imNoRefs (equationalModelN (nounPhraseSP "calculation of landing position") landPosQD)
  [qwC launSpeed $ UpFrom (Exc, exactDbl 0),
   qwC launAngle $ Bounded (Exc, exactDbl 0) (Exc, half $ sy pi_)]
  (qw landPos) [UpFrom (Exc, exactDbl 0)]
  (Just landPosDeriv) "calOfLandingDist" [angleConstraintNote, gravitationalAccelConstNote, landPosConsNote]

landPosQD :: SimpleQDef
landPosQD = mkQuantDef landPos E.landPosExpr

landPosDeriv :: Derivation
landPosDeriv = mkDerivName (phrase landPos) (weave [landPosDerivSents, map eS landPosDerivEqns])

landPosDerivSents :: [Sentence]
landPosDerivSents = [landPosDerivSent1, landPosDerivSent2, landPosDerivSent3, landPosDerivSent4]

landPosDerivSent1, landPosDerivSent2, landPosDerivSent3, landPosDerivSent4 :: Sentence
landPosDerivSent1 = foldlSentCol [S "We know that" +:+.
  foldlList Comma List
    [eqnWSource (sy ixPos $= exactDbl 0) launchOrigin,
     eqnWSource (sy xConstAccel $= exactDbl 0) accelXZero],
  S "Substituting these", plural value, S "into the x-direction" `S.of_`
  refS posVecGD, S "gives us"]
landPosDerivSent2 = foldlSentCol [S "To find the", phrase landPos `sC`
  S "we want to find the", ch xPos, phrase value, sParen (ch landPos),
  S "at", phrase flightDur, fromSource timeIM]
landPosDerivSent3 = foldlSentCol [S "From", refS speedIX,
  sParen (S "with" +:+ E (defines (sy iSpeed) (sy launSpeed))), S "we can replace", ch ixVel]
landPosDerivSent4 = S "Rearranging this gives us the required" +: phrase equation

landPosDerivEqns :: [ModelExpr]
landPosDerivEqns = D.landPosDeriv ++ [express landPosQD]
```

An [[InstanceModel]] extending a transient [[EquationalModel]] (also extending [[landing position (SimpleQDef)]]) with [[Inputs]]:
* [[launch speed (ConstrConcept)]] $> 0$
* $0 <$ [[launch angle (ConstrConcept)]] $< \frac{\pi}{2}$
Outputting a [[landing position (ConstrConcept)]]. It also contains 3 notes that note the constraints come from [[posXDirection (ConceptInstance)]] and [[yAxisGravity (ConceptInstance)]], [[launch (LabelledContent)]] shows [[launch angle (ConstrConcept)]], and [[gravitational acceleration (ConstQDef)]] is defined by [[gravAccelValue (ConceptInstance)]].
  
```haskell
angleConstraintNote = foldlSent [atStartNP (the constraint),
  eS (realInterval launAngle (Bounded (Exc, exactDbl 0) (Exc, half $ sy pi_))) `S.is` S "from",
  refS posXDirection `S.and_` refS yAxisGravity `sC`
  S "and is shown" `S.in_` refS figLaunch]

gravitationalAccelConstNote = ch gravitationalAccelConst `S.is`
  S "defined in" +:+. refS gravAccelValue

landAndTargPosConsNote = atStartNP' (the constraint) +:+
  eS (sy landPos $> exactDbl 0) `S.and_` eS (sy targPos $> exactDbl 0) `S.are` S "from" +:+. refS posXDirection
```

It also contains a derivation containing the following steps:
* Substitute known zero-values from [[launchOrigin (ConceptInstance)]] and [[accelXZero (ConceptInstance)]] (i.e., $p_x^i = 0$ and $a_x^c = 0$) into [[Position vector as a function of time for 2D motion under constant acceleration (GenDefn)]].
* Substitute the formula from [[x-component of initial velocity (DataDefinition)]] (${{v_{\text{x}}}^{\text{i}}}={v^{\text{i}}}\,\cos\left(θ\right)$).
* Rearrange for the final formula.

#todo Does this derivation need to be reformatted?