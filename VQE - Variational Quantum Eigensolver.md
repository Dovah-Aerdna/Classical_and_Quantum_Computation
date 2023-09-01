#algorithm #quantum #classical 

Very similar to [[QAOA - Quantum Approximate Optimization algorithm]].

VQE tries to minimize a cost function by running a parametric quantum circuit multiple times, modifying the parameters using a classical optimizer.
The cost function is associated to the energy of the system described by a certain Hamiltonian. Therefore the goal of VQE is to retrieve the lowest eigenvalue $\lambda_0$:
$$\lambda_0=\min_{|\psi\rangle}\langle\psi|H|\psi\rangle$$
If the full [[eigenvalue spectrum retrival|spectrum is known]] it is sufficient to take the smallest eigenvalue.
The same problems that a classical optimization experience are also present in VQE, for example it is possible to find a local minima instead of the global one, or there could be convergence problems.
An idea to explore the space of states is to parametrize them:

$$|\psi\rangle=|\psi(\theta)\rangle$$ and explore that space by a [[random walk]]. In general this space will be a subset of all the possible $2^n$ discrete states, parametrized by $\theta=(\theta_1, \theta_2, \cdots)$. Therefore the search for the minimum is usually performed on a subset of the full possible search space. 

**Observation:** In the cost must be considered also the time for the classical computation needed to [[compile]] and generate the pulses for each new circuit.

**Observation:** a clever [[Hamiltonial map]] to represent the problem must be found.

**Observation:** [[polygrouping]] is a technique that allows to recover a general observable by measuring only the expectation of the three [[Pauli matrices|Pauli Operators]]. 

**Observation:** always check the complexity class of the problem under study.