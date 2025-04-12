```haskell
data Literal where
    Int      :: Integer -> Literal
    Str      :: String -> Literal
    Dbl      :: Double -> Literal
    ExactDbl :: Integer -> Literal
    Perc     :: Integer -> Integer -> Literal
    deriving Eq
```

A simple DSL that lets contain mathematical literals. Dbl and ExactDbl should be Real and WholeReal.