Tags: [[Analisi 2 e Probabilità]] [[University]] 

>**DEFINIZIONE (Limite di Successione)**
	Data una successione di punti ${\{x_k\}}^\infty_{k=1}$ di $\mathbb{R}^n$. Si dice $$x_k\longrightarrow x_0 \ per \ k\rightarrow +\infty \quad se \ |x_k-x_0|\rightarrow0$$

>**DEFINIZIONE (Limite)**
	1) $f:\mathbb{R}^n\rightarrow\mathbb{R}$ definita almeno in un intorno specifico di $x_0\in\mathbb{R}^n$ (escluso al più $x_0$) sia $L\in\mathbb{R}$ ($L\in\mathbb{R}$ o $L\pm\infty$). Si dice che $$\lim_{x\to+\infty}f(x)=L$$ se, per ogni successione $\{x_k\}$ t.c. $x_k\to x_0$ per $k\to+\infty$ ($x_k\ne x_0\ \forall k$), si ha $$\lim_{k\to+\infty}f(x)=L$$
	2) $(\epsilon-\delta)$ Sia $f:\mathbb{R}^n\rightarrow\mathbb{R}$ definita almeno in un intorno sferico di $x_0\in\mathbb{R}^n$ (escluso al più $x_0$) e $L\in\mathbb{R}$, si dice che $$\lim_{x\to x_0}f(x)=L$$ se, per ogni $\epsilon>0$, esiste un $\delta>0$ t.c. $0<|x-x_0|<\delta$ , implica $$|f(x)-L|<\epsilon$$ $L=+\infty$ o $-\infty$,    $\lim_{x\to x_0} f(x)=+\infty$(o $-\infty$) se, per ogni $k>0$, esiste $\delta>0 \quad 0<|x-x_0|<\delta \quad f(x)>k (f(x)<-k)$

>**OSSERVAZIONE**
	1) $f:\mathbb{R}^n\rightarrow\mathbb{R}\rightsquigarrow$ non è scomponibile in funzioni di 1 variabile
	2) $f:\mathbb{R}\rightarrow\mathbb{R}^m\rightsquigarrow$ m funzioni $f_i \ i=1,\ldots,m$ , $f_i:\mathbb{R}\rightarrow\mathbb{R}$

$f:A\subseteq\mathbb{R}^n\to\mathbb{R}$
- Teorema di unicità del limite
- Teorema sul limite di somma, prodotti,...
- La definizione di funzione continua
	$f:A\to\mathbb{R},\ x_0\in A$ di accumulazione. $f$ è *continua* se $\lim_{x\to x_0}f(x)=f(x_0)$

>**TEORMA (Permanenza del Segno)**
	$f:\mathbb{R}^n\rightarrow\mathbb{R}$ definita almeno in un intorno sferico di $x_0$ (escluso al più $x_0$). Si suppone che $\lim_{x\to x_0}f(x)=L\in\overline{\mathbb{R}}$ 
		1) Se $L>0$, allora $f$ si mantiene positiva in un intorno di $x_0$, cioè esiste $\delta>0$ t.c. $f(x)>0$ perché $0<|x-x_0|<\delta$.
		2) Se $f(x)\ge0$ in un intorno di $x_0$ (escluso al più $x_0$) allora $L\ge0$ (NOTA: non si può dire che $L>0$ anche se $f(x)>0$)
		3)(conseguenza si 1) + continuità di $f$) Se $f$ è continua e $f(x_0)>0$ allora $f$ si mantiene positiva in un intorno di $x_0$

>**DEFINIZIONE**
	$f:\mathbb{R}^n\rightarrow\mathbb{R}$ definita per $|x|$ abbastanza grande. Si dice che $\lim_{|x|\to+\infty}f(x)=L\in{\mathbb{R}}\quad$ se $\forall\epsilon>0 \ \exists R>0$ t.c. $\forall x\in\mathbb{R}^n$ se $|x|>R$  allora $|f(x)-L|<\epsilon$. 
	Nel caso $\lim_{|x|\to +\infty}f(x)=+\infty(o \ -\infty)$: $\forall k>0 \ \exists R>0$ t.c. $\forall x\in\mathbb{R}^n$ se $|x|>R$ $f(x)>K$ (o $f(x)<-k$)

>**ESEMPI**
	a) $\lim_{(x,y)\to(0,0)} \frac{2^{y+1}\cos{x}}{x^2+4}$
		$f$ continua
		$\lim_{(x,y)\to(0,0)}f_a(x,y)=f(0,0)=\frac{1}{2}$
	b) $\lim_{(x,y)\to(0,0)} \frac{x^2+y^4}{x^4+y^2}$
		$\left[ \frac{0}{0} \right]$ $\frac{x^2+y^4}{x^4+y^2}$
		non si possono calcolare i limiti in 2 variabili facendo tendere le variabili al punto limite separatamente e non si farà mai uso delle stime asintotiche su funzioni di più variabili.

>**OSSERVAZIONE**
	Se $\lim_{(x,y)\to(x_0,y_0)}f(x,y)=L$, questo valore si deve ottenere lungo qualsiasi percorso
	![[limiti]]

