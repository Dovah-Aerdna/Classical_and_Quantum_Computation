#algorithm #classical 

Given 2 non negative (not both zero) integers $n$ and $m$, find their greatest common divisor.

It's related to the problem of [[Integer Factorization]], since the gcd is given by all the common prime factors of  $n$ and $m$, taken with the minimum power. However it is way simpler than integer factorization, as there are fast classical algorithms to solve this problem.
The most famous is [[Euclid's algorithm]], that can be easily extended on more general algebraic structures.