# Exercises

#### Scope

1. Is `y` in scope for `z`? Yes, second declaration.

   1. ```haskell
      Prelude> let z = 5
      Prelude> let y = 7
      Prelude> let z = x * y
      ```

2. Is `h` in scope for `g`? No, not declared anywhere.

   1. ```haskell
      Prelude> let f = 3
      Prelude> let g = 6 * f + h
      ```

3. Is everything in scope? No. `d` in body of `r` is not declared anywhere. The `d` in `area` is bound in the signature but not used in function body, however it is in the local scope of `area` function only.

   1. ```haskell
      area d = pi * (r * r)
      r = d / 2
      ```

4. Are `r` and `d` in scope for `area`? Yes. `r` is a local declaration in the `area` function. `r` uses the variable `d` which is bound in the function that it is declared insides of.

   1. ```haskell
      area d = pi * (r * r)
        where r = d / 2
      ```

#### Syntax Errors

1. `++ [1, 2, 3] [4, 5, 6]`. The `++` operator is infix and therefore must be enclosed in parenthesis if used at the start or used in between the arguments without them.
2. `'<3' ++ ' Haskell'`. Single quotations are for characters, since these are strings, they must be surrounded using double quotations. 
3. `concat ["<3", " Haskell"]`. No errors.

#### Reading Syntax

1. Identify and correct syntax.

   1. `concat [[1, 2, 3], [4, 5, 6]]`. Correct.
   2. `++ [1, 2, 3] [4, 5, 6]`. Prefixed infix operator must be enclosed in parenthesis.
   3. `(++) "hello" " world"`. Correct.
   4. `["hello" ++ " world]`. Second string is not terminated. This will evaluate to a list with a single element, which might not be intentional.
   5. `4 !! "hello"`. The first argument must be the list.
   6. `(!!) "hello" 4`. Correct.
   7. `take "4 lovely"`. There is only one argument.
   8. `take 3 "awesome"`. Correct.

2. Match code to results.

   1. `concat [[1 * 6], [2 * 6], [3 * 6]]` => `[6, 12, 18]`

   2. `"rain" ++ drop 2 "elbow"` => `"rainbow"`

   3. `10 * head [1, 2, 3]` => `10`

   4. `(take 3 "Julie") ++ (tail "yes")` => `"Jules"`

   5. ```haskell
      concat [tail [1, 2, 3],
              tail [4, 5, 6],
              tail [7, 8, 9]]
              
      -- Answer: [2, 3, 5, 6, 8, 9]
      ```

#### Building Functions

1. Write expressions that take the expected input and return the expected output.

   1. `"Curry is awesome"` => `"Curry is awesome!"`
      1. `"Curry is awesome" ++ "!"`
   2. `"Curry is awesome!"` => `"y"`
      1. `"Curry is awesome!" !! 4 : ""`
   3. `"Curry is awesome!"` => `"awesome!"`
      1. `drop 9 "Curry is awesome!"`

2. Write expressions from previous question as functions.

   1. `fn x = x ++ "!"`
   2. `fn x = x !! 4  ""`
   3. `fn x = drop 9 x`

3. ```haskell
   thirdLetter :: String -> Char
   thirdLetter x = x !! 2
   ```

4. ```haskell
   letterIndex :: Int -> Char
   letterIndex x = "Curry is awesome!" !! x
   ```

5. `rvrs x = drop 9 x ++ drop 5 (take 9 x) ++ take 5 x`