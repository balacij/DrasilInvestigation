```haskell
-- | Contains a 'Reference' and 'RawContent'.
data LabelledContent = LblC { _ref :: Reference
                            , _ctype :: RawContent
                            }
```

Extends a [[Reference]] with [[RawContent]].

See https://github.com/JacquesCarette/Drasil/pull/4023 .

Satisfies:
* [[HasUID]]
* [[HasRefAddress]]
* [[HasContents]]
* [[HasShortName]]
* [[Referable]]

