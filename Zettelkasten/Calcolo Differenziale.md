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

![[Pasted image 20241213165210.png]]
Piano $y=y_0\rightsquigarrow$ curva $z=f(x,y_0)$
Piano $x=x_0\rightsquigarrow$ una curva $z=f(x_0,y)$
Il piano tangente è individuato da $r_1$ e $r_2$ 
L'equazione di $r_1$ nello spazio $$\begin{cases}
z=f(x_0,y_0)+\partial_xf(x_0,y_0)(x-x_0) \\
y=y_0
\end{cases}$$L'equazione di $r_1$ nel piano $y=y_0$ è $$z=f(x_0,y_0)+\partial_xf(x_0,y_0)(x-x_0)$$Per $r_2$ vale lo stesso discorso:$$\begin{cases}
z=f(x_0,y_0)+\partial_yf(x_0,y_0)(y-y_0) \\
x=x_0
\end{cases}$$Il piano che contiene entrambe le rette ha equazione $$z=f(x_0,y_0)+\partial_xf(x_0,y_0)(x-x_0)+\partial_yf(x_0,y_0)(y-y_0)$$Il piano (costruito con un ragionamento grafico) non è tangente alla superficie:$$\begin{align} \\
&f(x,y)=
\begin{cases}
\frac{xy}{x^2+y^2} & (x,y)\ne(0,0) \\
0 & (x,y)=(0,0)
\end{cases} \\
& \partial_xf(0,0)=0=\partial_yf(0,0)
\end{align}$$$\overset{piano \ xy}{z=0}$ usando la formula di prima $\rightarrow f\big|_{y=x} \frac{1}{2}\Rightarrow$ localmente $z=0$ non approssima $f$.

In conclusione la sola derivabilità non implica né la continuità né l'esistenza del piano tangente.

## Differenziabilità
$n=1$
$$\begin{align}
&g'(t)=\lim_{h\to0} \frac{g(t+h)-g(t)}{h} \\
&g(t+h)-g(t)=g'(t)h+o(h), \ h\to 0
\end{align}$$
	L'incremento della funzione coincide con l'incremento lungo la retta tangente e questi differiscono per un infinitesimo di ordine superiore a $h$.
$n=2$ 0 $n>1$
	Ci si aspetta che l'incremento di $f$ sia uguale all'incremento calcolato lungo il piano tangente più un infinitesimo di ordine superiore alla lunghezza $(h,k)$.$$\small 
	\underset{incremento \ di \ f}{f(x_0+h,y_0+k)-f(x_0,y_0)}=\overset{incremento \ lungo \ il \ piano \ tangente}{\frac{\partial f}{\partial x}(x_0,y_0)(x-x_0)+ \frac{\partial f}{\partial y}(x_0,y_0)(y-y_0)}+\underset{

\begin{align}
&errore \ infinitesimo \ di \ ordine \\
& superiore\ a\ |(h,k)|
\end{align}
	
	}{o(\sqrt{h^2+k^2})}
	$$^8607d7 ^3ca816
>**DEFINIZIONE**
	Se vale la condizione precedente, si dice che $f$ è *Differenziabile* in $(x_0,y_0)$.
	Se $f:A\subseteq\mathbb{R}^n\to\mathbb{R}$ ($A$ aperto) e $x_0\in A$, $f$ è differenziabile se esiste $a\in\mathbb{R}^n$ t.c.$$ 
	f(x_0+h)-f(x_0)=\underset{\in\mathbb{R}^n}{a}\cdot h+o(|h|), \ h\to 0
	$$

>**PROPOSIZIONE**
	Se $f$ è differenziale in $x_0\in\mathbb{R}^n$, allora 
		1) è derivabile in $x_0$ e $a=\nabla f(x_0)$
		2) è continua in $x_0$

>**DIMOSTRAZIONE**
	Si prendono $h=he_i$ con $h$ piccolo (incremento solo lungo un asse coordinato), $a=(a_1,\ldots,a_n)$$$
	\begin{align}
&\lim_{h\to0} \frac{f(x_0+he_i)-f(x_0-a_ih)}{h}=\iff \\
& \underset{\underset{def}{=} \frac{\partial f}{\partial x_i}(x_0)}{\lim_{h\to0} \frac{f(x_0+he_i)-f(x_0)}{h}=a_i}\Longrightarrow a_i= \frac{\partial f}{\partial x_i}(x_0)
\end{align}
	$$$f$ è derivabile in $x_0$ e $a=\nabla f(x_0)$. Questo dimostra 1).
	Per 2):$$f(x_0+h)-f(x_0)=a\cdot h+o(|h|)\quad per \ h\to0$$Se $h\to0$ il la to destro tende a $0$$$f(x_0+h)\to f(x_0)\Longrightarrow f \ continua \ in \ x_0$$

