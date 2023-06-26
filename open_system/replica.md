# Unravelling the Master equation
## Master equation
$$
\begin{align*}
\dot{\rho} & =-i[H,\rho]+\gamma\sum_{m}(2L_{m}\rho L_{m}^{\dagger}-L_{m}^{\dagger}L_{m}\rho-\rho L_{m}^{\dagger}L_{m})\\
& =-i[H-i\gamma \sum_m L_m^\dagger L_m,\rho]'+\gamma\sum_{m}2L_{m}\rho L_{m}^{\dagger}\\
\end{align*}
$$
## Jump Process
$$
\begin{aligned}
|d\psi\rangle =&-i(H-i\gamma\sum_{m}L_{m}^{\dagger}L_{m}+i\gamma\sum_{m}\langle L_{m}^{\dagger}L_{m}\rangle)|\psi\rangle dt\\
 & +\sum_{m}dN_{m}(\frac{L_{m}}{\sqrt{\langle L_{m}^{\dagger}L_{m}\rangle}}-1)|\psi\rangle\\
dN_{i}dN_{j} =&\delta_{ij}dN_{j}\\
E(dN_{i}) =&2\gamma\langle L_{m}^{\dagger}L_{m}\rangle dt
\end{aligned}
$$
## Diffusion Process
$$
\begin{align*}
|d\psi\rangle =&-iH|\psi\rangle dt+\sum_{m}(2\langle L_{m}^{\dagger}\rangle L_{m}-L_{m}^{\dagger}L_{m}-\langle L_{m}^{\dagger}\rangle\langle L_{m}\rangle)|\psi\rangle \gamma dt\\
 & +\sum_{m}(L_{m}-\langle L_{m}\rangle)|\psi\rangle \sqrt{\gamma}d\xi_{m}\\
E(d\xi_{m}) =&0\\
E(\overline{d\xi_{m}}d\xi_{n}) =&2\delta_{mn}dt\ \ (Gaussian\ noise)
\end{align*}
$$

### Why Fang's method is correct?
It is correct under Totterization:

$$
\begin{aligned}
|\psi_{next}\rangle =&exp[-i(H-i\gamma\sum_{m}L_{m}^{\dagger}L_{m}+i\gamma\sum_{m}\langle L_{m}^{\dagger}L_{m}\rangle)dt\\
 & +\sum_{m}dN_{m}(\frac{L_{m}}{\sqrt{\langle L_{m}^{\dagger}L_{m}\rangle}}-1)]|\psi\rangle\\
 =& \{\prod_m exp[dN_{m}(\frac{L_{m}}{\sqrt{\langle L_{m}^{\dagger}L_{m}\rangle}}-1)]\}\\
 
 &exp[-i(H-i\gamma\sum_{m}L_{m}^{\dagger}L_{m})dt]&\\
& exp[-ii\gamma\sum_{m}\langle L_{m}^{\dagger}L_{m}\rangle] dt|\psi\rangle\\
\end{aligned}
$$
The last line is a normalization factor, which is included in QR decomposition.
$$
\begin{aligned}
exp[dN_m(\frac{L_{m}}{\sqrt{\langle L_{m}^{\dagger}L_{m}\rangle}}-1)]\sim &1+dN_m(\frac{L_{m}}{\sqrt{\langle L_{m}^{\dagger}L_{m}\rangle}}-1) \\
dN_{i}dN_{j} =&\delta_{ij}dN_{j}\\
E(dN_{i}) =&2\gamma\langle L_{m}^{\dagger}L_{m}\rangle dt
\end{aligned}
$$
$dN_i=0\ or\ 1$, So the numerical method is the same as diffusion process.
# Replica dynamics

Single replica:

$$
\begin{aligned}
d\rho =& -i(H\rho-\rho H)dt\\
 & +2\gamma\sum_mL_m\rho L_m^\dagger dt-\gamma \sum_m\{L_m^\dagger L_m,\rho\}dt \\
 &+\sqrt{\gamma} \sum_m d\xi_m(M_m\rho+\rho M_m^\dagger)\\
 =& L\rho+\sqrt{\gamma} \sum_m d\xi_m(M_m\rho+\rho M_m^\dagger)
