Tags: [[Analisi 2 e Probabilità]] [[University]] 

# Riassunto Prima Parte
Una v.a. si dice *Continua* se esiste una funzione non negativa $f_X$, chiamata *Densità*, t.c. per ogni insieme $B$ $$P\{X\in B\}=\int_B f_X(x)\ dx$$ $f_X$ continua a tratti e integrabile in senso generalizzato
- $\int_{-\infty}^\infty f_X(x)\ dx=1$
- Se $X$ è continua, la funzione di distribuzione $F_x$ è derivabile e $$F'_X(x)=f_X(x)$$
- $E[X]=\int_{-\infty}^\infty xf_X(x)\ dx$
- $E[g(x)]=\int_{-\infty}^\infty g(x)f_X(x)\ dx$
Come nel caso discreto $$Var(X)=E[(X-E[X])^2]=E[X^2]-(E[X])^2\quad \small{E[X]^2=\int_\mathbb{R} x^2 f_X(x)\ dx}$$
### Esempi
1) Variabili uniformi su $(\alpha,\beta)$ $$\begin{align}
&f_X(x)=\begin{cases}
\frac{1}{\beta-\alpha} & \alpha<x<\beta \\
0 & altrimenti
\end{cases} \\
&E[X]= \frac{\alpha+\beta}{2}\quad Var(X)= \frac{(\beta-\alpha)^2}{12}
\end{align}$$
2) Variabili normali di parametri $\mu$ e $\sigma^2$ $$\begin{align}
&f_X(x)= \frac{1}{\sigma\sqrt{2\pi}}e^{- \frac{(x-\mu)^2}{2\sigma^2}}\quad x\in\mathbb{R} \\
&E[X]=\mu\quad Var(X)=\sigma^2\qquad X\sim N(\mu,\sigma^2)\Longrightarrow Z= \frac{X-\mu}{\sigma}\sim N(0,1)
\end{align}$$Dal teorema di De Moivre - Laplace le variabili normali approssimano le $B(n,p)$ ($np(1-p)\ge 10$)
3) Variabile esponenziale $$\begin{align}
&f_X(x)=\begin{cases}
\lambda e^{-\lambda x} & x\ge 0 \\
0 & altrimenti
\end{cases} \\
& E[X]= \frac{1}{\lambda}\quad Var(X)= \frac{1}{\lambda^2}
\end{align}$$
4) Caso particolare della Distribuzione Gamma $$\begin{align}
&f_X(x)=\begin{cases}
\frac{\lambda e^{-\lambda x}(\lambda x)^{\alpha-1}}{\Gamma(\alpha)} & x\ge 0 \\
0 & altrimenti
\end{cases} \\
&\Gamma(\alpha)=\int_0^\infty e^{-x}x^{\alpha}\ dx , \ \alpha>1 \\
&E[X]=\frac{\alpha}{\lambda}\quad Var(X)= \frac{\alpha}{\lambda^2} 
\end{align}$$Variabile esponenziale si ottiene per $\alpha=1$
# Riassunto Seconda Parte
In caso di v.a. $(X,Y)$, si definisce la distribuzione la distribuzione congiunta di $X$ e $Y$ $$F_{X,Y}(a,b)=P\{X\le a, Y\le b\}\quad a,b\in\mathbb{R}$$Le distriubuzione delle singole variabili $$F_X(a)=\lim_{b\to\infty} F_{X,Y}(a,b)\quad F_y(b)=\lim_{a\to\infty} F_{X,Y} (a,b)$$$X$, $Y$ discrete, si definisce la *Densità Discreta* $$\begin{align}
&p_{X,Y}(i,j)=P\{X=i,Y=j\} \\
&p_X(i)=P_X\{X=1\}=\sum_j p_{X,Y}(i,j)\quad p_Y(j)=\sum_i p_{X,Y} (i,j) \ (*)
\end{align}$$Le variabili $X$ e $Y$ si dicono *Congiuntamente Continue* se esiste una $f_{X,Y}$ integrabile t.c. $\forall C\subseteq\mathbb{R}^2$ $$P\{(X,Y)\in C\}=\iint_Cf_{X,Y}\ dxdy$$Si ha 
- $f_{X,Y}\ge0$
- $\iint_{\mathbb{R}^2}$
Se $X$, $Y$ sono congiuntamente continue, allora lo sono individualmente $$f_X(x)=\int_{-\infty}^\infty f_{X,Y}(x,y)\ dy,\ f_Y(t)=\int_{-\infty}^\infty f_{X,Y}(x,y)\ dx$$(Similmente al caso discreto)

