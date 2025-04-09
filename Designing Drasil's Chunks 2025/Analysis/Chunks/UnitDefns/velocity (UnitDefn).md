```haskell
..., velU :: UnitDefn
...
velU            = newUnit "velocity"             $ metre /: second
```

A [[UnitDefn]] that defines "velocity" as a derived unit based on [[Metre (UnitDefn)]] and [[Second (UnitDefn)]].