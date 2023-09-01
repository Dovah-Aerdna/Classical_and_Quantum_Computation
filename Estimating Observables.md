#algorithm #quantum 

The idea is similar to [[Iterative phase estimation]]: a single auxiliary qubit and some controlled operations are used to retrieve information on some expectation values.

![[estimating_observables_circuit.png]]

The operator $V$ is applied if the control is $|1\rangle$ and $U$ is executed on the $|0\rangle$ state (inverted control). The measurement is done in $X+iY$. Of course $V$ or $U$ can be the identity. 

## Analysis

It can be shown that (use relation of H [[Gates|gate]] and the multiplication relation of [[Pauli matrices]]):
$$\langle X+iY\rangle=\langle HZH\rangle+\langle ZHZH\rangle$$
These observables must be measured separately, running the experiment multiple times.
Prior to the measurement the state is:

$$|\psi\rangle=\frac{U|\psi\rangle|0\rangle+V|\psi\rangle|1\rangle}{\sqrt{2}}$$
Considering the expected values:

$$\langle HZH\rangle=\langle\psi| HZH|\psi\rangle=\frac{1}2 \langle \psi|U^\dagger V|\psi\rangle+\frac{1}2 \langle \psi|V^\dagger U|\psi\rangle$$
$$\langle ZHZH\rangle=\langle\psi| ZHZH|\psi\rangle=\frac{1}2 \langle \psi|U^\dagger V|\psi\rangle-\frac{1}2 \langle \psi|V^\dagger U|\psi\rangle$$
## Time evolution of Observables

The same idea can be used to characterize the time evolution:

![[time_evolution_observable_circuit.png]]

Of course $A$ and $B$ are arbitrary and so can be the identity, or the same.
With this techniques it is measured the [[correlation]] between $B^\dagger(t)=e^{i H t} B^\dagger e^{-iHt}$ (i.e.  $B^\dagger$ is operated on the evolved system) and $A$. This quantity can be interpreted as a dynamical response.

This technique can estimate the dynamic of quantum systems. The time evolution $U(t)$ can be implemented by various approximations such as [[Trotter-Suzuki approximation]] or [[linear combination of unitaries approximation]].

This technique can be used to get the full [[eigenvalue spectrum retrival|eigenvalue spectrum]] by a classical postprocessing. 