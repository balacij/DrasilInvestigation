```haskell
cartesian   = dccWDS "cartesian" (pn' "Cartesian coordinate system") $ S "a coordinate system that specifies each point uniquely in a plane by a set" `S.of_`
                                                                  S "numerical coordinates, which are the signed distances to the point from" +:+
                                                                  S "two fixed perpendicular oriented lines, measured in the same unit of length" +:+
                                                                  fromSource cartesianWiki
```

A [[ConceptChunk]] defining "Cartesian coordinate system" referring to the [[cartesianWiki (Citation)]].