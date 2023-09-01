#algorithm #quantum 

Is a [[Query model of computation|query algorithm]], and it give a provably exponential advantage over classical analogues.

![[Simon's_problem.png]]

As usual $\Sigma=\{0,1\}$
If a function satisfy the promise, there is only one string $s$ such that the property holds.

The algorithm consist in running the following circuit several times, plus a classical post processing.

![[Simon's_algorithm_circuit.png]]

- The circuit is very similar to the [[Deutsch-Jozsa algorithm]], but since the functions is $f: \Sigma^n \to \Sigma^m$, the input qubits are $n+m$. 
- Another key difference is that the bottom qubits are not initialised to $|1\rangle$, so there will not be any [[phase kickback]].

# Analysis

The evolution of the state after each layer of the circuit is:

![[Simon's_algorithm_analysis_1.png]]

The measurement is performed on the top $n$ qubits, i.e. the rightmost $n$ qubits in tensorial notation.

Computing the probability of measuring $y$:

![[Simon's_algorithm_analysis_2.png]]

Consider two cases:
![[Simon's_algorithm_analysis_3.png]]
If the string $s$ is the null string, the probability of obtaining $y$ is uniform over all the possibilities: the result of the measurement is a uniform random string.

On the other hand:
![[Simon's_algorithm_analysis_4.png]]
If the string $s$ is not the null string, the measurement $y$ is uniform over half of the possibilities: in particular over those string that have a null binary dot product with $s$.

The last step is a classical post processing that uses the information gained running the algorithm. 
For every $k=n+r$ measurement $y$, it will result $s\cdot y=0$. Therefore representing the measurements in a matrix, allows to think about the problem of finding $s$, as determining the null space of such matrix (working in $\mathbb{Z}_2$, i.e. modulo 2).

![[Simon's_algorithm_analysis_5.png]]

The task can be efficiently accomplished by [[Gaussian Elimination]], and the probability of obtaining the correct result will be greater than $1-2^{-r}$ (the matrix need at least to be a square matrix). The null space will contain only $\{0^n, s\}$, and every other false results will be eliminated with high probability ($1-2^{-r}$).

A classical algorithm that solve Simon's problem is very inefficient. In fact, any probabilistic algorithm making fewer than $2^{n/2-1}-1$ queries, will fail with probability at least $1/2$.

The quantum algorithm solve the Simon's problem in a linear number of queries, while the classical algorithm in an exponential.