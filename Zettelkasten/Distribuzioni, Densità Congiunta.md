### Distribuzione Gamma $(\alpha,\lambda)$
$$\begin{align}
&f(x)=\begin{cases}
\frac{\lambda e^{-\lambda x}(\lambda x)^{\alpha-1}}{\Gamma(\alpha)} & x\ge 0 \\
0 & altrimenti
\end{cases} \\
&\Gamma(\alpha)=\int_0^\infty e^{-y}y^{\alpha-1}\ dy\quad (\alpha\ge1)
\end{align}$$
1) $\Gamma(\alpha)=(\alpha-1)\Gamma(\alpha-1)\quad (\Gamma(n)=n!)$ $$\begin{align}
\Gamma(\alpha)&=-\int_0^\infty- e^{-y}y^{\alpha-1}\ dy=\cancel{-e^{-y}y^{\alpha-1}|_0^\infty}+\int_0^\infty (\alpha-1)y^{\alpha-2}e^{-y}\ dy \\
&= (\alpha-1)\int_0^\infty e^{-y}y^{(\alpha-1)-1}\ dy= (\alpha-1)\Gamma(\alpha-1) \\
\overset{\alpha=n\in\mathbb{N}}{\Gamma(n)}&=(n-1)\Gamma(n-1)=(n-1)(n-2)\Gamma(n-2)\ldots=(n-1)(n-2)\ldots\overset{=1}{\Gamma(1)} \\
\Gamma(1)&= \int_0^\infty e^{-y}\ dy=-e^{-y}|_0^\infty=1
\end{align}$$
2) $E[X]$, $Var(X)$ $$\begin{align}
&\Gamma(\alpha)=(\alpha-1)\Gamma(\alpha-1)\quad (oppure\ \Gamma(\alpha+1)=\alpha\Gamma(\alpha))
\end{align}$$$$\begin{align}
E[X]&=\int_0^\infty x f_x(x)\ dx= \int_0^\infty x \frac{\lambda e^{-\lambda x}(\lambda x)^{\alpha-1}}{\Gamma(\alpha)}\ dx=\frac{1}{\lambda\Gamma(\alpha)}\int_0^\infty e ^{-\lambda x}(\lambda x)^\alpha\lambda\ dx \\
&\overset{\lambda x= y}{=} \frac{1}{\lambda\Gamma(\alpha)}\underset{\Gamma(\alpha+1)}{\int_0^\infty e^{-y}y^\alpha\ dy}= \frac{\Gamma(\alpha+1)}{\lambda\Gamma(\alpha)}\overset{1)\Rightarrow\Gamma(\alpha+1)=\alpha\Gamma(\alpha)}{=} \frac{\alpha}{\lambda}
\end{align}$$ $$\begin{align}
Var(X)&=E[X^2]-(E[X])^2 \\
E[X^2]&=\int_0^\infty x^2 \frac{\lambda e^{-\lambda}(\lambda x)^{\alpha-1}}{\Gamma(\alpha)}\ dx= \frac{1}{\lambda\Gamma(\alpha)}\int_0^\infty \lambda^2x^2e^{-\lambda x}(\lambda x)^{\alpha-1}\ dx \\
&=\frac{1}{\lambda^2\Gamma(\alpha)}=\int_0^\infty e^{-\lambda x}(\lambda x) ^{\alpha+1}\lambda\ dx \overset{\lambda x=y}{=} \frac{1}{\lambda^2}\Gamma(\alpha)\int_0^\infty e ^{-y}y^{\alpha+1}\ dy = \frac{\Gamma(\alpha+2)}{\lambda^2+\Gamma(\alpha)} \\
&=\frac{\alpha(\alpha+1)}{\lambda^2}
\end{align}$$ $$Var(X)=\frac{\cancel{\alpha^1}+\alpha}{\lambda^2}- \left( \frac{\alpha}{\lambda} \right)^2=\frac{\alpha}{\lambda^2}$$

