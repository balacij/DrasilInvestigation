```haskell
offsetIM :: InstanceModel
offsetIM = imNoDerivNoRefs (equationalModelN (nounPhraseSP "offset") offsetQD)
  [qwC landPos $ UpFrom (Exc, exactDbl 0)
  ,qwC targPos $ UpFrom (Exc, exactDbl 0)]
  (qw offset) [] "offsetIM" [landPosNote, landAndTargPosConsNote]
```

An [[InstanceModel]] extending a transient [[EquationalModel]] extending [[offset (SimpleQDef)]] with [[Inputs]]:
* [[landing position (ConstrConcept)]] must be $> 0$
* [[target position (ConstrConcept)]] must be $> 0$
Indicating that it outputs [[offset (ConstrConcept)]] along with 2 notes:
* The two constraints come from [[posXDirection (ConceptInstance)]].
* [[landing position (ConstrConcept)]] is from [[Calculating of landing position (InstanceModel)]].
  

```haskell
landAndTargPosConsNote = atStartNP' (the constraint) +:+
  eS (sy landPos $> exactDbl 0) `S.and_` eS (sy targPos $> exactDbl 0) `S.are` S "from" +:+. refS posXDirection

landPosNote = ch landPos `S.is` S "from" +:+. refS landPosIM

landPosConsNote = atStartNP (the constraint) +:+
  eS (sy landPos $> exactDbl 0) `S.is` S "from" +:+. refS posXDirection
```