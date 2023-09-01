#algorithm #classical 

This is a very famous problem, it consist in finding the unique prime factors of a given positive integer greater than 2.

The factors are unique due to the *fundamental theorem of arithmetic* (which states exactly that).

A first brute force and inefficient approach is to search iteratively on all prime factors.

A better approach is the Pollard's rho algorithm. 
https://en.wikipedia.org/wiki/Pollard%27s_rho_algorithm

Another approach is the number field sieve, and is the most efficient approach (known as of 2023) to factor large numbers.
https://en.wikipedia.org/wiki/General_number_field_sieve

It is not known if an efficient classical algorithm exist, however this problem is believed to be in [[Complexity Classes|NP]].

A quantum algorithm that solve this problem is [[Shor's Algorithm]].