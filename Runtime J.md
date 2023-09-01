It is a parameter describing a "corrected runtime" for a quantum circuit, that takes into consideration the [[noise]], [[Quantum Circuit|depth and size]] and actual time. The definition is:

$$J=d \bar{\gamma}^{dn} \beta$$
where $d$ is the depth, $n$ the number of qubits, $\beta$ the average layer execution time (CLOPS, Circuit Layers Operation Per Second) and $\bar{\gamma}=\exp (4\bar{\lambda})$ where $\bar{\lambda}$ is the average error. Using this metric it can be explored how a noise corrected quantum computer can compare to classical computation and to [[error correction]]: 

![[runtime_classical_vs_quantum_error_corrected_mitigated.png]]