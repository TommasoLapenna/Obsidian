Tags: [[Analisi 2 e Probabilità]] [[University]]

### Definizione
$X$ è una v.a. *Continua* se esiste una funzione non negativa definita per ogni $\in\mathbb{R}$ t.c. per ogni sottoinsieme $B$ nei reali $$P\{X\in B\}=\int_B f(x) \ dx$$$f$ è la funzione di densità
### Osservazione
$$1=P\{X\in(-\infty,\infty)\}=\int^\infty_{-\infty} f(x)\ dx$$
1) $P\{a\le x\le b\}=\int_a^b f(x)\ dx$
2) $P\{X=a\}=\int_a^a f(x)\ dx=0$
3) $P\{x\subset a\}=P\{X\le a\}= F_x(a)=\int_{-\infty}^a f_x(x)\ dx$
### Esempio
$X$ v.a. continua $$f_x(x)=\begin{cases}
C(4x-2x^2) & 0<x<2 \\
0 & altrimenti
\end{cases}$$
1) Determinare $C$ $$\begin{align}
C:&\int_\infty^{+\infty}f_x(x)\ dx=1 \\
&\int_0^2C(4x-2x^2)\ dx=1 \\
&C\int_0^2(4x-2x^2)= C\left[ 2x^2-\frac{2}{3}x^3 \right]^2_0 \\
C&\left( 8-\frac{16}{3} \right)=1\quad C= \frac{3}{8}
\end{align}$$
2) Determinare $P\{X>1\}$ $$\begin{align}
&P\{X>1\}\overset{def}{=}\int_1^\infty f(x)\ dx=\int_1^2 \frac{3}{8}(4x-2x^2)\ dx= \frac{1}{2} \\
&P\{X\in B\}=\int_B f_x(x)\ dx\quad f_x(X)=\begin{cases}
\frac{3}{p}(4x-2x^2) & x\in(0,2) \\
0
\end{cases}\ (1,2) \\
&P\{X>1\}=\int^\infty_1 f_x(X)\ dx= \int_1^2 f_x(X)\ dx
\end{align}$$
$F_x(a)=P\{X\in (-\infty,a]\}=\int_{-\infty}^a f_x(x)\ dx$
Valgono le seguenti proprietà
1) $\forall a\in\mathbb{R}\quad 0\le F_x(a)\le1$
2) $F_X$ è non decresecnete $\quad a\le b\quad \{x\le a\}\quad\{x\le b\}$
3) $\lim_{a\to-\infty}F_X(a)=0,\quad \lim_{a\to+\infty}F_X(a)=1$
4) $F_X$ è continua a destra
Se $f_X$ è continua in un punto $a$ $$\frac{d}{da}F_X(a)=f_X(a)$$
### Esempio
$X$ v.a. $F_X$, $f_x$ 
$Y=2X$, $F_Y$, $f_Y$, $Y\in(-\infty,a]$ $$\begin{align}
&F_Y(a)\overset{def}{=} P\{Y\le a\}=P\{2X\le a\}=P\left\{ X\le \frac{a}{2} \right\}=F_X\left( \frac{a}{2} \right) \\
& f_Y(a)= \frac{d}{da} F_Y(a)= \frac{d}{da}\left( F_X\left( \frac{a}{2} \right) \right)=\frac{1}{2}F'_X\left( \frac{a}{2} \right)=\frac{1}{2}f_X\left( \frac{a}{2} \right)
\end{align}$$
# Valore Atteso e Varianza
$X$ variabile aleatoria discreta:
$$\begin{align}
&E[X]=\sum_x xP\{X=x\}=\sum_{x_i}x_iP\{X=x_i\} \\
&E[X]\overset{def}{=}\int_{-\infty}^\infty x f_x(x)\ dx \\
& E[X]=\int_{-\infty}^\infty xf_x(x)\ dx=\int_0^1 x(2x)\ dx = \frac{2}{3} x^3|^1_0=\frac{2}{3} 
\end{align}$$
$X$ variabile aleatoria continua, per ogni funzione $g$ a valori reali $$\begin{align}
&E[g(x)]\overset{def}{=}\int_{-\infty}^\infty g(x)f_x(x)\ dx \\
&a,b\in\mathbb{R} \\
& E[aX+b]=aE[X]+b \\
&Var(X)=E[(X-\mu)^2]0\underset{\int_{-\infty}^\infty x^2 f_x(x)\ dx}={E[x^2]}-(E[X])^2
\end{align}$$
### Esempio (precedente)
$$\begin{align}
&f_x(x)=\begin{cases}
2x & x\in[0,1] \\
0 & altrimenti
\end{cases} \\
&Var(X)=?\quad E[X^2]=\int_0^1\underset{f_x}{(2x)}x^2\ dx=\int_0^1(2x^3)\ dx= \frac{x^4}{2}\big|^1_0=\frac{1}{2} \\
&Var(X)=E[X^2]-(E[X])^2=\frac{1}{2}-\left( \frac{2}{3} \right)^2=\frac{1}{18} \\
&a\in\mathbb{R}\quad Var(aX)=a^2Var(X)\ldots
\end{align}$$
#### Variabile Aleatoria Uniforme
$X$ v.a.c uniforme su $(0,1)$ $$f_x(x)=\begin{cases}
1& se\ x\in(0,1) \\
0& altrimenti
\end{cases}$$(più in generale è uniforme su $(\alpha,\beta)$ se $x\in(\alpha,\beta)$ $$f_x(x)=\begin{cases}
\frac{1}{\beta-\alpha}& se \ x\in(\alpha,\beta) \\
0 & altrimenti
\end{cases}$$altrimenti $$\int_{-\infty}^\infty f_x(x)=1$$)
### Esempio
Gli autobus passano in una fermata ad intervalli di 15 minuti, a partire dalle 7:00 di mattina. Se un passeggero arriva alla fermata in un istante uniformemente distribuito tra le 7:00 e le 7:30, determinare la probabilità che il passeggere aspetti l'autobus:
$X=$ minuto dopo le 7:00 nel quale il passeggero arriva alla fermata $$f_x(x)=\begin{cases}
\frac{1}{30} & se \ x\in(0,30) \\
0 & altrimenti
\end{cases}$$
1) Meno di 5 minuti $$\begin{align}
P\{a\}&=P\{10<X<15\}+P\{25<X<30\}=\int^{15}_{10} \frac{1}{30}\ dx \\
&=\int_{25}^{30} \frac{1}{30}\ dx=\frac{5}{30}+\frac{5}{30}=\frac{1}{3}
\end{align}$$
2) Più di 10 minuti $$P\{b\}=P\{0<X<5\}+P\{15<X<20\}=\frac{1}{3}$$
#### Variabili Aleatorie Normali
$X\sim N(\mu,\sigma^2)\quad f_x(x)= \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{ (x-\mu)^2}{2\sigma^2}}\ x\in\mathbb{R}$
$\mu=0,\ \sigma=1$
```graph
bounds: [-3, 3, 3, -3]
elements: [
	{type: functiongraph, def: ["f:(1/(2^(1/2)))*Math.exp(-((x*x)/2))"]}
]
```

