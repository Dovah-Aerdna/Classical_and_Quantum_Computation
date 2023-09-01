- ## Standard Base
	$$|0\rangle=\begin{pmatrix} 1 \\ 0\end{pmatrix}$$
	$$|1\rangle=\begin{pmatrix} 0 \\ 1\end{pmatrix}$$
	$$|n\rangle=\bigotimes_i |b_i\rangle $$
	where $|b_i \rangle$ represent the $i$-th digit in the binary representation. For example
$$|3\rangle=|1\rangle | 1 \rangle \qquad | 5\rangle=|1\rangle|0\rangle|1\rangle$$
- ## Eigenvalues of Pauli 

	$X$
	$$|+\rangle\propto |0\rangle+|1\rangle \qquad |-\rangle\propto|0\rangle-|1\rangle$$
	$Y$
	$$|+i\rangle\propto |0\rangle+i|1\rangle \qquad |-i\rangle\propto|0\rangle-i|1\rangle$$
	$Z$
	$$|0\rangle \qquad |1\rangle$$


- ## Bell states
	Also called EPR states. 
	$$|\Phi^\pm\rangle = \frac{1}{\sqrt{2}} (|0\rangle \otimes |0\rangle \pm |1\rangle \otimes |1\rangle)$$
	$$\Psi^\pm\rangle = \frac{1}{\sqrt{2}} (|0\rangle \otimes |1\rangle \pm |1\rangle \otimes |0\rangle)$$
	Sometimes, an EPR state (which is maximally entangled in an entropic sense), is referred to as an *e-bit*, i.e. a unit of entanglement seen as a resource. A pair of ordinary classical bit in a correlated probabilistic state is also a resource: one bit of shared randomness. 
	If Alice and Bob share an e-bit, Alice has a qubit A, Bob a qubit B, and the pair (A,B) is an e-bit (a Bell state).
	Another useful notation (changing names) is:
	$$|\psi^{ij}\rangle=\mathbb{1}\otimes X^iZ^j |\psi^{00}\rangle$$	where $|\psi^{00}\rangle\propto |00\rangle+|11\rangle \propto |++\rangle+|--\rangle$.
	The following [[Quantum Circuit]] create a Bell state.
	
  ![[Bell_circuit.png]]

### Bell Measurement
The [[Quantum Circuit|adjoint of this circuit]] performs a Bell decoding, i.e. given a Bell state (also called EPR pair), return which one it is among the four given. It is a circuit that perform a measurement on the Bell basis.
	![[Bell_State_Decoder.jpg]]

- ## GHZ state
	$$GHZ=\frac{1}{\sqrt{2}}|000\rangle+\frac{1}{\sqrt{2}}|111\rangle$$
- ## W State
$$W= \frac{1}{\sqrt{3}}|001\rangle+\frac{1}{\sqrt{3}}|010\rangle+\frac{1}{\sqrt{3}}|100\rangle$$
- # Hadamard Transform 

State resulting from the application of a layer of Hadamard gates. 
For $a,b \in \{0,1\}$, the action of $H$ can be described usefully as:

$$H|a\rangle=\frac{1}{\sqrt{2}}\sum_b (-1)^{ab}|b\rangle$$
A layer of Hadamard will act as:

![[hadamard_layer.png]]

where $x \cdot y$ is the binary dot product defined as:

$$x \cdot y = \bigoplus_i x_iy_i$$

This transformation can convert from[[ binary strings probabilities to Pauli expectation values]]. 
The Hadamard transform is actually related to [[QFT - Quantum Fourier Transform|QFT]], seen as a general transformation of groups.
