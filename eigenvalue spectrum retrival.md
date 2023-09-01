#algorithm #quantum 
The same technique of [[Estimating Observables]] can be used

![[estimating_observables_circuit.png]]
 setting $V=\exp (-iHt)$ and $U=I$ and measuring $\langle X+iY\rangle$ result in actually measuring the expectation value on the state $|\psi\rangle$ of the time evolution operator. Remember that [[time evolution]] can be expressed as a linear combination of the evolution of eigenstates:
$$U(t)=\exp(-i H t)|\psi\rangle=\sum_n c_n \exp(-i \lambda_n t)|\lambda_n\rangle$$ where each frequency depends on the eigenvalue. Using this technique can be measured a time series $g(t)=\langle\psi|\exp(-iHt)|\psi\rangle$  and the [[Fourier Transform]] of this time series will have peaks on the eigenvalues of the Hamiltonian of the system.  The state $|\psi\rangle$ must have some amount of each eigenstate, therefore it can be initialized in a [[maximally mixed state]]. 