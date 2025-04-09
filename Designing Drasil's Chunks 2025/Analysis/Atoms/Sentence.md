`Sentence` is a language for constructing prose with inlined display of various atoms (which can be through referred to through a `UID` to other chunks which contain said atoms), such as [[USymb]], [[Symbol]], and [[ModelExpr]].

```haskell
-- | For writing 'Sentence's via combining smaller elements.
-- 'Sentence's are made up of some known vocabulary of things:
--
--     * units (their visual representation)
--     * words (via 'String's)
--     * special characters
--     * accented letters
--     * references to specific layout objects
infixr 5 :+:
data Sentence where
  -- | Ch looks up the term for a given 'UID' and displays the term with a given 'SentenceStyle' and 'CapitalizationRule'.
  -- This allows Sentences to hold plural forms of 'NounPhrase's and 'NamedIdea's.
  Ch    :: SentenceStyle -> TermCapitalization -> UID -> Sentence
  -- | A branch of Ch dedicated to SymbolStyle only.
  SyCh  :: UID -> Sentence
  -- | Converts a unit symbol into a usable Sentence form.
  Sy    :: USymb -> Sentence
  -- | Constructor for 'String's, used often for descriptions in Chunks.
  S     :: String -> Sentence
  -- | Converts the graphical representation of a symbol into a usable Sentence form.
  P     :: Symbol -> Sentence       -- should not be used in examples?
  -- | Lifts an expression into a Sentence.
  E     :: ModelExpr -> Sentence
  -- | Takes a 'UID' to a reference, a display name ('Sentence'), and any additional reference display information ('RefInfo'). Resolves the reference later (similar to Ch).
  Ref   :: UID -> Sentence -> RefInfo -> Sentence
  -- | Adds quotation marks around a Sentence.
  Quote :: Sentence -> Sentence
  -- | Used for a % symbol.
  Percent :: Sentence
  -- | Direct concatenation of two Sentences (no implicit spaces!).
  (:+:) :: Sentence -> Sentence -> Sentence
  -- | Empty Sentence.
  EmptyS :: Sentence
```