$$f_x(x)=\begin{cases}
\lambda e^{-\lambda x} & x\ge0 \\
0 & x<0
\end{cases}$$Caso particolare della distribuzione gamma $\Gamma(1)=1$ ($\alpha=1$) $$\begin{align}
&F_x(a)\overset{def}{=} P\{X\le a\}=-\int_0^a-\lambda e^{-\lambda x}\ dx=-e^{-\lambda x}|_0^a=\underset{a\ge0}{-e^{\lambda a}}+1 \\
& F_x(a)=1-e^{-\lambda a} \\
&E[X^n]= \frac{n}{\lambda} E[X^{n-1}]
\end{align}$$
### Osservazione
Se $X$ ha distribuzione esponenziale, $s>0$, allora vale $$P\{X>s+t|X>t\}=P\{X>Ss\}$$
Proprietà di assenza di memoria $$P\{X>s+t|X>t\}\overset{def}{=} \frac{P(\{X>s+t\}\cap \{X>t\})}{P\{X>t\}}=\frac{P\{X>s+t\}}{P\{X>t\}}$$ $$\frac{P\{X>s+t\}}{P\{X>t\}}= P\{X>s\}\Longrightarrow P\{X>s+t\}=P\{X>s\}P\{X>t\}$$ $$\begin{align}
&P\{X>s+t\}=e^{-\lambda(s+t)}=\int_{s+t}^\infty \lambda e^{-\lambda x}\ dx=-\lambda e^{\lambda x}|_{s+t}^\infty=\underset{=P\{X>s\}}{e^{-\lambda s}}\underset{=P\{X>t\}}{e^{-\lambda t}}
\end{align}$$
$\begin{cases}\lambda e^{-\lambda x} & x\ge0 \\ 0 & altrimenti\end{cases}$
# Leggi Congiunte di Variabili Aleatorie
$(x,y)$ si parla di *Distribuzione Congiunta* di $X$ e $Y$ $$
F_{X,Y}(a,b)=P\{X\le a, Y\le b\}$$
$$\begin{align}
F_X(a)&=P\{X\le a\}=P\{X\le a, Y<\infty\}
=P(\lim_{b\to\infty}\{ X\le a, Y\le b\}) \\
&=\lim_{b\to\infty}P\{X\le a, Y\le b\} 
\end{align}$$
$E_n$ successione (crescente $(\lim_{n\to\infty}E_n=\cup_{i=1}^\infty E_i)$ o decrescente $(\lim_{n\to\infty} E_n=\cap^\infty_{i=1} E_i)$ di eventi) $$\lim_{n\to\infty} P(E_n)=P(\lim_{n\to\infty} E_n)$$(La probabilità è una funzione di insieme continua)$$=\lim_{b\to\infty}F(a,b)=F(a, \infty)$$
### Esempio
Nota $F_{x,y}$, determinare $P\{X>a, Y>b\}$ $$\begin{align}
&=1-P(\overset{(\{X>a\}\cap\{Y>b\})^c}{\{X>a, Y>b\}^c})=1-P(\{X>a\}^c\cup\{Y>b\}^c) \\
&=1-P(\{X\le a\}\cup \{Y\le b\})=1-(P\{X\le a\}+P\{Y\le b\}-P\{X\le a, Y\le b\}) \\
&=1-P\{X\le a\}-P\{Y\le b\}+P\{X\le a,Y\le b\}=1-F_x(a)-F_y(b)+F_{x,y}(a,b)
\end{align}$$
##### Caso Discreto
è utile considerare la densità $p$ $$p(x,y)\overset{def}{=}P\{X=x, Y=y\}$$ Densità congiunta $$\begin{align}
&p_X(x)=P\{X=x\}=\sum_{y:p(x,y)>0}p(x,y) \\
&p_Y(y)=P\{Y=y\}=\sum_{x:p(x,y)>0}p(x,y)
\end{align}$$
### Esempio (Caso Discreto)
3 palline da un'urna (12 totali)
	3   R
	4   W
	5   B
