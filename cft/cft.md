

### 1. Entanglement Entropy
Let the Hilbert space of the system be a direct product:

$$
\mathcal{H} =\mathcal{H}_A\otimes \mathcal{H}_B,
$$

where $A$ and $B$ are two subsystems. The reduced density matrix of $A$ is $\rho_A=\mathrm{Tr}_B \rho $

The Entanglement Entropy(EE) we refer to is von Neumann entropy:
$$
S_A = \mathrm{Tr} \rho_A\ln \rho_A
$$

However, this quantity is hard to calculate directly. Here, we define nth the Rényi entropy:

$$
S^{(n)}_A = \frac{1}{1-n} \ln \mathrm{Tr} \rho_A^n.
$$

When taking the limit $n\to 1$, $S_A$ is recovered.

Here is a simple proof. Suppose that the reduced density matrix could be decomposed as $\rho_A = U\Lambda U^\dagger$, then
$$
\begin{aligned}
    \lim_{n\to1}S_A^{(n)}=&-\lim_{n\to1}\frac{1}{n-1}\ln \mathrm{Tr} \Lambda^n \\
    =&-\lim_{n\to1}\frac{\sum_i e^{n\ln \lambda_i}\ln \lambda_i}{\mathrm{Tr} \Lambda^n}\\
    =&-\sum_i\lambda_i \ln \lambda_i=S_A
\end{aligned}
$$

### 2. Path integral formulation

Now we want to calculate the Rényi entropy in path integral formulism. The first thing we should do is convert the reduced density matrix to path integral form.

Actually, we have met the form before. In statistical mechanics, the partition fucntion is $Z=\mathrm{Tr} e^{-\beta H}$, and the density matrix is $\rho=e^{-\beta H}/Z$. In path integral folmulation, 
$$Z=\int d\phi_0 d\phi_1..d\phi_N \exp\{-S\left[\phi\right ]\},$$
under the condition of $\phi_0=\phi_N$ for bosonic fields.
 This condition could be viewed as taking trace, as $\mathrm{Tr \hat{A}}=\sum_{i,j} \delta_{i,j}\langle i |\hat{A}|j \rangle$. 

 Thus, in the continuum limit, the density matrix could be expressed as:
 $$
 \begin{aligned}
     \rho_A(\{\phi_x\}|\{\phi^\prime _{x^\prime}\})=&Z^{-1}\int D\phi(y,\tau) \\
     &\prod_x \delta(\phi(y,0)-\phi^\prime _{x^\prime})\\
     &\prod_x \delta(\phi(y,\beta)-\phi_x)e^{-S_E},\\
 \end{aligned}
$$
 
where the states $\otimes |\{\phi_x\}\rangle = |\prod_x\{\phi_x\}\rangle$ form a basis.  

What about $\rho_A^n$? Comparing to the discrete version:

$$
\begin{aligned}
    \langle i_1 |\hat{A}^n|j_n\rangle=& \sum_{j_1;i_2,j_2...;i_n}\delta_{j_1,i_2}\delta_{j_2,i_3}..\delta_{j_{n-1},i_n}\\
    &\langle i_1 |\hat{A}|j_1\rangle\langle i_2 |\hat{A}|j_2\rangle...\langle i_n |\hat{A}|j_n\rangle,
\end{aligned}
$$

we find that the only trick is to "sewing" the boundary fields between each density matrix.  This trick is the so-called *replica trick*, i.e. make n copies of the reduced density matrix, label the fields by $1,2..., n$, then sew them along the boundary: $\phi_j(x,\beta^-)=\phi_{j+1}(x,0^+)$ where $n+1\equiv 1$, owing to the fact that we are taking the trace. 

The graph description of $\mathrm{Tr}\rho_A^3$ is shown below:

![Replica](replica.png)

The connected manifold here is called Riemann surface $R_{3,1}$, 3 means there are 3 sheets, 1 means there is only 1 cut. 

Formally, the $\mathrm{Tr}\rho_A^n$ is now expressed as:
 $$\mathrm{Tr}\rho_A^n=\frac{Z_n(A)}{Z^n}$$

### 3. CFT

Now we are going to use CFT to do the calculation. Specifically, we want to relate the $\mathrm{Tr}\rho_A^n$ to the expecation value of some primary fields in CFT. CFT has predicted the scaling behavior of that expectation value. So, after determining the scaling dimension of the operators, the Rényi entropy could be calculated directly, as well as the von Neumann entropy.




