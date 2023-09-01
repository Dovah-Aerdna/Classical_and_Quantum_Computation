Given an Hamiltonian for a quantum system, for example: 
$$\hat{H}=\frac{\hbar \omega}{2}\hat{X}$$
which define the $X$ [[Gates|gate]], the [[Unitary matrix|unitary]] evolution, given by the solution to [[Shroedinger equation]] is:

$$U(t)=\exp\left( -i \frac{\hat{H}}{\hbar}t\right)$$
In actual hardware implementation of [[Gates|gates]], unitary operator are applied to generate the required transformation. [[noisy gates|Imperfection]] in the physical implementation of such evolution operator (errors on time or on control parameters etc...) give rise to [[noise]].
Observe that the time evolution is intimately related to the eigenvalues $\lambda_n$ and eigenstate $|\lambda_n\rangle$ of $H$ (energy states):

$$U(t)=\exp(-i H t)|\psi\rangle=\sum_n c_n \exp(-i \lambda_n t)|\lambda_n\rangle$$