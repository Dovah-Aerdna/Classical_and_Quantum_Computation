#algorithm #quantum 

This [[Query model of computation|query algorithm]] solves the parity problem for function from 1-bit to 1-bit, also called Deutsch's problem.

The only 4 possible functions of this form, represented by truth tables, can be divided into 2 categories:
- constant, the output is always 0 or always 1;
- balanced, the output is 0 for half of the possible inputs, 1 for the other half.

![[Deutsch_problem.png]]

A classical algorithm need 2 query to solve this problem.

A quantum version, however, only need 1 query. The algorithm is represented in the following circuit.

![[Deutsch_circuit.png]]

It works by creating on the first qubit superposition, and using the second qubit for [[phase kickback]], in order to encode the output of the oracle on the phases.
In particular:

![[Deutsch_analysis_1.png]]

Where it was used the equality:
$$|0\oplus a \rangle - |1 \oplus a \rangle = (-1)^a (|0\rangle-|1\rangle)$$
The bottom qubit is used as registry to xoring the value of the query, as standard for the query oracles. The bottom qubit correspond to the first in the tensor product.
The creation of $|-\rangle$ state is crucial, in order to encode the queries in the phase: this is the [[phase kickback]]. 
The state after the oracle can be rewritten as:

![[Deutsch_analysis_2.png]]

And the final application of $H$ on the top qubit (rightmost in the tensor product), allows to distinguish $|+\rangle$ and $|-\rangle$ states, and therefore to discriminate the two possible cases: balanced and constant.

Note that there is *no* entanglement. This algorithm use only superposition (top qubit is on a superposition) and interference ([[phase kickback]]).