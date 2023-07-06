

### 1. Entanglement Entropy
Let the Hilbert space of the system be a direct product:

$$
\mathcal{H} =\mathcal{H}_A\otimes \mathcal{H}_B,
$$

where $A$ and $B$ are two subsystems. The reduced density matrix of $A$ is $\rho_A=\mathrm{Tr}_B \rho$

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
 
where the states $\otimes |\{\phi_x\}\rangle = |\prod_x\{\phi_x\}\rangle$ form a basis. The following diagram is a graph description of the reduced density matrix.

![Density](density.png)

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

The connected manifold here is called Riemann surface $\mathcal{R}_{3,1}$, 3 means there are 3 sheets, 1 means there is only 1 cut. 

Formally, the $\mathrm{Tr}\rho_A^n$ is now expressed as:
 $$\mathrm{Tr}\rho_A^n=\frac{Z_n(A)}{Z^n}$$

### 3. CFT

Now we are going to use CFT to do the calculation. Specifically, we want to relate the $\mathrm{Tr}\rho_A^n$ to the expecation value of some primary fields in CFT. 

CFT has predicted the scaling behavior of that expectation value. So, after determining the scaling dimension of the operators, the Rényi entropy could be calculated directly, as well as the von Neumann entropy.

### 4. Twist fields

Now, suppose that we are dealing with free bosonic theory, in which only terms like $\phi^2$ and $(\partial \phi)^2$ exist. The action of $\mathcal{L}_n(\phi_1,\phi_2,...,\phi_n)$ is $\mathcal{L}(\phi_1)+\mathcal{L}(\phi_2)+...+\mathcal{L}(\phi_n)$. The difficulty in calculating the integral is the boundary condition $\phi_j(x,\beta^-)=\phi_{j+1}(x,0^+),\quad x\in [u,v]$. We will decouple the fields by Fourier transformation, with the cost of introducing the so-called "twist fields".

We note that there is a symmetry in the original theory: if we change the label of $\phi_j$ to $\phi_{j+1}$, the action stays unchanged. 

Now we define the twsit operators: 

$$
\begin{aligned}
T_n &\equiv T_\sigma, &\sigma:& i\to i+1\mod n\\
\tilde{T}_n &\equiv T_{\sigma^{-1}}, &\sigma^{-1}:& i\to i-1\mod n\\
\end{aligned}
$$

These operators encodes the boudary conditions, the partition function is proportional to $\langle T_n(u)\tilde{T}_n(v) \rangle_C$. The benefit is that, after introducing such a field, we could calculate the correlation function on a complex plane.

Further, if an operator $O(x,\tau;i)$ is defined on the $i^{th}$ sheet, the correlation function is:

$$
\langle  O(x,\tau;i)\rangle_{\mathcal{R}_{n,1}}=\frac{\langle T_n(u)\tilde{T}_n(v)O_i(x,\tau)\rangle_C}{\langle T_n(u)\tilde{T}_n(v) \rangle_C}
$$

$O_i(x,\tau)$ is the field coming from the $i^{th}$ copy of the original theory.

You may not sure why the operators coudl be viewed as "fields", I will give a brief explanation below.

### 5. Clarifying the role of twist operators

Considering the Fourier transform:

$$
\tilde{\phi}_k = \sum_{j=1}^n e^{2\pi i \frac{k}{n}j}\phi_j, \quad k=0,1...,n-1.
$$

The original action is now

$$
\mathcal{L}=\mathcal{L}(\tilde{\phi}_1)+\mathcal{L}(\tilde{\phi}_2)+...+\mathcal{L}(\tilde{\phi}_n).
$$

It seems to be unchanged under this transformation. Let's look at the boundary condition. 

$$
\begin{aligned}
\tilde{\phi}_k(x,\beta^-) =& \sum_{j=1}^n e^{2\pi i \frac{k}{n}j}\phi_j(x,\beta^-)\\
=&\sum_{j=1}^n e^{2\pi i \frac{k}{n}j}\phi_{j+1}(x,0^+)\\
=&e^{-2\pi i \frac{k}{n}}\sum_{j=1}^n e^{2\pi i \frac{k}{n}(j+1)}\phi_{j+1}(x,0^+)\\
=&e^{-2\pi i \frac{k}{n}}\tilde{\phi}_k(x,0^+)
\end{aligned}
$$

This phase factor could be viewed as the conribution from a gauge field at the point $(u,0)$. There is another gauge field at $(v,0)$ which contributes a phase factor of $e^{2\pi i \frac{k}{n}}$.

By gauge tranformation, terms like $\bar{\phi}\gamma^\mu iA_\mu \phi$ appear in the action. Finally, the partition function could be written as:

