
This theorem is about diagonalization of linear operators. A linear operator is diagonalized if, expressed in some basis, has the form of a diagonal matrix.

Let $M$ be a [[normal matrix|normal]] $n \times n$ complex matrix ($MM^\dagger=M^\dagger M$). The eigenvectors forms an orthonormal basis $\{ |\psi_i\rangle\}, \quad i=1\cdots n$ that diagonalize $M$:

$$M=\sum _{k=1}^n\lambda_k |\psi_k\rangle$$
The complex values $\lambda_k$ are the eigenvalues and this form is called **spectral decomposition**. Note that the spectral decomposition can be obtained using others orthonormal basis, but in the expression the eigenvalues will always be present.

The eigenvector can be used to create a [[change of basis]] matrix. The matrix $M$ can be decomposed:

$$M=U\Lambda U^\dagger$$
where $\Lambda$ is the diagonal matrix of the eigenvalues, and the column vectors of $U$ are the eigenvectors of $M$. The matrix $U$ is [[Unitary matrix|unitary]]. 