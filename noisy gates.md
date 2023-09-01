In real hardware, gates are [[noise|noisy]]. Often, [[time evolution|unitary evolution]] of the physical qubit is harnessed to create a [[Gates|gate]], but the result is not perfect. It can be in a first approximation, described by a non precise rotation on the [[Bloch Sphere]]. 

$$\tilde{G}=G_\varepsilon G$$
i.e. the noisy gate $\tilde{G}$ can be decomposed in an ideal component $G$ and an error dependent by some parameter $\varepsilon$. 

For example, in the case of a chain of $X$ gates, the difference between the ideal case and the noisy one is given by the effect of the error in the rotation.

![[noisy_X_gates.png]]

This picture do not take into account [[Coherence|decoherence]]: it actually is an example of [[coherent noise]].