$$
\begin{aligned}
Z_n=&\prod_{k=1}^n Z_k\\
Z_k=&\langle e^{i\int A^k_\mu j^\mu_kd^2x}\rangle 
\end{aligned}
$$

Twist operators is diagonal under the $\{\tilde{\phi_k}\}$ basis. Thus we could write $T_n=T_{n,1}T_{n,2}...T_{n,n}$, and 

$$
\begin{aligned}
    T_{n,k}\tilde{\phi}_k =& e^{2\pi ik/n}\tilde{\phi}_k\\
    T_{n,k}\tilde{\phi}_{k^\prime} =& \tilde{\phi}_{k^\prime}\\
\end{aligned}
$$

In this decomposition, $Z_k$ could be written as $\langle T_{n,k}(u,0) \tilde{T}_{n,k}(v,0) \rangle$. Now, we could use CFT to predcit the scaling of this expecation value.

It's important to clarify the monifold we are dealing with. Before introducing twsit fields, we are doing integration on Riemann surface, after decoupling the fields with twsit fields, each $Z_k$ is on its own complex plane. 

### 6. Calculation in CFT

Considering a complex plane, whose complex coordinate is $w=x+i\tau$, we perform a comformal mapping $z\to \left [\frac{w-u}{w-v} \right ]^{\frac{1}{n}}$. This transformation maps $u$ to original point, $v$ to infinity, and folds the Riemann surface into a complex plane.

In CFT, the transformation of a stress tensor is

$$
T(w)=(\frac{dz}{dw})^2T(z)+\frac{c}{12}\{z,w\},
$$

where $\{z,w\}=(z^{\prime\prime\prime}z^\prime-\frac{3}{2}z^{\prime\prime})/{z^{\prime}}^2$ is the Schwarzian derivative.

Taking the expectation value on boh sides, and using $\langle T(z)\rangle_C=0$, we could get
$$
\langle T(z)\rangle_{\mathcal{R}_{n,1}}=\frac{c}{12}\{z,w\}=\frac{c(1-n^{-2})}{24}\frac{(v-u)^2}{(w-u)^2(w-v)^2}.
$$

From above, this is equal to 

$$
\frac{\langle T_n(u)\tilde{T}_n(v)T(z)\rangle_C}{\langle T_n(u)\tilde{T}_n(v) \rangle_C}.
$$

Using conformal Ward identity, we get

$$
\langle T_n(u)\tilde{T}_n(v)T(z)\rangle_C=(\frac{1}{w-u}\frac{\partial}{\partial u}+\frac{h_{T_n}}{(w-u)^2} +\frac{1}{w-v}\frac{\partial}{\partial v}+\frac{h_{\tilde{T}_n}}{(w-v)^2})\langle T_n(u)\tilde{T}_n(v) \rangle_C.
$$

Suppose $\langle T_n(u)\tilde{T}_n(v) \rangle_C\propto |u-v|^{-2\Delta_n}$. Put it into the formula above, and comparing with the $\langle T(z)\rangle_{\mathcal{R}_{n,1}}$, we get

$$
\begin{aligned}
     & \frac{c(1-n^{-2})}{24}\frac{(v-u)^2}{(w-u)^2(w-v)^2}\\
    =& \frac{-\Delta_n}{(w-u)(u-v)}+\frac{\Delta_n}{(w-v)(u-v)}+\frac{h_n}{(w-u)^2}+\frac{\bar{h}_n}{(w-v)^2}\\
    =& \frac{\Delta_n(u-v)}{(w-u)(w-v)(u-v)}+\frac{h_n}{(w-u)^2}+\frac{\bar{h}_n}{(w-v)^2}\\
    =& \frac{\Delta_n(w-v)(w-u)+h_n(w-v)^2+\bar{h}_n(w-u)^2}{(w-u)^2(w-v)^2}\\
    &\text{Let}\ \Delta_n=2h_n=2\bar{h}_n.\\
    =& h_n\frac{\left [ (w-v)-(w-u)\right ]^2}{(w-u)^2(w-v)^2}= h_n\frac{(u-v)^2}{(w-u)^2(w-v)^2}.\\
\end{aligned}
$$

So,

$$
\begin{aligned}
    \Delta_n =& \frac{c(1-n^{-2})}{12}\\
    Z_n(A) \propto & |u-v|^{-\frac{c(n^2-1)}{6n}}.
\end{aligned}
$$

We could expect that,

$$
\mathrm{Tr}\rho_A^n=c_n \left (\frac{v-u}{a}\right)^{-c(n-1/n)/6},
$$

where $a$ is the cut-off, $c_n$ is a constant which could not be determined here, but $c_1$ should be 0.

Take it into the Rényi entropy formula:

$$S_A^{(n)}=\frac{-c(n-1/n)\log((v-u)/a)}{6(1-n)}+c_n^\prime,$$

