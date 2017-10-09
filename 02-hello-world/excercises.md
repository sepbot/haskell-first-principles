# Exercises

#### Comprehension Check

1. Source to REPL
   1. `half x = x / 2` =REPL=> `let half x = x /2`.
   2. `square x = x * x` =REPL=> `let square x = x * x`.
2. Common function for `3.14 * (5 * 5)`, `3.14 * (10 * 10)`, `3.14 * (2 * 2)`, `3.14 * (4 * 4)`: `f x = 3.14 * (x * x)`.
3. Use Prelude: `f x =  pi * (x * x)`

#### Parentheses and Association

1. `8 + 7 * 9` and `(8 + 7) * 9`: Multiplication operator takes precedance so they are different expressions. First expression can be noted as `8 + (7 * 9)`.
2. `perimeter x y = (x * 2) + (y * 2)` and `perimiter x y = x * 2 + y * 2`: They are the same since multiplication takes precedence over addition.
3. `f x =  x / 2 + 9` and `f x = x / (2 + 9)`: Division takes precedence over addition, therefore they are different expressions. The first function if equal to `f x = (x / 2) + 9`.

#### Broken code

1. `let area x = 3. 14 * (x * x)`: Space within the decimal number `3.14`.

2. `let double x = b * 2`: `b` is a free variable that is not bound.

3. ```haskell
   x = 7
    y = 10
   f = x + y
   ```
   Second line is indented.

#### let in where

1. `let x = 3; y = 1000 in x * 3 + y`

   1. ```haskell
      f = x * 3 + y
        where x = 3
              y = 1000
      ```

2. `let y = 10; x = 10 * 5 + y in x * 5`

   1. ```haskell
      f = x * 5
        where y = 10
              x = 10 * 5 + y
      ```

3. ```haskell
   let x = 7
       y = negate x
       z = y * 10
   in z / x + y
   ```

   1. ```haskell
      f = z / x + y
        where z = y * 10
              x = 7
              y = (-x)
      ```

#### Parenthesization

1. `2 + 2 * 3 - 1` => `2 + (2 * 3) - 1`
2. `(^) 10 $ 1 + 1` => `(^) 10 $ (1 + 1)`
3. `2 ^ 2 * 4 ^ 5 + 1` => `(2 ^ 2) * (4 ^ 5) + 1`

####Equivalent Expressions

1. `1 + 1` and `2`: Equal
2. `10 ^ 2` and `10 + 9 * 10`: Equal
3. `400 - 37` and `(-) 37 400`: Not equal, position in subtraction is changed.
4. ```100 `div` 3``` and `100 / 3`: Equal
5. `2 * 5 + 18` and `2 * (5 + 18)`: Not equal, multiplication takes precedence.