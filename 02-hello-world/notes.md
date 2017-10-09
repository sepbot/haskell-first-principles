# Hello World

Prelude - library of standard functions in Haskell base package.

Everything in Haskell is an expression or a declaration.

Expressions can be evaluated to results. These include values or functions applied to values.

Declarations are bindings that allow naming of expressions. Naming expressions allow using of them easier as they can be used by their name instead.

Redex - expression that is reducible. Once an expression is in normal form, it is no longer a redex.

Given an input, functions in Haskell return an output. All functions accept one parameter and return one output. It may seem like some functions accept multiple paramters, these functions are curried, which means that they are series of nested function applications.

Function definition syntax: `name parameter = body`. For example `double x = 2 * x`.

Function application syntax: `name parameter`. For example `double 5`.

Function names must begin with a lowercase character.

Variable names must also begin with a lowercase character.

Evaluation (function application) in Haskell is nonstrict or lazy. This means that a function is not evaluated until the reduced value of it is required. Evaluation happens to weak head normal form (WHNF).

---

Operator functions can be used infix (between two parameters).

Regular functions can be infixed by surrounding the name with back ticks. For example `name p1 p2` is equal to ```p1 `name` p2```. Operator functions can be prefixed by sorrounding the name with parenthesis. For example `p1 + p2` is equal to `(+) p1 p2`.

By default functions with alphanumeric names are prefix and functions whose names are a symbol are infix by default.

Infix functions with higher precendence will get applied first.

Associativity of infix functions defines the order of evaluation where multiple of the same infix function is used in succession. Left associated infix functions will be evaluated left to right and right associated infix functions will be evlauted right to left.

---

Whitepace in Haskell is significant, spaces must be used and not tabs. Whitespace replaces block markers.

Expressions can be expressed over multiple lines, however they will need to be indented beyond the starting column of the first line of that expression.

---

`mod` and `rem` differ in how the sign of the result is evaluated:

```haskell
mod (-5)  2    --   1
mod 5    (-2)  --  -1
mod (-5) (-2)  --  -1
rem (-5)  2    --  -1
rem 5    (-2)  --   1
rem (-5) (-2)  --  -1
```

When using `mod`, sign of the result comes from the divisor.

When using `rem`, sign of the result comes from the dividend.

As it can be seen above, negative numbers must be enclosed within parentheses when evaluated as part of an expression. The negative sign on numerical values is synthetic sugar for the keyword `negate`.

`$` is an infix operator with lower possible precedence and right associativity, which does not perform any operations. It is used to make expressions to right of it evaluate first. Using parenthesis is likely to be more readable.

---

Sectioning allows passing of partially applied functions.

```haskell
x = (2 +) -- partially applied function
x 1 -- Evaluates to 3
```

---

`let ... in ...` can be used in any places where expressions are allowed. `where` can be used for declaration.  There is [more to it](https://wiki.haskell.org/Let_vs._Where) besides stylistic preferences.