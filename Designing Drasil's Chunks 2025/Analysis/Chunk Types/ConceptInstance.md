```haskell
-- | Contains a 'ConceptChunk', reference address, and a 'ShortName'.
-- It is a concept that can be referred to, or rather, a instance of where a concept is applied.
-- Often used in Goal Statements, Assumptions, Requirements, etc.
--
-- Ex. Something like the assumption that gravity is 9.81 m/s. When we write our equations,
-- we can then link this assumption so that we do not have to explicitly define
-- that assumption when needed to verify our work.
data ConceptInstance = ConInst { _cc :: ConceptChunk , ra :: String, shnm :: ShortName}
```

An extension of a [[ConceptChunk]] that includes a [[ShortName]] and a [[HasRefAddress]] target (a `String`).

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[ConceptDomain]]
* [[HasShortName]]
* [[HasRefAddress]]
* [[Referable]]