$X=$ numero di palline rosse, $Y=$ numero di palline bianche $$\begin{align}
&p(i,j)=P\{X=i, Y=j\} \\
&p(0,0)= \frac{\begin{pmatrix}
5 \\
3
\end{pmatrix}}{\begin{pmatrix}
12 \\
3
\end{pmatrix}}=\frac{10}{220} \\
&p(1,0)=\frac{\begin{pmatrix}
3 \\
1
\end{pmatrix}\cdot\begin{pmatrix}
5 \\
2
\end{pmatrix}}{\begin{pmatrix}
12 \\
3
\end{pmatrix}}= \frac{30}{220} \\
&\vdots
\end{align}$$
![[Pasted image 20250111012325.png]]
### Definizione
$X$, $Y$ si dicono congiuntamente continue se esiste una $f=f(x,y)$ integrabile t.c. per ogni sottoinsieme $C$ di $\mathbb{R}^2$ $$P\{(X,Y)\in C\}=\iint_C f(x,y)\ dxdy$$se  $C=\{(x,y\in\mathbb{R}^2:x\in A,y\in B\}$ $$P\{X\in A, Y\in B\}=\int_B\int_A f(x,y)\ dxdy$$
Per definizione: $$F_{X,Y}(a,b)\overset{def}{=}P\{X\in\overset{X\le a}{(-\infty,a]},Y\in\overset{Y\le b}{Y\in(-\infty,b]}\}=\int_{-\infty}^a\int_{-\infty}^b f(x,y)\ dx$$Differenziando $$f_{x,y}(a,b)=\frac{\partial^2}{\partial a \partial b}F_{X,Y}(a,b)$$
### Esempio
La densità congiunta di $X$ e $Y$ è data da $$ f_{X,Y}(x,y)\begin{cases}
2e^{-x}e^{-2y} & x>0 \ e \ y>0 \\
0 & altrimenti
\end{cases}$$Calcolare 
1) $P\{X>1, Y<1\}$ $$\begin{align}
P\{X>1,Y<1\}&\overset{def}{=}\int_0^1\int_1^\infty 2e^{-x}e^{-2y}\ dx = \int_0^1 2e^{-2y}\int_1^\infty e^{-x}\ dxdy  \\
&= e^{-1}\int_0^1 2e^{-2y}\ dy= e^{-1}(1-e^{-2})
\end{align}$$
2) $P\{X<Y\}=\iint_D f_{X,Y} (x,y)\ dxdy$ $$D=\{(x,y):0<x<y\}=\{(x,y):y>0,0<x<y\}=\int_0^\infty\int_0^y 2e^{-x}e^{-2y}\ dxdy$$

Se $X$, $Y$ sono congiuntamente continue $$P\{X\in A\}=P\{P\in A, Y\in (-\infty,\infty)\}=\int_A\int_{-\infty}^\infty f_{X,Y}(x,y)\ dy\ dx = \int_A f_X(x) \ dx$$dove 
	$f_X(x)=\int_{-\infty}^{\infty} f_{X,Y}(x,y)\ dy$ Densità marginale di $X$
	$f_Y(y)=\int_{-\infty}^\infty f_{X,Y}(x,y)\ dx$ Densità marginale di $Y$
### Proposizione
Se $X$, $Y$ sono discrete e hanno densità congiunta $p(X,Y)$ $$E[g(X,Y)]=\sum_y\sum_x g(x,y)p(x,y)\quad \left(E[g(x)]\overset{def}{=} \sum_x g(x)p(x)\right)$$Se $X$, $Y$ sono continue con densità congiunta $f_{X,Y}$ $$E[g(x,y)]=\int_{-\infty}^\infty \int_{-\infty}^{\infty} g(x,y)f_{X,Y}(x,y)\ dxdy$$
(nel secondo caso si assume che $\iint|g|f_{X,Y}<\infty$)
# Variabili Aleatorie Indipendenti
### Definizione
$X$, $Y$ sono continue. Si dicono *Indipendenti* se per ogni coppia di sottoinsiemi della retta reale $A$ e $B$ $$P\{X\in A, Y\in B\}=P\{X\in A\}P\{X\in B\}$$In altre parole, $X$ e $Y$ sono indipendenti se, $\forall A, B\subseteq \mathbb{R}$, gli eventi $E_A=\{X\in A\}$ e $F_B=\{Y\in B\}$ sono indipendenti.
- Se $X,Y$ sono indipendenti se $$p(x,y)=P_X(x)\cdot P_Y(y)$$
#### Disuguaglianze Notevoli
### Proposizione (Caso Continuo)
Se $X$ v.a. che assume valori non negativi e $a>0$ 
	$P\{X\ge A\}\le \frac{E[X]}{a}$ (Dis. di Markov)
