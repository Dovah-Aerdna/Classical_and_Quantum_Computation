#algorithm #classical #quantum 
$$O(n^2)$$

Any computation that can be performed by a [[Boolean Circuit]] can also be performed by a [[Quantum Circuit]].

Remember that the Toffoli gate can be seen as a [[Query model of computation|query gate]] for the classical AND:

![[toffoli_gate.png]]

To simulate Boolean gates in quantum circuits are needed only X, CNOT, CCNOT. In particular, using only those 3 gates, it is possible to construct quantum circuits that return the correct classical output when given as input, qubit in standard bases.

This complete procedure will work only for [[deterministic algorithms]].

# Not

Classical NOT is trivially simulated by X gate.

# AND, OR

Can be simulated with a Toffoli and a X gate (remember, the computation must be reversible).

![[AND_OR_gate.png]]

# FANOUT

Can be easily simulated with a CNOT:

![[Fanout_gate.png]]

# Composing

From a general boolean circuit $\mathcal{C}$, it is possible to substitute the classical gates, with the quantum ones, obtaining a quantum gate $\mathcal{R}$ having a number of gates linear in the size (the number of elementary gates) of $\mathcal{C}$. To make the conversion possible, in general are needed $k$ ancillae qubit initialized to $|0\rangle$: 1 for each gate excluding NOT in the boolean circuit (i.e. AND, OR, FANOUT). After the application of $\mathcal{R}$, the ancillae qubits will be in the state $|g(x)\rangle$, representing some garbage (the leftover of the ancillae qubits).

![[Classical_to_quantum_gate.png]]

In general, the garbage will ruin the interference pattern needed in larger algorithm, in order to use this gate as a subroutine. To address this problem, it is possible to invert $\mathcal{R}$, fanning the result of the operation on another free register of qubits:

 ![[remove_garbage_classical_to_quantum_gate.png]]

This gate can be seen as a [[Query model of computation|query gate]].
This procedure can of course be optimised.