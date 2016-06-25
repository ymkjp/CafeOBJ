## Ex 1
Let us consider the module NATLIST. Write the traces of reductions of the following terms:
1) hd(0|1|nil) 2) tl(0|1|nil) 3) [2..5]

## Ex 2
Let us consider the module GCD. Write the trace of reduction of gcd(2015,31031).

## Ex 3
Let us consider the module FACT. Write the trace of reduction of fact(5).

## Ex 4
Let is consider the module OEDC-FACT. Write the trace of reduction of oedc-fact(5).

## Ex 6
Let us consider the module QSORT. Write the trace of reduction of qsort(4 | 7 | 5 | 1 | 0 | 3 | 6 | 2 | nil).

## Ex 7
Let us consider the module ERATOSTHENES‐SIEVE. Write the trace of reduction of primesUpto(10).
Note that each equation used should be given a unique name and you can use the following pseudo‐equations as rewrite rules.

```
eq X rem NzX = remainder of dividing X by NzX .
eq X < Y = true if so & false otherwise .
eq X > Y = true if so & false otherwise .
eq NzX divides X = true if X is a multiple of NzX & false otherwise .
eq X * Y = multiplication of X and Y .
eq sd(X,Y) = symmetric difference (| X – Y |) between X and Y . eq p NzX = the previous number of NzX .
(rem) (<) (>)
(divides) (*) (sd) (p)
```
