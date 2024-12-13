Tags: [[Analisi 2 e Probabilità]] [[University]] 

# Derivate Parziali, Piano Tangente, Differenziabilità

Introduzione al concetto di derivate per $f:A\subseteq\mathbb{R}^n\to\mathbb{R}$
	$n=2)\quad(x_0,y_0)\quad f$ è a valori in $\mathbb{R}\quad\frac{f(x_0+f)-f(x_0)}{h}$ 
Si incrementa una variabile alla volta:
	si tiene costante $y=y_0$ e si derivata:
		a) $x\mapsto f(x,y_0)$ e si deriva rispetto ad $x$
			$\frac{\partial f}{\partial x}(x_0,y_0)= \lim_{h\to 0} \frac{f(x_0+h,y_0)-f(x_0,y_0)}{h}$ (derivata parziale rispetto ad $x$)
	viceversa si fissa $x=x_0$:
		b) $y\mapsto f(x_0,y)$ e si deriva rispetto a $x$
			$\frac{\partial f}{\partial x}(x_0,y_0)= \lim_{k\to 0} \frac{f(x_0,y_0+k)-f(x_0,y_0)}{k}$ (derivata parziale rispetto ad $y$)

 >**DEFINIZIONE** 
	 Il vettore che ha per componenti le derivate parziali di $f$ rispetto a $(x_0,y_0)$ si dice *Gradiente* di $f$ in $(x_0,y_0)$ $$\nabla f(x_0,y_0)=(\partial_xf(x_0,y_0), \ \partial_y f(x_0,y_0))$$

>**ESEMPIO**
	$f(x,y)=x^2y^3$  $\partial_x?$ $$\begin{align}
&\partial_x(x^2y^3)=2xy^3 \\
& \partial_xf(1,2)=\partial_xf(x_2)\big|_{x=1}=\partial_x(x^2\cdot8)\big|_{x=1}=16x\big|_{x=1}=16
\end{align}$$

>**ESEMPIO**
	In alcuni casi è necessario applicare la definizione:
		$f(x,y)=y\sqrt{x}\quad\partial_xf(0,0)?$ $$\begin{align}
&\partial_x( y\sqrt{x})= \frac{y}{2\sqrt{x}} \ in \ (0,0) \ \left[ \frac{0}{0} \right] \\
& \partial_x(y\sqrt{x})\big|_{(x,y)=(0,0)}=\partial_x(0\cdot\sqrt{x})\big|_{x=0}=\partial_x(0)=0
\end{align}$$La derivata rispetto a $x$ in $(0,0)$ esiste e vale $0$
	n>1)$$\begin{align} 
\frac{\partial f}{\partial x_i}(x^0)&=\lim_{h\to0} \frac{f(x^0+he_i)-f(x^0)}{h} \ (1)\qquad \begin{matrix}
x^0=(x_1^0,x_2^0,\ldots,x_n^0) \\ e_i=(0,0,\ldots,\underset{i}{1},0,\ldots,0)
\end{matrix} \\
&=\lim_{h\to0} \frac{f(x^0_1,x_2^0,\ldots,x_{i-1}^0+\overset{he_i}{h\cdot1},x_{i+1},\ldots,x_n^0)-f(x_1^0,x_2^0,\ldots,x_n^0)}{h} \ (2)
\end{align}$$

>**OSSERVAZIONE**
	Da qui in avanti $f:A\subseteq\mathbb{R}^n\to\mathbb{R}$ con $A$ aperto.
	Infatti se $A$ è aperto si può calcolare $f(x_0+he_i)$ in modo che $x_0+he_i\in A$

