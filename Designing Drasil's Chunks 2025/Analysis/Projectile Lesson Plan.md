The Projectile Lesson Plan (PLP) is an offshoot of [[Projectile]]. [[SystemInformation]] (SI) does not quite fit the bill for PLP's needs, as can be seen through the almost complete lack of subtance in the PLP SI:

```haskell
si :: SystemInformation
si = SI {
  _sys         = projectileMotion,
  _kind        = Doc.notebook,
  _authors     = [spencerSmith],
  _purpose     = [],
  _background  = [], 
  _motivation  = [],
  _scope       = [],
  _quants      = [] :: [QuantityDict],
  _instModels  = [],
  _datadefs    = [],
  _configFiles = [],
  _inputs      = [] :: [QuantityDict],
  _outputs     = [] :: [QuantityDict],
  _constraints = [] :: [ConstrainedChunk],
  _constants   = [] :: [ConstQDef],
  _sysinfodb   = symbMap,
  _usedinfodb  = usedDB
}
```