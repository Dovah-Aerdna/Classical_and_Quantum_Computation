#algorithm #quantum 

It is an algorithm to perform [[QPE - Quantum Phase Estimation]] on a single auxiliary qubit to store the phase, in order to be more precise on near term quantum hardware.

QPE requires a lot of _SWAP_ operations to be executed in order to select the controlled qubits, and require the [[QFT - Quantum Fourier Transform]] which is very expensive, so it is problematic in near term hardware.

## Idea

The idea is to use a single auxiliary qubit to determine the digits one at a time.  The first observation is on the state obtained after the application of $2^k$ controlled $U$:


![[iterative_QPE_analysis.png]]

Therefore after $2^{m-1}$ application of the controlled $U$, the relative phase depends only on the last digit $\theta_m$. The full algorithm add a rotation to eliminate the previously measured phases components:

1. choose the precision $m$;
2. execute the circuit:
	![[iterative_QPE_step_1.png]]
	to determine the digit $\theta_m$
3. Apply a the same circuit, halving the number of $U$ application and adding a corrective rotation dependent on the previous measurement:
	![[iterative_QPE_step_2.png]]
4. execute iteratively the circuit:
	![[iterative_QPE_step_k.png]]
	for each digit.