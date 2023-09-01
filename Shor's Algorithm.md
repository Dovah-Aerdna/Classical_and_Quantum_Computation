#algorithm #quantum #classical 

$$O(n^2 \log n \log \log n)$$

This algorithm has a subroutine that can be implemented on a quantum computer gaining an exponential speed up. In partiicular, Shor's algorithm is used to solve the [[Integer Factorization]] problem and use as a quantum subroutine the [[Order finding by QPE]]. 

Provided that $N$ is odd and not a [[prime power algorithm|prime power]] (there are efficient classical methods for those cases), the following algorithm give a factor of $N$ with probability at least $1/2$:

1. Choose $a\in \{2, \cdots, N-1\}$ at random;
2. Compute $d=gcd(a,N)$ using for example [[Euclid's algorithm]]. If $d\geq 2$ otput $d$ and stop, since it is a factor of $N$. If $d=1$ then $a\in\mathbb{Z}_N^*$ and the order of $a$ is well defined;
3. *Quantum subroutine:* compute the [[Order finding problem|order]] $r=\text{ord}(a)$ modulo $N$ by [[Order finding by QPE]];
4. If $r$ is even, compute $d=\text{gcd}(a^{r/2 -1},N)$ If $d\geq2$ output $d$ and stop, Else the algorithm has failed and need to be run again.

