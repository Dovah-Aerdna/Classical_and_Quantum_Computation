Are the elementary operations in the [[Quantum Circuit|quantum circuit model of computation]].
Columns of gates gives the action on basis elements (ex: first column is the outcome of the gate applied to $|0\rangle$).
Gates with more than 2-qubits can always be [[multiqubit gate decomposition|decomposed]] as 1 qubit and 2 qubits gates.

# 1-qubit gates
- ## General Gate
$$U(\theta,\phi,\lambda)={\begin{bmatrix}\cos(\theta /2)&-e^{-i\lambda}\sin(\theta /2)\\e^{-i\phi}\sin(\theta /2)&e^{i(\lambda+\phi)}\cos(\theta /2)\end{bmatrix}}$$

- ## Pauli matrices

Are represented by [[Pauli matrices]] and corresponds to $\pi$ rotations on the [[Bloch Sphere]] around  the corresponding axis.
$$\begin{align}
  \sigma_1 = \sigma_\mathrm{x} =X &=
    \begin{pmatrix}
      0&1\\
      1&0
    \end{pmatrix} \\
  \sigma_2 = \sigma_\mathrm{y} = Y &=
    \begin{pmatrix}
      0& -i \\
      i&0
    \end{pmatrix} \\
  \sigma_3 = \sigma_\mathrm{z}= Z &=
    \begin{pmatrix}
      1&0\\
      0&-1
    \end{pmatrix} \\
\end{align}$$
$X$ is a *bit-flip* or *not*. 
$$ X|0\rangle =|1\rangle \qquad X|1\rangle = |0\rangle$$
Its representation is 
![[X_gate.png]]
or, a plus sign, since its action on the computational basis (NOT) is analogous to $|b \oplus 1 \rangle$ 
![[X_gate_plus.png]]

$Z$ is a *phase-flip*;
$$Z|0\rangle=|0\rangle \qquad Z|1\rangle=-|1\rangle$$

The eigenstates are:


	$X$
	$$|+\rangle\propto |0\rangle+|1\rangle \qquad |-\rangle\propto|0\rangle-|1\rangle$$
	$Y$
	$$|+i\rangle\propto |0\rangle+i|1\rangle \qquad |-i\rangle\propto|0\rangle-i|1\rangle$$
	$Z$
	$$|0\rangle \qquad |1\rangle$$


- ## Phase
	add phase to the component $|1\rangle$:
	$$P_\theta=\begin{pmatrix}
      1&0\\
      0&e^{i\theta}
    \end{pmatrix}$$
    Z is a phase gate with $\theta=\pi$
    Other important examples are:
    $$S=P_{\pi /2} = \sqrt{Z} = \begin{pmatrix}
      1&0\\
      0&i
    \end{pmatrix}$$
    $S$ gate apply a $\frac{\pi}{2}$ rotation around the $\hat{z}$ axis:
    $$S|+\rangle=|+i\rangle \qquad S|-\rangle=|-i\rangle$$
    so it is used to change from Z to Y. In addition:
    $$S|+i\rangle=|-\rangle \qquad S|-i\rangle=|+\rangle$$
    Similarly, the $T$ gate rotate of $\frac{\pi}{4}$:
    $$T=P_{\pi / 4}=\begin{pmatrix}
      1&0\\
      0&\frac{1+i}{\sqrt{2}}
    \end{pmatrix}$$
   - ## Hadamard
	extremely important, create superposition:
	$$H=\frac{1}{\sqrt{2}}\begin{pmatrix}
      1&1\\
      1&-1
    \end{pmatrix}$$
    Hadamard gate maps:
    $$|0\rangle \mapsto \frac{|0\rangle + |1\rangle}{\sqrt{2}}=|+\rangle$$
    $$|1\rangle \mapsto \frac{|0\rangle - |1\rangle}{\sqrt{2}}=|-\rangle$$
    Since $H^\dagger=H^{-1}=H$
	$$|+\rangle \mapsto |0\rangle$$
	$$|-\rangle \mapsto |1\rangle$$
	When used to perform a change of basis, it will swap $\hat{x}$ and $\hat{z}$:
	$$HZH=X$$
	$$HXH=Z$$
	$$H\sqrt{X}H=\sqrt{Z}=S$$
	Applied to Y:
$$HYH=-Y$$

