Tags: [[Analisi 2 e Probabilità]] [[University]]

In analisi 1, $f:A\in \mathbb{R}^1\rightarrow\mathbb{R}^1$, 1 ingresso - 1 uscita
**Obiettivo:** estendere il caso in cui i dati in ingresso sono più di uno
### DEFINIZIONE
- Si dice *Funzione di una variabile* una funzione su $A\subset\mathbb{R}$
- Si dice *Funzione di più variabili* una funzione definita su $A\subset\mathbb{R}^n,n>1$	
-  Si dice *Funzione a valori reali* una funzione che ha immagine $f(A)\subseteq\mathbb{R}$ 	
-  Si dice *Funzione a valori vettoriali* una funzione t.c. $f(A)\subseteq\mathbb{R}^n,n>1$

### OSSERVAZIONE
$f:A\subset \mathbb{R}\rightarrow\mathbb{R}^m, \ m=2,3$ hanno significato geometrico
	n=2 curve nel piano
		m=3 curve nello spazio
	Funzioni reali in più variabili $f:A\subset\mathbb{R}\rightarrow \mathbb{R}$ : grafico, linee di livello e domini.

**RAPPRESENTAZIONE 1**
### DEFINIZIONE
$f:A\subseteq\mathbb{R}^n\rightarrow\mathbb{R}$. Il grafico di $f$ 
	$\{(\underset{\in \mathbb{R}^n}{\mathbf{x}},f(\mathbf{\underset{\in\mathbb{R}}x}):x\in A\}\subseteq \mathbb{R}^{n+1}$ 
NOTA: se $n=2$ il grafico è in 3D, se $n>2$ il grafico non è più visualizzabile

**RAPPRESENTAZIONE 2**
### DEFINIZIONE
$f:A\subseteq\mathbb{R}^n\rightarrow\mathbb{R}$. Gli insiemi di livello di $f$ sono
	$\{x\in \mathbb{R} :f(x)=c \}$
al variare di $c\in\mathbb{R}$

### ESEMPIO
$f(\overset{\in\mathbb{R}}x,\overset{\in\mathbb{R}}y)=x^2+y^2$	
è definita in tutto $\mathbb{R}^2, \ \ge 0$
	$\{(x,y):x^2+y^2=c\}, \ c\in\mathbb{R},c=1,2,\ldots$
Le linee di livello sono circonferenze di centro $(0,0)$ e di raggio $1,\sqrt{2},\ldots$ 

*GRAFICO: PARABOLOIDE* ($z=x^2+y^2$)
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

### ESEMPIO
$f(x,y)=x^2-y^2$
Definita su $\mathbb{R}^2$, assume sia valori positivi che negativi
	$\{(x,y):x^2-y^2=c\},c\in \mathbb{R}$
	$c=0 \quad y=\pm x$
	$c\ne0$ sono iperboli equilatere con $y=\pm x$ come asintoti
	($c>0$: vertice sull'asse $x$, $c<0$ vertice 
```graph
bounds: [-2, 2, 2, -2]
keepAspectRatio: true
elements: [
	{type: implicitcurve, def: ["(x**2)-(y**2)"]},
	{type: implicitcurve, def: ["(x**2)-(y**2)-1"]},
	{type: implicitcurve, def: ["(x**2)-(y**2)+1"]},
	{type: implicitcurve, def: ["(x**2)-(y**2)-2"]},
	{type: implicitcurve, def: ["(x**2)-(y**2)+2"]},
	{type: implicitcurve, def: ["(x**2)-(y**2)-3"]},
	{type: implicitcurve, def: ["(x**2)-(y**2)+3"]}
]
```

*GRAFICO: PARABOLOIDE IPERBOLICO* ($x^2-y^2-z=0$)
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:x*x-y*y", [-5, 5], [-5, 5]]}
]
```
Simmetria radiale ($f$ ha lo stesso valore nei punti che hanno la stessa distanza dall'origine)
# Domini
$n=1\leadsto D_f=I$ o unione di intervalli
### ESEMPIO (in $\mathbb{R}^2$)
$f(x,y)=\frac{\sqrt{x^2-y}}{log(x+y)}$
l'insieme di definizione di $f$ è dato da 
	a - $x^2-y\ge0$ (radicando non negativo)
	b - $x+y>0$ (argomento del $log>0$)		c- $x+y\ne 1$ (denominatore $\ne 0$)
	$D_f=\{(x,x)\in\mathbb{R}^2: \quad \overset{a}{y\le x^2}, \quad \overset{b}{y>-x},\quad \overset{c}{ y\ne -x+1} \}$
```graph
bounds: [-10, 10, 10, -10]
keepAspectRatio: true
elements: [
	{type: functiongraph, def: ["f:x*x"]},
	{type: inequality, def: ["e0"], att: {inverse:true, fillOpacity: 0.1}},
	{type: functiongraph, def: ["f:-x+1"]},
	{type: inequality, def: ["e2"], att: {inverse:true, fillOpacity: 0.1}},
	{type: functiongraph, def: ["f:-x"]},
	{type: curveintersection, def: ["e1", "e3"], att: {fillColor: "yellow", fillOpacity: 0.6}}
]
```