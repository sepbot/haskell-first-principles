# Strings

String - synthetic sugar for array of characters. `type String = [Char]`

A character is delimited by single quote (') and a String is delimited by double quotes (").

Type of `'a'` is `Char` while type of `"a" is [Char]`

We can write strings to console using `print :: Show a => a -> IO ()` or functions that are specific to strings such as `putStr :: String -> IO ()` and `putStrLn :: String -> IO ()`.

When building with Stack, a `main` executable is expected in `Main.hs`.

The keyword `do` can be optionally used in order to sequence actions. For instance:

```haskell
fn = do
  print "Hello"
  print " "
  print "World"
```

Strings can be concatenated using `++`. For instance:

```haskell
foobar :: String
foobar = "foo" ++ "bar"
```

Alternatively a list concatenation may suffice:

```haskell
foobar :: String
foobar = concat ["foo", "bar"]
```

Definitions can occur at the top level, or a local definition can be made within the body of a function by placing the declaration(s) after the `where` keyword.

```haskell
module Test where

top :: String
top = "foo"

fn :: String
fn = top ++ local
  where local :: String
        local = "bar"
```

The type of `++` is `[a] -> [a] -> [a]`. This means that the operator function is a curried function that accepts a list of a specific type and another list of the same type as arguments and returns a list of the same type. 

The type of `concat` is `[[a]] -> [a]` (it's actually `Foldable t => t [a] -> [a]`). This means that the function accepts a list which holds list of a specific type as argument and returns a list that contains the type of the second level list from the argument.

The functions `++` and `concat` work for the type `String` since that is simply `[Char]`.

The fact that these functions accept and return lists of any type as long as the types on all the lists are the same, makes them polymorphic.

Some list operations applied to strings:

- `'f' : "oobar"` => `"foobar"`
- `head "foobar"` => `'f'`
- `take 3 "foobar"` => `"foo"`
- `drop 3 "foobar"` => `"bar"`
- `"foobar" !! 3` => `'b'` Character at index 3.

These functions are not safe as they throw errors in circumstances such as empty inputs or out of range indexes.