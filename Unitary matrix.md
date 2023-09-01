#tofinish 
A matrix is unitary if its conjugate transpose is also its inverse:

$$M^{-1}=M^\dagger$$
The columns of a unitary matrix form an orthonormal basis. This can be shown as follow. 
From the definition:

$$M^\dagger M = \mathbb{1} \qquad \implies \qquad (M^\dagger M)_{ij}= \delta_{ij}$$
Expanding the matrix product, the above expression is equivalent to taking the scalar product of rows and columns, and in particular the inner product since the rows of $M^\dagger$ are the transpose conjugate of the columns of $M$.  Using [[Bra-ket]] notation:
$$\langle M_k|M_k\rangle=\delta_{ij}$$
Another important property of unitary matrices is related to the modulus of its eigenvalues:
Let $|\psi\rangle=U|x\rangle$ for a unitary matrix $U$ (finite dimensional case). Then:

$$\langle\psi|\psi \rangle = \langle x|U^\dagger U|x\rangle=\langle x|x\rangle$$
Obtained using the definition of unitary matrix. This means that Unitary matrices do not change the magnitude of vectors. Furthermore, considering the eigenvalues:
$$ \langle x|U^\dagger U|x\rangle=\langle x|\lambda^* \lambda |x\rangle \qquad \implies \qquad |\lambda|^2=1 \qquad \implies \lambda=e^{i \theta}$$
Therefore, in accordance with the preservation of the norm, eigenvalues of unitary matrices have unitary norm, and they lies on $S^1$ (the complex unit circle). The form of the eigenvalue implies that unitary matrices add a global phase on the eigenvectors.

Since the [[determinant|determinant]] can be computed as the product of eigenvalues, the modulus of the determinant of a unitary matrix is unitary:

$$\det(U)=\prod_i \lambda_i \qquad \implies \qquad |\det(U)|=1$$
Unitary matrices are the only norm preserving matrices.