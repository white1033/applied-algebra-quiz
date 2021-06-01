# El Gamal Cryptosystem
### 1. (a) Consider the prime $$p = 107$$. Show that $$2$$ generates $$ {\mathbb{F}_{107}}^{\star}$$.
Since $$ |{\mathbb{F}_{107}}^{\star}| = 106 = 2 * 53 $$,  it's satisfied to prove that
$$ 2^{53} \equiv -1\ (\textrm{mod}\ 107) $$ .

Consider that $$ 53 = 32 + 16 + 4 + 1 $$, then

$$\begin{align} 
    2^{53} & \equiv 2^{32} * 2^{16} * 2^{4} * 2^{1} \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 29 * 52 * 16 * 2 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv (52 * 2) * 29 * 16 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv -3 * 29 * 16 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv (29 * 4) * (-3) * 4 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 9 * (-3) * 4 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv -108 \ (\textrm{mod}\ 107) 
\notag \\
& \equiv -1 \ (\textrm{mod}\ 107) 
    \notag
\end{align}$$

Therefore, $$2$$ generates $$ {\mathbb{F}_{107}}^{\star}$$.

### (b) Take $$ p=107 $$ and $$\alpha=2$$. You select $$d=13$$. What is the public key?

We now need to compute $$2^{13} \ \textrm{mod}\ 107  $$, then

$$ \begin{align} 
    2^{13} & \equiv 2^{8} * 2^{4} * 2^{1} \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 42 * 16 * 2 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 14 * (3 * 16 * 2) \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 14 * (-11) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 2 * (7 * (-11)) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 2 * 30 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 60 \ (\textrm{mod}\ 107) 
\notag
\end{align}
$$

Therefore public key is $$(107, 2, 60)$$.

### \(c\) Suppose that Alice selects $$e = 5$$ and would like to send message $$m = 88$$ to you. What would she send?

We now need to compute $$ 2^{5} \ \textrm{mod}\ 107$$ and $$ 60^{5} * 88 \ \textrm{mod}\ 107$$. 

Firstly it's easy to see that $$ 2^{5} \equiv 32 \ (\textrm{mod}\ 107) $$, secondly 

$$ 
\begin{align} 
    60^{5} * 88 & \equiv 60^{4} * 12 * (5 * 22) * 4 \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 60^{4} * 12 * 3 * 4 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 60^{4} * 37 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 60^{3} * 20 * (3 * 37) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv  60^{3} * 20 * 4 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 60^{3} * 2^{3} * 10 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 120^{3} * 10 \ (\textrm{mod}\ 107) 
\notag \\
 & \equiv 13^{3} * 10 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 169 * 130 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 62 * 23 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv (60+2) *(20+3) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 1200 + 40 + 180 + 6 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 23 + 40 + 73 + 6 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 23 + 113 + 6 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 23 + 6 + 6 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 35 \ (\textrm{mod}\ 107) 
    \notag
\end{align}
$$

Therefore, she would send $$(32, 35)$$.

### (d) If you receive $$(32, 88)$$, what is the message $$m$$?

We should compute $$32^{13} \ \textrm{mod}\ 107$$ first, 

$$ 
\begin{align} 
    32^{13} & \equiv {(2^{5})}^{13} \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 2^{65} \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 2^{64} * 2^1 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 92 * 2 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 184 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 77 \ (\textrm{mod}\ 107)
    \notag 
\end{align}
$$

Secondly we will compute $$77^{-1} \ \textrm{mod}\ 107$$ by using Euclidean Algorithm, 

$$ 
\begin{align} 
    107 & = 77 * 1 + 30
    \notag  \\
   77 & = 30 * 2 + 17
    \notag  \\
    30 & = 17 * 1 + 13
    \notag  \\
   17 & = 13 * 1 + 4
    \notag  \\
 13 & = 4 * 3 + 1
    \notag 
\end{align}
$$

Then, 

$$ 
\begin{align} 
    1 & = 13 - 4*3
    \notag  \\
     & = 13 - (17-13) *3
    \notag  \\
     & = 13*4 - 17 *3
    \notag  \\
        & = (30-17)*4 - 17 *3
    \notag  \\
     & = 30*4 - 17 *7
    \notag  \\
     & = 30*4 - (77-30*2) *7
    \notag  \\
     & = 30*18 - 77 *7
    \notag  \\
     & = (107-77)*18 - 77 *7
    \notag  \\
     & = 107*18 - 77 *25
\notag
\end{align}
$$

We get $$77 * (-25) \equiv  1 \ (\textrm{mod}\ 107) $$, i.e. $$77^{-1} \equiv  -25 \ (\textrm{mod}\ 107)$$.

Finally, we compute $$(-25) * 88 \ \textrm{mod}\ 107$$ in order to decrypt the message, 

$$
\begin{align} 
    (-25) * 88 & \equiv (-25 * 4) * 22 \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv (-100) * 22 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 7 * 22 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 154 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 47 \ (\textrm{mod}\ 107) 
\notag
\end{align}
$$ 

Therefore, our message $$m$$ is equal to 47.
