#algorithm #quantum 

It is a [[Query model of computation|query algorithm]] solvable using the [[Deutsch-Jozsa algorithm]]. 

![[Bernstein-Vazirani_problem.png]]

Its goal is to find the secret string $s$ that generate the oracle. The same circuit used for the Deutsch-Jozsa algorithm can be used to solve this problem.

![[Bernstein-Vazirani_circuit.png]]

Just before the measurement the state is: 

![[Bernstein-Vazirani_analysis.png]]

Any probabilistic classical algorithm must make at least $n$ queries to find $s$.
In the original paper, the authors describe a more complicated problem based recursively on this, amplifying the advantage of the quantum solution upon the classical one. This more complex problem was the very first known example of superpolynomial advantage.