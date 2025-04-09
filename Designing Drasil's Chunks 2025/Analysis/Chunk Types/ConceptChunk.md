```haskell
-- | The ConceptChunk datatype records a concept that contains an idea ('IdeaDict'),
-- a definition ('Sentence'), and an associated domain of knowledge (['UID']).
--
-- Ex. The concept of "Accuracy" may be defined as the quality or state of being correct or precise.
data ConceptChunk = ConDict { _idea :: IdeaDict -- ^ Contains the idea of the concept.
                            , _defn' :: Sentence -- ^ The definition of the concept.
                            , cdom' :: [UID] -- ^ Domain of the concept.
                            }
```

A `ConceptChunk` is a chunk that extends an [[IdeaDict]] with a [[Sentence]] that defines the term the [[IdeaDict]] defines (via [[Definition]]) and information about which [[ConceptDomain|concept domain]]s it is relevant to.

Satisfies:
* [[HasUID]]
* [[NamedIdea]]
* [[Idea]]
* [[Definition]]
* [[ConceptDomain]]