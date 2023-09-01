#algorithm #quantum 

Given an [[Operators|operator]] $U$ which is [[Unitary matrix|unitary]], and an eigenstate $|\psi\rangle$

$$U|\psi\rangle=\exp(i \theta) |\psi\rangle$$
(remember that unitary operator have always eigenvalues with unitary modulus). The problem of QPE is to estimate the phase $\theta$.
It is often important in quantum simulation, since this eigenvalue can be related to specific physical properties of the system investigated.
****

**Observation:** since the [[time evolution|Hamiltonian evolution]] of physical systems is unitary, QPE has an important role in quantum simulations.


QPE is related to the [[phase kickback]] trick. In particular the following circuits explain the *QPE trick*:

![[QPE_trick.png]]

After the controlled gate, the phase is encoded in the $|1\rangle$ component of the first qubit. The last Hadamard allows to perform the measurement.
With a bit of algebra and the [[duplication formulae]], the proability of measuring $0$ or $1$ is:

$$P_0(\theta)=\left| \frac{1+e^{i\theta}}{2} \right|^2=\cos^2\left( \frac{\theta}{2}\right)$$
$$P_1(\theta)=\left| \frac{1-e^{i\theta}}{2} \right|^2=\sin^2\left( \frac{\theta}{2}\right)$$
This "trick" is actually QPE using 1 qubit. 
- The phase can be found by repeating the experiment and obtaining statistic on the probabilities. 
- If instead a single measurement is made, the information gained is binary. This means that the information gained is a bit $a$ after the fractional point of: $\theta/(2\pi)=0.a$  

To get more precision, i.e. more decimal points, more qubits must be used. In the i-th qubits, it is encoded the information about the i-th binary fractional digit. This can be achieved observing that:

$$U^{2^x}|\psi\rangle=e^{i\theta 2^x}|\psi \rangle$$

The information written in the first register after the series of controlled $U$ is exactly the  [[QFT - Quantum Fourier Transform|QFT]] (with phase $2\pi \theta/2^n$), therefore the inverse QFT can be applied as a final step in the circuit for QPE:

![[QPE_circuit.png]]


With respect to the 1-qubit case, it is easier to find a more precise value of the global phase $\theta$, at the expense of using more qubits. QPE is **very expensive** in terms of gates, but another method that can be used is the [[Iterative phase estimation]], that allows for some saving.