- Poisson approssima $X\sim B(n,p)$, $n$ grande, $p$ piccolo, $np=\lambda$
- $N(\mu,\sigma^2)$ approssimano bene $B(n,p)$, $np(1-p)\ge10$
Verificare che $\int^\infty_{-\infty} f_x(x)\ dx=1$ 
$$\begin{align}
&\frac{1}{\sqrt{2\pi}\sigma}\int^\infty_{-\infty}e^{-\frac{(x-\mu)^2}{2\sigma^2}}\ dx=1 \\
&y= \frac{x-\mu}{\sigma}\quad I= \frac{1}{\sqrt{2\pi}}\int_{-\infty}^\infty e^{-\frac{y^2}{2}}\ dy\overset{?}{=}1 \quad\int^\infty_{-\infty} e^{-\frac{y^2}{2}}\ dy=\sqrt{2\pi} \\
&J=\int_{-\infty}^\infty e^{- \frac{y^2}{2}}\ dy\quad J^2=\int^\infty_{-\infty}e^{-\frac{y^2}{2}}\ dy\int_{-\infty}^\infty e^{-\frac{x^2}{2}}\ dx=\int_{-\infty}^\infty\int_{-\infty}^\infty e^{-\frac{x^2+y^2}{2}}\ dxdy \\ \\
&\begin{cases}
x=\rho\cos\theta & \rho\in[0,+\infty) \\
y=\rho\sin\theta & \theta\in[0,2\pi]
\end{cases} \\ \\
&J^2=\int^\infty_0\int_0^{2\pi} e^{-\frac{\rho^2}{2}}\rho\ d\theta d\rho=2\pi\int_0^\infty \rho e^{-\frac{\rho^2}{2}}\ d\rho=2\pi e^{-\frac{\rho^2}{2}}|^\infty_0=2\pi \\
&J=\sqrt{2\pi}\Longrightarrow I= \frac{1}{\sqrt{2\pi}}J=1
\end{align}$$