>**OSSERVAZIONE**
	Il viceversa non è vero $$continua\cancel{\Longrightarrow}differziabilta'$$

>**ESEMPIO**
	$f(x,y)=|x|$ è continua in $(0,0)$, ma $\partial_xf(0,0)\nexists$ (non si può scrivere [[Calcolo Differenziale#^8607d7|*]])  

>**OSSERVAZIONE**$$derivabilita'\cancel\Longrightarrow differenziabilita'$$

>**ESEMPIO**$$f(x,y)=\begin{cases}
\frac{xy}{x^2+y^2} & (x,y)\ne(0,0) \\
0 & (x,y)=(0,0)
	\end{cases}$$
	$f$ è differnziabile se vale [[Calcolo Differenziale#^3ca816|*]], cioè $$
	L=\lim_{(h,k)\to(0,0)} \frac{\frac{hk}{h^2+k^2}-0-h\cdot0-k\cdot0}{\sqrt{h^2+k^2}}=\lim_{(h,k)\to(0,0)} \frac{hk}{(h^2+k^2)\sqrt{h^2k^2}}\quad\nexists
	$$

>**DEFINIZIONE**
	Se $f$ è differenziabile in $(x_0,y_0)$ si dice *Differenziale* di $f$ in $(x_0,y_0)$ l'applicazione lineare $$\begin{align}
df(x_0,y_0)&:\mathbb{R}^2\to\mathbb{R} \\
df(x_0,y_0)&:(h,k)\mapsto\nabla \underset{\in\mathbb{R}}{f(x_0,y_0)\cdot(h,k)}
\end{align}$$

>**OSSERVAZIONE**
	La quantità di $\nabla f(x_0,y_0)\cdot(0,0)$ rappresenta l'incremento della funzione nel passare da $(x_0,y_0)$ a $(x_0+h,y_0+k)$ lungo il piano tangente a $f$ in $(x_0,y_0)$

>**TEOREMA (Condizione Sufficiente di Differenziabiltà)**
	$f:A\subseteq\mathbb{R}^2\to\mathbb{R}, \ A \ aperto$
	$$f\in\underset{\begin{align}
&le \ derivate \ parziali \ esistono \\ &e \ sono \ continue \ in \ A
\end{align}} {C'(A)}\Longrightarrow f\ differenziabile \ in A$$
>**OSSERVAZIONE**
	Il viceversa non vale, infatti la funzione $$f(x,y)=\begin{cases}
(x^2+y^2)\sin\left(  \frac{1}{x^2+y^2} \right) & in \ (x,y)\ne(0,0) \\
0 & in \ (x,y)=(0,0)
\end{cases}$$Se $(x,y)\ne(0,0)$ $$\begin{align}
&\frac{\partial f}{\partial x}\underset{(x,y)\in\mathbb{R}^2}{(x,y)}=2x\sin\left( \frac{1}{x^2+y^2} \right)+(x^2+y^2)\cos\left( \frac{1}{x^2+y^2} \right)\left( -\frac{2x}{x^2+y^2} \right) \\
& \frac{\partial f}{\partial x}(0,0)=\lim_{h\to0} \frac{f(0+h,0)-f(0,0)}{h}=\lim_{h\to0} \frac{h^{\cancel{2}}\sin \frac{1}{h^2}}{\cancel h}=0 
\end{align}$$Similmente: $$\frac{\partial f}{\partial y}, \quad \frac{\partial f}{\partial y}(0,0)=0$$Si valuta se $f$ è differenziabile ([[Calcolo Differenziale#^3ca816|*]]) $$\begin{align}
&\lim_{(h,k)\to(0,0)} \frac{f(h,k)-f(0,0)-h\partial_x f(0,0)-k\partial_yf(0,0)}{\sqrt{h^2+k^2}}= \\
& \lim_{(h,k)\to(0,0)} \frac{(h^2+k^2)\sin\left( \frac{1}{h^2+k^2} \right)-0-h\cdot0-k\cdot0}{\sqrt{h^2+k^2}}= \\
&\lim_{(h,k)\to(0,0)} \sqrt{h^2+k^2}\sin\left( \frac{1}{h^2+k^2}\right) \underset{\underset{0\le|\sqrt{h^2+k^2}\sin\left( \frac{1}{h^2+k^2} \right)|\le\sqrt{h^2+k^2}\to0}{T. \ del \ confronto}}{=}0 \\
&\partial_x f(x,y) = 2x\sin\left( \frac{1}{x^2+y^2} \right)- \frac{2x}{x^2+y^2}\cos\left( \frac{1}{x^2+y^2} \right) \\
&\lim_{(x,y)\to(0,0)}\partial_xf(x,y) \ \nexists 
\end{align}$$

>**ESEMPIO**$$f(x,y)=\arctan\sqrt{4x^2+y^2}$$
	Calcolare $\nabla f(0,1)$, scrivere l'equazione del piano tangente in $(0,1)$. Calcolare, se esistono, le derivate parziali in $(0,0)$ $$\begin{align}
& \partial_xf=\frac{1}{1+(4x^2+y^2)} \frac{1}{2\sqrt{4x^2+y^2}}\cdot8x \\
& \partial_y f= \frac{1}{1+(4x^2+y^2)} \frac{1}{2\sqrt{4x^2+y^2}}\cdot 2y
\end{align}$$Sono continue in $\mathbb{R}^2\backslash\{(0,0)\}$. $f\in C'(\mathbb{R}^2\backslash\{0\})$ è differenziabile in $(0, \frac{1}{2})$ $$\nabla f(0,1)=\left( 0, \frac{1}{2} \right)$$Piano tangente: $$\begin{align}
& z=f(0,1)+\partial_xf(0,1)(x-0)+\partial_yf(0,1)(y-1)= \\
& \frac{\pi}{4}+0+\frac{1}{2}(y-1)= \\
& \frac{\pi}{4}+\frac{1}{2}(y-1)
\end{align}$$In (0,0) $$\begin{align}
&\frac{\partial_f}{\partial x}=\lim_{h\to0} \frac{f(h,0)-f(0,0)}{h}=\lim_{h\to0} \frac{\arctan\sqrt{4h^2}}{h} \\
& \lim_{h\to0} \frac{\arctan2|h|}{h}=\begin{cases}
2 & h\to0^+ \\
-2 & h\to0^-
\end{cases}
\end{align}$$Si verifica lo stesso per $\frac{\partial f}{\partial y}$

CONDIZIONE SUFFICIENTE DI DIFFERENZIABILITÀ $f:A\in\mathbb{R}^2\to\mathbb{R}$ A aperto, $f\in C'(A)\Longrightarrow$ f differnziabile.
$$f(x,y)=xy^{\frac{1}{3}}$$In quali punti è differenziabile? $$\begin{align}
&\partial_xf=y^{\frac{1}{3}} \ definita \ e \ continua \ su \ \mathbb{R}^2  \\
&\partial_yf=\frac{1}{3}xy^{-\frac{2}{3}} \quad y\ne 0
\end{align}$$$A=\{(x,y)\in\mathbb{R}^2: \ y\ne0\}$ aperto. In $A$, $f\in C'(A)\Longrightarrow f$ è differenziabile per il criterio.
In $(x_0,0), \ x_0\in\mathbb{R}$, si deve calcolare $\partial_yf$ con la definizione.
Per $x_0\ne0$ $$\partial_yf(x_0,0)=\partial_y(x_0y^{\frac{1}{3}})\big|_{y=0}\underset{x_0\ne0}{=}x_0\partial_y(y^{\frac{1}{3}})\big|_{y=0} \ \nexists$$Per $x_0=0$ $$\partial_yf(0,0)=\partial_y(0\cdot y^{\frac{1}{3}})\big|_{y=0}=0$$
- In $A$ è differenziabile
- In $(x_0,0),  \ x_0\ne0$, $f$ non  è derivabile $\Longrightarrow f$ non è differenziabile
- In $(0,0)$, $f$ è derivabile
	$f(0,0)=\partial_xf(0,0)=\partial_yf(0,0)=0$ 
Non si può applicare il criterio in un aperto contenente $(0,0)$, quindi si usa la definizione $$\begin{align}
&f(\underset{=0}{x_0}+h,y_0+k)-\underset{=0}{f(x_0,y_0)}-\underset{=0}{\partial_xf(x_0,y_0)}h-\underset{=0}{\partial_yf(x_0,y_0)}k=o(\sqrt{h^2+k^2}) \\
&f(h,k)=o(\sqrt{h^2+k^2}) \quad per \ (h,k)\to(0,0) \\ & hk^{\frac{1}{3}}=o(\sqrt{h^2+k^2})
\end{align}$$
$$\lim_{(h,k)\to(0,0)} \frac{hk^{\frac{1}{3}}}{\sqrt{h^2+k^2}}\overset{?}{=}0$$$f$ è differenziabile in $(0,0)$, usando le coordinate polari: $$\begin{cases}
h=\rho\cos\theta \\
k=\rho\sin\theta
\end{cases} \quad \frac{\rho\cos\theta(\rho\sin\theta)^{\frac{1}{3}}}{\rho}\le\ldots\le \underset{\to0}{g(\rho)}$$
## Derivate Direzionali
$\partial_{x_i}\rightsquigarrow$ velocità di crescita lungo gli assi $x_i$
$x_0$, spostamento lungo un versore $v$ uscente da $x_0$ $$x=x_0+tv,\quad t\in\mathbb{R}$$(se $v=e_i$ lo spostamento è lungo $x_i$)
Incremento $f(x_0+tv)-f(x_0)$

>**DEFINIZIONE**
	$f:A\subseteq\mathbb{R}^2\to\mathbb{R}$ aperto, $x_0\in A$, $v$ versore.
	Si dice *Derivata Direzionale* di $f$ rispetto a $v$ nel punto $x_0$ $$D_vf(x_0)=\lim_{t\to0} \frac{f(x_0+tv)-f(x_0)}{t}$$Purché esiste finito
	$g(t)=f(x_0+tv), \quad \mathbb{R}\to\mathbb{R}$ è equivalente a chiedere $$D_vf(x_0)=g'(0)$$

>**OSSERVAZIONE** (n=2)
	$v=(\cos\theta, \sin\theta)$ $$\begin{align}
&D_vf(x_0,y_0)=\lim_{t\to0} \frac{f(x_0+t\cos\theta,y_0+t\sin\theta)-f(x_0,y_0)}{t} \\
&g(t)= f(x_0+t\cos\theta,y_0+t\sin\theta) \\
&D_vf(x_0,y_0)= g'(0)
\end{align}$$

>**ESEMPIO**
	- $f(x,y)=xe^{xy}\quad D_vf(0,0)$ per $v$ generico $$\begin{align}
&v=(\cos\theta,\sin\theta) \\
& g(t)=f(t\cos\theta, t\sin\theta)=t\cos\theta e^{t^2\cos\theta\sin\theta)} \\ 
&\begin{aligned}g'(t)=&\cos\theta  e^{t^2\cos\theta\sin\theta}+t\cos\theta(2t\cos\theta\sin\theta)e^{t^2\cos\theta\sin\theta}= \\
=&\cos\theta e^{t^2\cos\theta\sin\theta}(1+2t^2\sin\theta\cos\theta) \end{aligned} \\
&D_vf(0,0)=g'(0)=\cos\theta
	\end{align}$$Se $\theta=\frac{\pi}{4}\Longrightarrow v=\left( \frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2} \right)$ $$D_vf(0,0)\underset{\theta=\frac{\pi}{4}}{=} \frac{\sqrt{2}}{2}$$
	- $f(x,y)=\sqrt[3]{x^2y} \quad D_vf(0,0)$ $$\begin{align}
& v=(\cos\theta,\sin\theta) \\
&g(t)=f(t\cos\theta,t\sin\theta)=\sqrt[3]{t^2\cos^2\theta t\sin\theta}=t(\cos\theta)^{\frac{2}{3}}(\sin\theta)^{\frac{1}{3}} \\
&D_vf(0,0)=\overset{def.}{=}g'(0)=(\cos\theta)^{\frac{2}{3}}(\sin\theta)^{\frac{1}{2}}\quad \begin{matrix}
\small{v=e_1=(1,0}) \\
\small{v=e_2=(0,1)}
\end{matrix}
\end{align}$$La funzione ha tutte le derivate direzionali in $(0,0)$ (non nulle) $$0=\partial_x f(0,0)=\partial_y f(0,0)$$Verificare con la definizione che $f$ non è differenziabile in $(0,0)$ (anche con la formula successiva)

>**TEOREMA (Formula del Gradiente)**
	$f:A\subseteq\mathbb{R}^n\to\mathbb{R}$, $A$ aperto, $f$ differenziabile in $x_0\in A$.
	Allora per ogni versore $v$ esiste $D_vf(x_0)$ e vale $$D_vf(x_0)=\nabla f(x_0)\cdot v=\sum^n_{i=1} \frac{\partial f}{\partial x_i}(x_0)v_i$$Per $n=2$: $$\begin{align}
D_vf(x_0,y_0)&=\left( \frac{\partial f}{\partial x}(x_0,y_0), \frac{\partial f}{\partial y}(x_0,y_0) \right)\cdot (\cos\theta,\sin\theta)= \\
&= \left( \frac{\partial f}{\partial x}(x_0,y_0)\cos\theta+ \frac{\partial f}{\partial y}(x_0,y_0)\sin\theta \right)
\end{align}$$ ^43dc1d

>**OSSERVAZIONE**
	Nell'esempio precedente $$\partial_xf(0,0)=\partial_y(0,0)=0$$il lato destro di [[Calcolo Differenziale#^43dc1d|*]] =0, quindi non vale la formula del gradiente e $f$ non è differenziabile.

**DIMOSTRAZIONE**
	- $f$ differenziabile $\Longrightarrow f(x_0+h)-f(x_0)=\nabla f(x_0)\cdot h+o(|h|)\quad h\to0$ $$\begin{align}
&h=tv\quad t\ne0,\quad v\ versore \Longrightarrow |h|=|tv|\overset{|v|=1}{=}|t| \\
& f(x_0+tv)-f(x_0)=\nabla f(x_0)\cdot tv+o(|t|) \\
& \underset{\overset{def.}{=}D_vf(x_0)}{\lim_{t\to0} f(x_0) \frac{f(x_0+tv)-f(x_0)}{t}}=\underset{=\nabla f(x_0)\cdot v= \sum^n_{i=1} \frac{\partial f}{\partial x_i}(x_0)v_i}{\lim_{t\to0}\nabla f(x_0)\cdot v}+ \frac{o(|t|)}{\underset{\to0}{t}}
\end{align}$$
>**OSSERVAZIONE (Corollario)**
	$D_vf(x_0,y_0)=v\cdot\nabla f(x_0,y_0)=|v||\nabla f(x_0,y_0)|\cos\alpha$, $\alpha$ angolo tra $v$ e $\nabla f(x_0,y_0)$
	$-1\le\cos\alpha\le1\quad D_v f(x_0,y_0)$ assume valori tra $|\nabla f(x_0,y_0)|$ ($v$ punta nella direzione del $\nabla f$) e $-|\nabla f(x_0,y_0)|$ (direzione opposta).
		- $\nabla f$ indica la direzione di massima crescita
		- $-\nabla f$ indica la direzione minima di crescita
	Se $\alpha = \frac{\pi}{2}\quad D_vf(x_0,y_0)=0$ la direzione è quella tangente alle curve di livello, cioè il gradiente è ortogonale alle curve di livello

**RIASSUNTO**
$f\in C'(A)\Longrightarrow$ f differenziabile in $A$ (ha l'iper piano tangente) $\Longrightarrow \begin{cases} f\ continua \ in \ A \\ f \ derivabile \ in \ A \\ f \ ha \ derivate \ direzionali \ e \ vale \ la \ formula \ del \ gradiente \end{cases}$ 
Invece:
- $f$ continua, derivabile, dotata di tutte le derivate direzionali$\Longrightarrow f$  differenziabile
- $f$ derivabile, dotata di tutte le derivate direzionali $\Longrightarrow f$ continua
## Calcolo delle Derivate
>**TEOREMA (Formula di Calcolo delle Derivate)**
	1) $f:A\subseteq\mathbb{R}^2\to\mathbb{R},\ g:I\subseteq\mathbb{R}\to\mathbb{R}$ e si suppone che $h(x)=g(f(x))$ sia definita per almeno un intorno $U$ di $x_0\in A$. Se $f$ è differenziabile in $x_0$ e $g$ è derivabile in $f(x_0)$, allora $$h=g\circ f:U\subseteq\mathbb{R}^n\to\mathbb{R}$$è differenziabile in $x_0$ e vale $$\nabla h(x_0)=g'(f(x_0))\nabla f(x_0)$$
	2) $r:I\subseteq\mathbb{R}\to\mathbb{R}^n, \ f:A\subseteq\mathbb{R}^n\to\mathbb{R}$ e si suppone che la funzione composta $$g(t)=f(r(t))$$sia definita almeno in un intorno $J$ di $t_0\in I$. Se $r$ è derivabile in $t_0$ e $f$ è differenziabile in $r(t_0)$, allora $$g=f\circ r:J\subseteq\mathbb{R}\to\mathbb{R}$$è derivabile in $t_0$ e $$g'(t_0)=\nabla f(r(t_0))\cdot r'(t_0)=\sum^n_{i=1}\partial_{x_i} f(r(t_0))r'_i(t_0)$$
>**APPLICAZIONE**
	a) *Gradiente di una funzione radiale*
		$h(x)=g(|x|)\quad h:\mathbb{R}^n\to\mathbb{R}$ dove $g:[0,+\infty)\to\mathbb{R}$ $$
		\begin{align}
&\left.\begin{matrix}
\rho=|x|=\sqrt{\sum_{j=1}^nx^2_j} \\
\partial_{x_i} = \frac{x_i}{\underset{\rho}{|x|}}=\frac{x_i}{\rho}x\ne0
\end{matrix}\right\}\Longrightarrow\nabla\rho=\left( \overset{1}{\frac{x_1}{\rho}},\ldots, \overset{n}{\frac{x_n}{\rho}} \right)\Longrightarrow|\nabla\rho|=1 \\
 &\small\left( \sqrt{\frac{x_1^2}{\rho^2}+\ldots+ \frac{x_n^2}{\rho^2}}=\sqrt{\frac{\rho^2}{\rho^2}}=1 \right) \\ \\

&1)(T.\ delle \ funzioni \ composte)\Longrightarrow \nabla h(x,y)=\left( \frac{x}{\rho}, \frac{y}{\rho} \right) \frac{d}{d\rho}(2\log\rho) \\
&\quad=\left( \frac{x}{\rho}, \frac{y}{\rho} \right)\cdot \frac{2}{\rho}=\left( \frac{2x}{\rho^2}, \frac{2y}{\rho^2} \right) \\
& |\nabla h(x,y)|=\sqrt{\frac{4x^2}{\rho^4}+\frac{4y^2}{\rho^4}}=\sqrt{\frac{4\rho^2}{\rho^4}}=\frac{2}{\rho}
\end{align}
		$$
	b) *Ortogonalità del gradiente con le curve di livello (vedi oss.)*
		$n=2\quad f:\mathbb{R}^2\to\mathbb{R}$ differenziabile e $\underset{curve \ di \ livello}{f(x,y)=c}$.
		Si suppone che le curve di livello siano descritte da $r=r(t)$ $$
		\begin{align}
