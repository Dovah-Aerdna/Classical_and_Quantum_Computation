An Hermitian matrix or a self-adjoint matrix, is a complex square matrix equal to its own conjugate transpose:

$$M=M^\dagger$$
Hermitian matrices always have real eigenvalues, as real [[Symmetric and Antisymmetric matrix|symmetric matrices]]. Because of this property, in quantum mechanics they describe operators with necessarily real eigenvalues, i.e. observables. An eigenvalue of an Hermitian operator describe one possible outcome of the measurement, after which the state will collapse on the relative eigenstate.

## Reality of quadratic forms

A $n \times n$ matrix $M$ is Hermitian if and only if:

$$\langle v, M \rangle \in \mathbb{R} \qquad v\in\mathbb{C}^n$$

where the brackets indicates the internal product.

- Given an arbitrary square matrix $A$, the sum $A+A^\dagger$ is an hermitian matrix.
- Similarly, the difference $A-A^\dagger$ is anti-hermitian. This implies that the commutator of two Hermitian matrices is skew-Hermitian.
- An arbitrary square matrix $C$ can be written as the sum of a Hermitian matrix $A$ and a skew-Hermitian matrix $B$ ([[Toeplitz decomposition]])
$$C = A + B \quad\text{with}\quad A = \frac{1}{2}\left(C + C^\mathsf{H}\right) \quad\text{and}\quad B = \frac{1}{2}\left(C - C^\mathsf{H}\right)$$