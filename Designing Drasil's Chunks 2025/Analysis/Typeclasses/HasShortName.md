```haskell
-- | A 'ShortName' is the text to be displayed for a link.
--
--   Used for referencing within a document that can include symbols and whatnot if required.
--   Visible in the typeset documents (pdf).
class HasShortName  s where
  shortname :: s -> ShortName
```

Some chunks might expose display text for rendering in the SRS documents and such, via [[ShortName]].