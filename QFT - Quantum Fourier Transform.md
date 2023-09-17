#algorithm #quantum 

$$O(n^2)$$

The quantum analogue of the [[Fourier Transform|DFT]].
The QFT is a change of basis from computational basis to Fourier basis. Can be [[generalized Fourier transform|generalized]] to work on finite abelian groups. 

For $n$ qubits, there are $N=2^n$ computational states. The QFT is defined as:

$$|\tilde{x}\rangle =QFT|x\rangle= \frac{1}{\sqrt{N}} \sum_{y=0}^{N-1} \exp{\left( \frac{2 \pi i \ xy}{N}\right)}|y\rangle \qquad x= 0, \cdots , N-1$$
Defining:

$$\omega_{_N}=\exp \frac{2\pi i}{N}$$
The QFT can be written as:

$$|\tilde{x}\rangle =QFT|x\rangle= \frac{1}{\sqrt{N}} \sum_{y=0}^{N-1} \omega_{_N}^{xy} |y\rangle \qquad x= 0, \cdots , N-1$$
In order to have a representation to help build the circuit, the previous expression can be expanded in:

$$ \begin{align}|\tilde{x}\rangle &=  \frac{1}{\sqrt{N}} \sum_{y=0}^{N-1} \omega_{_N}^{xy} |y\rangle=  \frac{1}{\sqrt{N}} \sum_{y_0=0}^1 \cdots \sum_{y_{n-1}=0}^{1} \omega_{_N}^{x \sum y_k 2^{k}} |y_0y_1\cdots y_{n-1}\rangle\\

&=\frac{1}{\sqrt{N}} \sum_{y_0=0}^1 \cdots \sum_{y_{n-1}=0}^{1} \bigotimes_{k=0}^{n-1} \omega_{_N}^{xy_k 2^k} |y_0y_1\cdots y_{n-1}\rangle = \frac{1}{\sqrt{N}} \bigotimes_{k=0}^{n-1} \sum_{y_k=0}^1 \omega_{_N}^{xy_k 2^k} | y_k \rangle\\

&=  \frac{1}{\sqrt{N}} \bigotimes_{k=0}^{n-1} \left( |0\rangle + \omega_{_N}^{x2^k} |1\rangle \right) =

 \frac{1}{\sqrt{N}} \bigotimes_{k=0}^{n-1} \left( |0\rangle + e^{2\pi i \ x 2^{k-n}} |1\rangle \right)

\end{align}$$

Depending on $k$, the phase of $|1\rangle$ varies and encode more and more binary fractional digits. The power of 2 shifts them and the other ones are absorbed by the periodicity of the complex exponential. 
Relabeling the indices ([[endianiness]]), the action of QFT is understood as:
$$|x\rangle=|x_1x_2\cdots x_n \rangle$$
$$|x_k\rangle \mapsto |0\rangle + \exp \left({2 \pi i \frac{x}{2^k}}\right)|1\rangle$$
$$|x_k\rangle \mapsto |0\rangle +\exp\left(2\pi i [0.x_k \cdots x_2x_1]\right) |1\rangle$$
where it was Introduced the binary fractional notation:
	$$[0.x_ax_{a+1}\cdots x_{b}]=\frac{x_a}{ 2^{1}}+\frac{x_{a+1}} {2^{2}}+ \cdots+\frac{x_{b}}{2^{b-a+1}}$$

Using this notation, the effect of the QFT can be finally understood as an encoding in the relative phase of each qubit, the fractional part of $x/2^k$. 
For example:

  

$$|3\rangle=|110\rangle \qquad \text{since} \qquad 3=1\cdot2^0+1\cdot2^1+0\cdot2^2$$
$$3_{b10}=011_{b2}  \xrightarrow{\cdot 2^{-1}} 01.1=[0.1]  \xrightarrow{\cdot 2^{-1}} 0.11=[0.11] \xrightarrow{\cdot 2^{-1}} 0.011=[0.011]$$

*Example. 1-qubit*:
	The fourier basis for 1 qubit is $\{|\tilde{0}\rangle=|+\rangle, |\tilde{1}\rangle=|-\rangle\}$. The QFT is just the application of H gate.

*Example, n-qubit*:
	the computational basis are transformed in the fourier basis, representing a counting of phases in the equatorial plane. In particular the [[endianiness|LSB, least significative bit]],  is transformed to a qubit changing phases with minimum angle, the [[endianiness|MSB - most significative bit]] change by $\pi$. 
	In the first gif there is the binary counting in standard basis,
![[zbasis-counting.gif]]
while in the second gif, there is the transformation of each qubit in the fourier basis.

![[fourierbasis-counting.gif]]

## Circuit

Calling the [[Gates|Phase Gate]] of $\theta_k=\frac{2 \pi}{2^k}$:

$$R_k=\pmatrix{ 1 & 0\\
				0 & e^{i \theta_k}}$$

The circuit implementing the QFT is (do not consider the exact order of qubits):

![[QFT_circuit.png]]