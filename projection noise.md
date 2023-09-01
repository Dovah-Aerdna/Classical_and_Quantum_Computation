It is related to the intrinsic randomness in [[Projection measurement|measurements]] and create on graphs noise fluctuation from a mean distribution.

The outcome for a single shot measurement follows a [[Bernoulli distribution]].
For multiple shots, the variance is reduced by the number $M$ of shots taken:

$$\text{Var}(X)=p(1-p) \quad \implies \quad \text{Var}\left(S=M^{-1}\sum X_m\right)=\frac{\text{Var}(X)}{M}$$
(The variance for the single shot, as said, follows the [[Bernoulli distribution]]). Therefore the standard deviation is reduced by the square root of shots:

$$\sigma_{_S}=\sqrt{\frac{\text{Var}(X)}{M}}$$
There are [[tail and bounds inequalities|more sophisticated methods]] to control the statistical error.