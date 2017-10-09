#Exercises

####Find the equivalent lambda.

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

####Determine if combinator.

1. $\lambda x.xxx​$ - Yes, only variable is $x​$ which is bound.
2. $\lambda xy.xz$ - No, $z$ is a free variable.
3. $\lambda xyz.xy(zx)$ - Yes. All variables in function body, $x$ and $y$ and $z$, are bound.
4. $\lambda xyz.xy(xzy)$ - Yes. All variables in function body, $x$ and $y$ and $z$, are bound.
5. $\lambda xy.xy(xyz)$ - No, $z$ is a free variable.

####Normal form or divergence?

1. $\lambda x.xxx$ - Normal, it is already in beta normal form and cannot be reduced any further.
2. $(\lambda z.zz)(\lambda y.yy)$ - Diverge, next reduction step reduces to $(\lambda z.zz)(\lambda y.yy)$.
3. $(\lambda x.xxx)z$ - Normal, after reduction we get $zzz$.

####Evaluate to normal form.

1. $(\lambda abc.cba)zz(\lambda wv.w)$
   1. $(\lambda bc.cbz)z(\lambda wv.w)$
   2. $(\lambda c.czz)(\lambda wv.w)$
   3. $(\lambda wv.w)zz$
   4. $(\lambda v.z)z$
   5. $z$
2. $(\lambda x.\lambda y.xyy)(\lambda a.a)b$
   1. $(\lambda xy.xyy)(\lambda a.a)b$
   2. $(\lambda y(\lambda a.a)yy)b$
   3. $(\lambda a.a)bb$
   4. $bb$
3. $(\lambda y.y)(\lambda x.xx)(\lambda z.zq)$
   1. $(\lambda x.xx)(\lambda z.zq)$
   2. $(\lambda z.zq)(\lambda z.zq)$
   3. $(\lambda z.zq)q$
   4. $qq$
4. $(\lambda z.z)(\lambda z.zz)(\lambda z.zy)$
   1. $(\lambda z.zz)(\lambda z.zy)$
   2. $(\lambda z.zy)(\lambda z.zy)$
   3. $(\lambda z.zy)y$
   4. $yy$
5. $(\lambda x.\lambda y.xyy)(\lambda y.y)y$
   1. $(\lambda y.(\lambda y.y)yy)y$
   2. $(\lambda y.y)yy$
   3. $yy$
6. $(\lambda a.aa)(\lambda b.ba)c$
   1. $(\lambda b.ba)(\lambda b.ba)c$
   2. $(\lambda b.ba)ac$
   3. $aac​$
7. $(\lambda xyz.xz(yz))(\lambda x.z)(\lambda x.a)$
   1. $(\lambda xyz.xz(yz))(\lambda x.b)(\lambda x.a)$ - rename second $z$ to $b$ since it is not equal to the other $z$ which is a bound value.
   2. $(\lambda yz.(\lambda x.b)z(yz))(\lambda x.a)$ - Bind first
   3. $(\lambda z.(\lambda x.b)z((\lambda x.a)z))$ - Bind second
   4. $(\lambda z.z((\lambda x.z)a))$ - Bind first inner
   5. $(\lambda z.za)$ - Bind second inner