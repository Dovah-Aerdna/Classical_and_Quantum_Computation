#algorithm #quantum 

$$O(n^3)$$

The [[Order finding problem]] can be solved by a quantum algorithm using [[QPE - Quantum Phase Estimation]]. It represent the quantum subroutine of [[Shor's Algorithm]].

The classical states represent $\mathbb{Z}_N=\{0,1, \cdots , N-1\}$ and the oracle $M_a$ is constructed:

$$M_a|x\rangle=|ax\rangle \qquad a\in \mathbb{Z}_N^* \quad ,\quad x\in \mathbb{Z}_N$$
$$M_a|x\rangle=|x\rangle \qquad , \qquad x\notin \mathbb{Z}_N$$ 
Where, following the usual notation $\mathbb{Z}_N^*=\{a \in \mathbb{Z}_N : gcd(a,N)=1\}$ (is an [[Groups|abelian group]] under multiplication) and the value $ax$ is computed $\mod N$. The operator $M_a$ is just a multiplication by $a$ and can be implemented from its [[Classical Computation on Quantum Circuits|classical representation]]. Since $gcd(a,N)=1$, the operator $M_a$ is [[Unitary matrix|unitary]], resulting in a one to one map from $\mathbb{Z}_N$ to itself, i.e. a permutation. 
The eigenvalues of $M_a$, that can be found by [[QPE - Quantum Phase Estimation|QPE]] are related to the order of $a$, in particular:

	$$|\psi_j\rangle=\frac{|1\rangle+\omega_r^{-j}|a\rangle+\cdots+\omega_r^{-j(r-1)}|a^{r-1}\rangle}{\sqrt{r}} \qquad w_r=\exp \left(\frac{2\pi i}{r}\right)$$
$$M_a|\psi_j\rangle=\omega_r^j|\psi_j \rangle= \exp \left( \frac{2\pi i j}{r}\right)|\psi_j \rangle  \qquad j\in\{0, \cdots,r-1\}$$
The trick is to do a random sampling of those eigenvalues, use [[QPE - Quantum Phase Estimation|QPE]] to estimate the  phases $j/r$, and use the classical algorithm of [[continued fraction algorithm|continued fraction]], to find $j$ and $r$. Since $j$ and $r$ could share some factors, taking the least common multiple of the various denominators recovered will result in $r$.
To get a sufficient precision, in the QPE must be used $m=2 \log(N)+1$ qubits.
Therefore the QPE circuit solve for the order finding problem, but is necessary to postprocess the results to find $j$ and $r$. The precision on QPE is also important, in particular we need to be able to discriminate $1/r$ (if j=1) from nearby possibilities, $1/(r-1)$ and $1/(r+1)$. The distance between the two numbers we need to discriminate is in the worst case: 

$$\frac{1}{r}-\frac{1}{r+1}=\frac{1}{r(r+1)}$$

The distance between the measured phase $y/2^m$ and $1/r$ must be less than the half of that distance, and taking the worst case where $r\to N$ we get:

$$\left| \frac{y}{2^m} - \frac{1}{r} \right| \leq \frac{1}{2N^2}$$

From this, the minimum precision required to ensure a high probability of success is:

$$m= 2 \log(N)+1$$

However, in general $j\neq 1$, so we need to use a trick to still extract the correct value of $r$.
## Eigenvectors and cost

How to select uniformly the eigenvectors $|\psi_j\rangle$ ? It can be used the relation:

$$|1\rangle=\frac{|\psi_0\rangle+|\psi_1\rangle+ \cdots + |\psi_{r-1}\rangle}{\sqrt{r}}$$
This can be verified by:

  $$\frac{1}{\sqrt{r}}\sum_{j=0}^{r-1}|\psi_j\rangle=\frac{1}{r}\sum_{j=0}^{r-1}\sum_{k=0}^{r-1}\omega_r^{-jk}|a^k\rangle=|1\rangle+\frac{1}{r}\sum_{k=1}^{r-1}\left(\sum_{j=0}^{r-1} \omega_r^{-jk}\right)|a^k\rangle=|1\rangle$$

where it was used the [[geometric series]] formula.
Therefore the following circuit implements the QPE solving for the order finding problem.

![[Order_finding_by_qpe.png]]

The cost of implementing the controlled unitary operation $M_a$ in QPE would increase exponentially. However, it is possible to create using the [[Classical Computation on Quantum Circuits|standard method]] a different $M_{b=a^k \mod N}$ for each iteration of QPE instead of using the powers of $M_a$ with cost $O(n^2)$ with $n=\log(N)$.  If this wasn't the case, the order finding problem wouldn't be solvable efficiently on a quantum computer! In particular, in QPE are needed:
- $m$ Hadamard gate: cost $O(n)$
- $m$ controlled unitary operations requiring $O(n^2)$ each: cost $O(n^3)$ 
- Inverse [[QFT - Quantum Fourier Transform]] requiring $O(n^2)$ 

Therefore the total cost is $O(n^3)$ 