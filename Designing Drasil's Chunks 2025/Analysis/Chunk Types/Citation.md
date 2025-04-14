```haskell
-- | All citations require a unique identifier used by the Drasil chunk.
-- We will re-use the 'UID' part as an EntryID ('String') used for creating reference links.
-- Finally we will have the reference information ('CitationKind', 'CiteField's, and a 'ShortName').
--
-- Ex. A reference to a thesis paper like Koothoor's "Document driven approach to certifying
-- scientific computing software" would include the affiliated university, publishing year, and city.
data Citation = Cite
  { _citeKind :: CitationKind
  , _fields   :: [CiteField]
  , _citeID   :: UID
  ,  sn       :: ShortName
  }
```

A [[Citation]] is approximately a [[bibtex]] entry in chunk form.

It satisfies:
* [[HasUID]]
* [[HasShortName]]
* [[HasFields]]
* [[Referable]]
* [[HasRefAddress]]
