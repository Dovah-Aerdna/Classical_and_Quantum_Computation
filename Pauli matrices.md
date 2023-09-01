#tofinish 

compacted:
$$\sigma_j = 
    \begin{pmatrix}
      \delta_{j3}                   &  \delta_{j1} - i\,\delta_{j2}\\
      \delta_{j1} + i\,\delta_{j2}  & -\delta_{j3}
    \end{pmatrix}$$
They are [[involutory matrix|involutory]]:
$$\sigma_1^2 = \sigma_2^2 = \sigma_3^2 = -i\,\sigma_1 \sigma_2 \sigma_3 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \mathbb{1}$$
From the involution property the multiplication relations follows:

$$\sigma_i\sigma_j=-\sigma_j\sigma_i=i\sigma_k \qquad ijk=123 \text{ or even permutation}$$


Their determinant and trace are:
$$\begin{align}
               \det \sigma_j &~=\ -1, \\
  \operatorname{tr} \sigma_j &~=~~~\; 0
\end{align}$$
From which, we can deduce that each matrix $\sigma_j$ has eigenvalues +1 and −1.
With the inclusion of the identity matrix, the Pauli matrices form an orthogonal basis of the Hilbert space of 2 × 2 Hermitian matrices over $\mathbb {R}$$, and the Hilbert space of all complex 2 × 2 matrices.
Their commutator is:
$$[\sigma_i, \sigma_j] = 2 i \varepsilon_{i j k}\,\sigma_k\ $$
These commutation relations make the Pauli matrices the generators of a representation of the Lie algebra $(\mathbb{R}^3, \times) \cong \mathfrak{su}(2) \cong \mathfrak{so}(3) ~$.
Their anticommutator is:
$$\{\sigma_j, \sigma_k\} = 2 \delta_{j k}\,\mathbb{1}$$
