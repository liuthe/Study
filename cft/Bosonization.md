I will doing bosonization on a 1D lattice model

# Discrete model
$$
\begin{aligned}
    H=& H_0+H_{int}\\
    H_0=&-\frac{1}{2}\sum_n \psi_{n+1}^\dagger \psi_n+\psi_{n}^\dagger \psi_{n+1}\\
    H_{\mathrm{I}} = &\Delta \sum_n (\psi_n^\dagger \psi_n -\frac{1}{2})(\psi_{n+1}^\dagger \psi_{n+1} -\frac{1}{2})
\end{aligned}
$$
## Linear spectrum
Doing linearization around two Femi points:

$$
\begin{aligned}
\psi(j) & =\int_{-\pi}^{\pi} \psi(K) e^{i K j} \frac{d K}{2 \pi} \\
& \simeq \int_{-\Lambda}^{\Lambda} \psi\left(K_{\mathrm{F}}+k\right) e^{i K_{\mathrm{F}} j} e^{i k j} \frac{d k}{2 \pi}+\int_{-\Lambda}^{\Lambda} \psi\left(-K_{\mathrm{F}}+k\right) e^{-i K_{\mathrm{F}} j} e^{i k j} \frac{d k}{2 \pi} \\
& \equiv a^{\frac{1}{2}}\left[e^{i K_{\mathrm{F}} j} \psi_{+}(x=a j)+e^{-i K_{\mathrm{F}} j} \psi_{-}(x=a j)\right] \\
& =a^{\frac{1}{2}}\left[e^{i \frac{\pi}{2} j} \psi_{+}(x)+e^{-i \frac{\pi}{2} j} \psi_{-}(x)\right] \text { since } K_{\mathrm{F}}=\frac{\pi}{2} \text { here. }
\end{aligned}
$$

## Continuous form
Now, The Hamiltonian becomes:

$$
\begin{aligned}
    H_0 = & -\frac{1}{2} a \sum_{j}\left[-i e^{-i \frac{\pi}{2} j} \psi_{+}^{\dagger}(x=j a+a)+i e^{i \frac{\pi}{2} j} \psi_{-}^{\dagger}(x=j a+a)\right] \\
& \times\left[e^{i \frac{\pi}{2} j} \psi_{+}(x=j a)+e^{-i \frac{\pi}{2} j} \psi_{-}(x=j a)\right]+\text { h.c. } \\
= & \frac{a}{2} \sum_{j}\left[i \psi_{+}^{\dagger}(x) \psi_{+}(x)-i \psi_{-}^{\dagger}(x) \psi_{-}(x)+i a \frac{\partial \psi_{+}^{\dagger}(x)}{\partial x} \psi_{+}(x)-i a \frac{\partial \psi_{-}^{\dagger}(x)}{\partial x} \psi_{-}(x)\right] \\
& + \text { h.c. }+ \text { ignorable terms and terms oscillating at } \pm 2 K_{\mathrm{F}}, \\
H_{0 c}= & \frac{H_{0}}{a}=\int d x\left[\psi_{+}^{\dagger}(x)\left(-i \partial_{x}\right) \psi_{+}(x)+\psi_{-}^{\dagger}(x)\left(i \partial_{x}\right) \psi_{-}(x)\right],

\end{aligned}
$$

When considering half filling case:

$$
\psi_j^\dagger\psi_j-\frac{1}{2} = :\psi_j^\dagger\psi_j:
$$

$$
\begin{aligned}
H_{\mathrm{Ic}}= & \frac{H_{\mathrm{I}}}{a} \\
= & a \Delta \sum_j\left[: \psi_{+}^{\dagger}(x) \psi_{+}(x)+\psi_{-}^{\dagger}(x) \psi_{-}:+(-1)^j\left(\psi_{+}^{\dagger}(x) \psi_{-}(x)+\psi_{-}^{\dagger}(x) \psi_{+}(x)\right)\right] \\
& \times\left[: \psi_{+}^{\dagger}(x) \psi_{+}(x)+\psi_{-}^{\dagger}(x) \psi_{-}(x):-(-1)^j\left(\psi_{+}^{\dagger}(x) \psi_{-}(x)+\psi_{-}^{\dagger}(x) \psi_{+}(x)\right)\right] \\
\end{aligned}
$$


# Bosonization

Now doing bosonization:

$$
\begin{aligned}
    \psi_{\pm}(x) = &\frac{1}{\sqrt{2\pi\alpha }}e^{\pm i\sqrt{4\pi}\phi_{\pm}(x)}\\
    \phi_{\pm}(x)=&\frac{1}{2}[\phi(x)\mp \int_{-\infin}^x \Pi(x^\prime)dx^\prime]\\
    [\phi(x),\Pi(y)]=&i\delta(x-y)
