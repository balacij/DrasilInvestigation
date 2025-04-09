```haskell
-- | The reason behind the constraint's existence.
data ConstraintReason = Physical | Software

-- | Type synonym for 'ConstraintE'
type ConstraintE = Constraint Expr

-- | Holds constraints. May occur between an interval of 'Expr', a list of 'Double's, or a list of 'String's.
data Constraint a where
  -- | By default, physical and software constraints are ranges.
  Range          :: ConstraintReason -> RealInterval a a -> Constraint a

  Elem           :: ConstraintReason -> a -> Constraint a
```

A `Constraint` is an atom that imposes either a [[RealInterval]]-based or set-inclusion-based restriction on _something purely unkown and external_. Alone, a `Constraint` is useless. It also contains a reference to the "where" of "where the constraint comes from/is relevant to," which can be [[Physical]] or [[Software]].

<div style="background: rgba(255, 255, 0, 0.3);">
  <b>Note</b>: I'm ignoring <code>ConstraintReason</code>. It's purely an accidental complexity.
</div>