Se $X$ v.a. con media $\mu$ e varianza $\sigma^2$ 
	$P\{|x-\mu|\ge\eta\}\le \frac{Var(X)}{y^2}$ (Dis. di Chebyshev)

### Esempio 1
$$\begin{align}
&\lim_{(x,y)\to (1,0)} \frac{\overset{(x-1)^2}{(x^2-2x+1)}y}{(x^2-2x+1+y^2)^\alpha},\quad \alpha>0 \\
&x=1+\rho\cos\theta \\
&y=\rho\sin\theta \\
\end{align}$$
$$\begin{align}
\rho(1+\rho\cos\theta,\rho\sin\theta)= &\frac{\rho^2\cos^2\theta\rho\sin\theta}{\rho^2\alpha}=\rho^{3-2\alpha}\cos^2\theta\sin\theta\overset{\rho\to 0}{\to}3-2\alpha>0 \\
&\begin{matrix}
0<\alpha< \frac{3}{2} & l=0 \\
\alpha=\frac{3}{2} & g(\rho,\theta)\ dipende \ da \ \theta \ \nexists l \\
\alpha> \frac{3}{2} & g(\rho,\theta)\to\infty
\end{matrix}
\end{align}$$
### Esempio 2
$$f(x,y)=\begin{cases}
\frac{(\sin\sqrt{xy})^2}{y} & x>0,y>0 \\
x & altrimenti
\end{cases}$$
1) $f$ è continua in tutti i punti fuori dagli assi perché composizione e prodotto di funzioni continue $$\begin{align}
&(x_0,0)\quad (0,y_0) \\
&(\sin\sqrt{z})^2=z+o(z),\ z\to0 \\
&\lim_{(x,y)\to(x_0,0)} \frac{(\sin(\sqrt{xy}))^2}{y}=x_0\quad f\ continua \ in \ (x_0,0) \\
&f(x_0,0)\overset{def}{=} x_0  \\
&\lim_{(x,y)\to (0,y_0)} \frac{\sin^2(\sqrt{xy})}{y}=0 \quad f \ continua\ in \ (0,y_0) \\
&f(0,y_0)=0
\end{align}$$
2) Differenziabilità in $(0,0)$ $$\begin{align}
&\begin{matrix}
f_X(0,0)  & f(x_0,0)=x_0  & \overset{def}{\Longrightarrow}  &  f_X(0,0)=1 \\
f_Y(0,0)  & f(0,y_0)=0  & \Longrightarrow  &  f_y(0,0)=0
\end{matrix} \\
&\lim_{(h,k)\to(0,0)} \frac{f(h,k)-f(0,0)-f_X(0,0)h-f_Y(0,0)k}{\sqrt{h^2+k^2}}=0 \\
&\lim_{(h,k)\to(0,0)} \frac{(\sin\sqrt{hk})^2-0-1\cdot h-0\cdot k}{\sqrt{h^2k^2}}=\lim_{(h,k)\to(0,0)} \frac{(\sin\sqrt{hk})^2-hk}{k\sqrt{h^2+k^2}}=0 \\
& (\sin\sqrt{z})^2-z=\left( \sqrt{z}- \frac{(\sqrt{z})^3}{6}+ o(z^2) \right)^2-z=-\frac{1}{3}z^2+o(z^2) \\
&\lim_{(h,k)\to(0,0)} \frac{-\frac{1}{3}h^2k^2}{k\sqrt{h^2+k^2}} \\
&f(\rho\cos\theta,\rho\sin\theta)=\ldots
\end{align}$$
### Esempio 3
$$f(x,y)=x^3+y^3-6(x^2-y^2)$$
1) $$\begin{align}
&\nabla f(x,y)=(3x^2-12x,3y^2+12y)=(0,0) \\
&(0,0),\ (4,0),\ (0,-4),\ (4,-4)
\end{align}$$
2) $$\begin{align}
& f(t,0)=t^3-6t^2=g_1(t)\quad  \ in \ t=0\ max\ locale \\
& f(0,t)=t^3+6t^2= g_2(t)\quad \ in \ t=0\ min\ locale
\end{align}$$
3) $$\begin{align}
&f(z+h)=f(z)+\underset{=0}{\cancel{\nabla f(z)\cdot h}}+ \frac{1}{2} Hf(z)h\cdot h+o(|h|^2)\quad z=(4,0) \\
&H_f(x,y)=\begin{pmatrix}
6x-12  & 0 \\
0 & 6y+12
\end{pmatrix} \\
&H_f(4,0)=\begin{pmatrix}
12  & 0 \\
0  &  12
\end{pmatrix}\quad H_f(4,0)h\cdot h=\begin{pmatrix}
12 & 0 \\ 0 & 12
\end{pmatrix} h\cdot h \\
& f(z+h)-f(z)= \frac{1}{2}12|h|^2+o(|h|^2)= 6|h|^2+o(|h|^2)
\end{align}$$
4) $$\begin{align}
&(0,-4),\ (4,-4) \\
& H_f(0,-4)=\begin{pmatrix}
-12 & 0 \\
0 & -12
\end{pmatrix}\quad (0,-4)\ max\ locale \\
&H_f(4,-4)=\begin{pmatrix}
-12 & 0 \\
0 & 12
\end{pmatrix}\quad (4,-4) \ sella 
\end{align}$$
### Esempio 4
$$\begin{align}
&\iint_D y\ dxdy \\
&x^2-6x+y^2\le 0 \ e \ y\ge0 \\
&(x-3)^2+y^2\le 9 \ e \ y\ge0 \\
&\begin{cases}
x=\rho\cos\theta \\
y=\sin\theta
\end{cases}\quad \iint_\overset{\sim}{D} \rho\sin\theta\rho\ d\rho d\theta=18 \\
&\overset{\sim}{D}=\left\{ (\rho,\theta):0\le\rho\le6\cos\theta, \ 0\le\theta\le \frac{\pi}{2}  \right\} \\
& x=3+\rho\cos\theta,\ y=\rho\sin\theta\quad 0\le\rho\le 3,\ 0\le\theta\le \pi
\end{align}$$
![[Pasted image 20250111174731.png]]
### Esempio
Si suppone che il numero di prodotti di un'industria in una settimana sia una v.a. con media 50 ($X=$ numero aleatorio degli articoli prodotti in una settimana)
1) Cosa si può dire riguardo la probabilità che la produzione della settimana superi 75 prodotti? $$\begin{align}
&P\{X>75\}\overset{dis.\ di\ Markov}{\le} \frac{E[X]}{75}= \frac{50}{75}=\frac{2}{3} \\
&P\{X>a\}\le \frac{E[X]}{a}
\end{align}$$
2) Se la varianza della produzione settimanale è 25, cosa si può dire riguardo la probabilità che in questa settimana la produzione sia compresa tra 40 e 60 $$\begin{align}
&P\{40<X<60\}=P\{-10<X-50<10\}=P\{|X-50|<10\} \\
&P(\{|X-50|<10\})=1-P\{|X-50|\ge 10\} \\
&P\{|X-50|\ge \overset{y}{10}\}\overset{dis. \ di \ Chebysev}{\le} \frac{Var(X)}{\underset{y^2}{100}}= \frac{25}{100}= \frac{1}{4} \\
&P\{|X-50|<10\}=1-P\{|X-50|\ge10\}\ge1- \frac{1}{4}= \frac{3}{4} \\
\end{align}$$
