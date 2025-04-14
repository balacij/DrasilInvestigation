```haskell
timeIM :: InstanceModel
timeIM = imNoRefs (equationalModelN (nounPhraseSP "calculation of landing time") timeQD)
  [qwC launSpeed $ UpFrom (Exc, exactDbl 0)
  ,qwC launAngle $ Bounded (Exc, exactDbl 0) (Exc, half $ sy pi_)]
  (qw flightDur) [UpFrom (Exc, exactDbl 0)]
  (Just timeDeriv) "calOfLandingTime" [angleConstraintNote, gravitationalAccelConstNote, timeConsNote]

timeQD :: SimpleQDef 
timeQD = mkQuantDef flightDur E.flightDur'

timeDeriv :: Derivation
timeDeriv = mkDerivName (phrase flightDur) (weave [timeDerivSents, map eS timeDerivEqns])

timeDerivSents :: [Sentence]
timeDerivSents = [timeDerivSent1, timeDerivSent2, timeDerivSent3, timeDerivSent4, timeDerivSent5]

timeDerivSent1, timeDerivSent2, timeDerivSent3, timeDerivSent4, timeDerivSent5 :: Sentence
timeDerivSent1 = foldlSentCol [S "We know that" +:+.
  foldlList Comma List
    [eqnWSource (sy iyPos $= E.iyPos) launchOrigin,
     eqnWSource (sy yConstAccel $= E.yConstAccel) accelYGravity],
  S "Substituting these", plural value, S "into the y-direction" `S.of_`
  refS posVecGD, S "gives us"]
timeDerivSent2 = foldlSentCol [S "To find the", phrase time, S "that the",
  phrase projectile, S "lands" `sC` S "we want to find the", ch time, phrase value,
  sParen (ch flightDur), S "where", eS (sy yPos $= exactDbl 0) +:+. sParen (S "since the" +:+
  phrase target `S.is` S "on the" +:+ phrase xAxis +:+ S "from" +:+ refS targetXAxis),
  S "From the", phrase equation, S "above we get"]
timeDerivSent3 = foldlSentCol [S "Dividing by", ch flightDur,
  sParen (S "with the" +:+ phrase constraint +:+ eS (sy flightDur $> exactDbl 0)),
  S "gives us"]
timeDerivSent4 = S "Solving for" +:+ ch flightDur +: S "gives us"
timeDerivSent5 = foldlSentCol [S "From", refS speedIY,
  sParen (S "with" +:+ eS (sy iSpeed $= E.iSpeed)), S "we can replace", ch iyVel]

timeDerivEqns :: [ModelExpr]
timeDerivEqns = D.timeDeriv ++ [express timeQD]
```

An [[InstanceModel]] that extends a transient [[EquationalModel]] for [[flight duration (SimpleQDef)]]. It declares that its [[EquationalModel]] "outputs" a single variable (a transient [[QuantityDict]] extracted from [[flight duration (ConstrConcept)]]), $t_\textit{flight}$, from [[Inputs]]:
* a transient [[QuantityDict]] extracted from [[launch speed (ConstrConcept)]] paired with a [[RealInterval]] constraint ($> 0$), and
* a transient [[QuantityDict]] extracted from [[launch angle (ConstrConcept)]] paired with a [[RealInterval]] constraint ($0 < \theta < \frac{1}{\pi}$, dependant on [[pi (DefinedQuantityDict)]])).

The [[InstanceModel]] is also given a derivation (below) along with 3 supplementary notes ([[Sentence]]s) that indicate that:
1. The constraint placed on $\theta$ comes from 3 assumptions: [[posXDirection (ConceptInstance)]], [[yAxisGravity (ConceptInstance)]], and that a demonstration is shown in [[launch (LabelledContent)]].
2. $g$ is given a definition in [[gravAccelValue (ConceptInstance)]].
3. The constraint on $t_\mathit{flight}$ is from [[timeStartZero (ConceptInstance)]].

The derivation involves the following steps:
1. Substituting known formulas [[launchOrigin (ConceptInstance)]] and [[accelYGravity (ConceptInstance)]] into [[Position vector as a function of time for 2D motion under constant acceleration (GenDefn)]].
2. Solving for $t_\mathit{flight}$ after substituting known formula [[targetXAxis (ConceptInstance)]].
3. Substituting in [[y-component of initial velocity (DataDefinition)]].