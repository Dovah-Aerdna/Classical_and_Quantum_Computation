#algorithm #quantum 

Is a [[Query model of computation|query algorithm]], and it is an extension of [[Deutsch's algorithm]], as it works on input function from n-bit to 1-bit.
Like its simplified version, its aim is to distinguish between two classes of input functions:
- constant, the output is always 0 or always 1;
- balanced, the output is 0 for half of the possible inputs, 1 for the other half.

There are, of course, functions that are not constant nor balanced, but by assumption, the oracle is represented by a constant or a balanced binary function.

![[Deutsch-Jozsa_problem.png]]

The circuit that solve this problem is:
![[Deutsch-Jozsa_circuit.png]]

The output must be classically post processed, to check if there are ones or not. In particular the output is the OR of the measurements.

# Analysis

Using the formula for a [[Famous States|layer of Hadamard]]:

![[Deutsch-Jozsa_analysis_1.png]]

After the application of the oracle, the state will be:

![[Deutsch-Jozsa_analysis_2.png]]

where the [[phase kickback]] phenomenon happens: the value $f(x)$ is "kicked" into the phase.
After the last layer of hadamard, the state prior to the measurement will be in:

![[Deutsch-Jozsa_analysis_3.png]]

The probability to measure the zero string from this state is:

![[Deutsch-Jozsa_analysis_4.png]]

Therefore this algorithms solves the Deutsch-Jozsa problem in a single query, instead of an exponential number (classically we need at least $2^{n-1}+1$, but a probabilistic algorithm just a very small number). 