\end{aligned}
$$
$$
\overline{\xi_m\xi_{m'}} = 2\delta_{m,m'}dt
$$

$$
M_m = L_m-\langle L_m\rangle
$$
For replica, where $O^{(1)}\equiv O\otimes I,\ O^{(2)}\equiv I\otimes O$:

$$
\begin{aligned}
d\rho^{(R_2)} =& \overline{d\rho\otimes\rho}+ \overline{\rho\otimes d\rho}+\overline{d\rho\otimes d\rho}\\
=&dtL^{(1)}\rho^{(R_2)}+dtL^{(2)}\rho^{(R_2)}\\
&+2\gamma dt\sum_m\overline{\{M_m^{(1)},\{M_m^{(2)},\rho\}'\}'}
\end{aligned}
$$

$$
\{\rho,A\}'\equiv \rho A + A^\dagger \rho
$$

Doing mean field approximation, by defining: $\langle \langle ... \rangle \rangle \equiv Tr[...\rho^{(R_2)}]$

$$
\begin{aligned}
\overline{\langle L_m^{(\dagger)}\rangle\rho\otimes\rho} & = \langle \langle L_m^{(\dagger)(1,2)} \rangle \rangle\rho^{(R_2)}\\
\overline{\langle L_m^{(\dagger)}\rangle\langle L_m^{(\dagger)}\rangle\rho\otimes\rho} & = \langle \langle L_m^{(\dagger)(1)}L_m^{(\dagger)(2)} \rangle \rangle\rho^{(R_2)}
\end{aligned}
$$

The dynamics now becomes:

$$
\begin{aligned}
d\rho^{(R_2)} =&dt\mathscr{L}^{(1)}\rho^{(R_2)}+dt\mathscr{L}^{(2)}\rho^{(R_2)}\\
&+2\gamma dt\sum_m\{L_m^{(1)}-\langle \langle L_m^{(1)} \rangle \rangle,\{L_m^{(2)}-\langle \langle L_m^{(2)} \rangle \rangle,\rho^{(R_2)}\}'\}'\\
&+2\gamma dt\sum_m\langle \langle (L_m^{(1)}+L_m^{\dagger(1)})(L_m^{(2)}+L_m^{\dagger(2)}  )\rangle \rangle \rho^{(R_2)}\\
&- 2\gamma dt\sum_m(\langle \langle L_m^{(1)}\rangle \rangle+\langle \langle L_m^{\dagger(1)}\rangle \rangle)(\langle \langle L_m^{(2)\rangle \rangle}+\langle \langle L_m^{\dagger(2)}  \rangle \rangle)\rho^{(R_2)}
\end{aligned}
$$
$$
\begin{aligned}
\mathscr{L} \equiv& -i(H\rho-\rho H)dt\\
 & +2\gamma\sum_mL_m\rho L_m^\dagger dt-\gamma \sum_m\{L_m^\dagger L_m,\rho\}dt \\
 \end{aligned}
$$

Omitting the constant term:

$$
\begin{aligned}
d\rho^{(R_2)} =&dt\mathscr{L}^{(1)}\rho^{(R_2)}+dt\mathscr{L}^{(2)}\rho^{(R_2)}\\
&+2\gamma dt\sum_m\{L_m^{(1)}-\langle \langle L_m^{(1)} \rangle \rangle,\{L_m^{(2)}-\langle \langle L_m^{(2)} \rangle \rangle,\rho^{(R_2)}\}'\}'\\
\end{aligned}
$$
# From lattice model to continuous and Bosonized model 
In this model,
$$
H = J\sum_i c^\dagger_{i+1}c_i+h.c.
$$
$$
\begin{aligned}
L_i =& e^{i\theta n_{i+1}}\frac{1}{2}（c^\dagger_{i}-ic^\dagger_{i+1}）(c_{i}+ic_{i+1})\\
=&\frac{1}{2}(n_{i}+n_{i+1}-ic^\dagger_{i+1}c_i+ic^\dagger_ic_{i+1})\\
&\frac{e^{i\theta}-1}{2}(n_{i+1}n_{i}+n_{i+1}-ic^\dagger_{i+1}c_i)\\
=&\frac{1}{2}(n_{i}+e^{i\theta}n_{i+1}-ie^{i\theta}c^\dagger_{i+1}c_i+ic^\dagger_ic_{i+1})\\
&\frac{e^{i\theta}-1}{2}n_{i+1}n_{i}\\
\end{aligned}
$$

$$
L_i^\dagger L_i = \frac{1}{2}（c^\dagger_{i}-ic^\dagger_{i+1}）(c_{i}+ic_{i+1})
$$

More specifically, $\theta = \pi$:

$$
\begin{aligned}
L_i =&\frac{i}{2}(c^\dagger_{i+1}c_i+c^\dagger_ic_{i+1})\\
&-(n_{i}-\frac{1}{2})(n_{i+1}-\frac{1}{2})\\
&-(n_{i+1}-\frac{1}{2})-\frac{1}{4}.\\
\end{aligned}
$$

Writing in continuous limit and doing Bosonization(Following Quantum Field Theory and Condensed Matter, Shankar):

$$
\begin{aligned}
L(x) =&-\frac{i}{2}(\partial_0 \phi)^2-\frac{i}{2}(\partial_1 \phi)^2\\
&-\frac{2}{\pi}(\partial_1 \phi)^2-\frac{1}{2\pi^2\alpha^2}\cos(4\sqrt{\pi}\phi)\\
&-(\frac{1}{\sqrt{\pi}}\partial_1 \phi+oscillations)-\frac{1}{4}
\end{aligned}
$$
Where $\alpha$ is  the cut off,  

$$\frac{1}{\pi\alpha} =\Lambda.$$

The term $n_i$ only shift the $\partial_1 \phi$ by a constant, it could be absorbed into the field. Thus it is omitted in the following calculation for clarity.

By the same trick, the original Hamiltonian is:

$$
H= -J\int dx[(\partial_0 \phi)^2+(\partial_1 \phi)^2]
$$

$$
\begin{aligned}
L^\dagger_i L_i =&\frac{i}{2}(-c^\dagger_{i+1}c_i+c^\dagger_ic_{i+1})\\
L^\dagger L=&\frac{i}{2}(\partial_0 \phi)^2+\frac{i}{2}(\partial_1 \phi)^2.\\
\end{aligned}
$$
# Split 2-replica to (a,r) coordinates

# Packet velocity
Define the center of the wave packet to be:

$$
\overline{x(t)} = \sum_{s=1}^{L}s\overline{\langle \psi_t |\hat{n}_s|\psi_t\rangle}/\overline{\langle \psi_t |\psi_t\rangle}
$$

The overline on R.H.S means the average over trajectories.
$$
\begin{aligned}
\frac{d\overline{x}}{dt}=&\sum_{s=1}^{L}s \overline{[ \langle d\psi_t |\hat{n}_s|\psi_t\rangle+\langle \psi_t |\hat{n}_s|d\psi_t\rangle+\langle d\psi_t |\hat{n}_s|d\psi_t\rangle]}/\overline{\langle \psi_t |\psi_t\rangle}\\
&-\sum_{s=1}^{L}s \overline{\langle \psi_t |\hat{n}_s|\psi_t\rangle}\overline{[ \langle d\psi_t |\psi_t\rangle+\langle \psi_t |d\psi_t\rangle+\langle d\psi_t |d\psi_t\rangle]}/\overline{\langle \psi_t |\psi_t\rangle}^2\\
\end{aligned}
$$
Note that:

$$
\begin{aligned}
    &\overline{[ \langle d\psi_t |\psi_t\rangle+\langle \psi_t |d\psi_t\rangle+\langle d\psi_t |d\psi_t\rangle]}\\
    =& \langle \psi_t |iH^\dagger +\sum_m dN_m (\frac{L^\dagger_m}{\sqrt{\langle L^\dagger_m L_m\rangle}}-1)  |\psi_t\rangle\\
    &+ \langle \psi_t |-iH+\sum_m dN_m (\frac{L_m}{\sqrt{\langle L^\dagger_m L_m\rangle}}-1)  |\psi_t\rangle\\
    &+ \langle \psi_t |\sum_m dN_m (\frac{L^\dagger_m}{\sqrt{\langle L^\dagger_m L_m\rangle}}-1)(\frac{L_m}{\sqrt{\langle L^\dagger_m L_m \rangle}}-1)  |\psi_t\rangle\\
    =&\langle \psi_t |iH^\dagger -iH |\psi_t\rangle\\
    &+\langle \psi_t |\sum_m dN_m( \frac{L^\dagger_m L_m}{\langle L^\dagger_m L_m\rangle}-1) |\psi_t\rangle\\
    =&\langle \psi_t |iH^\dagger -iH |\psi_t\rangle
\end{aligned}
$$
## Evolution without jump
$$
\begin{aligned}
\frac{d\overline{x}}{dt}=&\sum_{s=1}^{L}s \{ i\langle \psi_t |(H_{eff}^\dagger \hat{n}_s-\hat{n}_sH_{eff})|\psi_t\rangle dt\}\\
&+\sum_{s=1}^{L}s\langle \psi_t |\hat{n}_s|\psi_t\rangle\gamma \langle \psi_t |\sum_m 2L_m^\dagger L_m|\psi_t\rangle\\
=&\sum_{s=1}^{L}s \{ i\langle \psi_t |(H_{eff}^\dagger \hat{n}_s-\hat{n}_sH_{eff})|\psi_t\rangle dt\}\\
&-\sum_{s=1}^{L}s\langle \psi_t |\hat{n}_s|\psi_t\rangle \langle \psi_t |iH^\dagger -iH |\psi_t\rangle\\
\end{aligned}
$$




## Jump velocity
$$
\begin{aligned}
    &\overline{[ \langle d\psi_t |x|\psi_t\rangle+\langle \psi_t |x|d\psi_t\rangle+\langle d\psi_t |x|d\psi_t\rangle]} \\
    =& \langle \psi_t |iH^\dagger x+\sum_m dN_m (\frac{L^\dagger_m}{\sqrt{\langle L^\dagger_m L_m\rangle}}-1)x  |\psi_t\rangle\\
    &+ \langle \psi_t |-ixH+\sum_m dN_m x(\frac{L_m}{\sqrt{\langle L^\dagger_m L_m\rangle}}-1)  |\psi_t\rangle\\
    &+ \langle \psi_t |\sum_m dN_m (\frac{L^\dagger_m}{\sqrt{\langle L^\dagger_m L_m\rangle}}-1)x(\frac{L_m}{\sqrt{\langle L^\dagger_m L_m \rangle}}-1)  |\psi_t\rangle\\
    =&\langle \psi_t |iH^\dagger x-ixH |\psi_t\rangle\\
    &+\langle \psi_t |\sum_m dN_m( \frac{L^\dagger_m xL_m}{\langle L^\dagger_m L_m\rangle}-x) |\psi_t\rangle\\
\end{aligned}
$$

$$
\begin{aligned}
\frac{d\overline{x}}{dt}=&\sum_{s=1}^{L}s \{ i\langle \psi_t |(H_{eff}^\dagger \hat{n}_s-\hat{n}_sH_{eff})|\psi_t\rangle dt\\
&+\gamma \langle \psi_t |\sum_m 2L_m^\dagger\hat{n}_sL_m|\psi_t\rangle\}\\
\end{aligned}
$$

Where $H_{eff} = H-i\gamma\sum_m L_m^\dagger L_m$

Because $L_i = U_iP_i=e^{i\theta n_{i+1}}P_i$, so $L_i^\dagger n_s L_i=P_iU_i^\dagger n_sU_i P_i=P_ie^{-i\theta n_{i+1}} n_se^{i\theta n_{i+1}} P_i=P_in_sP_i$. Thus, the jump velocity operator is independent of $\theta$.

However, the evolution of $| \psi\rangle$ is affected by $\theta$. So the velocity is still a $\theta$ dependent quantity.


### Deal with $2\gamma \sum_m\langle \psi_t | L_m^\dagger\hat{n}_sL_m|\psi_t\rangle$
Note that
$$
i(H_{eff}-H_{eff}^\dagger) = 2\gamma\sum_m L_m^\dagger L_m = 2\gamma\sum_m P_m
$$
The split the expectation into two part:
$$
\begin{aligned}
    &2\gamma\sum_s s \sum_m\langle \psi_t | L_m^\dagger\hat{n}_sL_m|\psi_t\rangle\\
   =&2\gamma\sum_s s \sum_m\langle \psi_t | P_m\hat{n}_sP_m|\psi_t\rangle\\
   =&2\gamma\sum_s s \sum_m[\langle \psi_t | P_m[\hat{n}_s,P_m]|\psi_t\rangle+\langle \psi_t | P_m\hat{n}_s|\psi_t\rangle]\\
   =&2\gamma \sum_m [m\langle \psi_t | P_m[\hat{n}_m,P_m]|\psi_t\rangle+ (m+1)\langle \psi_t | P_m[\hat{n}_{m+1},P_m]|\psi_t\rangle]\\
    &+\sum_s s\langle \psi_t | i(H_{eff}-H_{eff}^\dagger)\hat{n}_s|\psi_t\rangle\\
\end{aligned}
$$
For the latter term, note $i(H_{eff}-H_{eff}^\dagger)$ by $A$

$$
\begin{aligned}
&\sum_s s\langle \psi_t | A_{i,j}c^\dagger_i c_j\hat{n}_s|\psi_t\rangle\\
=&A_{i,j}s[\langle c^\dagger_i c_j \rangle\langle c^\dagger_s c_s \rangle+\langle c^\dagger_i c_s \rangle (\delta_{j,s}-\langle c^\dagger_s c_j \rangle)]\\
=& Tr(A^TC)Tr(\Lambda(1:L)C)+A_{i,j}jC_{i,j}-Tr(A^TC\Lambda(1:L)C)\\
=& Tr(\Lambda(1:L)C)Tr(A^TC)+Tr(\Lambda(1:L)A^TC-\Lambda(1:L)CA^TC)\\
\end{aligned}
$$
For the first part:
$$
\begin{aligned}
    [\hat{n}_m,P_m] =& \frac{1}{2}(-in_mc_{m+1}^\dagger c_m+in_mc_m^\dagger  c_{m+1})  \\ 
    & -\frac{1}{2}(-ic_{m+1}^\dagger c_mn_m+ic_m^\dagger  c_{m+1}n_m)  \\ 
    =& \frac{1}{2}(ic_m^\dagger  c_{m+1}+ic^\dagger_{m+1}c_m)  \\ 
    [\hat{n}_{m+1},P_m] =& \frac{1}{2}(-in_{m+1}c_{m+1}^\dagger c_m+in_{m+1}c_m^\dagger  c_{m+1})  \\ 
    & -\frac{1}{2}(-ic_{m+1}^\dagger c_mn_{m+1}+ic_m^\dagger  c_{m+1}n_{m+1})  \\ 
    =& \frac{1}{2}(-ic_{m+1}^\dagger  c_{m}-ic^\dagger_{m}c_{m+1}). \\ 
\end{aligned}
$$

So for OBC case:

$$
\begin{aligned}
    &\sum_{m=1}^{L-1}[m\langle \psi_t | P_m[\hat{n}_m,P_m]|\psi_t\rangle+ (m+1)\langle \psi_t | P_m[\hat{n}_{m+1},P_m]|\psi_t\rangle]\\
    =&-\frac{i}{2}\sum_{m=1}^{L-1}\langle \psi_t | P_m(c_{m+1}^\dagger  c_{m}+c^\dagger_{m}c_{m+1})|\psi_t\rangle\\
    =&-\frac{i}{4}\sum_{m=1}^{L-1}\langle \psi_t | (n_m+n_{m+1}-ic_{m+1}^\dagger c_m+ic_m^\dagger  c_{m+1})(c_{m+1}^\dagger  c_{m}+c^\dagger_{m}c_{m+1})|\psi_t\rangle\\
    =&-\frac{i}{4}\sum_{m=1}^{L-1}\langle \psi_t | (c_{m+1}^\dagger  c_{m}+in_m(1-n_{m+1}))|\psi_t\rangle\\
    &-\frac{i}{4}\sum_{m=1}^{L-1}\langle \psi_t | (c^\dagger_{m}c_{m+1}-in_{m+1}(1-n_{m}))|\psi_t\rangle\\
    =&-\frac{i}{4}\sum_{m=1}^{L-1}\langle \psi_t | (c_{m+1}^\dagger  c_{m}+c^\dagger_{m}c_{m+1}+in_m-in_{m+1})|\psi_t\rangle\\
\end{aligned}
$$


## Diffusion velocity
Then the velocity is:

$$
\begin{aligned}
\frac{d\overline{x}}{dt}=&\sum_{s=1}^{L}s \{ \langle \psi_t |(iH)\hat{n}_s|\psi_t\rangle dt\\
&+\gamma [\sum_{m}\langle \psi_t |(2\langle L_{m}\rangle L_{m}^{\dagger}-L_{m}^{\dagger}L_{m}-\langle L_{m}^{\dagger}\rangle\langle L_{m}\rangle)\hat{n}_s|\psi_t\rangle dt]\\
&+\langle \psi_t |\hat{n}_s(-iH)|\psi_t\rangle dt\\
&+\gamma [\sum_{m}\langle \psi_t |\hat{n}_s(2\langle L_{m}^{\dagger}\rangle L_{m}-L_{m}^{\dagger}L_{m}-\langle L_{m}^{\dagger}\rangle\langle L_{m}\rangle)|\psi_t\rangle dt]\\
&+2\gamma [\sum_m\langle \psi_t |(L_m^\dagger-\langle L_m^\dagger\rangle)\hat{n}_s(L_m-\langle L_m\rangle)|\psi_t\rangle]\}\\

=&\sum_{s=1}^{L}s \{ i\langle \psi_t |[H,\hat{n}_s]|\psi_t\rangle dt\\
&+\gamma \langle \psi_t |[\sum_m 2L_m^\dagger\hat{n}_sL_m-\{L_m^\dagger L_m,\hat{n}_s\}]|\psi_t\rangle\}\\

=&\sum_{s=1}^{L}s \{ i\langle \psi_t |(H_{eff}^\dagger \hat{n}_s-\hat{n}_sH_{eff})|\psi_t\rangle dt\\
&+\gamma \langle \psi_t |\sum_m 2L_m^\dagger\hat{n}_sL_m|\psi_t\rangle\}\\
\end{aligned}
$$
The last line exhibits a diffuse velocity.

Considering $L_i^\dagger \hat{n}_sL_i$:

$$
\begin{aligned}
P_i=&\frac{1}{2}(n_i+n_{i+1}-ic_{i+1}^\dagger c_i+ic_i^\dagger  c_{i+1})\\
L_i^\dagger \hat{n}_sL_i=&\frac{1}{4}（c^\dagger_{i}-ic^\dagger_{i+1}) (c_{i}+ic_{i+1})n_s (c^\dagger_{i}-ic^\dagger_{i+1}）(c_{i}+ic_{i+1})\\
=&\frac{1}{4}P_i(n_sn_i+n_sn_{i+1}-in_sc_{i+1}^\dagger c_i+in_sc_i^\dagger  c_{i+1})\\
=&\frac{1}{4}(n_sn_in_i+n_sn_in_{i+1}-\cancel{in_sn_ic_{i+1}^\dagger c_i}+in_sn_ic_i^\dagger  c_{i+1}\\
&+n_sn_{i+1}n_i+n_sn_{i+1}n_{i+1}-in_sn_{i+1}c_{i+1}^\dagger c_i+\cancel{in_sn_{i+1}c_i^\dagger  c_{i+1}}\\
&-ic_{i+1}^\dagger c_in_sn_i-\cancel{ic_{i+1}^\dagger c_in_sn_{i+1}}\\
&-\cancel{c_{i+1}^\dagger c_in_sc_{i+1}^\dagger c_i}+c_{i+1}^\dagger c_in_sc_i^\dagger  c_{i+1}\\
&+\cancel{ic_{i}^\dagger c_{i+1}n_sn_i}+ic_{i}^\dagger c_{i+1}n_sn_{i+1}\\
&+c_{i}^\dagger c_{i+1}n_sc_{i+1}^\dagger c_i-\cancel{c_{i}^\dagger c_{i+1}n_sc_i^\dagger  c_{i+1}})\\
=&\frac{1}{4}(n_s(n_i+n_{i+1})+2n_sn_in_{i+1}\\
&+in_sc_i^\dagger  c_{i+1}-in_sc_{i+1}^\dagger c_i-ic_{i+1}^\dagger c_in_s+ic_{i}^\dagger c_{i+1}n_s\\
&+c_{i}^\dagger c_{i+1}n_sc_{i+1}^\dagger c_i+c_{i+1}^\dagger c_in_sc_i^\dagger  c_{i+1})\\
\end{aligned}
$$

For the last line:

$$
\begin{aligned}
&c_{i}^\dagger c_{i+1}c_s^\dagger c_sc_{i+1}^\dagger c_i \\
=& c_{i}^\dagger c_{i+1}c_s^\dagger (\delta_{s,i+1}-c_{i+1}^\dagger c_s) c_i\\
=&\delta_{s,i+1}c_{i}^\dagger c_{i+1} c_s^\dagger c_i-c_{i}^\dagger c_{i+1}c_{i+1}^\dagger c_s^\dagger c_i c_s\\
=&\delta_{s,i+1}c_{i}^\dagger c_{i+1} c_s^\dagger c_i-\delta_{si}c_{i}^\dagger c_{i+1}c_{i+1}^\dagger c_s+c_{i}^\dagger c_{i+1}c_{i+1}^\dagger c_i n_s\\
=&(\delta_{s,i+1}-\delta_{s,i})n_{i} (1-n_{i+1})+n_{i} (1-n_{i+1}) n_s\\
\end{aligned}
$$

$$
\begin{aligned}
   & c_{i+1}^\dagger c_ic_s^\dagger c_sc_i^\dagger  c_{i+1}\\
   =&c_{i+1}^\dagger c_ic_s^\dagger (\delta_{i,s}-c_i^\dagger c_s)  c_{i+1}\\
   =&\delta_{i,s}c_{i+1}^\dagger c_ic_s^\dagger c_{i+1}-c_{i+1}^\dagger c_ic_i^\dagger c_s^\dagger c_{i+1}c_s\\
   =&\delta_{i,s}c_{i+1}^\dagger c_ic_s^\dagger c_{i+1}-\delta_{s,i+1}c_{i+1}^\dagger c_ic_i^\dagger c_s+c_{i+1}^\dagger c_ic_i^\dagger c_{i+1} n_s\\
   =&(\delta_{i,s}-\delta_{i+1,s})n_{i+1}(1-n_i) +n_{i+1}(1-n_i) n_s\\
\end{aligned}
$$

$$
\begin{aligned}
&c_{i}^\dagger c_{i+1}c_s^\dagger c_sc_{i+1}^\dagger c_i+c_{i+1}^\dagger c_ic_s^\dagger c_sc_i^\dagger  c_{i+1} \\
=& (\delta_{i,s}-\delta_{i+1,s})(n_{i+1}-n_i )+(n_i+n_{i+1}-2n_{i+1}n_i) n_s
\end{aligned}
$$

Now, it becomes:

$$
\begin{aligned}
    &\frac{1}{4}(2n_s(n_i+n_{i+1})\\
&+in_sc_i^\dagger  c_{i+1}+ic_{i}^\dagger c_{i+1}n_s-in_sc_{i+1}^\dagger c_i-ic_{i+1}^\dagger c_in_s\\
&(\delta_{i,s}-\delta_{i+1,s})(n_{i+1}-n_i ))\\

\end{aligned}
$$

 For $s=i,i+1$:

$$
\begin{aligned}
    &\frac{1}{4}(2n_in_{i+1}+n_i+n_{i+1}+ic_i^\dagger  c_{i+1}-ic_{i+1}^\dagger c_i)\\
    =&\frac{1}{4}(2C_{i,i}C_{i+1,i+1}-2C_{i,i+1}C_{i+1,i}\\
    &+C_{ii}+C_{i+1,i+1}+iC_{i,i+1}-iC_{i+1,i})
\end{aligned}
 $$

 else:

$$
\begin{aligned}
    &\frac{1}{4}(2n_s(n_i+n_{i+1})+i2n_sc_i^\dagger  c_{i+1}-i2n_sc_{i+1}^\dagger c_i)\\
=&\frac{1}{2}(\langle n_s\rangle \langle n_i+n_{i+1}\rangle-|\langle c_s^\dagger c_i \rangle|^2-|\langle c_s^\dagger c_{i+1} \rangle|^2\\
&+i\langle n_s\rangle \langle c_i^\dagger  c_{i+1}\rangle-i\langle c_s^\dagger c_{i+1}\rangle\langle c_i^\dagger c_s\rangle\\
&-i\langle n_s\rangle \langle c_{i+1}^\dagger c_i\rangle+i\langle c_s^\dagger c_{i}\rangle\langle c_{i+1}^\dagger c_s\rangle)
\end{aligned}
 $$

From Wick's Theorem:

$$
\begin{aligned}
\langle a_i^\dagger a_{j} a_k^\dagger a_l\rangle =& \langle a_i^\dagger a_j\rangle\langle a_k^\dagger a_l\rangle+\langle a_i^\dagger a_l\rangle(\delta_{kj}-\langle a_k^\dagger a_j\rangle)\\
\langle c_s^\dagger c_{s} c_{i+1}^\dagger c_{i+1}\rangle =& \langle n_s\rangle\langle n_{i+1}\rangle+\langle c_s^\dagger c_{i+1}\rangle(-\langle c_{i+1}^\dagger c_s\rangle)\\
\langle c_s^\dagger c_{s} c_i^\dagger c_{i+1}\rangle =& \langle c_s^\dagger c_s\rangle\langle c_{i}^\dagger c_{i+1}\rangle+\langle c_s^\dagger c_{i+1}\rangle(\delta_{si}-\langle c_i^\dagger c_s\rangle)\\
\langle c_s^\dagger c_{s} c_{i+1}^\dagger c_{i}\rangle =& \langle c_s^\dagger c_s\rangle\langle c_{i+1}^\dagger c_{i}\rangle+\langle c_s^\dagger c_{i}\rangle(\delta_{s,i+1}-\langle c_{i+1}^\dagger c_s\rangle)\\
\end{aligned}
$$


 
<!-- $$
    L_i=e^{i\theta n_{i+1}}\frac{1}{2}（c^\dagger_{i}-ic^\dagger_{i+1}）(c_{i}+ic_{i+1})e^{-i\theta n_{i+1}}e^{i\theta n_{i+1}}
$$

$$

    e^{i\theta n_{i+1}}c_ie^{-i\theta n_{i+1}}&=c_i\\
    e^{i\theta n_{i+1}}c_i^\dagger e^{-i\theta n_{i+1}}&=c_i^\dagger\\
    e^{i\theta n_{i+1}}c_{i+1}e^{-i\theta n_{i+1}}&=e^{-i\theta}c_{i+1}\\
    e^{i\theta n_{i+1}}c_i^\dagger e^{-i\theta n_{i+1}}&=e^{i\theta}c_{i+1}^\dagger\\
\end{aligned}
$$

So

$$
\begin{aligned}
L_i &= \frac{1}{2}（c^\dagger_{i}-ie^{i\theta}c^\dagger_{i+1}）(c_{i}+ie^{-i\theta}c_{i+1})e^{i\theta n_{i+1}}\\
L_i^\dagger &= \frac{1}{2}e^{-i\theta n_{i+1}}（c^\dagger_{i}-ie^{i\theta}c^\dagger_{i+1}）(c_{i}+ie^{-i\theta}c_{i+1})\\
L_i L_i^\dagger&=\frac{1}{2}（c^\dagger_{i}-ie^{i\theta}c^\dagger_{i+1}）(c_{i}+ie^{-i\theta}c_{i+1})
\end{aligned}
$$ -->