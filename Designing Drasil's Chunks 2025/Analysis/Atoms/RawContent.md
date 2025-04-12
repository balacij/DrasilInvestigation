```haskell
-- | Types of layout objects we deal with explicitly.
data RawContent =
    Table [Sentence] [[Sentence]] Title Bool -- ^ table has: header-row, data(rows), label/caption, and a bool that determines whether or not to show label.
  | Paragraph Sentence                       -- ^ Paragraphs are just sentences.
  | EqnBlock ModelExpr                       -- ^ Block of Equations holds an expression.
  | DerivBlock Sentence [RawContent]         -- ^ Grants the ability to label a group of 'RawContent'.
  | Enumeration ListType                     -- ^ For enumerated lists.
  | Defini DType [(Identifier, [Contents])]  -- ^ Defines something with a type, identifier, and 'Contents'.
  | Figure Lbl Filepath MaxWidthPercent HasCaption
                                             -- ^ For creating figures in a document includes whether the figure has a caption.
  | Bib BibRef                               -- ^ Grants the ability to reference something.
  | Graph [(Sentence, Sentence)] (Maybe Width) (Maybe Height) Lbl -- ^ Contain a graph with coordinates ('Sentence's), maybe a width and height, and a label ('Sentence').
  | CodeBlock CodeExpr                       -- ^ Block for codes
```

Abstraction for things that would go in generic documents.