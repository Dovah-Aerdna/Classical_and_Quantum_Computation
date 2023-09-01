Establishes an upper bound to the amount of information that can be known about a quantum state.

Alice has a classical random variable X, taking values in a discrete set with some corresponding probabilities. Alice then prepare a specific quantum state after extracting a value, and give this state to Bob. Bob's goal is to find the value of X, performing a measurement, obtaining the classical outcome Y. In this context, the amount of accessible information, that is, the amount of information that Bob can get about the variable _X_, is the maximum value of the *mutual information* 
$$I(X:Y)=\sum_{y \in Y} \sum_{x \in X} P_{(X,Y)}(x, y) \log\left(\frac{P_{(X,Y)}(x, y)}{P_X(x)\,P_Y(y)}\right)$$

 (Intuitively, mutual information measures the information) between the random variables _X_ and _Y_ over all the possible measurements that Bob can do.

Statement of the theorem:

Let $\{\rho_1, \cdots , \rho_n\}$ be a set of [[density matrix|mixed states]] and let $\rho_x$ be one of these states drawn according to the probability distribution $P=\{p_1, \cdots, p_n\}$ . Then, for any measurement described by [[POVM]] elements and performed on $\rho=\sum_x p_x \rho_x$ the amount of accessible information about the variable _X_ knowing the outcome _Y_ of the measurement is bounded from above as follows:
$$I(X:Y) \leq S(\rho) - \sum_i p_i S(\rho_i):= \chi$$

where $S(\cdot)$ is the von Neumann entropy:

$$S(\rho)=- \operatorname{tr}(\rho \ln \rho)$$
The bounds is referred to as the Holevo's bound, Holevo information or Holevo $\chi$ quantity.