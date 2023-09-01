Quantum systems tends to collapse and lose their coherence, i.e. change their behavior from a quantum mechanical regime to a classical one. This process is called **decoherence**.

In particular, qubits can experience decoherence for a multitude of reasons. A crucial parameter to measure the efficiency of [[Qubits]] is to measure for how long they remain coherent:
- $T_1$ is called the *relaxation time*, describe the decay from the excited state $|1\rangle$ to the ground state $|0\rangle$;
- $T_\phi$ is the *dephasing time*, describe the randomization of the phase;
- $T_2$ is a metric describing the overall decoherence time:
$$\frac{1}{T_2}=\frac{1}{2T_1}+\frac{1}{T_\phi}$$