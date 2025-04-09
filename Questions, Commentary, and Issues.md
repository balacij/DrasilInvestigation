## Questions
* What's the effective difference between referring to a [[Real]] [[Space]] and referring to a hypothetical "Real (ConceptChunk)"? A [[Space]] is a closed set of terms that don't have any definitions internally known to Drasil, but the hypothetical [[ConceptChunk]] would. At the Haskell level, the [[ConceptChunk]] wouldn't us 
* [[DefiningExpr]], [[Definition]], and [[DefinesQuantity]] look like they can (should) be merged. But _should they?_ [[DefiningExpr]] and [[DefinesQuantity]] really mean "for this _quantity_, I can provide you a _formula_ to solve for it (likely in a _mathematical context_)." [[Definition]] means "for this _concept_, I have a dictionary definition (in English) you can read."
## Commentary
* [[pi (DefinedQuantityDict)]] indicates that it is _unitless_ through a `Nothing :: Maybe UnitDefn`. I think we should be explicit in referencing "`unitless`" somehow instead. A lot of our code should be self-documenting.
## Issues
* [[UID]]s also (ab)used for references and citations unique label creation (within both $\LaTeX{}$ and HTML).
