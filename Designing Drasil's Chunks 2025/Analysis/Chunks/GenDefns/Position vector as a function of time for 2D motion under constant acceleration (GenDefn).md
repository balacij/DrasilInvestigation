A [[GeneralDefinition]] that extends the transient [[EquationalModel]] (also extending [[Position vector as a function of time for 2D motion under constant acceleration (ModelQDef)]]) with unit information (the unit of [[position (UnitalChunk)]] / [[Metre (UnitDefn)]]) and a derivation dependant on:
* [[twoDMotion (ConceptInstance)]]
* [[cartSys (ConceptInstance)]]
* [[constAccel (ConceptInstance)]]
* [[timeStartZero (ConceptInstance)]]

```haskell
posVecGD :: GenDefn
posVecGD = gdNoRefs (equationalModel' posVecQD) (getUnit position) 
           (Just posVecDeriv) "posVec" [{-Notes-}]

posVecQD :: ModelQDef
posVecQD = mkQuantDef' position (nounPhraseSent $ foldlSent_ 
  [atStart position, S "vector as a function" `S.of_` phrase time `S.for`
   getAcc twoD, S "motion under", phrase QP.constAccel])
  E.posVecExpr

posVecDeriv :: Derivation
posVecDeriv = mkDerivName (phrase positionVec) [posVecDerivSent, eS' posVecQD]

posVecDerivSent :: Sentence
posVecDerivSent =
  vecDeriv [(position, E.positionXY), (velocity, E.velocityXY), (acceleration, E.accelerationXY)] rectPosGD

...

-- Helper for making vector derivations
vecDeriv :: [(UnitalChunk, ModelExpr)] -> GenDefn -> Sentence
vecDeriv vecs gdef = foldlSentCol [
  S "For a", phraseNP (combineNINI twoD cartesian), sParen (refS twoDMotion `S.and_` refS cartSyst) `sC`
  S "we can represent" +:+. foldlList Comma List 
  (map (\(c, e) -> foldlSent_ [phraseNP (the c), phrase vector, S "as", eS e]) vecs),
  atStartNP (the acceleration) `S.is` S "assumed to be constant", sParen (refS constAccel) `S.andThe`
  phrase constAccelV `S.is` S "represented as" +:+. eS E.constAccelXY, 
  atStartNP (the iVel) +:+ sParen (S "at" +:+ eS (sy time $= exactDbl 0) `sC` S "from" +:+ refS timeStartZero) `S.is`
  S "represented by" +:+. eS (sy iVel $= vec2D (sy ixVel) (sy iyVel)), 
  S "Since we have a",
  phrase cartesian `sC` refS gdef, S "can be applied to each", phraseNP (coordinate `ofThe`
  (fst . head) vecs), phrase vector, S "to yield the required", phrase equation]
```