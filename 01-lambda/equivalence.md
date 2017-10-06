# Equivalence Exercises



Find the equivalent lambda.

1. $\lambda xy.xz$
   1. $\lambda xz.xz$
   2. $\lambda mn.mz$ - As per alpha equivalence, $x$ is equal to $m$ and $y$ is equal to $n$. $z$ is an abstract term that is present in both function bodies.
   3. $\lambda z.(\lambda x.xz)$
2. $\lambda xy.xxy$
   1. $\lambda mn.mnp$
   2. $\lambda x.(\lambda y.xy)$
   3. $\lambda a.(\lambda b.aab)$ - The expanded lambda is $\lambda x.(\lambda y.xxy)$. As per alpha equivalence, $x$ is equal to $a$ and $y$ is equal to $b$.
3. $\lambda xyz.zx$
   1. $\lambda x.(\lambda y.(\lambda z.z))$
   2. $\lambda tos.st$ - As per alpha equivalence, $x$ is equal to $t$, $y$ is equal to $o$ and $z$ is equal to $t$. Therefore the function body of $zx$ is equal to $st$.
   3. $\lambda mnp.mn$

