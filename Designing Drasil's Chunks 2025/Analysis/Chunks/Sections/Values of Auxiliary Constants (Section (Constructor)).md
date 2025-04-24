```haskell
-- | Standard SRS section builders.
..., valsOfAuxCons, ... :: [Contents] -> [Section] -> Section
-- | Values of Auxiliary Constants section.
valsOfAuxCons cs ss = section (titleize Doc.consVals)                  cs ss valsOfAuxConsLabel
```

A [[Section]] chunk constructor commonly (ab)used to grab the `UID` of the "Values of Auxiliary Constants" section before it is created.

Example use:
```
gravAccelValueDesc :: Sentence
gravAccelValueDesc = atStartNP (the acceleration) +:+ S "due to" +:+
  phrase gravity +:+ S "is assumed to have the" +:+ phrase value +:+ 
  S "provided in the section for" +:+. namedRef (SRS.valsOfAuxCons [] []) (titleize consVals) -- HACK!!!!
```
Here, the section is constructed and used in the "gravitational acceleration value" assumption's description from Projectile.