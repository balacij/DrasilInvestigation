---
assumesExistenceOfHack: "[[Values of Auxiliary Constants (Section (Constructor))]]"
---
```haskell
messageIM :: InstanceModel
messageIM = imNoDerivNoRefs (equationalModelN (nounPhraseSP "output message") messageQD)
  [qwC offset $ UpFrom (Exc, neg (sy targPos))
  ,qwC targPos $ UpFrom (Exc, exactDbl 0)]
  (qw message)
  [] "messageIM" [offsetNote, targPosConsNote, offsetConsNote, tolNote]
```

An [[InstanceModel]] defining a transient [[EquationalModel]] extending [[message (SimpleQDef)]] defining constraints on two [[Inputs]]:
* [[offset (ConstrConcept)]]
* [[target position (ConstrConcept)]]
Explaining that the IM outputs [[message (QuantityDict)]]. It also contains 4 notes:
* [[offset (ConstrConcept)]] is from [[Offset (InstanceModel)]].
* The [[constraint (ConceptChunk)]] ... is from the fact that ... (from [[posXDirection (ConceptInstance)]]).
* The [[constraint (ConceptChunk)]] ... is from the fact that ... (expression containing [[flight duration (ConstrConcept)]]) is from [[timeStartZero (ConceptInstance)]].
* [[tolerance (ConstQDef)]] is defined in [[Values of Auxiliary Constants (Section (Constructor))]].

```haskell

offsetNote = ch offset `S.is` S "from" +:+. refS offsetIM

offsetConsNote = foldlSent [atStartNP (the constraint), eS (sy offset $> neg (sy targPos)) `S.is`
  S "from the fact that", eS (sy landPos $> exactDbl 0) `sC` S "from", refS posXDirection]

targPosConsNote = atStartNP (the constraint) +:+
  eS (sy targPos $> exactDbl 0) `S.is` S "from" +:+. refS posXDirection

timeConsNote = atStartNP (the constraint) +:+
  eS (sy flightDur $> exactDbl 0) `S.is` S "from" +:+. refS timeStartZero

tolNote = ch tol `S.is` S "defined in" +:+. refS (SRS.valsOfAuxCons ([]::[Contents]) ([]::[Section]))
```