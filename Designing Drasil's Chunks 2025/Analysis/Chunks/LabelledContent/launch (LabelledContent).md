```haskell
figLaunch :: LabelledContent
figLaunch = llcc (makeFigRef "Launch") $ figWithWidth (atStartNP (the physicalSystem))
  (resourcePath ++ "Launch.jpg") 70
```

A [[LabelledContent]] that extends a transient [[Reference]] chunk defining "Launch" along with an external figure with a caption: "the [[physical system (IdeaDict)]]."