&g(t)=f(r(t))\Longrightarrow g(t)=c\ \forall t\Longrightarrow g'(t)=0\Longrightarrow g'(t)=0 \\
&2)\Longrightarrow g'(t)=\nabla f(r(t))\cdot r'(t)=0
\end{align}
		$$$\Longrightarrow$ il gradiente è ortogonale in ogni punto alla linee di livello ($r'(t)$ è tangente alle curve di livello)
	c) *Analogo del Teorema di Lagrange in più variabili* 
		$x_0,x_1\in\mathbb{R}^n$, il segmento di estremi $x_0,x_1$:$$r(t)=tx_0+(1-t)x_1\quad t\in[0,1]$$

>**TEOREMA (del Valore Medio)**
	$A\subseteq\mathbb{R}^n$ aperto, $f:A\to\mathbb{R}$ differenziabile in $A$. Allora per ogni coppia di punti $x_0,x_1\in A$  esiste $x^*\in\underset{sostegno \ di \ r(t)}{[x_0,x_1]}$ t.c.$$f(x_1)-f(x_0)=\nabla f(x^*)\cdot(x_1-x_0)$$

>**DIMOSTRAZIONE**$$g(t)=f(r(t))\quad t\in[0,1]$$
	Applicare a $g(t)$ il teorema di Lagrange in 1 variabile e usare 2)

>**NOTA**
	Sul punto 2) $r:I\to\mathbb{R}^m, \ t_0\in I, \ r$ è derivabile in $t_0$ se esiste finito $$\begin{align}
r'(t_0)=&\lim_{h\to0} \frac{r(t_0+h)-r(t_0)}{h}= \\
&=\left( \lim_{h\to0}  \frac{r_1(t_0+h)-r_1(t_0)}{h},\ldots,\lim_{h\to0} \frac{r_m(t_0+h)-r_m(t_0)}{h}\right) \\
&=(r'_1(t_0),\ldots,r'_m(t_0))
\end{align}$$ 