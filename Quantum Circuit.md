The ordering is bottom-to-top $\mapsto$ left-to-right. Visually, you can rotate clockwise a circuit in order to have inputs at the top: so the bottom bit is the most significative bit.

In a circuit model of computation, a [[Gates]] is seen as an elementary operation.
To describe a quantum circuit model of computation, is first chosen a universal set of gates.

- the *size* of a circuit ([[Boolean Circuit]] or quantum), is the total number of gates (elementary operations) it includes. Therefore circuit size corresponds to [[sequential]] running time.
- the *depth* of a circuit is the maximum number of gates encountered on any path from an input wire to an output wire. Therefore circuit depth corresponds to [[parallel]] running time. The depth is equivalent to the number of layers the circuits is composed of. 


Since each circuit has a fixed size, to analyse the scaling of the algorithm it implements, a family of circuits $\{\mathcal{C}_1, \mathcal{C}_2, \cdots\}$  is actually needed (typically, one circuit for each input length).

A quantum circuit can perform any computation that a [[Boolean Circuit]] can perform, see [[Classical Computation on Quantum Circuits]].

## example: adjoint of circuit

Consider the circuit creating [[Famous States|Bell states]]:
$$\mathcal{C}=(H \otimes \mathbb{1}) CNOT$$
The adjoint of this circuit, the [[Famous States|Bell measurement]] or Bell decoder, is (using standard algebra):

$$\mathcal{C}^\dagger=((H \otimes \mathbb{1}) CNOT)^\dagger=CNOT^\dagger(H\otimes\mathbb{1})^\dagger=CNOT(H\otimes \mathbb{1})$$
