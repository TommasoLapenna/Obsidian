Tags: [[Analisi 2 e Probabilità]] [[University]]

# Proprietà delle Funzioni Continue
>**DEFINIZIONE**
	Sia $E\subseteq\mathbb{R}^n$. $E$ si dice *Limitato* se esiste una costante $k>0$ t.c.$$|x|\le k \forall \quad x\in E$$ In altre parole, $E$ è limitato se è contenuto in una sfera di raggio abbastanza grande.

>**DEFINIZIONE**
	$E\subseteq\mathbb{R}^n$ chiuso e limitato si dice di *Compatto*

>**TEOREMA (Di Weierstrass)** 
	$E\subseteq\mathbb{R}^n$ e $f:E\to\mathbb{R}$ continua. $f$ ammette max e min su $E$ $$x_m,x_m\quad f(x_m)\le f(x)\le f(x_M)\quad \forall x\in E$$(NO DIM)

>**DEFINIZIONE**
	$E\subseteq\mathbb{R}^n$ si dice *Connesso (per archi)* se per ogni coppia di punti $x,y\in E$ esiste una funzione continua $r:[0,1]\to\mathbb{R}^n$ (arco)  t.c.$$\begin{align} \\
 &r(0)=x \\ &r(1)=y \\ & r(t)\in E \quad \forall t\in[0,1] \ \text{(r è contenuto in E)} \end{align}$$
	 Significato: $E$ è composto da un "pezzo solo".

>**TEOREMA (Del Valore Intermedio)**
	$E\subseteq\mathbb{R}^2$ connesso per archi e $f:E\to\mathbb{R}$. Allora per ogni $c\in\mathbb{R}$ t.c.$$\inf f<c<\sup f$$esiste $z\in E$ t.c. $f(z)=c$

>**OSSERVAZIONE** 
	Nel caso $n>1$. Il concetto di "connesso per archi" sostituisce quello di intrevallo.

>**PROPOSIZIONE (Aperti Connessi Per Archi)** 
	$E\subseteq\mathbb{R}^n$. $E$ è connesso per archi se e solo se vale la proprietà seguente: 
		- Non esistono due aperti $A_1,A_2$ in $\mathbb{R}^n$ t.c.
			1) $A_1\ne\emptyset,A_2\ne\emptyset$
			2) $A_1$ e $A_2$ sono disgiunti $A_1\cap A_2=\emptyset$
			3) $E=A_1\cup A_2$
	(DIM NO)

>**TEOREMA (Degli Zeri)**
	$E\subseteq\mathbb{R}^n$ connesso per archi
	$f:E\to\mathbb{R}$ continua. Se $x,y\in E$ t.c. $$f(x)>0 \quad f(y)<0$$Allora esiste $z\in E$ t.c. $f(z)=0$

