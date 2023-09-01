#tofinish 

In this techniques the noise model is learned and inverted. To learn the noise model it can be used [[Pauli Twirling]] to each layer. The inversion is approximate. It is a very expensive technique since it needs to be run many times to find a good approximation of the noise channel, and the results must be classically "inverted". 

![[Probabilistic_error_cancellation.png]]

In the scheme, $\Lambda_i$ are the noise channels for the ideal gates $U_i$. The actual [[noisy gates]] are $\tilde{U_i}$ and can be approximatively transformed back to the ideal ones by $\Lambda_i^{-1}$ representing a kind of inverse of the learned noise model relative to the $i$-th layer. . 