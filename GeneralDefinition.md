```haskell
-- | A general definition is a 'ModelKind' that may have units, a derivation,
-- references (as 'DecRef's), a shortname, a reference address, and notes.
data GenDefn = GD { _mk    :: ModelKind ModelExpr
                  , gdUnit :: Maybe UnitDefn -- TODO: Should be derived from the ModelKinds
                  , _deri  :: Maybe Derivation
                  , _rf    :: [DecRef]
                  , _sn    :: ShortName
                  , _ra    :: String -- RefAddr
                  , _notes :: [Sentence]
                  }
```

A `GeneralDefinition` is an extension of a [[ModelKind(s)]].