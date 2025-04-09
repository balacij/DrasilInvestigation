```haskell
-- | Stages are what part of the development process we are in.
-- There are currently two:
-- 1) The Equational stage (should be called Specification) 
-- 2) The Implemenation stage
--
-- The point is that information may be rendered differently depending
-- at what stage we're at. Being able to talk about stages lets us also
-- attach different display information.

data Stage = Equational -- AKA Specification
           | Implementation -- AKA Implementation
```
