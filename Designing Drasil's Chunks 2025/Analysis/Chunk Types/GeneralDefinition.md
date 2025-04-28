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

A `GeneralDefinition` is an extension of a [[ModelKind(s)]] that exclusively exposes theory items _not usable for code generation._ To make them usable for code generation, they must be converted into [[Expr]]s or users must provide the polyfill information to make them usable (e.g., ODEs).

A `GeneralDefinition` extends a [[ModelKind(s)]] with:
* Maybe a [[UnitDefn]] -- Used for displaying the unit shown in the displayed box. This box probably shouldn't exist in the SRS because not all theories will need to display units in their own unique box -- variable units may be shown in the listing of the variables.
* Maybe a [[Derivation]].
* A list of [[DecRef]]s (Decorated references) -- For the "Source" field of the theory display box.
* A [[ShortName]] -- the "code name identity" (e.g., "GD:$X", $X is the ShortName provided).
* A reference address for the SRS (note: the same for the LaTeX and HTML!) -- the same as the [[ShortName]] except with the "GD:" prepended.
* A list of notes (via [[Sentence]]) that are directly displayed in the presentation box.

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[ConceptDomain]]
* [[Express]]
* [[Express]]
* [[MayHaveDerivation]]
* [[HasDecRef]]
* [[HasShortName]]
* [[HasRefAddress]]
* [[HasAdditionalNotes]]
* [[MayHaveUnit]]
* [[CommonIdea]]
* [[Referable]]
