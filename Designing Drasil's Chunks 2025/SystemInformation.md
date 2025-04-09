```haskell
-- | Data structure for holding all of the requisite information about a system
-- to be used in artifact generation.
data SystemInformation where
 SI :: (CommonIdea a, Idea a,
  Idea b,
  Quantity e, Eq e, MayHaveUnit e,
  Quantity h, MayHaveUnit h,
  Quantity i, MayHaveUnit i,
  HasUID j, Constrained j) => 
  { _sys         :: a
  , _kind        :: b
  , _authors     :: People
  , _purpose     :: Purpose
  , _background  :: Background
  , _scope       :: Scope
  , _motivation  :: Motivation
  , _quants      :: [e]
  , _instModels  :: [InstanceModel]
  , _datadefs    :: [DataDefinition]
  , _configFiles :: [String]
  , _inputs      :: [h]
  , _outputs     :: [i]
  , _constraints :: [j]
  , _constants   :: [ConstQDef]
  , _sysinfodb   :: ChunkDB
  , _usedinfodb  :: ChunkDB
  } -> SystemInformation
```

## What is it?

[[Drasil/Designing Drasil's Chunks 2025/SystemInformation|SystemInformation]] (SI) is [[Drasil]]'s equivalent of a "root/single model" ([[PaigeOstroff2002SingleModelPrinciple]]). It is _the_ model/thing that all "generation" should begin from (and does begin from). The title of each of our case studies are effectively defined by their SIs.

SI was grown for operational purposes of developing Drasil's existing case studies. Thus, its design has become confused and the SI data type has become bloated with information very loosely defined. Rather than explaining what SI _is_, which we don't have a good definition for yet, we will try to excavate such by understanding how an SI assigns meaning to [[Drasil]]'s [[Projectile]] case study (see [[Projectile System]]).