where $c_n^\prime\equiv\frac{\log c_n}{1-n}$.

When $n$ approaches 1, we get

$$S_A = \frac{c}{3}\log(\frac{v-u}{a})+c_1^\prime.$$

## 2. Introduction to conformal field theory

A conformal field theory(CFT) is a field theory which is invariant under conformal transformations. 

### 2.1. Conformal transformations

Considering a line element
$ds^2=g_{\mu\nu}dx^\mu dx^\nu$, $g_{\mu\nu}(x)\to g_{\mu\nu}^\prime(x^\prime)=\frac{\partial x^\alpha}{\partial x^{\prime\mu}}\frac{\partial x^\beta}{\partial x^{\prime\nu}}g_{\alpha\beta}(x)$ under the transformation of $x\to x^\prime$.

A conformal tranformation of coordinates is an invertible mapping $x \to x^\prime$, leaving the metric tensor invariant up to a scale:

$$g^\prime_{\mu\nu}(x^\prime)=\Lambda(x)g_{\mu\nu}(x).$$

Why we call it conformal? You will find that this constraints keeps the angle($vw/(v^2w^2)^{1/2}$) between the vectors $v$ and $w$, where $vw = g_{\mu\nu}v^\mu w^\nu$.

If we considering the infinitesimal coordinate transformation $x^\mu\to x^\mu+\epsilon^\mu$, the line element changes as 

$$
\begin{aligned}
    ds^2\to& (dx^\mu+d\epsilon^\mu)g_{\mu\nu}(dx^\nu+d\epsilon^\nu)\\
    =&ds^2+d\epsilon_\nu dx^\nu+d\epsilon_\mu dx^\mu\\
    =&ds^2+d\epsilon_\nu dx^\nu+d\epsilon_\mu dx^\mu\\
    =&ds^2+\partial_\mu\epsilon_\nu dx^\mu dx^\nu+\partial_\nu\epsilon_\mu dx^\nu dx^\mu\\
    =&ds^2+(\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu )dx^\mu dx^\nu\\
\end{aligned}
$$

We need the second part to be proportinal to $g_{\mu\nu}$, so

$$(\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu )=f(x)g_{\mu\nu}.$$

Contract the stress tensor by multiplying $g^{\mu\nu}$:

$$
\begin{aligned}
    g^{\mu\nu}(\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu )&=f(x)g_{\mu\nu}g^{\mu\nu}\\
    (\partial_\mu\epsilon^\mu+\partial_\mu\epsilon^\mu )&=f(x)d\\
    f(x)=&\frac{2}{d}(\partial_\mu  \epsilon^\mu)\\
    (\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu )=&\frac{2}{d}(\partial_\mu  \epsilon^\mu)g_{\mu\nu}.\\
\end{aligned}
$$

If taking derivative on both side, we will find the third derivative of $\epsilon$ is 0, this directly(may be not that directly) produces the conformal group for $d>2$.

Here, we only care about the case when $d=2$ and $g_{\mu\nu}=\delta_{\mu\nu}$.

The constraints now becomes

$$
\begin{aligned}
    \partial_1\epsilon_1=&\partial_2 \epsilon_2\\
    \partial_1\epsilon_2=&-\partial_2 \epsilon_1.\\
\end{aligned}
$$

This is exactly the Cauchy-Riemann equation. It's then natually to use complex coordinates, and the infinitesimal tramsformation is analytic around $x$.

Suppose the 2-D coordinate conformal transformations is 

$$
z\to f(z),\quad \bar{z}\to\bar{f}(\bar{z}),
$$

then the line element is

$$ds^2=dzd\bar{z}\to \left | \frac{\partial f}{\partial z}\right |^2dzd\bar{z}.$$

We could find a basis for the transformations, the corresponding infinitesinal generators are verified to satisfy the Witt algebra. 

In the quantum case, the algebra will be "central extended" to Virasoro algebra, it will get a new constant term proportional to the so-called central charge c.

However, the algebra above is called local conformal algebra, because it may not be well defined and invertible goblally on Riemann sphere $S^2$. Take that into consideration, we will find the allowed global transformation is 

$$
z\to \frac{az+b}{cz+d},\quad \bar{z}\to \frac{\bar{a}\bar{z}+\bar{b}}{\bar{c}\bar{z}+\bar{d}}.
$$
 composition of transformation corresponding to matrix transformation 

### 2.2. Primary fields and its OPE
Deifine a theory with conformal invariance to satisfy some straight for ward properties:


By translational invariance, N-point functions only depend on $x_i-x_j$, by rotational invariance the, they only depend on $|x_i-x_j|$, by special conformal transformation, cross ratio is invariant 
### 2.3. Stress tensor and its OPE


