```haskell
message :: QuantityDict
message = vc "message" (nounPhraseSent (S "output message as a string")) lS String
```

`message` is a [[QuantityDict]] that implicitly defines an [[IdeaDict]] ("motion", via `vc`) with an English definition, a symbol ($s$), and as $String$-typed.