\end{aligned}
$$

$\alpha$ is a moment cutoff here, its meaning is shown below.

$$
\phi_\pm(x) = \pm \int_0^{\pm \infty}\frac{dp}{2\pi \sqrt{2|p|}}[e^{ipx}\phi(p)+h.c.]e^{-\frac{1}{2}\alpha|p|}
$$
## Some useful relations
### Fourier transformation
$$
\begin{array}{l}
\begin{array}{l}
\phi(x)=\int_{-\infty}^{\infty} \frac{d p}{2 \pi \sqrt{2|p|}}\left[\phi(p) e^{i p x}+\phi^{\dagger}(p) e^{-i p x}\right] e^{-\frac{1}{2} \alpha|p|}, \\
\Pi(x)=\int_{-\infty}^{\infty} \frac{d p|p|}{2 \pi \sqrt{2|p|}}\left[-i \phi(p) e^{i p x}+i \phi^{\dagger}(p) e^{-i p x}\right] e^{-\frac{1}{2} \alpha|p|},
\end{array}\\
\left[\phi(p), \phi^{\dagger}\left(p^{\prime}\right)\right]=2 \pi \delta\left(p-p^{\prime}\right) .
\end{array}
$$
$\alpha$ is a convergence control number.
### Commuattion relation
$$
\begin{aligned}
    [\phi_\pm (x),\phi_\pm (y)] =& \pm \frac{i}{4} sgn(x-y)\\  
    [\phi_+ (x),\phi_- (y)] =& \frac{i}{4} \\
\end{aligned}
$$
### proof:
Directly put the commutation relation into above.

###  An Identity

If  $A$ and $B$ are linear operators of $\phi_\pm$:
$$
\begin{aligned}
    e^{A+B}=&e^A e^B e^{-\frac{1}{2}[A,B]}\\
    e^Ae^B=&:e^{A+B}:e^{\langle  AB+(A^2+B^2)/2 \rangle }.\\
\end{aligned}
$$
### proof:

$$
\begin{aligned}
    :e^A:&=e^{A^+}e^{A^-}=e^Ae^{\frac{1}{2}[A^+,A^-]}\\
    :e^B:&=e^{B^+}e^{B^-}=e^Be^{\frac{1}{2}[B^+,B^-]}\\
    :e^{A+B}:&=e^{A^++B^+}e^{A^-+B^-}=e^{A+B}e^{\frac{1}{2}[A^++B^+,A^-+B^-]}\\
\end{aligned}
$$

Then:

$$
\begin{aligned}
    :e^{A+B}:&=e^{A}e^Be^{-\frac{1}{2}[A,B]}e^{\frac{1}{2}[A^++B^+,A^-+B^-]}\\
    &=e^Ae^Be^{-[A^-,B^+]}e^{\frac{1}{2}[A^+,A^-]}e^{\frac{1}{2}[B^+,B^-]}\\
    &=e^Ae^Be^{-\langle AB\rangle}e^{\frac{1}{2}\langle A^2\rangle}e^{\frac{1}{2}\langle B^2\rangle   }\\
    e^Ae^B&=:e^{A+B}:e^{\langle AB+\frac{1}{2}(A^2+B^2)\rangle}
\end{aligned}
$$

### Correlation function
The correlation fucntion could be derived using the Fourier transformation above:
$$
\begin{aligned}
G_{ \pm}(x) & =\left\langle\phi_{ \pm}(x) \phi_{ \pm}(0)-\phi_{ \pm}^{2}(0)\right\rangle \\
& =\frac{1}{4 \pi} \ln \frac{\alpha}{\alpha \mp i x}, \\
G(x) & =\left\langle\phi(x) \phi(0)-\phi^{2}(0)\right\rangle \\
& =\frac{1}{4 \pi} \ln \frac{\alpha^{2}}{\alpha^{2}+x^{2}} .
\end{aligned}
$$
### proof:

$$
\begin{aligned}
    G_+(x)&=\int_0^\infty\frac{dp}{2\pi \sqrt{2|p|}}e^{-\frac{1}{2}\alpha |p|}\int_0^\infty\frac{dq}{2\pi \sqrt{2|q|}}e^{-\frac{1}{2}\alpha |q|}\langle \phi(p)\phi(q)^\dagger\rangle(e^{ipx}-1)\\
    &=\int_0^\infty\frac{dp}{4\pi |p|}(e^{ipx}-1)e^{-\alpha p}\\
    &=\frac{1}{4\pi}\ln \frac{\alpha^2}{\alpha^2+x^2}
\end{aligned}
$$

Use the Fourier's expansion



## Transformed Hamiltonian
Fisrtly, using the Bosonization relation to reproduce some of the terms in the Hamiltonian.

