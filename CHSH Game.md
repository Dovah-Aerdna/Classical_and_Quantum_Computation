#algorithm #quantum 

Nonlocal game, see also a video on gamification of Bell's theorem:
https://www.youtube.com/watch?v=v7jctqKsUMA 

Once the game start Alice and Bob cannot communicate. 

The "input" is binary, $x$ for A and $y$ for B. Using the strategy, A will answer with a bit a, and B with b.

In CHSH, $(x,y)$ is chosen uniformly, and $(a,b)$ wins if and only if:

$$a\oplus b=x \land y$$
In other words:

| $(x,y)$ | win | 
| -------- | -------- | 
| (0,0) | $a=b$ |
| (0,1) | $a=b$ |
| (1,0) | $a=b$ |
| (1,1) | $a \neq b$ |

No deterministic strategy can win every time. Actually the bound on every classical (also probabilistic and correlated) strategy is $\frac{3}{4}=75\%$

Using an e-bit, i.e. using a quantum strategy, they can break this bound.

## Strategy

Let:
$$|\psi_\theta \rangle=\cos \theta |0\rangle+\sin \theta | 1 \rangle$$
the [[Bra-ket|inner product]] of two such kets is:

$$\langle \psi_\alpha |\psi_\beta \rangle=\cos(\alpha-\beta)$$
by geometric definition or by addition formulas.
Consider:

$$\langle \psi_\alpha \otimes\psi_\beta|\phi^+\rangle=\frac{\cos(\alpha-\beta)}{\sqrt{2}}$$
Consider the unitary operator:
$$U_\theta=|0\rangle\langle\psi_\theta|+|1\rangle\langle\psi_{\theta+\pi/2}|$$
![[CHSH_strategy.png]]

Using the formula above to simplify each state like the following (obtained for $x=0, \ y=0$:

$$(U_0\otimes U_{\pi/8})|\phi^+\rangle$$
the probabilities of measurements can be obtained:

$$\Pr (a=b)=\frac{2+\sqrt{2}}{4}\approx 85\%$$
$$\Pr (a\neq b)=\frac{2-\sqrt{2}}{4}\approx 15\%$$
All the other cases gives equal probabilities, in favour of the winning case. This strategy is also the best quantum one. This fact is known as Tsirelson Bound or inequality.
A geometric interpretation can be given:

![[CHSH_geometric_00.png]]![[CHSH_geometric_01.png]]![[CHSH_geometric_10.png]]![[CHSH_geometric_11.png]]

Blu corresponds to the 0 measurement, and red to the outcome 1. If the angle between two vector is small, the cosine is large, so the probability is large. The probabilities are linked to the angles between these vectors.