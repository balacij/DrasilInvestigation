```haskell
-- | Models can be of different kinds: 
--
--     * 'NewDEModel's represent differential equations as 'DifferentialModel's
--     * 'DEModel's represent differential equations as 'RelationConcept's
--     * 'EquationalConstraint's represent invariants that will hold in a system of equations.
--     * 'EquationalModel's represent quantities that are calculated via a single definition/'QDefinition'.
--     * 'EquationalRealm's represent MultiDefns; quantities that may be calculated using any one of many 'DefiningExpr's (e.g., 'x = A = ... = Z')
--     * 'FunctionalModel's represent quantity-resulting function definitions.
--     * 'OthModel's are placeholders for models. No new 'OthModel's should be created, they should be using one of the other kinds.
data ModelKinds e where
  NewDEModel            :: DifferentialModel -> ModelKinds e
  -- TODO: Analyze all instances of DEModels, convert them to (new, where
  -- applicable) variants of NewDEModel, and get rid of this.
  DEModel               :: RelationConcept   -> ModelKinds e
  EquationalConstraints :: ConstraintSet e   -> ModelKinds e
  EquationalModel       :: QDefinition e     -> ModelKinds e
  EquationalRealm       :: MultiDefn e       -> ModelKinds e
  -- TODO: Remove OthModel after having removed all instances of it.
  OthModel              :: RelationConcept   -> ModelKinds e

-- | 'ModelKinds' carrier, used to carry commonly overwritten information from
-- the IMs/TMs/GDs.
data ModelKind e = MK {
  _mk     :: ModelKinds e,
  _mkUID  :: UID,
  _mkTerm :: NP
}
```

The real chunk here is `ModelKind`. A `ModelKind` contains the substantial thing that is developed in a theory (and displayed in the theory's output, i.e., TMs, GDs, and IMs, DDs too, but those are exclusively [[QDefinition]]s).

The most common theory kind is the [[EquationalModel]], which means that a theory exposes a formula for a quantity. Since [[Projectile]] exclusively uses [[EquationalModel]], I won't write about the other ones here.

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[ConceptDomain]]
* [[Express]]
* [[RequiresChecking]]