### $\psi_+^\dagger\psi_-+\psi_-^\dagger\psi_+$

It becomes:

$$
\begin{aligned}
     &\frac{1}{2\pi \alpha}(e^{-i\sqrt{4\pi}\phi_+}e^{-i\sqrt{4\pi}\phi_-}+h.c.)\\
    =&\frac{1}{2\pi \alpha}(e^{-i\sqrt{4\pi}\phi}e^{-2\pi\frac{i}{4}}+h.c.)\\
    =&\frac{1}{2\pi \alpha}(-2\sin(\sqrt{4\pi}\phi))\\
    =&-\frac{1}{\pi \alpha}\sin(\sqrt{4\pi}\phi)
\end{aligned}
$$

### $\psi_+^\dagger(x+\epsilon)\psi_+(x)$

It becomes:

$$
\begin{aligned}
     &\frac{1}{2\pi \alpha}e^{-i\sqrt{4\pi}\phi_+(x+\epsilon)}e^{i\sqrt{4\pi}\phi_+(x)}\\
    =&\frac{1}{2\pi \alpha}:e^{-i\sqrt{4\pi}(\phi_+(x+\epsilon)-\phi_+(x))}:e^{4\pi\langle \phi_+(\epsilon)\phi_+(0)-\phi_+(0)^2\rangle}\\
    =&\frac{1}{2\pi (\alpha-i\epsilon)}:1-i\sqrt{4\pi}\frac{\partial \phi_+(x)}{\partial x}\epsilon+...:\\
    =&\frac{i}{2\pi \epsilon}+\frac{1}{\sqrt{\pi}}\frac{\partial \phi_+(x)}{\partial x}\quad (\alpha \ll \epsilon)\\
\end{aligned}
$$
 The same is for $\psi_-^\dagger(x+\epsilon)\psi_-(x) = -\frac{i}{2\pi \epsilon}+\frac{1}{\sqrt{\pi}}\frac{\partial \phi_-(x)}{\partial x}\quad (\alpha \ll \epsilon)$

So, $\psi_+^\dagger\psi_++\psi_-^\dagger\psi_-= \frac{1}{\sqrt{\pi}}\frac{\partial \phi(x)}{\partial x}$


### $\psi^\dagger_+\partial_x \psi_+=\psi_+^\dagger(x)(\psi_+(x+\epsilon)-\psi_+(x+\epsilon))/2\epsilon$

It becomes:

$$
\begin{aligned}
     &\frac{1}{4\pi \alpha\epsilon}[e^{-i\sqrt{4\pi}\phi_+(x)}e^{i\sqrt{4\pi}\phi_+(x+\epsilon)}-e^{-i\sqrt{4\pi}\phi_+(x)}e^{i\sqrt{4\pi}\phi_+(x-\epsilon)}]\\
    =&\frac{1}{4\pi \alpha\epsilon}[:e^{-i\sqrt{4\pi}(\phi_+(x)-\phi_+(x+\epsilon))}:e^{4\pi\langle \phi_+(0)\phi_+(\epsilon)-\phi_+(0)^2\rangle}\\
    &-:e^{-i\sqrt{4\pi}(\phi_+(x)-\phi_+(x-\epsilon))}:e^{4\pi\langle \phi_+(0)\phi_+(-\epsilon)-\phi_+(0)^2\rangle}]\\
    =&\frac{1}{4\pi \epsilon}[\frac{1}{\alpha+i\epsilon}:1+i\sqrt{4\pi}\frac{\partial \phi_+(x)}{\partial x}\epsilon-2\pi(\frac{\partial \phi_+(x)}{\partial x})^2\epsilon^2:\\
    &-\frac{1}{\alpha-i\epsilon}:1-i\sqrt{4\pi}\frac{\partial \phi_+(x)}{\partial x}\epsilon-2\pi(\frac{\partial \phi_+(x)}{\partial x})^2\epsilon^2:]\\
    =&\frac{1}{2\pi i \epsilon^2}-\frac{1}{i}(\frac{\partial \phi_+(x)}{\partial x})^2\quad (\alpha \ll \epsilon)\\
\end{aligned}
$$

$\psi^\dagger_-\partial_x \psi_-=\psi_-^\dagger(x)(\psi_-(x+\epsilon)-\psi_-(x+\epsilon))/2\epsilon$

