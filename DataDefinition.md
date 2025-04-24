```haskell
-- | A scope is an indirect reference to a 'UID'.
newtype Scope = Scp { _spec :: UID }

-- | Determines the scope of data.
data ScopeType =
    Local Scope -- ^ Only visible within a limited scope.
  | Global      -- ^ Visible everywhere.

data DDPkt = DDPkt {
  _pktUID :: UID,
  _pktST  :: ScopeType,
  _pktDR  :: [DecRef],
  _pktMD  :: Maybe Derivation,
  _pktSN  :: ShortName,
  _pktS   :: String,
  _pktSS  :: [Sentence]
}
makeLenses ''DDPkt

-- | A data definition is a 'QDefinition' that may have additional notes: 
-- the scope, any references (as 'DecRef's), maybe a derivation, a label ('ShortName'), a reference address, and other notes ('Sentence's).
data DataDefinition where
  DDE  :: SimpleQDef -> DDPkt -> DataDefinition
  DDME :: ModelQDef -> DDPkt -> DataDefinition
```

A `DataDefinition` is essentially an extension of [[QDefinition]] with some extra data and a unique [[UID]]:
* A "ScopeType" (Local/Global, but only Global is used) and a "Scope" (unused).
* A list of [[DecRef]]s (i.e., [[Reference]]s decorated with [[RefInfo]]) used for the [[Source]].
* Maybe a [[Derivation]].
* A [[ShortName]].
* A String for its [[HasRefAddress]] instance's label.
* Additional notes, via a list of [[Sentence]]s.

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[DefinesQuantity]]
* [[HasOutput]]
* [[Express]]
* [[HasDecRef]]
* [[MayHaveDerivation]]
* [[HasAdditionalNotes]]
* [[HasShortName]]
* [[HasRefAddress]]
* [[ConceptDomain]]
* [[CommonIdea]]
* [[Referable]]
* [[RequiresChecking]]


All scopes are currently `Global`:
```haskell
-- | Smart constructor for data definitions.
ddE :: SimpleQDef -> [DecRef] -> Maybe Derivation -> String -> [Sentence] -> DataDefinition
ddE q []   _   _  = error $ "Source field of " ++ showUID q ++ " is empty"
ddE q refs der sn = DDE q . DDPkt (ddUid q) Global refs der (shortname' $ S sn) (prependAbrv dataDefn sn)

-- | Smart constructor for data definitions with no references.
ddENoRefs :: SimpleQDef -> Maybe Derivation -> String -> [Sentence] -> DataDefinition
ddENoRefs q der sn = DDE q . DDPkt (ddUid q) Global [] der (shortname' $ S sn) (prependAbrv dataDefn sn)

-- | Smart constructor for data definitions.
ddME :: ModelQDef -> [DecRef] -> Maybe Derivation -> String -> [Sentence] -> DataDefinition
ddME q []   _   _  = error $ "Source field of " ++ showUID q ++ " is empty"
ddME q refs der sn = DDME q . DDPkt (ddUid q) Global refs der (shortname' $ S sn) (prependAbrv dataDefn sn)

-- | Smart constructor for data definitions with no references.
ddMENoRefs :: ModelQDef -> Maybe Derivation -> String -> [Sentence] -> DataDefinition
ddMENoRefs q der sn = DDME q . DDPkt (ddUid q) Global [] der (shortname' $ S sn) (prependAbrv dataDefn sn)
```