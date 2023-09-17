#tofinish 

**Input:** positive integers $a$ and $N$ such that $gcd(a,N)=1$ 

**Output:** the smallest positive integer $r$ such that: $a^r\equiv 1 \mod N$ 
****

There are no efficient classical algorithms to solve this problem. Furthermore, an efficient algorithm that solve this problem, would imply an efficient algorithm that solves the [[Integer Factorization]] problem, using [[Shor's Algorithm]]. The other way around is also true: an efficient algorithm for factorization would imply an efficient algorithm for order finding.
This problem can be [[Order finding by QPE|solved by a quantum algorithm]] using [[QPE - Quantum Phase Estimation]].
This problem is called the order finding problem since $r$ is the order of $a$ under the following definitions:
$$\mathbb{Z}_N=\{0,1,\cdots,N-1\}$$
Is the [[Rings|ring]] The elements coprime to $N$ are:
$$\mathbb{Z}_N^*=\{a\in\mathbb{Z}_N : gcd(a,N)=1\}$$
For every element $a\in \mathbb{Z}_N^*$ there exist an integer $r$ such that $a^r\equiv1 \ \mod N$  and the smallest  $r$ is the **order** of $a$. 

$$\text{ord}(a):= \min\{r: a^r \equiv 1 \mod N\}$$
Elements in $\mathbb{Z}_N \setminus \mathbb{Z}_N^*$ do not have an order, since it never happens that $a^r\equiv1$.
