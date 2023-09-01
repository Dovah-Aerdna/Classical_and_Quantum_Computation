
Is the process of choosing the physical qubit to run the [[Quantum Circuit]] on. The numbering of the qubit have a considerable effect since it can change the number of SWAP gates needed and can take advantage of hardware characteristics to reduce [[noise]] or improve efficiency. This type of optimization is usually performed during [[Transpiler|transpilation]].
It can be broadly divided into:
- Routing
- Layout

### Routing

Quantum chip topology (the specific connectivity among qubits) forces to use SWAP gate to communicate between physically distant qubits. This problem is tackled using the [[SABRE algorithm]]. 

As an example consider the two possible circuit for creating a 5 qubit [[Famous States|GHZ state]].

![[5_qubit_GHZ_routing.png]]

The first one is a star topology, where $q_0$ is the center, while the second one is a linear topology. It is important to create circuits friendly with the topology of the hardware.  For example the star topology in a [[heavvy exagon topology]] would need one swap:

![[5_GHZ_routing_star_topology.png]]

### Layout

Consider the errors induced by the specific operations that will be applied to some specific qubit, and choose the most efficient physical qubits. This is done by searching and scoring (by error) among all the possible ways to matching to a subset of physical qubits the layout of the circuit compatible with the SWAP network chosen in the routing step. This problem is solved by [[VF2 Layout algorithm]]. 