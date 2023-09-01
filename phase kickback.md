#algorithm #quantum 

It is a general technique, expanded by [[QPE - Quantum Phase Estimation|QPE]].

## Query Gate

A [[Query model of computation|query gate]] works in the following manner:

$$U_f|b\rangle|a\rangle=|b\oplus f(a)\rangle|a\rangle$$

Since, for $b=\{0,1\}$: 
$$|b\oplus r\rangle=X^r|b\rangle$$
The action of a generic query gate on a generic state can be expressed as:

$$U_f|\psi\rangle|a\rangle=X^{f(a)}|\psi\rangle|a\rangle$$
If $|\psi\rangle=|-\rangle$ something interesting happens; the phase kickback is the following observation:

$$U_f|-\rangle|a\rangle=(-1)^{f(a)}|-\rangle|a\rangle$$
since the minus state is the eigenstate of $X$ gate, $X|-\rangle=-|-\rangle$ . In other words, the phase of the new state, encodes some information, in particular the value $f(a)$.

## Controlled U

Another way to think about phase kickback is actually the first step in [[QPE - Quantum Phase Estimation|QPE]]:
![[Phase_kickback_control_U.png]]

$$U(I\otimes H)|\lambda\rangle|0\rangle = |\lambda\rangle\frac{|0\rangle+\exp{i2\pi\theta}|1\rangle}{\sqrt{2}} $$
$U$ is a controlled unitary operation, where the control qubit is initialized in $|+\rangle=H|0\rangle$. The state $|\lambda\rangle$ of the other qubits is an eigenstate of the target part of $U$. The effect of this circuit is to encode the phase on the $|1\rangle$ component of the first qubit (relative phase).

*Observation*:  the phase can be expressed as $\exp{i\theta}$ and so $\theta \in [0,2\pi[$ or $\exp{i2\pi \theta}$ and thus $\theta \in [0,1[$ represent a fraction of a full $2\pi$ rotation and can be written in binary fractional form:

$$\theta=0.\theta_1\theta_2\cdots\theta_m=\frac{\theta_1}{2^1}+\frac{\theta_2}{2^2}+\cdots+\frac{\theta_m}{2^m}$$
where $\theta_i=\{0,1\}$ are the binary fractional digits.