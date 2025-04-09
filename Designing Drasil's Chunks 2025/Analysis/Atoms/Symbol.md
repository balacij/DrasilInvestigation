A `Symbol` is a [[Domain-Specific Language|DSL]] for building mathematical symbols, also (ab)used for code-related symbols.

```haskell
-- | A 'Symbol' is actually going to be a graphical description of what gets
-- rendered as a (unique) symbol.  This is actually NOT based on semantics at
-- all, but just a description of how things look.
-- 
-- Symbols can be:
-- 
--     * @'Variable'@ (string such as "x" that represent a value that can vary) 
--     * @'Label'@ (strings such as "max" or "target" that represent a single idea)
--     * @'Special'@ characters (ex. unicode)
--     * @Decorated@ symbols using 'Atop'
--     * @Concatenations@ of symbols, including subscripts and superscripts
--     * @'Empty'@! (this is to give this a monoid-like flavour)
data Symbol =
    Variable String -- ^ Basic variable name creation.
  | Label    String 
    -- ^ For when symbols need more context, but we don't want to add a new variable name.
    -- For example, @v_f@ may be encoded as @Concat [variable "v", label "f"]@.
  | Integ    Int -- ^ For using numbers in Symbols.
  | Special  Special 
    -- ^ For now, special characters are the degree and partial
    -- differentiation symbols. These should eventually move elsewhere
    -- and the 'Special' type removed.
  | Atop     Decoration Symbol
    -- ^ Used to decorate symbols. For things like vectors (which need to be bold),
    -- primes, magnitudes, etc. See 'Decoration' for more details.
  | Corners  [Symbol] [Symbol] [Symbol] [Symbol] Symbol
    -- ^ Order of Symbols: upleft   lowleft  upright  lowright base. Ex:
    --
    -- >Corners [1]   [2]   [3]   [4]   [5]
    -- @
    --  Visually:  [1]   [3]
    --
    --                [5]
    --
    --             [2]   [4]
    -- @
  | Concat   [Symbol] -- ^ Concatentation of two symbols: @[s1, s2] -> s1s2@
  | Empty -- ^ Placeholder for when a symbol is not needed.
  deriving Eq
```