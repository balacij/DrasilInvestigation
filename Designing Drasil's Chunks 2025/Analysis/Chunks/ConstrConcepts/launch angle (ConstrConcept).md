```haskell
launAngle = constrained'    (ucStaged C.launAngle (autoStage lTheta  ) Real radian) [physRange $ Bounded (Exc, exactDbl 0) (Exc, half $ sy pi_)] (sy pi_ $/ exactDbl 4)
```

A [[ConstrConcept]] extending a transient [[UnitalChunk]] (also extending a [[ConceptChunk]], [[launch angle (ConceptChunk)]], with a display [[Symbol]], $\theta$, type information, [[Real]], and a unit, [[radian (UnitDefn)]]) with a bounded [[ConstraintE]], $0 < \theta < \pi/2$, and a reasonable value: $\frac{\pi}{4}$, dependant on [[pi (DefinedQuantityDict)]].
