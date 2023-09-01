This type of noise is connected to the observation that the quantum computer is not an isolated quantum object, but rather an [[open quantum system]]. It is responsible for an exponential decay in [[fidelity]]. 

## Quantum trajectories

Consider an single qubit operation, an incoherent noise can be represented as the effect of choosing with probability $1-p$ to also apply another gate $G_A$ and with probability $p$ a gate $G_B$. This situation is described by the [[density matrix]] formalism, and the average effect of error is:

$$\Lambda(\rho)=(1-p)\rho_A+p\rho_B$$
This is an expression for a [[channel]], i.e. a map transforming [[density matrix|density matrices]] into density matrices, representing the error induced by the channel of communication. A repetition of application of a noise channel reduce exponentially the [[Fidelity]] of the state, i.e. linear to first order in contrast to quadratically as [[coherent noise]].

Incoherent noise corresponds to an uneven contraction of the [[Bloch Sphere|bloch vector]] i.e. a loss of [[density matrix|purity]].  

There are different noise models, described as channels:
- $X$ bit-flip noise, $X$ gate with probability $p$
- Phase noise, $Z$ gate with probability $p$
- Depolarizing noise, $X,Y,Z$ with probability $p$
- Stochastic Pauli noise,  $X,Y,Z$ with probability $p_X,p_Y,p_Z$ 
- Amplitude dumping, related to the relaxation time $t_1$ ([[Coherence]])
- etc...