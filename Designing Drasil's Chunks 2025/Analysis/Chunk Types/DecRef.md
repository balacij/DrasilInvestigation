```haskell
-- | For holding a 'Reference' that is decorated with extra information (ex. page numbers, equation sources, etc.).
data DecRef = DR {
  _rf     :: Reference,
  refInfo :: RefInfo
}
makeLenses ''DecRef
```

A `DecRef` extends a [[Reference]] with display information (via [[RefInfo]]).

Satisfies:
* [[HasUID]]
* [[HasRefAddress]]
* [[HasShortName]]
