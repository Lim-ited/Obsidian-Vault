Let $N = 2n$, and identify the set $\{0, . . . , N − 1\}$ with $\{0, 1\}^n$. Let $j \oplus s$ be the n-bit string obtained by bitwise adding the $n$-bit strings $j$ and $s$ mod 2, so for example $00110 \oplus 10101 = 10011$.

>[!Definition]
>For $N = 2n$, we are given $x = (x_0, . . . , x_{N−1})$, with $x_i ∈ \{0, 1\}^n$, with the property that there is some unknown nonzero $s ∈ \{0, 1\}^n$ such that $x_i = x_j$ iff ($i = j$ or $i = j \oplus s$). The goal is to find s.

This definition is from the original paper [[@Simon1994]]