>**DIMOSTRAZIONE**
	$E$ connesso per archi $\exists:\underset{arco}{[a,b]}\to E$ t.c.$$\begin{align} \\
 & r(a)=x \\ & r(b)=y \\ & f\circ r:[a,b]\to\mathbb{R} \ \text{1d continua} \\ & f(r(a))\underset{per \ ipotesi}{>}0\quad f(r(b)\underset{per \ ipotesi}{<} 0 \end{align}$$Per il teorema degli zeri (n=1) $\exists E\in[a,b],\ z=r(F) \ t.c. \ f(z)=f(r(F))=0$

Insiemi aperti e chiusi definiti da funzioni continua $f:\mathbb{R}^n\to \mathbb{R}$ 
	$\{x\in\mathbb{R}^n:f(x)>0\}$
	$\{x\in\mathbb{R}^n:f(x)<0\}$ Sono Aperti
	$\{x\in\mathbb{R}^n:f(x)\ne0\}$

	$\{x\in\mathbb{R}^n:f(x)\ge0\}$
	$\{x\in\mathbb{R}^n:f(x)\le0\}$ Sono Chiusi
	$\{x\in\mathbb{R}^n:f(x)=0\}$

>**DEFINIZIONE**
	$E\subseteq\mathbb{R}^n$. 
	- *Interno* di $E$ ($\overset{\circ}{E}$) l'insieme dei punti di intorno di $E$
	- *Frontiera* di $E$ ($\partial E$) l'insieme dei punti di frontiera
	- Chiusura di $E$  $\overline{E}=\overset{\circ}{E}\cup\partial E$

>**ESEMPI**
				$$\lim_{(x,y)\to(0,0)} \frac{x^3+y^5}{x^2+y^4} \quad \begin{align} & \left|\frac{x^3+x^5}{x^2+y^4}\right|\overset{?}{\le} g(x,y)\to 0 \ ((x,y)\to0) \\  \\
& \left| \frac{x^3+y^5}{x^2+y^4} \right|\underset{dis.\ triangolare}{\le}\left| \frac{x^3}{x^2+\underset{\ge 0}{y^4}} \right|+ \left| \frac{y^5}{\underset{\ge0}{x^2}+y^4} \right| \\
& \underset{\frac{1}{x^2+y^4}\le \frac{1}{x^2}}{x^2\le x^2+y}\le \frac{|x|^3}{x^2}+ \frac{|y|^5}{y^4} \underset{\underset{(ii) \frac{y^5}{x^2+y^4\le \frac{y^5}{y^4}}}{(ii) \frac{x^3}{x^2+y^4}\le \frac{x^3}{x^2}}} {\le} \underset{g(x,y)}{\underline{|x|+|y|}}\to0 \\
\\& g(x,y)=|x|+|y| \ \text{è continua in }(0,0) \quad g(x,y)\to0 \ per \ (x,y)\to(0,0) \\ & \text{Quindi }f\to0\text{ per il teorema del confronto}
	\end{align}$$$$\lim_{(x,y)\to(0,0)} \frac{y^3+x^5}{x^2+y^4}\quad \begin{align}&  \left| \frac{y^3+x^5}{x^2+y^4} \right|\le \left| \frac{y^3}{x^2+y^4} \right| + \left| \frac{x^5}{x^2+y^4} \right|  \\
 & \left|\frac{y^3+x^5}{x^2+y^4}\right| \underset{\underset{\frac{|y|^3}{x^2+y^4}\le \frac{|y|^3}{y^4}\le \frac{1}{|y|}}{\frac{|x|^5}{x^2+y^4}\le \frac{|x|^5}{x^2}}\le|x|^3}{\le} \frac{1}{|y|}+|x|^3 \\
& \frac{1}{|y|}\cancel{\to}0 \\
& \quad -\ f(x,x)\underset{y=x}{=} \frac{x^3+x^5}{x^2+x^4}\sim \frac{x^3}{x^2}=x\to 0  \\
& \quad -\ f(\underset{x=y^2}{y^2},y)= \frac{y^3+y^{10}}{y^4+y^4}\sim \frac{y^3}{2y^4}\to\pm\infty \\
  & \nexists \ lim_{}. \\
& \frac{\rho^3\sin^3\theta+\rho^5\cos^5\theta}{\rho^2\cos^2\theta+\rho^4\sin^4\theta} \\
& \left| \frac{\rho^3\sin^3\theta}{\rho^2\cos^2\theta+\rho^4\sin^4\theta} \right| \le \frac{\rho^3}{\ldots}\le g(\rho) \\
& \overset{\frac{1+xy}{x^2}=k\quad k\in\mathbb{R}}{-\lim_{(x,y)\to(0,0)}\left(  \frac{xy^2+2y^{\frac{1}{3}}\sin^2x}{x^2+y^2} \right)e^{\frac{x^2-y^2}{x^2+y^2}}}  \end{align} $$

>**DEFINIZIONE**
	$f:A\subseteq\mathbb{R}^2\to\mathbb{R}, \ x_0\in A$, $x_0$ è un punto di max (rispettivamente minimo) assoluto per $f$ in $A$ se $\forall x\in A$ $$f(x)\underset{(\ge)}{\le} f(x_0)$$ $f(x)$ è max (min)

**METODO DELLE CURVE DI LIVELLO**
	Studiare estremi assoluti di $f(x,y$ delle quali sappiamo disegnare le curve di livello $$f(x,y)=k,\quad k\in\mathbb{R}$$
	$\begin{align} f(x,y)&=ax+by+c \ &\text{rette}\\ &=ax^2+by^2&\text{ellissi} \\ &=y-ax^2&\text{parabole} \\ &=ax^2-by^2&\text{iperboli} \end{align}$
		$f:A\subseteq\mathbb{R}^2\to\mathbb{R}$, $A$ compatto (si può applicare il Teorema di Weierstrass)
	
1) Si disegna la generica curva di livello $f(x,y)=k,\quad k\in\mathbb{R}$
2) Si considera le intersezioni $\{f(x,y)=k\}$ con $A$ (sono i sottoinsiemi di dove $f$ vale $k$)
3) Si calcola il valore di $K_{max}$ per cui $\{(x,y):f(x,y)=k\}$ ha intersezione non vuota con $A$
4) Si calcola il valore $K_{min}$ (analogamente)

