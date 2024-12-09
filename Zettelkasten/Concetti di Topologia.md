Tags: [[Analisi 2 e Probabilità]] [[University]]

>**DEFINIZIONE** 
	Si dice *Intorno Sferico* di centro $x_0\in\mathbb{R}^n$ e raggio $r>0$$$B_r(x_0)=\{x\in\mathbb{R}^n:|x-x_0|<r\}$$$B_r(x_0)$ = (iper)sfere centrate in $x_0$

>**DEFINIZIONE**
	$E\subseteq\mathbb{R}^n$. Un punto $x_0\in\mathbb{R}^n$ si dice
		- *Interno ad $E$* se esiste un intorno sferico di $x_0$ contenuto in $E$
		- *Interno in $E$* se esiste un intorno sferico di $x_0$ contenuto in $E^c$ (complementare di $E$)
		- *Di Frontiera* se ogni intorno sferico di $x_0$ contiene almeno un punto di $E$ ed uno di $E^c$

>**ESEMPIO**
	$E=\{(x,y)\{x\in\mathbb{R}^n:\ x^2+y^2\le1,\ y>x^2\}$
```graph
bounds: [-2, 2, 2, -2]
keepAspectRatio: true
elements: [
	{type: functiongraph, def: ["f:x*x"]},
	{type: inequality, def: ["e0"], att: {inverse: true, fillOpacity: 0.1}},
	{type: functiongraph, def: ["f:-x*x+1"]},
	{type: inequality, def: ["e2"], att: {inverse:false, fillOpacity: 0.1}},
	{type: curveintersection, def: ["e3", "e1"], att: {fillColor: "yellow", fillOpacity: 0.6}}
]
```
>$\left( 0, \frac{1}{2} \right)$ è interno a $E$
>$(1,0)$ è esterno a $E$
>$(0,0)$ è di frontiera (non appartiene a $E$)
>(0,1) è di frontiera (appartiene a $E$)

>**OSSERVAZIONE**
1. Dato $E\subseteq\mathbb{R}^n$ e $x_0\in\mathbb{R}^n$ si verificano necessariamente una delle seguenti condizioni:
		(i) $x_0$ è interno a $E$
		(ii) $x_0$ è esterno a $E$
		(iii) $x_0$ è di frontiera a $E$ 
2. Se $x_0$ è interno $\Rightarrow x_0\in E$
3. Se $x_0$ è esterno $\Rightarrow x_0\in E$
4. Un punto di frontiera può appartenere all'insieme $E$ 

>**DEFINIZIONE**
	$E\subseteq\mathbb{R}^n$
	Aperto, se ogni punto interno ad $E$
	Chiuso, se il suo complementare è aperto

>**ESEMPI**
	$E_1=\{(x,y)\{x\in\mathbb{R}^n:x^2+y^2<1\}$ è aperto
	$E_2=\{(x,y)\{x\in\mathbb{R}^n:y\ne0\}$ è aperto
	$E_3=\{(x,y)\{x\in\mathbb{R}^n:x^2+y^2\le 4\}$ è chiuso
	$E_4=\{(x,y)\{x\in\mathbb{R}^n:2x+3y-1=0\}$ è chiuso
	$E_5=\{(x,y)\{x\in\mathbb{R}^n:x^2+y^2\le1 \ e \ y<x^2\}$ non è né aperto né chiuso
	$E_6=\mathbb{R}^n$ è aperto ($\emptyset$ è chiuso)
	$E_7=\emptyset$ è aperto ($\mathbb{R}^2$ è chiuso)
 Nel caso $n=1$
	$(a,b),\ (a,+\infty),\ (-\infty, \ b)$, $a,b\in\mathbb{R}$ sono aperti di $\mathbb{R}$
	$[a,b],\ [a,+\infty],\ [-\infty, \ b]$, $a,b\in\mathbb{R}$ sono chiusi di $\mathbb{R}$

Dato $x_0\in\mathbb{R}^n$:
>**DEFINIZIONE**
	Si dice *Intorno* di $x_0$ un qualsiasi insieme aperto contenente $x_0$
>**OSSERVAZIONE**
	- Un intorno sferico di $B_r(x_0)$ è un intorno di $x_0$ 
	- Ogni intorno di $x_0$ contiene almeno un intorno sferico di $x_0$
	
>**PROPOSIZIONE**
	$E\subseteq\mathbb{R}^n$. Un punto $x_0\in\mathbb{R}^n$
	- Interno ad $E\iff$ esiste un intorno di $x_0$ contenuto in $E$
	- Esterno ad $E\iff$ esiste un intorno di $x_0$ contenuto in $E^c$
	- Di frontiera per $E\iff$ ogni intorno di $x_0$ contiene almeno un punto di $E$ e uno di $E^c$

>**TEOREMA (NO DIM)**
	- L'unione di una famiglia qualsiasi (anche infinita)  di aperti e l'intersezione di un numero finito di aperti sono insiemi aperti
	- L'intersezione di una famiglia qualsiasi di chiusi e l'unione di un numero finito di chiusi sono insiemi chiusi

>**DEFINIZIONE**
	Si dice che $x_0$ è un *Punto di Accumulazione* per $A\subseteq\mathbb{R}^n$ se in ogni intorno sferico di $x_0$ esiste almeno un punto di $A$ diverso da $x_0$
	![[Punto di Accumulazione]]

>**OSSERVAZIONE**
	I punti interni di $A$ sono di accumulazione, mentre i punti esterni di $A$ non sono di accumulazione.
	I punti di frontiera di $A$ possono essere di accumulazione oppure no

>**ESEMPI**
	Un punto di accumulazione per $A$ non deve necessariamente appartenere ad $A$. Si prenda $$A=\{x\in\mathbb{R}^2:|x<1|\}\cup\{(2,0)\}$$Ogni $x_0\in\mathbb{R}^2$ t.c. $|x_0|=1$ è di accumulazione per $A$ anche se $x_0\notin A$.
	Invece $(2,0)\in A$, ma non è di accumulazione (è punto isolato) 
