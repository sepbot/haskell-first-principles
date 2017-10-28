# Basic Datatypes

Every value in Haskell has a type.

Types allow grouping of values together.

Type constructor, the name of the type, is capitalized.

Data constructors are values that build up the particular type they are defined in.

This is the data declaration for type `Bool`: `data Bool = False | True`. It is built-up of the type constructor (the name) and data constructors for each possible value. This is a sum type as indicated by the pipe which means that the type is one or the other data constructor.

Typeclasses allow addition of reusable functionality across types that have instances of the typeclass. For example the presence of `Bounded` instance in numerical types provides indication of upper and lower limits for that type.

When a typeclass is a superclass of another typeclass, then types that have instance of the other typeclass will also need to have the superclass as well. For instance `Num` is a superclass of `Fractional` therefore all values that are considered `Fractional` can also be considered `Num`.

## Numbers

These numbers have the `Num` typeclass. This typeclass provides standard operations such as (+), (-), (*), etc.

Numbers are polymorphic under the hood and the compiler assign a concrete type to them as lazily as possible.

1. Integral
   1. Int: Fixed range
   2. Integer: Arbitrary range
2. Fractional
   1. Float: Fixed single precision floating points. Can shift how many bits is used for pre and post decimal point. Not very safe if precision is significant.
   2. Double: Like Float but with double precision.
   3. Rational: Ratio between two numbers, for instance $$1/2$$. Arbitrary precision, less space efficient than scientific.
   4. Scientific:  Not part of standard library. Like rational but with space optimizations.

Comparison operators:

-  `==`: equals
- `/=`: not equals
- `<` and `>`: greater than or less than

Comparison operators are actual infix functions that return `Bool`.

In order to use equality check functions, the arguments need to have typeclass `Eq` and in order to use inequality check functions, the arguments need to have the typeclass `Ord`.

Comparison is not limited to numbers and can be used as long as typeclass constraints are met.