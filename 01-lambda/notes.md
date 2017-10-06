#Lambda Calculus

Referential transparency (purely functional) - The same function, given the same inputs will always return the same outputs. This allows for predictable code that in turn allows making abstractions easy. Abstractions allow for production of reusable code.

Alpha equivalence - Two lambdas are equivalent when their substituted parameter values have the exact same operations performed on them and free variables are the same across them. For example $\lambda x.x+z$ and $\lambda y.y+z$ are equivalent but they are not equivalent to $\lambda k.k + n$ because $z$ and $k$ are different free variables.

Beta reduction - substituting (binding) values passed to the head of the function into the body of the function and removing the head since it has now served it's purpose. Consider $\lambda x.x+1$, when $x$ is $1$ then the function is reduced to $1+1$ which is equal to $2$.

Each lambda is able to substitute or bind a single parameter; therefore when a function consist of multiple arguments, multiple nested lambdas are required to bind everything. This is called currying. For example if body of a function is $xy​$ then the lambda notation for that function is $\lambda x.(\lambda y.xy)​$. The following is a shorthand for this notation: $\lambda xy.xy​$.

The following outlines notation of lambdas and substitutions:

1. $\lambda xy.xy$ - This is our lambda
2. $(\lambda xy.xy) 1 \hspace{3pt} 2$ - We want to substitute $1$ in place of $x$ and $2$ in place of $y$
3. $(\lambda x(\lambda y.xy)) 1 \hspace{3pt} 2$ - This is what the previous lambda expands out to
4. $(\lambda y.1y) 2​$ - We substitute the first parameter.
5. $1\space 2$ - We substitute the second parameter.

Parameters do not necessarily need to be numerical values, other lambdas may be substituted:

1. $\lambda xy.xy​$ - This is our lambda
2. $(\lambda xy.xy) (\lambda z.a) 1$ - We want to substitute $(\lambda z.a)$ in place of $x$ and $1$ in place of $y$. 
3. $(\lambda x(\lambda y.xy)) (\lambda z.a) 1$ - This is the expansion of the lambda.
4. $(\lambda y.(\lambda z.a)y) 1$ - We substitute $(\lambda z.a)$ in place of $x$.
5. $(\lambda z.a)1$ - We substitute in $1$ in place of $y$. The result can still be evaluated further.
6. $a$ - We substituted $1$ in place of $z$, the result is $a$, which itself is a free variable (abstract value) and cannot be reduced any further.

Beta normal form - When a lambda reaches a point where it is not possible to perform any more beta reduction, it is said that the lambda is in beta normal form.

Combinators - A function the body of which has no free variables.

Diverging lambda - A lambda that is not reducible because the process of reduction will never terminate. For example the reduced lambda for $(\lambda x.xx)(\lambda x.xx)$ is $(\lambda x.xx)(\lambda x.xx)$. Reducible lambdas eventually converge.