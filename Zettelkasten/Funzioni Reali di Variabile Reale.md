Tags: [[Analisi 2 e Prbabilità]] [[University]]

In analisi 1, $f:A\in \mathbb{R}^1\rightarrow\mathbb{R}^1$, 1 ingresso - 1 uscita
**Obiettivo:** estendere il caso in cui i dati in ingresso sono più di uno
>**DEFINIZIONE**
	- Si dice *Funzione di una variabile* una funzione su $A\subset\mathbb{R}$
	- Si dice *Funzione di più variabili* una funzione definita su $A\subset\mathbb{R}^n,n>1$
	- Si dice *Funzione a valori reali* una funzione che ha immagine $f(A)\subseteq\mathbb{R}$ 
	- Si dice *Funzione a valori vettoriali* una funzione t.c. $f(A)\subseteq\mathbb{R}^n,n>1$

>**OSSERVAZIONE**
	$f:A\subset \mathbb{R}\rightarrow\mathbb{R}^m, \ m=2,3$ hanno significato geometrico
		n=2 curve nel piano
		m=3 curve nello spazio
	Funzioni reali in più variabili $f:A\subset\mathbb{R}\rightarrow \mathbb{R}$ : grafico, linee di livello e domini.

**RAPPRESENTAZIONE 1**
>**DEFINIZIONE**
	$f:A\subseteq\mathbb{R}^n\rightarrow\mathbb{R}$. Il grafico di $f$ 
		$\{(\underset{\in \mathbb{R}^n}{\mathbf{x}},f(\mathbf{\underset{\in\mathbb{R}}x}):x\in A\}\subseteq \mathbb{R}^{n+1}$ 
	NOTA: se $n=2$ il grafico è in 3D, se $n>2$ il grafico non è più visualizzabile

**RAPPRESENTAZIONE 2**
>**DEFINIZIONE**
	$f:A\subseteq\mathbb{R}^n\rightarrow\mathbb{R}$. Gli insiemi di livello di $f$ sono
		$\{x\in \mathbb{R} :f(x)=c \}$
	al variare di $c\in\mathbb{R}$

>**ESEMPIO**
	$f(\overset{\in\mathbb{R}}x,\overset{\in\mathbb{R}}y)=x^2+y^2$
	è definita in tutto $\mathbb{R}^2, \ \ge 0$
	$\{(x,y):x^2+y^2=c\}, \ c\in\mathbb{R},c=1,2,\ldots$
	Le linee di livello sono circonferenze di centro $(0,0)$ e di raggio $1,\sqrt{2},\ldots$ 

GRAFICO: PARABOLOIDE ($z=x^2+y^2$)
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:x*x+y*y", [-5, 5], [-5, 5]]}
]
```
Simmetria radiale ($f$ ha lo stesso valore nei punti che hanno la stessa distanza dall'origine).

>**ESEMPIO**
	$f(x,y)=x^2-y^2$
	Definita su $\mathbb{R}^2$, assume sia valori positivi che negativi
	