( * ) $C\subset \mathbb{R}^2$, $f,C$ sono limitati, $C$ dominio normale rispetto a $x/y$ (valgono le formule di riduzione) 
Se $f$ o $C$ illimitati $$\int_a^b\left( \int_{g_1(x)}^{g_2(x)} f(x,y)\ dx \right)dy$$Rispetto ad $y$, $a,b$, $g_1$ o $g_2$ sono $+\infty$ o $-\infty$
è necessario che $$\int_a^b\left(\int_{g_1}^{g_2} |f_{X,Y}(x,y)|\ dx\right)dy<+\infty$$
- $f_{X,Y}\ge0$
- $\iint_{\mathbb{R}^2} f_{X,Y}=1$
- $X$, $Y$ indipendenti se $$P\{X\in A, Y\in B\}=P\{X\in A\}P\{Y\in B\}$$($E_A=\{X\in A\}$, $F_B=\{Y\in B\}$ sono indipendenti) $$\begin{align}
\iff& f_{X+Y}(x,y)=f_X(x)f_Y(y) \\
&F_{X+Y}(x,y)= F_X(x)F_y(X)
\end{align}$$
# Somma di Variabili Indipendenti
$X$, $Y$ indipendenti
**Domanda:** come ottenere la distribuzione di $X+Y$ a partire da quelle di $X$ e $Y$? $$\begin{align}
F_{X+Y}(a)&=P\{X+Y\le a\}\overset{indip.}{=}\iint_{\{X+Y\le a\}}f_X(x)f_Y(y)\ dxdy\quad \small\begin{matrix}
\{ (x,y)\in\mathbb{R}^2: \ x\le a-y\} \\
\{y\in(-\infty,a-y) \}
\end{matrix} \\
&=\int_{-\infty}^{\infty}\left( \int_{-\infty}^{a-y} f_X(x)\ dx \right)f_Y(y)\ dy\overset{def}{=} \int_{-\infty}^\infty F_X(a-y)f_Y(y)\ dy
\end{align}$$$F_{X+Y}$ è deta *Convoluzione* delle distanze $F_X$ e $F_Y$ $$\begin{align}
f_{X+Y}&= \frac{d}{da}\int_{-\infty}^\infty F_X(a-y) f_Y(y)\ dy = \int_{-\infty}^\infty \frac{d}{da} F_X(a-y)f_Y(y)\ dy \\
&=\int_{-\infty}^\infty f_X(a-y)f_Y(y)\ dy
\end{align}$$
### Esempio
Se $X$, $Y$ sono indipendenti con distribuzione gamma $$f(y)= \frac{\lambda e^{-\lambda y}(\lambda y)^{t-1}}{\Gamma(t)}, \ y\ge0$$
1) Se $X$ e $Y$ sono indpendenti e hanno distribuzione $(s, \lambda)$, $(t,\lambda)$ rispettivamente $\Longrightarrow X+Y$ è una variabile con distribuzione gamma di parametri $(s+t,\lambda)$ $$\begin{align}
&f_{X+Y}(a)=\int_{-\infty}^\infty f_X(\overset{\ge0}{a-y})f_Y(\overset{\ge0}{y})\ dy \\
&f(x)=\begin{cases}
\frac{\lambda e^{-\lambda  x}(\lambda x)^{t-1}}{\Gamma(\alpha)} & x\ge0 \\
0 & altrimenti
\end{cases}
\end{align}$$$f$ è 0 per valori negativi della variabile $f_X(\overset{\ge0}{a-y})$ $$\begin{align}
&=\frac{1}{\Gamma(s)\Gamma(t)}\int_0^a \underset{f_X(a-y)}{\lambda e^{-\lambda(a-y)[\lambda(a-y)]^{s-1}}}\underset{f_Y(y)}{\lambda e^{-\lambda y}(\lambda y)^{t-1}}\ dy = \frac{e^{-\lambda a}\lambda^{t+s}}{\Gamma(s)\Gamma(t)}\int_0^a (a-y)^{s-1}y^{t-1}\ dy \\
&\overset{x=\frac{y}{a}}{=} \frac{e^{-\lambda a}\lambda^{t+s}}{\Gamma(s)\Gamma(t)}\left( \int_0^1 (1-x)^{s-1} x^{t-1}\  dx \right)a^{s+t-1}=C e^{-\lambda a}a^{s+t-1}\quad s,t\ge1 \\
 \\
&C=\frac{\lambda^{t+s}}{\Gamma(s)\Gamma(t)}\int_0^1(1-x)^{s-1}x^{t-1}\ dx \ t.c. \ \int^\infty_{-\infty}f_{X+Y}(a)\ da=1 \\
&C\int_0^\infty e^{-\lambda a}a^{s+t-1}\ da=1\overset{\lambda a=z}{\Longrightarrow} C= \frac{\lambda^{s+t}}{\Gamma(s+t)} \\
 \\
