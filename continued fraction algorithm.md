#algorithm #classical 

Is used in [[Order finding by QPE]]. 

(Nielsen and Chuang, pag 230 box 5.3)

The idea of the continued fractions algorithm is to describe real numbers in terms
of integers alone, using expressions of the form>

$$[a_0,a_1, \cdots, a_n]=a_0+\frac{1}{a_1+\frac{1}{\cdots \ +\ \frac{1}{a_n}}}$$
where $a_k$ are positive integers ($a_0$ can be 0). The $m$-th convergent ($0\leq m \leq n$) to this continued fraction to be $[a_0,a_1, \cdots, a_m]$. The continued fractions algorithm is a method for determining the continued fraction expansion of an arbitrary real number. It is easily understood by example. 

Suppose we are trying to decompose 31/13 as a continued fraction. . The first step of the continued fractions algorithm is to split 31/13 into its integer and fractional part using  [[Euclid's algorithm]]:

$$\frac{31}{13}=2+\frac{5}{13}$$
Next we invert the fractional part, obtaining

$$\frac{31}{13}=2+\frac{1}{\frac{13}{5}}$$
These steps – split then invert – are now applied to 13/5, giving:

$$\frac{31}{13}=2+\frac{1}{2+\frac{1}{\frac{3}{5}}}$$
It’s clear that the continued fractions algorithm terminates after a finite number of ‘split and invert’ steps for any rational number, since the numerators which appear (31, 5, 3, 2, 1 in the example) are strictly decreasing.

### Best rational approximation

This algorithm can be used to compute the best rational approximation of a number, with the denominator under a certain $N$. For example, the continued fraction of $\sqrt{3}$ is:

$$\sqrt{3}=[1;1,2,1,2,1,2,1,2, \cdots]$$
the $m$-th convergent is the best possible approximant for its denominator. The sequence obtained by truncating the continued fraction representation is:
$$2,\frac{5}{3},\frac{7}{4},\frac{19}{11},\frac{26}{15}, \cdots$$
One can also expand the search for best approximants (finding more granular denominator) by reducing the last term of the truncation by a given amount (there are some subtleties, just not reduce to less than its value). Example: $[0;1,5,2,2]$ can be approximated by $[0;1] \ , \ [0,1,3=5-2] \ , \ [0,1,4=5-1] \ , \ [0,1,5] \ , \ [0,1,5,1=2-1] \ , \ [0,1,5,2] \ etc...$ 

Another method, deriving from the [[Farey sequence]] use the [[mediant]].
The idea is to start with two fractions, _a_/_b_ = 0/1 and _c_/_d_ = 1/1. We update either _a_/_b_ or _c_/_d_ at each step so that _a_/_b_ will be the best lower bound of _x_ in $[0,1]$ with denominator no bigger than _b_, and _c_/_d_ will be the best upper bound with denominator no bigger than _d_. At each step we do a sort of [[binary search]] by introducing the _mediant_ of the upper and lower bounds. The mediant of _a_/_b_ and _c_/_d_ is the fraction (_a_+_c_)/(_b_+_d_) which always lies between _a_/_b_ and _c_/_d_.


def farey(x, N):

    a, b = 0, 1
    c, d = 1, 1
    
    while (b <= N and d <= N):
        mediant = float(a+c)/(b+d)
        
        if x == mediant:
            if b + d <= N:
                return a+c, b+d
            elif d > b:
                return c, d
            else:
                return a, b
                
        elif x > mediant:
            a, b = a+c, b+d
        else:
            c, d = a+c, b+d
            
    if (b > N):
        return c, d
    else:
        return a, b