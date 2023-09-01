#classical 

For boolean circuit, an elementary gate set, universal for deterministic computation, is:
- AND
- OR
- NOT
- FANOUT

Some gates can be universal on their own, for example NAND.



- the *size* of a circuit ([[Boolean Circuit]] or quantum), is the total number of gates (elementary operations) it includes. Therefore circuit size corresponds to [[sequential]] running time.
- the *depth* of a circuit is the maximum number of gates encountered on any path from an input wire to an output wire. Therefore circuit depth corresponds to [[parallel]] running time. The depth is equivalent to the number of layers the circuits is composed of. 


Since each circuit has a fixed size, to analyse the scaling of the algorithm it implements, a family of circuits $\{\mathcal{C}_1, \mathcal{C}_2, \cdots\}$  is actually needed (typically, one circuit for each input length). 

To obtain a boolean circuit from a function there are various procedures. The most simple ones consist in reading the truth table and use:
- DNF, Disjuntive normal form, consisting of a disjunction of conjunctions. It is in a circuit form an OR and ANDs, and can be seen as a sum of products. 
- CNF, Conjunctive normal form, consisting in a conjunction of disjunctions. It is in a circuit form an AND of of ORs, and can be seen as a product of sums.