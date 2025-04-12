A `ChunkDB` is our "global UID reference table," at least that's what we want it to be. Each [[Chunk]] is supposed to have its own unique [[UID]]. Those [[UID]]s are then mapped to unique [[Chunk]]s through this "chunk database." It is expected that each [[SystemInformation|Drasil system/case study]] contain a single `ChunkDB` that contains all the "knowledge" (aka chunks) necessary to unambiguously define a software problem.

It currently contains:
* [[QuantityDict]]s
* [[IdeaDict]]s
* [[ConceptChunk]]s
* [[ConceptInstance]]s
* [[UnitDefn]]s
* [[DataDefinition]]s
* [[InstanceModel]]s
* [[GeneralDefinition]]s
* [[TheoryModel]]s
* [[Citation]]s
* [[Reference]]s
* [[LabelledContent]]

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