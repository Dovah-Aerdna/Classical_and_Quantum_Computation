#algorithm #quantum

Transport an *unknown* quantum state from A to B, communicating 2 classical bits. The transmitting state could be in correlation (including entanglement) with another system. 
Observation: it is not possible to communicate classically a generic quantum state! It would violate the [[No-Cloning theorem]]. Also for the same reason, during a qantum teleportation, the transmitter must no longer have the qubit in its original state.

A and B share an [[Famous States|e-bit]], which is consumed after the execution of the protocol.

![[Teleportation_circuit.png]]

This circuits can be seen as a [[Famous States|Bell measurement]] and a controlled operations on Bob's qubit.

The initial state can be expressed by describing the system $S$ we want to send, and the Alice and Bob qubits. Isolating the Bob subsystem:

$$|\psi\rangle_S \otimes |\psi^{00}\rangle_{AB}= \frac{1}{2} \left[ |\psi^{00}\rangle_{SA} \otimes |\psi\rangle_B+|\psi^{01}\rangle_{SA}\otimes X |\psi\rangle_B+|\psi^{10}\rangle_{SA}\otimes Z |\psi\rangle_B+|\psi^{11}\rangle_{SA} \otimes XZ |\psi \rangle_B   \right]$$
Therefore, measuring in the Bell Basis will make the state collapse in one of the above states, which need to be "cleaned" in order to be exactly $|\psi\rangle$.