& f_{X+Y}(a)= \frac{\lambda^{s+t-1+1}}{\Gamma(s+t)}e^{-\lambda a}a^{s+t-1}= \frac{\lambda e^{-\lambda a}(\lambda a)^{s+t-1}}\Gamma(s+t)\quad a\ge0 \\
 \\
&C= \frac{\lambda^{s+t}}{\Gamma(s+t)} \\
& \frac{\lambda^{t+s}}{\Gamma(s)\Gamma(t)}\int_0^1(1-x)^{s-1}x^{t-1}\ dx = \frac{\lambda^{s+t}}{\Gamma(s+t)} \\
 \\
&\int_0^1(1-x)^{s-1}x^{t-1}\ dx \frac{\Gamma(s)\Gamma(t)}{\Gamma(s+t)}
\end{align}$$
### Esempio (Distribuzione Beta)
$$\begin{align}
&f(x)=\begin{cases}
\frac{1}{B(a,b)}x^{a-1}(1-x)^{b-1} & x\in(0,1) \\
0 & altrimenti
\end{cases} \\
& B(a,b)=\int_0^1 x^{a-1}(1-x)^{b-1}\ dx = \frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}
\end{align}$$N.B. $a,b>0$ (in questo caso $B(a,b)$ esiste finito), determinare valore atteso e varianza $$\begin{align}
E[X]&=\int_{-\infty}^\infty xf(x)\ dx = \frac{1}{B(a,b)}\int_0^1 x x^{a-1}(1-x)^{b-1}\ dx= \frac{1}{B(a,b)}\int_0^1 x^a(1-x)^{b-1}\ dx  \\
&= \frac{B(a+1)}{B(a,b)}= \frac{\Gamma(a+1)\Gamma(b)}{\Gamma(a+1+b)}\cdot \frac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)}= \frac{\Gamma(a+1)\Gamma(b)}{\Gamma(a+1+b)} \\
&= \frac{a\cancel{\Gamma(a)}\cancel{\Gamma(b)}}{(a+b)\cancel{\Gamma(a+b)}}\cdot \frac{\cancel{\Gamma(a+b)}}{\cancel{\Gamma(a)}\cancel{\Gamma(b)}}= \frac{a}{a+b}
\end{align}$$ $$\begin{align}
&Var(x)=E[X^2]-(E[X])^2 \\
& E[X^2]= \frac{1}{B(a,b)}\int_0^1x^2x^{a-1}(1-x)^{b-1}\ dx= \frac{1}{B(a,b)}\int_0^1x^{a+1}(1-x)^{b-1}\ dx \\
&=\frac{B(a+2,b)}{B(a,b)} = \frac{\Gamma(a+2)\Gamma(b)}{\Gamma(a+2+b)}\cdot \frac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)}= \frac{\Gamma(a+2)\Gamma(b)}{\Gamma(a+2+b)} \\
&= \frac{(a+1)a\cancel{\Gamma(a)}\cancel{\Gamma(b)}}{(a+b+1)(a+b)\cancel{\Gamma(a+b)}} \frac{\cancel{\Gamma(a+b)}}{\cancel{\Gamma(a)}\cancel{\Gamma(b)}}= \frac{a(a+1)}{(a+b+1)(a+b)} \\
&Var(X)= \frac{a(a+1)}{(a+b+1)(a+b)}- \left( \frac{a}{(a+b)} \right)^2= \frac{ab}{(a+b)^2(a+b+1)}
\end{align}$$
### Esempio 
La densità congiunta di $X$ e $Y$ $$\begin{align}
f_{X,Y}=\begin{cases}
e^{-(x+y)} & x>0,y>0 \\
0 & altrimenti
\end{cases}
\end{align}$$Si determini la funzione di densità della variabile $\frac{X}{Y}=Z$
1) $F_{\frac{X}{Y}}(a)\overset{def}{=}P\left\{ \frac{X}{Y}\le a \right\}$ $$\begin{align}
P\left\{ \frac{X}{Y}\le a \right\}&=\iint f_{X,Y}(x,y)\ dxdy= \iint_C e^{-(x+y)}\ dxdy \\
&C=\{0<x\le ay, y>0\}\quad =\int_0^\infty\left(\int^{ay}_0 (e^{x}e^y)\ dx \right)dy \\
&=\int_0^\infty e^{-y}(1-e^{-ay})\ dy= \int_0^\infty e^{-y}- \frac{1}{a+1}\int_0^\infty (a+1)e^{-(a+1)y}\ dy \\
&= -e^{-y}|^\infty_0 + \frac{e^{-(a+y)y}}{a+1}|^\infty_0=1- \frac{1}{a+1}= F_{\frac{X}{Y}}(a)
\end{align}$$
2) $$f_{\frac{X}{Y}}(a)= \frac{d}{da} F_{\frac{X}{Y}}(a)= \frac{d}{da}\left( 1- \frac{1}{a+1} \right)= \frac{1}{(a+1)^2}$$