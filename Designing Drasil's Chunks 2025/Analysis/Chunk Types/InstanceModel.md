```haskell
-- | An instance model is a ModelKind that may have specific inputs, outputs,
-- and output constraints. It also has attributes like references, derivation,
-- labels ('ShortName'), reference address, and notes.
data InstanceModel = IM {
    _mk       :: ModelKind Expr
  , _imInputs :: Inputs
  , _imOutput :: (Output, OutputConstraints)
  , _rf       :: [DecRef]
  , _deri     :: Maybe Derivation
  ,  lb       :: ShortName
  ,  ra       :: String
  , _notes    :: [Sentence]
}
```

An `InstanceModel` is our one theory type that is used for code generation. All `InstanceModel`s are expected to be usable in code generation in some way, or at least to have a clear way of knowing what information is needed to make it usable for code generation. In other words, it should have a computational interpretation up to user choices. For example, a plain [[EquationalModel]] (i.e., a [[QDefinition]] [[Expr]] with a bit more information) is readily usable because there is a computational interpretation of Expr to CodeExpr. On the other hand, an ODE in an instance model is only usable up to choice of libraries/tools/settings/etc.

An `InstanceModel` is an extension of a [[ModelKind(s)]] [[Expr]] with:
* Designated [[Inputs]]
* A _single_ designated [[Output]] along with a list of [[OutputConstraints]].
* A list of [[DecRef]]s (for the source field).
* Maybe a [[Derivation]].
* A [[ShortName]] (the label).
* A reference address (a String), same content as the [[ShortName]] w/ "IM:" prepended.
* A list of notes ([[Sentence]]s).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[ConceptDomain]]
* [[Express]]
* [[MayHaveDerivation]]
* [[HasDecRef]]
* [[HasShortName]]
* [[HasRefAddress]]
* [[HasAdditionalNotes]]
* [[CommonIdea]]
* [[Referable]]
* [[DefinesQuantity]]
* [[HasInputs]]
* [[HasOutput]]
* [[RequiresChecking]]
