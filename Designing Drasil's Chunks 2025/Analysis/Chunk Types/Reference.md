```haskell
-- | A Reference contains the identifier ('UID'), a reference address ('LblType'),
-- a human-readable shortname ('ShortName'), and any extra information about the reference ('RefInfo').
data Reference = Reference
  { _ui :: UID
  ,  ra :: LblType
  ,  sn :: ShortName}
makeLenses ''Reference
```

https://github.com/JacquesCarette/Drasil/pull/4022

Constructed with a [[LblType]] and a [[ShortName]].

Satisfies:
* [[HasUID]]
* [[HasRefAddress]]
* [[HasShortName]]