$$
\begin{aligned}
     &\frac{1}{4\pi \alpha\epsilon}[e^{i\sqrt{4\pi}\phi_-(x)}e^{-i\sqrt{4\pi}\phi_-(x+\epsilon)}-e^{i\sqrt{4\pi}\phi_-(x)}e^{-i\sqrt{4\pi}\phi_-(x-\epsilon)}]\\
    =&\frac{1}{4\pi \alpha\epsilon}[:e^{i\sqrt{4\pi}(\phi_-(x)-\phi_-(x+\epsilon))}:e^{4\pi\langle \phi_-(0)\phi_-(\epsilon)-\phi_-(0)^2\rangle}\\
    &-:e^{i\sqrt{4\pi}(\phi_-(x)-\phi_-(x-\epsilon))}:e^{4\pi\langle \phi_-(0)\phi_-(-\epsilon)-\phi_-(0)^2\rangle}]\\
    =&\frac{1}{4\pi \epsilon}[\frac{1}{\alpha-i\epsilon}:1-i\sqrt{4\pi}\frac{\partial \phi_-(x)}{\partial x}\epsilon-2\pi(\frac{\partial \phi_-(x)}{\partial x})^2\epsilon^2:\\
    &-\frac{1}{\alpha+i\epsilon}:1+i\sqrt{4\pi}\frac{\partial \phi_-(x)}{\partial x}\epsilon-2\pi(\frac{\partial \phi_-(x)}{\partial x})^2\epsilon^2:]\\
    =&-\frac{1}{2\pi i \epsilon^2}+\frac{1}{i}(\frac{\partial \phi_-(x)}{\partial x})^2\quad (\alpha \ll \epsilon)\\
\end{aligned}
$$

### $H_0$

Ignoring c numbers:

$$
\begin{aligned}
   \int dx -i\psi^\dagger_+\partial_x \psi_++i\psi^\dagger_-\partial_x \psi_-=&\int dx(\frac{\partial \phi_+(x)}{\partial x})^2+(\frac{\partial \phi_-(x)}{\partial x})^2 \\
    =&\int dx \frac{1}{2}(\Pi^2+(\frac{\partial \phi}{\partial x})^2)
\end{aligned}
$$

### $\left[\frac{1}{\pi \alpha} \sin \sqrt{4 \pi} \phi\right]^{2}$
$$
\begin{aligned}
    &\left[\frac{1}{\pi \alpha} \sin \sqrt{4 \pi} \phi(0)\right]^{2}\\
    =&-\frac{1}{4 \pi^{2} \alpha^{2}} \lim _{x \rightarrow 0}\left[e^{i \sqrt{4 \pi} \phi(x)}-c c\right] \cdot\left[e^{i \sqrt{4 \pi} \phi(0)}-c c\right]\\
=&-\frac{1}{2 \pi^{2} \alpha^{2}} \lim _{x \rightarrow 0}[\cos (\sqrt{4 \pi}(\phi(x)+\phi(0)))-\cos (\sqrt{4 \pi}(\phi(x)-\phi(0)))] .
\end{aligned}
$$
The second term produces a pecular term:
$$
\begin{aligned}
&\frac{1}{2 \pi^{2} \alpha^{2}} \lim _{x \rightarrow 0} \cos (\sqrt{4 \pi}(\phi(x)-\phi(0)) \\
=&\lim _{x \rightarrow 0} \frac{1}{2 \pi^{2} \alpha^{2}}: \cos (\sqrt{4 \pi}(\phi(x)-\phi(0)): \frac{\alpha^{2}}{x^{2}+\alpha^{2}} \\
=&\lim _{x \rightarrow 0} \frac{1}{2 \pi^{2} \alpha^{2}}: 1-\frac{x^{2}}{2}(4 \pi)\left(\partial_{x} \phi\right)^{2}+\cdots: \frac{\alpha^{2}}{x^{2}+\alpha^{2}} \\
=&-\frac{1}{\pi}\left(\frac{\partial \phi}{\partial x}\right)^{2}+c \text {-number, }
\end{aligned}
$$
So,
$\left[\frac{1}{\pi \alpha} \sin \sqrt{4 \pi} \phi\right]^{2}=-\frac{1}{\pi}\left(\frac{\partial \phi}{\partial x}\right)^{2}-\frac{1}{2 \pi^{2} \alpha^{2}} \cos \sqrt{16 \pi} \phi .$

### $H_{\mathrm{Ic}}$


$$
\begin{aligned}
&H_{\mathrm{Ic}}\\
= & a \Delta \sum_j\left[\frac{1}{\sqrt{\pi}} \partial_x \phi\right]^2-\left[\frac{1}{\pi \alpha}\sin(\sqrt{4\pi}\phi)\right]^2+(-1)^j \text { oscillations } \\
= & \Delta \int d x\frac{(\partial_x \phi)^2}{\pi}-\left[\frac{1}{\pi \alpha} \sin \sqrt{4 \pi} \phi \right]^2 \\
= &\Delta \int d x\left[\frac{2\left(\partial_x \phi\right)^2}{\pi}+\frac{1}{2 \pi^2 \alpha^2} \cos \sqrt{16 \pi} \phi\right]
\end{aligned}
$$
