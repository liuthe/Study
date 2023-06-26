

### RG

Now, let's begin at the action:
$$
S=\int \frac{1}{2}\left [ (\nabla\phi)^2 +y\Lambda^2 \cos \beta \phi \right ]d^2x
$$
$\Lambda$ is the momentum cutoff.

Split $\phi$ into fast and slow mode:
$$
\phi = \phi_s+\phi_f\equiv \phi(0\le k\le \Lambda(1-dt))+\phi( \Lambda(1-dt)\le k \le \Lambda)
$$

The free action now becomes:

$$
S_0 =\int \frac{1}{2}\left [(\nabla \phi_s)^2+ (\nabla \phi_f)^2\right ]d^2x
$$

The cross term is zero:

$$
\begin{aligned}
    &\int d^2x \partial_i \phi_s \partial_i \phi_f\\
   =&\int d^2x k_1^{i}k_2^{i} \int_{0\le k\le \Lambda(1-dt)} d^2k_1 \phi_k e^{ik_1x} \int_{\Lambda(1-dt)\le k \le \Lambda} d^2k_2 \phi_k e^{ik_2x}\\
   =& k_1^{i}k_2^{i} \int_{0\le k\le \Lambda(1-dt)} d^2k_1 \phi_{k_1}  \int_{\Lambda(1-dt)\le k \le \Lambda} d^2k_2 \phi_{k_2}\delta(k_1+k_2) \\
   =&0
\end{aligned}
$$

Now we introduce the interaction, integrate out  \phi_{\mathrm{f}}  as usual, and see happens to the coupling  y  of the slow modes that remain. Here is the abridged analysis:
$$
\begin{aligned}
Z & =\int d \phi_{\mathrm{s}} \int d \phi_{\mathrm{f}} \exp \left[-\int\left[\frac{1}{2}\left(\nabla \phi_{\mathrm{s}}\right)^{2}+\frac{1}{2}\left(\nabla \phi_{\mathrm{f}}\right)^{2}\right] d^{2} x-\frac{y \Lambda^{2}}{2} \int d^{2} x \cos \beta\left(\phi_{\mathrm{s}}+\phi_{\mathrm{f}}\right)\right] \\
& =\int d \phi_{\mathrm{s}} \exp \left[-\int \frac{1}{2}\left(\nabla \phi_{\mathrm{s}}\right)^{2} d^{2} x\right]\left\langle\exp \left[-\frac{y \Lambda^{2}}{2} \int d^{2} x \cos \beta\left(\phi_{\mathrm{s}}+\phi_{\mathrm{f}}\right)\right]\right\rangle_{\mathrm{f}} \\
& \simeq \int d \phi_{\mathrm{s}} \exp \left[-\int\left(\frac{1}{2}\left(\nabla \phi_{\mathrm{s}}\right)^{2}+\frac{y \Lambda^{2}}{2} \cos \beta \phi_{\mathrm{s}}\left\langle\cos \beta \phi_{\mathrm{f}}\right\rangle_{\mathrm{f}}\right) d^{2} x\right],
\end{aligned}
$$
where  $\langle\cdots\rangle_{\mathrm{f}}$  is the average over fast modes and we are using the leading term in the cumulant expansion  $\left(\left\langle e^{A}\right\rangle \simeq e^{\langle A\rangle}\right)$(Higher order analysis in in Nagaosa's book) ; the  $\sin \beta \phi_{\mathrm{s}} \sin \beta \phi_{\mathrm{f}}$  term is ignored because it has zero average over fast modes. The average  $\langle\cdots\rangle_{\mathrm{r}}$  above is only over the sliver of width  $\Lambda d t$ .
To perform the average we first set $A=i \beta \phi, B=0$  in 

$e^A e^B = :e^{A+B}:e^{\left\langle AB+ \frac{A^2+B^2}{2}\right\rangle}$

 to deduce that
$$
\left\langle e^{i \beta \phi}\right\rangle=e^{-\frac{1}{2} \beta^{2}\left\langle\phi^{2}\right\rangle}
$$
Using this result, we find that
$$
\begin{aligned}
\left\langle\cos \left(\beta \phi_{\mathrm{f}}\right)\right\rangle & =e^{-\frac{1}{2} \beta^{2}\left\langle\phi_{\mathrm{f}}^{2}\right\rangle} \\
& =\exp \left[-\frac{\beta^{2}}{2} \int_{\Lambda(1-d t)}^{\Lambda} \frac{k d k d \theta}{4 \pi^{2}} \frac{1}{k^{2}}\right] \\
& =\exp \left[-\frac{\beta^{2}}{4\pi} \int_{\Lambda(1-d t)}^{\Lambda}  \frac{d k}{k}\right] \\
& =(1-dt)^\frac{\beta^2}{4\pi}=1-\frac{\beta^{2}}{4 \pi} d t .
\end{aligned}
$$
The second equation is derived below:

$$
\begin{aligned}
    \left\langle\phi_{\mathrm{f}}^{2}\right\rangle =&\int  \frac{d^2k_1}{(2\pi)^2}\frac{d^2k_2}{(2\pi)^2}e^{i(k_1+k_2)x}\int D\phi_f\phi_{k_1}\phi_{k_2}\\
    &exp\left [-\int \frac{1}{2}k^2(\phi_k \phi_{-k})^2\frac{d^2k}{(2\pi)^2} \right] \\
     =&\int \frac{d^2k_1}{(2\pi)^2}d^2k_2\frac{\delta(k_1+k_2)}{k_1^2} \\
     =&\int_{\Lambda(1-dt)}^{\Lambda}\int_0^{2\pi}\frac{d^2k}{4\pi^2}\frac{1}{k^2} 
\end{aligned}
$$
Now we rescale the coordinates,
$$
\begin{aligned}
    dk &= (1-dt)dk^{\prime}\\
    dx &= (1+dt)dx^{\prime}\\
d^{2} x&=(1+2 d t) d^{2} x^{\prime}
\end{aligned}
$$
to obtain (on dropping primes)
$$
\begin{aligned}
\frac{y \Lambda^{2}}{2} \int d^{2} x \cos \beta \phi & \rightarrow \frac{y \Lambda^{2}}{2}\left(1+\left(2-\frac{\beta^{2}}{4 \pi}\right) d t\right) \int d^{2} x \cos \beta \phi, \\
\frac{d y}{d t} & =\left[2-\frac{\beta^{2}}{4 \pi}\right] y \\
& =(2-4 K) y \text { because } \\
\beta^{2} & =16 \pi K \text { in the Luttinger model. }
\end{aligned}
$$
Remember that, we need to keep free field terms invariant, in $D=2$, this means the field has zero scaling dimension.

Thus, we find that the interaction term(umklapp term) is
$$
\begin{array}{l} 
\text { irrelevant for } K>\frac{1}{2} \text { or } \beta^{2}>8 \pi, \\
\text { relevant for } K<\frac{1}{2} \text { or } \beta^{2}<8 \pi .
\end{array}
$$
We rescaled  $x$  but not  $\Lambda$ , which just stood there. 




