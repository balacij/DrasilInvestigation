```haskell
-- | A RealInterval is a subset of 'Real' (as a 'Space').
-- These come in different flavours.
-- For now, we embed 'Expr' for the bounds, but that will change as well.
data RealInterval a b where
  Bounded :: (Inclusive, a) -> (Inclusive, b) -> RealInterval a b -- ^ Interval from (x .. y).
  UpTo    :: (Inclusive, a) -> RealInterval a b                   -- ^ Interval from (-infinity .. x).
  UpFrom  :: (Inclusive, b) -> RealInterval a b                   -- ^ Interval from (x .. infinity).
```
An "interval" can be $> x$, $? < x$, or $x < ? < y$, where $<$ may be either $<$ ([[Exc]]) or $\le$ ([[Inc]]). The types `a` and `b` are usually filled in with either an [[Expr]] or a [[ModelExpr]].

<div style="background: rgba(255, 255, 0, 0.3);">
  <b>Note</b>: I'm ignoring <code>Inclusive</code>. It's purely an accidental complexity.
</div>