### Proprietà
$X\sim N(\mu,\sigma^2)$ allora $$Y=\alpha X+\beta\Longrightarrow Y\sim N(\alpha\mu+\beta,\ \alpha^2\sigma^2)$$
### Dimostrazione
$\alpha>0$ 
$$F_Y(a)=P\{Y\le a\}=P\{\alpha X+\beta\le a\} =P\left\{ X\le \frac{\alpha-\beta}{\alpha} \right\}\overset{def}{=} F_X\left( \frac{\alpha-\beta}{\alpha} \right)$$
$$ \begin{align}
f_y(a)&= \frac{d}{da}(F_Y(a))= \frac{d}{da}\left( F_X\left( \frac{\alpha-\beta}{\alpha} \right) \right)= \frac{1}{\alpha}f_X\left( \frac{\alpha-\beta}{\alpha} \right)=\frac{1}{\alpha} \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{\left ( \frac{\alpha-\beta}{\alpha}-\mu \right)^2}{2\sigma^2}} \\
&= \frac{1}{\alpha\sigma} \frac{1}{\sqrt{2\pi}}e^{-\frac{(\alpha-\beta-\mu\sigma)^2}{2\alpha^2\sigma^2}}=\frac{1}{\underset{\overset{\sim}{\sigma}}{\alpha\sigma}} \frac{1}{\sqrt{2\pi}} e^{- \frac{(a-\overset{\overset{\sim}{\mu}}{(\beta+\mu\alpha)})^2}{2\underset{\overset{\sim}{\sigma}^2}{\alpha^2\sigma^2}}} \\
& Y\sim N(\overset{\sim}{\mu}, \overset{\sim}{\sigma})=N(\alpha\mu+\beta,\ \alpha^2\sigma^2)
\end{align} 
$$
#### Conseguenza
$$Z= \frac{X-\mu}{\sigma} \ e \ X\sim N(\mu,\sigma^2)\Longrightarrow Z\sim N(0,1)$$$Z$ si dice *Variabile Normale Standard*
### Teorema (De Moivre - Laplace) 
$S_n=$ numero di successi che si realizzano in $n$ prove indipendenti, dove $p$ è la probabilità di successo, allora $$\begin{align}
&P\left\{ a\le \frac{S_n-np}{\underset{\sigma_{S_n}}{\sqrt{np(1-p)}}}\le b \right\}\overset{n\to+\infty}{\longrightarrow} \Phi(b)-\Phi(a) \\
&np=E[S_n] \\
&np(1-p)=Var(S_n)\Longrightarrow \sigma_{S_n}\sqrt{Var(S_n)}=\sqrt{np(1-p)} \\
&np(1-p)\ge 10
\end{align}$$
### Conclusione
2 approssimazioni delle $X\sim B(n,p)$
- Poisson: $n$ grande e $p$ piccolo
- Normale: $np(1-p)$ grande ($np(1-p)\ge10$)