>**DEFINIZIONE**
	$f:A\subseteq\mathbb{R}^n\to\mathbb{R}$ si dice *Derivabile* in un punto del dominio se in quel punto esistono tutte le derivate parziali.
	Se $f$ è derivabile
		$\nabla f(x)=(\partial_{x_1}f(x),\partial_{x_2}f(x),\ldots,\partial_{x_n}f(x)$

>**ESEMPIO**
	- $f:\mathbb{R}^n\to\mathbb{R}, \quad f(x)=e^{-|x|^2}$ $$

	\frac{\partial f}{\partial x}= \frac{\partial}{\partial x_i}\left( e^{-(x_1^2+\ldots+x_n^2)} \right)=-2x_ie^{-(x_1^2)}=-2x_ie^{|x|^2}
	
	$$$f$ derivabile in $\mathbb{R}^n$
	- $f:\mathbb{R}^n\to\mathbb{R}, \quad f(x)=e^{|x|}$$$

\frac{\partial}{\partial x_i}f= \frac{\partial}{\partial x_i}\left(e^{\sqrt{x_1^2+\ldots+e_n^2}}\right)=\frac{1}{\cancel{2}\sqrt{x_1^2+\ldots+x_n^2}}\cancel{2}x_i e^{\sqrt{x_1^2+\ldots+x_n^2}}= \frac{x_i}{|x|}e^{|x|}

$$$f$ derivabile in $\mathbb{R}^n\backslash{0}$. In $x=0$ perde significato, quindi si usa la definizione:$$

\frac{\partial f}{\partial x_i}(0)=\frac{\partial}{\partial x_i}(e^{|x|})\big|_{x=0}\underset{(1) \ o \ (2)}{=} \lim_{h\to 0} \frac{e^{|x|-1}}{h}\rightarrow\nexists

$$Simile per $e^{-|x|}$
	Controparte in $n=1$: $g(t)=e^{-t^2}$ è derivabile ovunque su $\mathbb{R}$, $g(t)=e^{-|t|}$ è derivabile ovunque su $\mathbb{R}^n\backslash{0}$

>**ESEMPIO**$$\begin{align}
&f(x,y)=\begin{cases}
x^2+y^2 & (x,y)\ne(0,0) \\
1 & (x,y)=(0,0)
\end{cases}\quad\partial_x f(0,0) \\
&f(0,0)=1 \ (costante)\cancel\Longrightarrow\partial_x f(0,0)=0 \ (sbagliato) \\
& \frac{\partial f}{\partial x}(0,0)=\lim_{h\to0} \frac{f(0+h,0)-f(0,0)}{h}=\lim_{h\to0} \frac{h^2-1}{h}\rightarrow\nexists\ \small{\left( \begin{cases}
h\to0^+ & -\infty \\
h\to0^- & +\infty
\end{cases}\right)} 
	\end{align}$$$\partial_xf(0,0) \ \nexists\Longrightarrow f$ non è derivabile lungo la direzione dell'asse $x$

Da Analisi 1, $f$ derivabile $\rightarrow$ $f$ continua. Per $n=2$:$$\begin{align}
&f(x,y)=\begin{cases}
\frac{xy}{x^2+y^2} & (x,y)\ne0  \\
0 & (x,y)=(0,0)
\end{cases} \\
& \partial_xf(0,0)=\lim_{h\to0} \frac{f(0+h,0)-f(0,0)}{h}=0\quad \partial_yf(0,0)=\lim_{} \frac{f(0,0+k)-f(0,0)}{k}=0
\end{align}$$$f$ non è continua, infatti $$\lim_{(x,y)\to(0,0)} \frac{xy}{x^2+y^2}\overset{f\big|_{x=y}}{=} \frac{x^2}{2}=\frac{1}{2}$$
>**OSSERVAZIONE**
	$f$ è un esempio di una funzione non continua in un punto per la quale esistono le derivate parizali.
	La nozione di dervabilità è troppo debole per avere le proprietà viste in Analisi 1

DERIVABILITÀ $\rightsquigarrow$ Retta tangente
Più dimensioni ($n=2$) $\rightsquigarrow$ Esiste il piano tangente
	