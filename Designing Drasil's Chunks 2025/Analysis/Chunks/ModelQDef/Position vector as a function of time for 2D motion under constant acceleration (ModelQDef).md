```haskell
posVecQD :: ModelQDef
posVecQD = mkQuantDef' position (nounPhraseSent $ foldlSent_ 
  [atStart position, S "vector as a function" `S.of_` phrase time `S.for`
   getAcc twoD, S "motion under", phrase QP.constAccel])
  E.posVecExpr
```

A [[ModelQDef]] that extends [[position (UnitalChunk)]] with a new term/name ("[[position (UnitalChunk)]] vector as a function of [[time (UnitalChunk)]] for [[two-dimensional (CI)]] motion under [[constant acceleration (UnitalChunk)]]") and a [[ModelExpr]]-based expression dependant on:
* [[x-component of initial position (UnitalChunk)]], [[y-component of initial position (UnitalChunk)]]
* [[x-component of initial velocity (UnitalChunk)]], [[y-component of initial velocity (UnitalChunk)]]
* [[x-component of constant acceleration (UnitalChunk)]], [[y-component of constant acceleration (UnitalChunk)]]
* [[time (UnitalChunk)]]
