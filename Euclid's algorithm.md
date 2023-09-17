#algorithm #classical 

Find the [[gcd - Greatest Common Divisor]] of two numbers.

At every step $k$, the Euclidean algorithm computes a quotient $Q_{_k}$ and remainder $r_{_k}$ from two numbers $r_{_{k-1}}$ and $r_{_{k-2}}$:

$$r_{_{k-2}}=Q_{_k}r_{_{k-1}}+r_{_k}$$


where the $r_{_k}$ is non-negative and is strictly less than the absolute value of $r_{_{k-1}}$.
Since in the basic version the quotients are not needed, one may replace Euclidean division by the modulo operation, which gives only the remainder. Thus the iteration of the Euclidean algorithm becomes simply:

$$r_{_k}= r_{_{k-2}} \mod r_{_{k-1}}$$

The pseudocode is:

**function** gcd(a, b)
    **while** b ≠ 0
        t := b
        b := a **mod** b
        a := t
    **return** a


At the beginning of the $k$th iteration, the variable $b$ holds the latest remainder $r_{_{k-1}}$, whereas the variable $a$ holds its predecessor, $r_{_{k-2}}$. 

## Extended Euclid's algorithm