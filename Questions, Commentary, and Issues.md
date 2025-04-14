## Questions
* What's the effective difference between referring to a [[Real]] [[Space]] and referring to a hypothetical "Real (ConceptChunk)"? A [[Space]] is a closed set of terms that don't have any definitions internally known to Drasil, but the hypothetical [[ConceptChunk]] would. At the Haskell level, the [[ConceptChunk]] wouldn't us 
* [[DefiningExpr]], [[Definition]], and [[DefinesQuantity]] look like they can (should) be merged. But _should they?_ [[DefiningExpr]] and [[DefinesQuantity]] really mean "for this _quantity_, I can provide you a _formula_ to solve for it (likely in a _mathematical context_)." [[Definition]] means "for this _concept_, I have a dictionary definition (in English) you can read."
## Commentary
* [[pi (DefinedQuantityDict)]] indicates that it is _unitless_ through a `Nothing :: Maybe UnitDefn`. I think we should be explicit in referencing "`unitless`" somehow instead. A lot of our code should be self-documenting.
* [[Calculation of landing time (InstanceModel)]]'s note about $g$ can be removed. Alternatively, we should have structured assumptions that let us assume variable constants, for which we can gather automatically into our table of auxiliary constants.
* [[ShortName]] is a wrapper for [[Sentence]] but should probably be one for [[NP]].
* "Reference" is far too overloaded in Drasil. All chunks and such related to it need to be rebuilt for various reasons -- see https://github.com/JacquesCarette/Drasil/pull/4022 .
* [[LabelledContent]] also needs to be rebuilt -- see https://github.com/JacquesCarette/Drasil/pull/4023 (related to References)
* [[HasFields]] is almost exclusively used for [[Citation]] but could be used more often.
## Issues
* [[UID]]s also (ab)used for references and citations unique label creation (within both $\LaTeX{}$ and HTML).
