Very simple model that allows to isolate and discuss about ideas in quantum (and classical) computing.  Some example of quantum query model algorithms are:
- [[Deutsch's algorithm]]
- [[Deutsch-Jozsa algorithm]]
- [[Simon's algorithm]] 


Other models are the [[Turing Machine]], [[Boolean Circuit]], [[Quantum Circuit|Quantum Circuit]], [[Measurement based Quantum Computing]]. This models describe isolated computation tasks.

In the query model, the input is in the form of a function, accessed by queries during the computation. The function is an _oracle_. A query is just the evaluation of this function:

$$f:\{0,1\}^n\to\{0,1\}^m$$
The efficiency of query algorithms is evaluated by the number of queries. Queries are represented by query gates in boolean circuits and in quantum circuits (in this case, they must be unitary).
In the case of quantum query gates:

![[Quantum_query_gate.png]]

This unitary gate will actually be a permutation matrix and will be hermitian, and its own inverse. It is defined in this way in order to be reversible.

Some examples of query problems are:

![[query_problems_examples.png]]