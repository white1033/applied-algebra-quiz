# El Gamal Cryptosystem
### 1. (a) Consider the prime $$p = 107$$. Show that $$2$$ generates $$ {\mathbb{F}_{107}}^{\star}$$.
Since $$ |{\mathbb{F}_{107}}^{\star}| = 106 = 2 \times 53 $$, and $$2^{2} \equiv 4 \not\equiv 1\ (\textrm{mod}\ 107)$$ it's satisfied to prove that
$$ 2^{53} \equiv -1\ (\textrm{mod}\ 107) $$ .

Consider that $$ 53 = 32 + 16 + 4 + 1 $$, then

$$\begin{align} 
    2^{53} & \equiv 2^{32} \times 2^{16} \times 2^{4} \times 2^{1} \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 29 \times 52 \times 16 \times 2 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv (52 \times 2) \times 29 \times 16 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv -3 \times 29 \times 16 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv (29 \times 4) \times (-3) \times 4 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 9 \times (-3) \times 4 \ (\textrm{mod}\ 107) 
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
    2^{13} & \equiv 2^{8} \times 2^{4} \times 2^{1} \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 42 \times 16 \times 2 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 14 \times (3 \times 16 \times 2) \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 14 \times (-11) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 2 \times (7 \times (-11)) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 2 \times 30 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 60 \ (\textrm{mod}\ 107) 
\notag
\end{align}
$$

Therefore our public key is $$(107, 2, 60)$$.

### \(c\) Suppose that Alice selects $$e = 5$$ and would like to send message $$m = 88$$ to you. What would she send?

We now need to compute $$ 2^{5} \ \textrm{mod}\ 107$$ and $$ 60^{5} \times 88 \ \textrm{mod}\ 107$$. 

Firstly it's easy to see that $$ 2^{5} \equiv 32 \ (\textrm{mod}\ 107) $$, secondly 

$$ 
\begin{align} 
    60^{5} \times 88 & \equiv 60^{4} \times 12 \times (5 \times 22) \times 4 \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv 60^{4} \times 12 \times 3 \times 4 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 60^{4} \times 37 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 60^{3} \times 20 \times (3 \times 37) \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv  60^{3} \times 20 \times 4 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 60^{3} \times 2^{3} \times 10 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 120^{3} \times 10 \ (\textrm{mod}\ 107) 
\notag \\
 & \equiv 13^{3} \times 10 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 169 \times 130 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 62 \times 23 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv (60+2) \times (20+3) \ (\textrm{mod}\ 107) 
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
    & \equiv 2^{64} \times 2^1 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 92 \times 2 \ (\textrm{mod}\ 107) 
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
    107 & = 77 \times 1 + 30
    \notag  \\
   77 & = 30 \times 2 + 17
    \notag  \\
    30 & = 17 \times 1 + 13
    \notag  \\
   17 & = 13 \times 1 + 4
    \notag  \\
 13 & = 4 \times 3 + 1
    \notag 
\end{align}
$$

Then, 

$$ 
\begin{align} 
    1 & = 13 - 4 \times 3
    \notag  \\
     & = 13 - (17-13) \times 3
    \notag  \\
     & = 13 \times 4 - 17 \times 3
    \notag  \\
        & = (30-17) \times 4 - 17  \times 3
    \notag  \\
     & = 30\times4 - 17 \times7
    \notag  \\
     & = 30\times4 - (77-30\times2) \times7
    \notag  \\
     & = 30\times18 - 77 \times7
    \notag  \\
     & = (107-77)\times18 - 77 \times7
    \notag  \\
     & = 107\times18 - 77 \times25
\notag
\end{align}
$$

We have $$77 \times (-25) \equiv  1 \ (\textrm{mod}\ 107) $$, i.e. $$77^{-1} \equiv  -25 \ (\textrm{mod}\ 107)$$.

Finally, we compute $$(-25) \times 88 \ \textrm{mod}\ 107$$ in order to decrypt the message, 

$$
\begin{align} 
    (-25) \times 88 & \equiv (-25 \times 4) \times 22 \ (\textrm{mod}\ 107)
    \notag  \\
    & \equiv (-100) \times 22 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 7 \times 22 \ (\textrm{mod}\ 107) 
    \notag \\
    & \equiv 154 \ (\textrm{mod}\ 107) 
    \notag \\
 & \equiv 47 \ (\textrm{mod}\ 107) 
\notag
\end{align}
$$ 

Therefore, our message $$m$$ is equal to $$47$$.
