```haskell
accelU, ... :: UnitDefn
accelU          = newUnit "acceleration"         $ metre /: s_2
```

A [[UnitDefn]] that defines "acceleration" as a derived unit based on [[Metre (UnitDefn)]] and [[Second (UnitDefn)]].