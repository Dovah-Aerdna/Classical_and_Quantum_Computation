A pure normalized 1.[[Qubits|qubit]] state can be represented on the surface of a unitary sphere.
For a more general representation see the [[Q-Sphere]].

$$|\psi \rangle = \cos \frac{\theta}{2} |0\rangle+e^{i \varphi} \sin \frac{\theta}{2} |1\rangle \qquad \qquad\theta \in [0,\pi] \quad \varphi\in [0,2\pi[$$

The coordinates of the point on the sphere are:

$$\vec{r}=\begin{pmatrix} \sin \theta \cos \varphi \\ sin\theta \sin \varphi \\ \cos \theta \end{pmatrix}$$
So, $|0\rangle$, described by $\theta=0$ is the north pole and $|1\rangle$, described by $\theta=\pi$, is the south pole:

$$|0\rangle = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \qquad \qquad |1\rangle=\begin{pmatrix} 0 \\ 0 \\ -1 \end{pmatrix}$$
Other important points are:
$$|+\rangle = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix} \qquad \qquad |-\rangle=\begin{pmatrix} -1 \\ 0 \\ 0 \end{pmatrix}$$

$$|+i\rangle = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} \qquad \qquad |-i\rangle=\begin{pmatrix} 0 \\ -1 \\ 0 \end{pmatrix}$$
On the Block sphere, $\theta$ angles (zenithal angles) are twice as big as in Hilbert Space. Orthogonal states in Hilbert space, will be on opposite poles on Bloch Sphere. However, azimuthal angles, $\phi$, will map perfectly (see the application of phase gates). Standard measurements on the Block sphere are projection on the axis (x, y or z). 