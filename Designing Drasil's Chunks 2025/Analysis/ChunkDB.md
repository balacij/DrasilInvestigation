#todo Explain.

```haskell
-- | Our chunk databases. \Must contain all maps needed in an example.\
-- In turn, these maps must contain every chunk definition or concept 
-- used in its respective example, else an error is thrown.
data ChunkDB = CDB {
  -- CHUNKS
    symbolTable           :: SymbolMap
  , termTable             :: TermMap 
  , defTable              :: ConceptMap
  , _unitTable            :: UnitMap
  , _dataDefnTable        :: DatadefnMap
  , _insmodelTable        :: InsModelMap
  , _gendefTable          :: GendefMap
  , _theoryModelTable     :: TheoryModelMap
  , _conceptinsTable      :: ConceptInstanceMap
  , _citationTable        :: CitationMap
  -- NOT CHUNKS
  , _labelledcontentTable :: LabelledContentMap -- TODO: LabelledContent needs to be rebuilt. See JacquesCarette/Drasil#4023.
  , _refTable             :: ReferenceMap -- TODO: References need to be rebuilt. See JacquesCarette/Drasil#4022.
  , _traceTable           :: TraceMap
  , _refbyTable           :: RefbyMap
  }
```