```haskell
-- | A TheoryModel is a collection of:
--
--      * tUid - a UID,
--      * con - a ConceptChunk,
--      * vctx - definition context ('TheoryModel's),
--      * spc - type definitions ('SpaceDefn's),
--      * quan - quantities ('QuantityDict's),
--      * ops - operations ('ConceptChunk's),
--      * defq - definitions ('QDefinition's),
--      * invs - invariants ('ModelExpr's),
--      * dfun - defined functions ('QDefinition's),
--      * ref - accompanying references ('DecRef's),
--      * lb - a label ('SpaceDefn'),
--      * ra - reference address ('SpaceDefn'),
--      * notes - additional notes ('Sentence's).
-- 
-- Right now, neither the definition context (vctx) nor the
-- spaces (spc) are ever defined.
data TheoryModel = TM 
  { _mk    :: ModelKind ModelExpr
  , _vctx  :: [TheoryModel]
  , _spc   :: [SpaceDefn]
  , _quan  :: [QuantityDict]
  , _ops   :: [ConceptChunk]
  , _defq  :: [ModelQDef]
  , _invs  :: [ModelExpr]
  , _dfun  :: [ModelQDef]
  , _rf    :: [DecRef]
  ,  lb    :: ShortName
  ,  ra    :: String
  , _notes :: [Sentence]
  }
```

A `TheoryModel` is our "top level theory type." These theories are the ones that are to be most generic, imported from "libraries of theories" and based on things directly from "textbook knowledge."

A `TheoryModel` is an extension of a [[ModelKind(s)]] [[ModelExpr]] (i.e., a theory that is not intended for code generation) with:
* ...
* A list of [[DecRef]]s (i.e., [[Reference]]s decorated with [[RefInfo]]) used for the "Source" field.
* Interestingly, no derivation!
* A [[ShortName]].
* A String for its [[HasRefAddress]] instance's label.
* A list of "additional" notes ([[Sentence]]s).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[HasDecRef]]
* [[ConceptDomain]]
* [[HasAdditionalNotes]]
* [[Theory]]
* [[HasShortName]]
* [[HasRefAddress]]
* [[CommonIdea]]
* [[Referable]]