>**ESERCIZIO**
	Calcolare max e min assoluti di $$f(x,y)=5+x$$ su $A_1=\{(x,y)\in\mathbb{R}^2:\ y\ge0, \ x^2+y^2\le 4\}$
	1) $f(x,y)=k\iff5+x=k,\quad k\in\mathbb{R} \Longrightarrow x=k-5$ famiglia di rette parallele all'asse $y$ 
	2)
```graph
bounds: [-5, 5, 5, -5]
keepAspectRatio: true
elements: [
	{type: functiongraph, def: ["f:0"]},
	{type: inequality, def: ["e0"], att: {inverse: true, fillOpacity: 0.0}},
	{type: circle, def: [[0,0],2]},
	{type: curveintersection, def: ["e1", "e2"], att: {fillColor: "yellow", fillOpacity: 0.6}},
	{type: line, def: [[-2.5,0], [-2.5, 1]], att: {chartStyle: "fit", name: "$k-5$", withlabel: "true"}},
	{type: point, def: [-2,0], att: {name: "$k_{min}$"}},
	{type: point, def: [2,0], att: {name: "$k_{max}$"}},
]
```
> 3-4) Al crescere di $k$ la retta si sposta verso destra e aumenta il valore di $f$ 
	valore minimo: $k=-2\quad k-5=-2\Longrightarrow k=3\Longrightarrow m=3$ in $(-2,0)$
	valore max: $k=2\quad k-5=2\Longrightarrow k=7\Longrightarrow M=7$ in $(2,0)$

>**ESEMPIO**
	Si può affermare (senza fare conti) che $f(x,y)=e^{x^2-y^2}$ ha max e/o min su $\underset{A}{x^2+y^2=1}$ ($M$ e $m$ esistono per Weierstrass)
	*METODO 1:*
		Si può sostituire l'espressione del vincolo $x^2+y^2\Longrightarrow y^2=1-x^2$ $$f(x,y) |_A=e^{x^2-y^2}|_A \underset{y^2=1-x^2}{=} e^{2x^2-1} =:g(x)\quad x\in[0,1]$$(Si può prendere $x\in[0,1]$ invece che $x\in[-1,1]$ perché $x^2$ è pari)
		$x^2$ è crescente in $[0,1]$ (non lo è in $[-1,1]$) $\Longrightarrow g$ è crescente in quanto composizione di funzioni crescenti.
		I candidati as essere estremi assoluti sono:$$\underset{min}{(0,1)}\qquad \underset{max}{(1,0)}\quad in \ [0,1]$$Considerando $[-1,1]$ $$\underset{min}{(0,-1)}\qquad \underset{max}{(-1,0)}$$ $\max_Af=f(\pm1,0)=e$, $\min_Af=f(0,\pm1)=e^{-1}$ 
	*METODO 2 (Curve di Livello):*
		$e^{x^2-y^2}=k\iff  \begin{align}&x^2-y^2=\log k:= C \\ & x^2-y^2=C\end{align}$
```graph
bounds: [-3, 3, 3, -3]
keepAspectRatio: true
elements: [
	{type: implicitcurve, def: ["f:x*x-y*y-1"]},
	{type: implicitcurve, def: ["f:x*x-y*y-2"]},
	{type: implicitcurve, def: ["f:x*x-y*y+1"]},
	{type: implicitcurve, def: ["f:x*x-y*y+2"]},
	{type: circle, def: [[0,0],1]}
]
```
>	$C_{min}=-1\rightsquigarrow(0,\pm1)$ punti di min
>	$C_{min}=-1\rightsquigarrow(\pm1,0)$ punti di max

**RIASSUNTO**
	max/min $f(x,y)$ su $A\subseteq\mathbb{R}^2$
	1) Metodo delle curve di livello
		Applicabile quando si sa disegnare le curve di livello (procedimento grafico)
	2) Nell'equazione del vincolo è possibile esplicitare una variabile rispetto alle altre
	 $\rightsquigarrow\max/\min \ 1d$ Permettono di risolvere problemi di ottimizzazione in casi "fortunati".