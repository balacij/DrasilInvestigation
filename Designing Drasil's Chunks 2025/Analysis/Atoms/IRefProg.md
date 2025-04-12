```haskell
-- | Created for different forms of references. Used in 'LblType'. 
data IRefProg =
    Deferred UID                -- ^ Deferred lookup; done later. Used for domains in a 'ConceptInstance'.
  | RS String                   -- ^ Lifts a 'String' into a 'RefProg'.
  | RConcat IRefProg IRefProg   -- ^ Concatenates with two subprograms.
  | Name                        -- ^ The 'Symbol' to insert the 'ShortName' directly.
```