- ## Rotations
	Rotation about _x_-axis:
	$$R_x(\theta)=\exp(-iX\theta /2)={\begin{bmatrix}\cos(\theta /2)&-i\sin(\theta /2)\\-i\sin(\theta /2)&\cos(\theta /2)\end{bmatrix}}$$
	Rotation about y-axis:
	$$R_y(\theta)=\exp(-iY\theta/2)=\begin{bmatrix} \cos(\theta/2) & -\sin(\theta/2) \\ \sin(\theta/2) & \cos(\theta/2) \end{bmatrix}$$
	Rotation about z-axis:
	$$R_z(\theta)=\exp(-iZ\theta/2)= \begin{bmatrix} \exp(-i\theta/2) & 0 \\0 & \exp(i\theta/2) \end{bmatrix}$$
# 2-qubit gates
- ## CNOT
	acts on 2 qubits, and performs the NOT operation on the second qubit only when the first qubit is $|1\rangle$ , and otherwise leaves it unchanged.
	$$\mbox{CNOT} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{bmatrix} $$
	The CNOT (or controlled Pauli-_X_) gate can be described as the gate that maps the basis states $$|a,b\rangle \mapsto |a,a \oplus b\rangle$$
	![[CNOT_gate.png]]

The role of control and target qubit can be exchanged by the following useful circuit identity:

![[CNOT_H_identity.png]]

- ## Swap 
	The swap gate swaps two qubits.
	$$\mbox{SWAP} = \begin{bmatrix} 1&0&0&0\\0&0&1&0\\0&1&0&0\\0&0&0&1\end{bmatrix}$$
	Its effect on a composite 2-qubit system is:
	$$SWAP|\phi \ \otimes\ \psi \rangle = | \psi\ \otimes\ \phi \rangle$$
	Its representation is:
	
![[swap_gate.png]]

Its effect on the [[Famous States|bell states]] is:
	$$SWAP|\phi^+\rangle=|\phi^+\rangle$$
	$$SWAP|\phi^-\rangle=|\phi^-\rangle$$
	$$SWAP|\psi^+\rangle=|\psi^+\rangle$$
	$$SWAP|\psi^-\rangle=-|\psi^-\rangle$$

The swap gate can be implemented using 3 CNOT:

![[Swap_gate_3_CNOT.png]]
- ## Controlled U
	A general controlled operation:
	$$ |0\rangle \langle0|\otimes\mathbb{1}+ |1\rangle \langle1|\otimes U = \begin{pmatrix}
      \mathbb{1}&0\\
      0&U
    \end{pmatrix}$$
# 3-qubit gates
- ## Toffoli
	The Toffoli gate, and also called the CCNOT gate, is a 3-bit gate which is universal for classical computation but not for quantum computation. The Toffoli gate is universal when combined with the single qubit Hadamard gate.
$$CCNOT = \begin{bmatrix}
 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\
 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\
 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\
 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \\
\end{bmatrix}$$
The Toffoli gate is related to the classical AND and XOR operations as it performs the mapping:
$$|a, b, c\rangle \mapsto |a, b, c\oplus (a \land b)\rangle =|a, b, c\oplus a b\rangle$$

This gate can be considered a [[Query model of computation|query gate]] for the classical AND function.
Toffoli gate, or CCNOT, is represented diagrammatically as:

![[toffoli_gate.png]]

Toffoli gate can be implemented using only H, CNOT, T, T$^\dagger$ as follow:

![[toffoli_gate_H_CNOT_T.png]]


- ## C-SWAP
	controlled SWAP, also called Fredkin gate:
	$$|0\rangle\langle0|\otimes\mathbb{1}+|1\rangle\langle1|\otimes SWAP = \begin{bmatrix}
 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\
 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\
 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \\
 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\
\end{bmatrix}$$
It is used in the [[Swap test]].

![[CSWAP_gate.png]]

# Universal sets

Any unitary operation can be closely approximated by a circuit made only by these gates.

- Rotations, Phase and CNOT
- Clifford set, T gate. The Clifford set (common generator of the Clifford group) by CNOT, _H_, S, and can be efficiently simulated on a classical computer, Gottesman-Knill theorem.
- Toffoli, H. As said before, the Toffoli gate alone forms a set of universal gates for reversible boolean algebraic logic circuits which encompasses all classical computation.
- A useful combination for ease of description, for example: X,Y,Z,H,S,S$^\dagger$,T, T$^\dagger$, CNOT.