>**PROPOSIZIONE**
	Se $\lim_{(x,y)\to(x_0,y_0)}f(x,y)=L$, allora per ogni sottoinsieme $C$ del dominio di $f$ si deve avere $$\lim_{\underset{(x,y)\in C}{(x,y)\to(x_0,y_0)}}f(x,y)=L$$ Utile per due motivi:
		- Individuare il candidato limite
		- Dimostrare che il limite non esiste

Qualsiasi delle forme di indeterminazione
	1) **Restrizione ad una curva per provare la non esistenza del limite**
		$f:A\subseteq\mathbb{R}^2\to\mathbb{R}$ 
		$r:I\subseteq\mathbb{R}\to\mathbb{R}^n$ arco di curva
		$g(t)=f(r(t))$ si dice *Restrizione di f alla curva r* ($g:\mathbb{R}\rightarrow\mathbb{R}$)
		Idea: per dimostrare che il limite per $x\to x_0 \ \nexists$ è sufficiente determinare due curve che passano per $x_0$ lungo le quali la funzione ha limiti diversi. 
		Vale la stessa conclusione se la restrizione di $f$ non ammette limite.
		ESEMPIO:
			1) Calcolare $\lim_{(x,y)\to(0,0)} \frac{xy}{x^2+y^2}$
				$f_{|_{y=x}}= \frac{x^2}{2x^2}= \frac{1}{2}$ , $f_{|_{y=-x}}= \frac{-x^2}{2x^2}= -\frac{1}{2}$  Il limite non esiste
			1) Studiare $\lim_{(x,y)\to(0,0)} \frac{xy^2}{x^2+y^4}$
				$f(x,0)=0=f(0,y)$, il candidato è L=0
				$y=mx$
				$C=\{(x,y):y=mx, \ x\ne 0\}$
				$\lim_{\underset{(x,y)\in C}{(x,y)\to(x_0,y_0)}}f=\lim_{x\to 0}f(x,mx)=\lim_{x\to} \frac{xm^2x^2}{x^2+m^4x^4}=$$\lim_{x\to 0} \frac{m^2x^3}{x^2+m^4x^4}=0$
			    Avvicinandosi lungo $x=y^2$
				$C'=\{(x,y):x=y^2\}$
				$\lim_{\underset{(x,y)\in C}{(x,y)\to(x_0,y_0)}}f=\lim_{x\to0} \frac{y^4}{y^4+y^4}=\frac{1}{2}$ 
				Quindi $\nexists$ il limite.
	2) **Uso di maggiorazioni con funzioni radiali**
		Se $n=2$
	    ![[coordpol]]
		$\rho=\sqrt{x^2+y^2}\quad\rho\in[0,+\infty], \ \theta\in[0,2\pi]$
		$\left\{ \begin{matrix} x=\rho\cos\theta \\ y=\rho\sin\theta\end{matrix}\right.$
	3) **Maggiorazioni**

>**PROPOSIZIONE (Criterio generale per provare l'esistenza del limite)**
	Per dimostrare $f(x,y)\to L$ se $(x,y)\to(0,0)$ è sufficiente scrivere una maggiorazione del tipo $$|f(x,y)-L|\le g(\rho), \quad g(\rho)\rightarrow0$$con $g$ indipendente da $\theta$.

>**OSSERVAZIONE**
	Se $(x,y)\to(x_0,y_0)$
		$\rho=\sqrt{(x-x_0)^2+(y-y_0)^2}$
		$\left\{\begin{matrix}  x=x_0+\rho\cos\theta \\ y=y_0+\rho\sin\theta \end{matrix}\right.$

>**ESEMPIO**
$$\lim_{(x,y)\to(1,0)} \frac{y^2\log x}{(x-1)^2+y^2}$$
	*Soluzione 1:*
		$\rho\to0\iff|\rho|\to0$
		$0\le \frac{y^2|\log x|}{(x-1)^2+y^2}\le|\log x|\to 0\qquad \left( \frac{y^2}{(x-1)^2+y^2}\le 1 \right)$
		Per il teorema del confronto, $\lim_{(x,y)\to(1,0)} \frac{y^2\log x}{(x-1)^2+y^2}=0$
	*Soluzione 2: (Coordinate polari)*
		$\left\{\begin{matrix} x=1+\rho\cos\theta \\ y=\rho\sin\theta \end{matrix}\right.$
		$\lim_{\rho\to0} \frac{\rho^2\sin^2\theta\log(1+\rho\cos\theta)}{\rho\cos^2\theta+\rho^2\sin^2\theta} = \lim_{\rho\to 0} \frac{\cancel{\rho^2}sin^2\theta log(1+\rho \cos\theta)}{\cancel{\rho}}=\lim_{\rho\to0\sin^2\theta\rho\cos\theta}$
		$\sin^2\theta\log(1+\underset{\rho\to0,\ \cos\theta \ è \ limitata}{\rho\cos\theta})\quad\rho\to0$
		$\log(1+\rho\cos\theta)\sim\rho\cos\theta\quad\rho\to0$
		$|\cos\sin^2\theta|\le1$
		$\Rightarrow|\rho\cos\theta\sin^2\theta|\le\underset{g(\rho)}{\rho}\to0$ per $\rho\to0$
		Per il criterio il limite è 0
