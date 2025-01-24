---
aliases:
---
Tags: [[Analisi 2 e Probabilità]] [[University]]

# Limiti, Continuità e Differenziabilità per $f:\mathbb{R}^n\to\mathbb{R}^m$
$x_0$ di accumulazione  per $A\subseteq\mathbb{R}^n$, $f:A\to\mathbb{R}^m$, $l\in\mathbb{R}^m$ $$\lim_{z\to x_0}f(x)=l$$se $\forall\epsilon>0 \ \exists\delta>0$ t.c. $$\underset{norme \ su \ \mathbb{R}^m}{|f(x)-l|}<\epsilon\quad\forall x \in A \backslash\{x_0\}:\underset{norme \ su \ \mathbb{R}^n}{|x-x_0|}<\gamma$$
- $\lim_{x\ \to x_0}(f_1(x),\ldots,f_m(x))=(\lim_{x\to x_0}f_1(x),\ldots,\lim_{x\to x_0}f_m(x))$
- $f$ continua in $x_0$ se $f(x)\overset{x\to x_0}{\to}f(x_0)$, $f\in C (A;\mathbb{R}^m)$
- $f:A\to\mathbb{R}^m$, $A$ aperto
$f$ è derivabile (parzialmente) in $x$ se ogni componente è derivabile in $x$ $$\begin{align}
\Longrightarrow& \exists Df \ (gradiente \ di \ f)\quad f:A\to\mathbb{R}^m \\
&Df\left( \partial \frac{f_j}{\partial x_i} \right)_{\begin{matrix}
i=1,\ldots,n \\
j=1,\ldots,m
\end{matrix}}=\begin{pmatrix}
\frac{\partial f_1}{\partial x_1} & \ldots &\frac{\partial f_1}{\partial x_n} \\
\frac{\partial f_2}{\partial x_1} & \ldots & \frac{\partial f_2}{\partial x_m} \\
\vdots & & \vdots \\
\frac{\partial f_m}{\partial x_1} & \ldots & \frac{\partial f_m}{\partial x_n}
\end{pmatrix}
\end{align}$$matrice $m\times n$
## Matrice Jacobiana
### Definizione (Differenzialabilità)
 $A$ aperto di $\mathbb{R}^n$, $f:A\to\mathbb{R}^m$. $f$ è *Differenziabile* in $x\in A$ se è derivabile in $x$ e $$\lim_{h\to0} \frac{\overset{\in\mathbb{R}^m}{f(x+h)}-\overset{\in\mathbb{R}^m}{f(x)}-\overset{\in \mathbb{R}^{m\times 1}}{Df(x)\cdot h}}{|h|}=0$$$x\in\mathbb{R}^n,\ h\in\mathbb{R}^n$
 $Df\in\mathbb{R}^{m\times n}\quad h^{n\times1}\quad Df(x)\cdot h$ è prodotto righe per colonne
 $m=1, \ f:A\subseteq\mathbb{R}^n\to\mathbb{R}$ $$Df(x)\cdot h=\left( \frac{\partial f}{\partial x_1} \cdots \frac{\partial f}{\partial x_n} \right)\cdot \begin{pmatrix}
h_1 \\
\vdots \\
h_n
\end{pmatrix}$$
## Differenziale 
$h\in\mathbb{R}^n$ $$\begin{align}
&df:\mathbb{R}^n\longmapsto(Df(x),h)\in\mathbb{R}^m \\
&df(x)(h)=Df(x)\cdot h
\end{align}$$
- Condizione sufficiente di differenziabilità: affinchè $f$ sia differenziabile in $x\in A$ è che gli elementi di $Df$ siano funzioni continue.
### Esempio
$H(u,v,w)=(\overset{H_1}{e^w-u-v}, \overset{H_2}{\sin(u+v)}$ $$\begin{align}
DH=& \begin{pmatrix}
\frac{\partial H_1}{\partial u} & \frac{\partial H_1}{\partial v} & \frac{\partial H_1}{\partial w} \\
\frac{\partial H_2}{\partial u} & \frac{\partial H_2}{\partial v} & \frac{\partial H_2}{\partial w}
\end{pmatrix}\quad \mathbb{R}^{2\times 3} \\
=&\begin{pmatrix}
-1 & -1 & e^w \\
\cos(u+v) & \cos(u+v) & 0
\end{pmatrix}
\end{align}$$
# Integrali Multipli 
- Integrale di Rieman:
	Area con segno di una regione di piano compresa tra il grafico di una funzione e l'asse $x$
- Integrali multipli
	Volume (con segno) della regione di spazio delimitata dal grafico fi una funzione di due variabili
![[Pasted image 20241228170502.png]]
$R=[a,b]\times[c,d]$, $V=\{(x,y,x)\in\mathbb{R}^3: a\le x\le b, \ \ c\le y \le d,\  \ 0\le z\le f(x,y)\}$
- Dividere $R$ in sottorettangoli
	- Si divide $[a,b]$ in sottointervalli $[x_{i-1},x_i]$
		$a=x_0<x_1<\ldots<x_n=b$
	- Si divide $[c,d]$ in sottointervalli $[y_{j-1},y_j]$
		$c=y_0<y_1<\ldots<y_m=d$
- Tracciando le rette $x=x_i$, $y=y_j$ si ottiene una partizione di $R\in\mathbb{R}$ in $n\cdot m$ rettangoli $$R_{ij}=[x_{i-1},x_i]\times [y_{j-1}, y_j]$$ciascuno di area $A_{ij}=(x_i-x_{i-1})(y_j-y_{j-1})$
- Ampiezza della partizione: lunghezza della più grande diagonale di un sottorettangolo $$\delta_{\mathcal P}=\max\left\{\sqrt{(x_i-x_{i-1})^2+(y_j-y_{j-1})^2}:\small{\begin{matrix}
i=1,\ldots,n \\
j=1,\ldots,m
\end{matrix}}\right\}$$
- Si scelogno $(x^*_{ij},y^*_{ij})$ in $R_{ij}$, si prende il parallelepipedo con base $R_{ij}$ e $f(x^*_{ij},y_{ij}^*)$ come altezza. Se si fa per ogni rettangolo $$\sum_{i=1}^n\sum_{i=1}^mf(x_{ij}^*,y_{ij}^*)A_{ij}$$*Somma di Riemann*
### Definizione
Le somme di Rieman di $f$ convergono a $S$ quando $\delta_{\mathcal P}\to0$ se:
	$\forall\epsilon>0$ $\exists\delta$ t.c. comunque si prenda una suddivisione di ampiezza $\delta_{\mathcal P}<\delta$ e $(x^*_{ij},y^*_{ij})\in R_{ij}$ vale $$\begin{align}
&\delta_{\mathcal P}<\delta\Longrightarrow|\sum_i\sum_jf(x^*,y^*)A_{ij}-S|<\epsilon \\
& S(\mathcal P)=\sum_i\sum_jm_{ij}A_{ij}\quad m_{ij}=\inf_{R_{ij}}f \\
& S(\mathcal P)=\sum_i\sum_j M_{ij}A_{ij}\quad M_{ij}=\sup_{R_{ij}}f
\end{align}$$Approssimazioni per difetto e per eccesso del volume
### Definizione
L'integrale doppio di $f$ doppio di $f$ su $R=[a,b]\times[c,d]$ $$\iint_R f(x,y)\ dxdy=\lim_{\delta_{\mathcal P\to0}}\sum_i\sum_jf(x^*_{ij},y^*_{ij})A_{ij}$$quando il limite delle somme di Rieman esiste.
Si chiama volume (con segno) della regione $V$ compresa tra $R$ e $f(x,y)$ il valore $$f\ge0\Longrightarrow Vol(V)=\iint_Rf(x,y) \ dxdy$$
### Teorema
Una funzione limitata è integrabile su $R$ (rettangolo) se e solo se $$\inf\{S(\mathcal P:\mathcal P \ partizione\}=\sup\{S(\mathcal P):\mathcal P \ partizione\}$$
### Esempio
1) Ogni costante $k$ è integrabile su $R=[a,b]\times[c,d]$ 
$$\begin{align}
&\iint_R K \ dxdy=K(b-a)(d-c)=K\cdot area(R)\quad\forall\mathcal P \\
& S(\mathcal P)=S(\mathcal P)=\sum_i\sum_j \overset{f}{k}A_{ij}=k\sum_i\sum_j(x_i-x_{i-1})(y_j-y_{j-1})=k(b-a)(d-c)
\end{align}$$
2) $R=[0,1]\times[0,1]$
$$\begin{align}
&f(x,y)=\begin{cases}
1 & (x,y)\in R \ e \ x,y \ sono \ razionali\\
0 & negli \ altri \ punti \ di \ R
\end{cases}\quad\forall\mathcal P \ di \ R \\
&S(\mathcal P)=\sum_i\sum_jm_{ij}A_{ij}=\sum_i\sum_j0\cdot A_{ij}=0 \\
&S(\mathcal P)=\sum_i\sum_jM_{ij}A_{ij}=\sum_i\sum_j1\cdot A_{ij}=1
		\end{align}$$
$f$ non è integrabile
### Teorema
Se $f$ è continua allora è integrabile in $R$.

**N.B** si procede in modo simile su $R=[a_1,b_1]\times\ldots\times[a_n,b_n]\subseteq\mathbb{R}^n$
### Teorema (Formule di Riduzione)
$R=[a,b]\times[c,d]$, $f$ continua in $R$ $$\iint_R f(x,y)\ dxdy=\int_a^b\left(\int_c^df(x,y) \ dy\right)\ dx=\int_c^d\left(\int_a^bf(x,y) \ dx\right)\ dy$$
### Osservazione 
Il Teorema ha il senso seguente:
- se $f$ è continua 
	$\forall x\in[a,b]$ la funzione $y\in[c,d]\mapsto f(x,y)\in \mathbb{R}$ è continua
	$\overset{AM1}{\Longrightarrow}\int_c^d f(x,y) \ dy$
		$x\longmapsto\int_c^d\overset{=g(x)}{f(x,y)} \ dy\in\mathbb{R}$ è continua
	$\overset{AM1}{\Longrightarrow}\int_a^b\left(\int_c^d f(x,y)\ dy\right)\ dx=\int_a^b g(x)\in\mathbb{R}$ 
### Esempio
1) .$I=\iint_{[1,2]\times[0,\pi]}^{h(x)\ g(x)}x\sin y\ dxdy$  $$\begin{align}
&=\int_1^2\left(\int_0^\pi x\sin y\ dy\right)dx=\int_1^2 x(-\cos y)|^{y=\pi}_{y=0}\ dx=\int_1^22x\ dx=2\left[ \frac{x^2}{2} \right]^{x=2}_{y=0}dx=3
\end{align}$$
2) Calcolare il volume del solido che giace sotto $z=y^2-x^2$ e sopra il rettangolo $R=[-1,1]\times[1,3]$ $$\begin{align}
Vol(V)\overset{def.}{=}&\iint_R(y^2-x^2)\ dxdy \\
=&\int_{-1}^1\left(\int_1^3(y^2-x^2\ )dy\right)dx \\
=&\int_{-1}^1\left[ \frac{y^3}{3} -x^2y\right]^{y=3}_{y=1}dx=\int_{-1}^1\left( \frac{27}{3}-3x^2-\frac{1}{3}+x^2 \right)dx \\
=&\int_{-1}^1\left( \frac{26}{3}-2x^2 \right)dx=\left[ \frac{26}{3}x-\frac{2x^3}{3} \right]^{x=1}_{x=-1}=16
\end{align}$$
## Integrazione su Domini Generici
$\iint_D f(x,y)\ dxdy$, $D$ generico e limitato $$\overline f(x,y)=\begin{cases}
f(x,y) & se \ (x,y)\in D \\
0 & altrimenti
\end{cases}$$
![[Pasted image 20241229114810.webp]]
L'integrale su $D$ è (se esiste) l'integrale di $\overline f$ su un qualunque rettangolo $R$ che racchiude $D$ $$\iint_D f(x,y)\ dxdy=\int_R \overline f(x,y) \ dxdy$$
Problema $\longrightarrow$ A quali insiemi si può associare un'area
## Teorema della Misura
### Definizione
Si dice che un sottoinsieme limitato di $\mathbb{R}^2$ è misurabile secondo Peano-Jordan se $f(x,y)\equiv 1$ è integrabile su $D$ $$|D|=Area(D)=\iint_D 1 \ dxdy$$Similmente se $D\subset\mathbb{R}^n \ |D|=\iint_D dxdy$

Nella teoria giocano un ruolo importante gli insiemi di misura nulla. $D$ ha misura nulla se $\mathcal X_D=\begin{cases}1 & x\in D \\ 0 & x \notin D\end{cases}$ è integrabile e $|D|=\iint_Dd_xd_y=0$
- **Linearità** $$\begin{align}
&\iint_D(f+g)=\iint_D f\ dxdy+\iint_D g\ dxdy \\
&\iint_Dcf\ dxdy=c\iint_Df \ dxdy
\end{align}$$
- **Monotonia** $$\begin{align}
 &se \ f\le g\Longrightarrow\iint_Df\le\iint_Dg \\
&|f| \ integrabile \ su \ D \ e \ \left|\iint_Df\right|\le\iint_D|f|
\end{align}$$
- **Criterio di Misurabilità**
### Proposizione
Un insieme $D\subset\mathbb{R}^n$ ha misura di Peano-Jordan nulla se:
- $\forall\epsilon>0$ esiste un numero finito di rettangoli $R_1,\ldots,R_N$ t.c.
	- $D\subseteq\underset{n}{\cup}R_n$
	- $\sum Vol(R_n)<\epsilon$
	$Vol([a,b]\times\ldots\times[a_n,b_n])=\prod^n_{j=1}(b_j-a_j)$
### Esempio
- $D=\{(x_0,y_0)\}\subset\mathbb{R}^n$ (oppure un insieme con un numero finito di punti)
Ha misura nulla in quanto $R_1=[x_0-r,x_0+r]\times[y_0-r,y_0+r]$ $$Vol(R)=(2r)^2=4r^2$$$\forall\epsilon>0$ se si sceglie $r$ t.c. $2(a-b)r<\epsilon \ \left( r<\frac{\epsilon}{2(b-a)} \right)$ 
- Il bordo di un poligono di $n$ lati ha misura nulla
- Il grafico di una funzione continua $g:[a,b]\to\mathbb{R}$ ha misura di Peano-Jordan nulla
### Proposizione
Un insieme $D$ è misurabile secondo Peano-Jordan se e solo se la sua frontiera ha misura nulla
### Osservazione
Ogni rettangolo $[a,b]\times[c,d]$ è misurabile secondo Peano-Jordan. Gli insiemi della geometria elementare (poligoni, archi, $\ldots$) sono misurabili secondo Peano-Jordan
- $[0,1]\times[0,1]$ con coordinate razionali ($\mathbb{Z}$) $$\iint\mathcal X_\mathbb Z \ dxdy\quad \mathcal X_\mathbb{Z}=\begin{cases}
1 & (x,y)\in [0,1]\times[0,1], \ x,y\in\mathbb{Z}
\end{cases}$$non è integrabile
### Teorema (di Lebegue-Vitali)
Una funzione limitata su un rettangolo e continua al di fuori di un insieme di misura nulla (secondo Peano-Jordan) è integrabile
### Teorema 
Se $D\subseteq\mathbb{R}^n$ misurabile secondo Peano-Jordan, $f:D\to\mathbb{R}$ limitata.
$f$ è integrabile si $D\iff f$ è continua a meno di un insieme di misura nulla di discontinuità
### Osservazione
$D$ compatto e misurabile $$f \ contnua \Longrightarrow f \ integrabile$$Infatti se $R$ è un rettangolo contenente $D$ e $\overline f$ estende $f$ a zero in $R\backslash D$, le sole discontinuità di $\overline f$ sono contenute in $\partial D$ che ha misura di Peano-Jordan nulla.
Si ragiona similmente per dedurre che $$f \ continua \ in \ D \ aperto \ misurabile \Longrightarrow è \ integrabile \ in \ D$$
$D=\{a\le x\le b\quad g_1\le y\le g_2(x)\}=\{c\le y\le d\quad h_1(y)\le x \le h_2(y)\}$ 

**N.B** $D\subseteq\mathbb{R}^n$ misurabile. Si definisce ill volume $n-dim$ di $D$ $$Vol_n(D)=\int_D1 \ dx$$($Vol_1(D)=$ lunghezza, $Vol_2(D)=$ area, $Vol_3(D)=$volume)
## Integrazioni su Regioni Semplici
### Definizione
$D\subset \mathbb{R}^2$ si dice $y$-semplice se è della forma $$D=\{(x,y)\in\mathbb{R}^2:a\le x\le b,\ g_1(x)\le y\le g_2(x)\}$$$g_1, \ g_2$ continue
![[Pasted image 20241229132455.png]]
D si dice $x-$semplice  se è della forma $$D=\{c\le y\le d, \ h_1(y)\le x\le h_2(y)\}$$$h_1,h_2$ continue
![[Pasted image 20241229132330.png]]
### Teorema (Formule di Riduzione)
Ogni funzione continua su un insieme semplice è integrabile in $D$. Valgono le formule:
- $D$ è $y-$semplice $$\iint_D f(x,y)\ dxdy=\int_a^b\left(\int_{g_1(x)}^{g_2(x)}f(x,y)\ dy\right)dx$$
- $D$ è $x-$semplice $$\iint_D f(x,y) \ dxdy=\int_c^d\left(\int_{h_1(y)}^{h_2(y)}f(x,y)\ dx\right)dy$$
![[Pasted image 20250102114734.png]]$$A(y)=\int_{h_1(y)}^{h_2(y)}f(x,y)\ dx\Longrightarrow \int_c^d A(y)\ dy$$
### Esempio
Calcolare $\iint_D (x+y^2)\ dxdy$
$D$ è la regione delimitata da $y=x^2$ e $y=2x+3$
```graph
bounds: [-10, 10, 10, -10]
keepAspectRatio: true
elements: [
	{type: functiongraph, def: ["f:2*x+3"]},
	{type: inequality, def: ["e0"], att: {inverse: true, fillOpacity: 0.0}},
	{type: functiongraph, def: ["f:x*x"]},
	{type: inequality, def: ["e2"], att: {inverse: true, fillOpacity: 0.0}},
	{type: curvedifference, def: ["e3", "e1"], att: {fillColor: "yellow", fillOpacity: 0.6}}
]
```
$$\begin{cases}
y=x^2  \\
y=2x+3
\end{cases} \quad x^2-2x-3=0 \ \begin{matrix}
\rightarrow x_1=3 \\
\rightarrow x_2=-1
\end{matrix}\quad y-semplice$$$f$ è continua $$\begin{align}
I&=\int_{-1}^3\left(\int_{x^3}^{2x+3}x+y^2\ dy\right)dx=\int_{-1}^{2}\left[xy+\frac{y^3}{3}\right]^{y=2x+3}_{y=x^2} dx=\int_{-1}^{3}\left[ xy+\frac{y^3}{3} \right]^{y=2x+3}_{y=x^2} dx \\
&=\int_{-1}^3\left(x(2x+3)+\frac{(2x+3)^3}{3}-x^3-\frac{x^6}{3}\right)dx \\
&=\int_{-1}^{3}\left(2x^2+3x+ \frac{(2x+3)^3}{3}-x^3-\frac{x^6}{3} \right)dx \\
&=\left[\frac{2}{3}x^3+\frac{3}{2}x^2+\frac{(2x+3)^3}{3}-\frac{x^4}{4}-\frac{x^7}{21}\right]^{x=3}_{x=-1}=\ldots= \frac{3776}{21}
\end{align}$$
### Osservazione
Se $D_1,\ldots,D_k$ regioni semplici che non hanno (a due a due) punti in comune oltre ad una parte della frontiera, allora ogni funzione continua su $$D_1\cup D_2\cup\ldots\cup D_k$$è integrabile e $$\iint_D f(x,y)\ dxdy=\iint_{D_1} f\ dxdy+\ldots+\iint_{D_k} f\ dxdy$$
# Cambiamento di Variabile negli Integrali Doppi 
$$\int_a^b f(x)\ dx=\int_{g^{-1}(a)}^{g^{-1}(b)} f(g(t))g'(t)\ dt$$ $x=g(t)$ derivabile e monotona 
### Definizione 
Un cambiamento di variabili $T:\mathbb{R}^2\to\mathbb{R}^2$ $$T:(u,v)\longmapsto(\underset{=x}{g(u,v)}, \underset{=y}{h(u,v)})$$lega le coordinate $(u,v)$ a $(x,y)$ $$\begin{bmatrix}
x \\
y
\end{bmatrix}=T\left(\begin{bmatrix}
u \\
v
\end{bmatrix}\right)=\begin{bmatrix}
g(u,v) \\
h(u,v)
\end{bmatrix}$$se $T$ è biunivoca, $T^{-1}$ inversa ![[Pasted image 20250102125719.png]]
### Teorema
$T:A\subset\mathbb{R}^2\to\mathbb{R}^2$, $A$ aperto misurabile di classe $C'$, $T(u,v)=g((u,v), h(u,v))$ che sia:
- biunivoca da un aperto misurabile $S$ del piano $(u,v)$ in un aperto misurabile $T=T(S)$ del piano $(x,y)$
- La matrice $$DT=\begin{pmatrix}
g_u & g_v \\
h_u & h_v
\end{pmatrix}\begin{matrix}
(\nabla g) \\
(\nabla h)
\end{matrix}$$ha determinante non nullo e limitato 
Allora, per ogni $f:T\to\mathbb{R}$ integrabile vale $$\iint_T f(x,y)\ dxdy=\iint_S f(g(u,v),h(u,v))|\det DT|\ dudv$$ $x=\rho\cos\theta=g(\rho,\theta)(u,v)=(\rho,\theta), \ y=\rho\sin\theta=h(\rho,\theta)$ $$\begin{align}
&\det\begin{pmatrix}
\cos\theta & -\rho\sin\theta \\
\sin\theta & \rho\cos\theta
\end{pmatrix}=\rho\cos^2\theta+\rho\sin^2\theta=\rho\quad \small\begin{matrix}
\rho\in[a,b] \\
\theta\in[\alpha, \beta]
\end{matrix} \\
&\iint_T f\ dxdy=\int_\alpha^\beta\left(\int_a^bf(\rho\cos\theta,\rho\sin\theta)\rho \ d\rho\right)d\theta
\end{align}$$
### Osservazione
Le coordinate polari sono utili nel caso di circonferenze, corone circolari, settori circolari.

Il teorema di prima è per aperti misurabili. Per le coordinate polari si ha bisogno del seguente:
### Corollario
$T:A\subset\mathbb{R}^2\to\mathbb{R}$ trasformazione di classe $C'$
- biunivoca da $(u,v)$ e $(x,y)$ come prima 
- $\det DT$ non nullo come prima
Allora, per ogni chiuso, limitati e misurabile $C\subset A$, ogni funzione $T:D=T(C)\to\mathbb{R}$ vale $$\iint_D f(x,y)\ dxdy=\iint_C f(g(u,v),h(u,v))|\det DT| dudv$$
### Esempio
$D$ quadrato di vertici $(\pm 1,0)$ e $(0,\pm1)$ $$\iint_D(x^2-y^2)\ dxdy$$![[Pasted image 20250102144519.png]]
Utilizzando il cambiamento di variabili $x=\frac{u+v}{2}$ $y=\frac{u-v}{2}$ $$T\left(\begin{bmatrix}
u \\
v
\end{bmatrix}\right)=\begin{pmatrix}
\frac{1}{2} & \frac{1}{2}  \\
\frac{1}{2} & -\frac{1}{2}
\end{pmatrix}\begin{pmatrix}
u \\
v
\end{pmatrix}$$Si ricava $u=x+y$, $v=x-y$ $$T^{-1}\left(\begin{bmatrix}
x \\
y
\end{bmatrix}\right)=\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}\begin{pmatrix}
x \\
y
\end{pmatrix}$$ $C=T^{-1}(D)\quad \underset{quadrato}{(1,1),\ (-1,1),\ (1, -1),\ (-1,-1)}$
$\det DT= -\frac{1}{2}\quad x=\frac{u+v}{2}$, $y=\frac{u-v}{2}$ $$\begin{align}
&\iint_D(x^2-y^2)^2\ dxdy =\iint_C\left(\left( \frac{u+v}{2} \right)^2 -\left( \frac{u-v}{2} \right)^2  \right)^2\underset{|\det DT|}{\frac{1}{2}}\ dudv  \\
&=\frac{1}{2}\iint_C \left( \frac{u^2+v^2+2uv}{4}- \frac{u^2+v^2-2uv}{4} \right)^2\ dudv = \frac{1}{2}\iint_C \left( \frac{4uv}{4} \right)^2\ dudv \\
&=\frac{1}{2}\iint_Cu^2v^2\ dudv=   \frac{1}{2} \iint_{[-1,1]\times[-1,1]}u^2v^2\ dudv = \frac{1}{2}\int_{-1}^{1} u^2\ du
\int_{-1}^1 v^2\ dv = \frac{2}{9}\end{align}$$
![[Pasted image 20250102150338.png]]
$x=\rho\cos\theta$, $y=\rho\sin\theta$
$$\int_0^{\pi/2}\int_1^2 f(\rho\cos\theta, \rho\sin\theta)\rho\ d\rho d\theta$$
$[0, \frac{\pi}{2}]\times[1,2]$ $\{1<x^2+y^2<2, \ x,y>0\}$

![[Pasted image 20250102151013.png]]
$$\iint_T \frac{x}{x^2+y^2}\ dxdy$$$T$ è la parte di corona circolare delimitata da $x^2+y^2=1$ e $x^2+y^2=4$ $$\begin{align}
&\begin{cases}
x=\rho\cos\theta \\
y=\rho\sin\theta
\end{cases}\quad \theta\in\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right], \ 1\le\rho\le2 \\
\iint_T \frac{x}{x^2+y^2}\ dxdy &=\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \frac{\rho\cos\theta}{\rho^2\cos^2\theta+\rho^2\sin^2\theta}\rho\ d\rho d \theta=\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \frac{\cancel{\rho}^2\cos\theta}{\cancel{\rho^2}}\ d\rho d\theta  \\
&=\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}[\rho\cos\theta]^{\rho=2}_{\rho=1}\ d\theta=\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}(2\cos\theta-\cos\theta)\ d\theta=\int_{-\frac{\pi}{2}}^{\frac{\pi}{2}}\cos\theta\ d\theta \\
&=\sin\theta|^{\pi/2}_{-\frac{\pi}{2}}=2
\end{align}$$

$$\begin{align}
&I_R=\iint_{\{x^2+y^2<R^2\}}e^{-(x^2+y^2)}\ dxdy \\
&\int_0^{2\pi}\int_0^R e^{-(\rho^2\cos\theta+\rho^2\sin^2\theta)}\rho\ d\rho d\theta=\int_0^{2\pi}\int_0^R\rho e^{-\rho^2}\ d\rho d\theta=\int_0^{2\pi}\left[ -\frac{1}{2}e^{-\rho^2} \right]^R_0\ d\theta \\
&=\int_0^{2\pi}\left( -\frac{1}{2}e^{-R^2}+\frac{1}{2} \right) d\theta=\left( -\frac{1}{2}e^{-R^2}+\frac{1}{2} \right)\theta|_0^{2\pi}=\pi(1-e^{-R^2})
\end{align}$$
# Integrali Doppi Generalizzati
$$\begin{align}
&I=\iint_\mathbb{R}^2 e^{-(x^2+y^2)}\ dxdy \\
&\lim_{R\to\infty}\iint_{\{x^2+y^2<R^2\}}e^{-(x^2+y^2)}\ dxdy = \lim_{R\to\infty}\pi(1-e^{-R^2})=\pi
\end{align}$$Integrale della Gaussiana.
Calcolare $$\begin{align}
&\int_\mathbb{R}e^{-t^2}\ dt \\
&\int_0^{+\infty}e^{-t^2}=\int_0^1e^-t^2\ dt<+\infty \\ \\

&e^{-t^2}\le e^{-t} \quad t\in[1,+\infty] \\
&I=\iint_{\mathbb{R}^2}e^{-(x^2+y^2)}\ dxdy=\pi \\
&\underset{J}{\int_\mathbb{R}e^{-x^2}}\ dx\underset{J}{\int_\mathbb{R}e^{-y^2}\ dx}=J^2\quad J=\int_\mathbb{R} e^{-t^2}\ dt  \\
&\Longrightarrow J^2=\pi\Longrightarrow J=\sqrt{I} =\sqrt{\pi}
\end{align}$$Il risultato per $J$ non è banale perché $e^{-t^2}$ non ha primitiva elementari 
$$\begin{align}
&\iint_{\{x^2+y^2<1\}} \frac{1}{(\sqrt{x^2+y^2})^\alpha}\ dxdy \quad \left( \int_0^1 \frac{1}{x^\alpha}\ dx\right) \\
&I=\lim_{r\to0^+}\iint_{\{r<x^2+y^2\}} \frac{1}{(\sqrt{x^2+y^2})^\alpha}\ dxdy = \lim_{r\to0^+}\int_0^{2\pi}\int_r^1 \frac{1}{\rho^\alpha}\rho\ d\rho d \theta \\
&= \lim_{r\to0^+}\int_r^1\int_0^{2\pi} \frac{1}{\rho^{\alpha-1}}\ d\theta d\rho= \lim_{r\to0^+}\int_r^1 \frac{1}{\rho^{\alpha-1}}\theta|_0^{2\pi}d\rho=\lim_{r\to 0^+}2\pi\int_\pi^1 \frac{1}{\rho^{\alpha-1}}d\rho \\
&\overset{\alpha\ne2}{=}\lim_{r\to 0^+}2\pi\left[ \frac{\rho^{2-\alpha}}{2-\alpha} \right]^{\rho=1}_{\rho=r}=\lim_{r\to 0^+}2\pi\left[ \frac{1}{2-\alpha}- \frac{r^{2-\alpha}}{2-\alpha} \right]= \lim_{r\to 0^+} \frac{2\pi}{2-\alpha}[1-r^{2-\alpha}]= \\
&=\begin{cases} \frac{2\pi}{2-\alpha} & \alpha<2 \\
+\infty & \alpha>2
\end{cases} \\
&\alpha=2\to I=\lim_{r\to 0^+} -2\pi\log r=+\infty
\end{align}$$Converge se $\alpha<2$, diverge se $\alpha\ge2$
### Esempio
Calcolare l'integrale doppio $$\iint_T\sqrt{x^2-y^2}\ dxdy$$dove $T$ è il trapezio del piano $xy$ di vertici $(1,-1),\ (1,-1),\ (2,2),\ (2,-2)$
![[Pasted image 20250102163530.png]]
$$\begin{align}
&T=\{(x,y)\in\mathbb{R}^2:\ 1\le x\le 2, \ -x\le y\le x\} \\
&\iint_T f\ dxdy =\int_1^2 \left( \int_{-x}^x\sqrt{x^2-y^2}\right)\ dx \\
&\int\sqrt{x^2-y^2}\ dy \quad y=x\sin t\quad x\in\mathbb{R} \ \left( t\in\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right] \right) \\
& \int\sqrt{x^2-x^2\sin^2t}\ x\cos t \ dt = \int x^2\cos^2 t \ dt =\int x^2\cos^2 t \ dt = x^2\int\cos^2 t \ dt =  \\
&\int\sqrt{x^2-y^2}\ x\cos t \ dt =\int x^2\cos^2t \ dt = x^2\int\cos^2 t \ dt \\
&\int\cos^2 t \ dt = \int\cos t \cos t = \sin t \cos t-\int(-\sin^2 t)\ dt = \sin t \cos t +\int\sin^2 t\ dt \\
&
\end{align}
$$
.........
## Cenni Integrale Lebesgue
[[Lebesgue.pdf]]
### Esercizi 
Sia $C$ il cerchio di raggio $r$ e centro $(r,0)$
![[Pasted image 20250103103847.png]]
- a) $\iint_C (x^2+y^2)\ dxdy$ $$\begin{align}
&\begin{cases}
x=r+\rho\cos\theta \\
y=\rho\sin\theta
\end{cases}  \\
\\
&x^2+y^2=(r+\rho\cos\theta)^2+\rho^2\sin^2\theta=r^2+\rho^2\cos^2\theta+2r\rho\cos\theta+\rho^2\sin^2\theta \\ \\
&= r^2+\rho^2+2r\rho\cos\theta \\
 \\
&C\rightsquigarrow A=\{(\rho,\theta):\ 0\le\rho\le r, \ 0\le\theta\le2\pi\} \\
&\iint_A (r^2+2r\rho\cos\theta+\rho^2)\rho\ d\rho d\theta=\ldots=\frac{3}{2}\pi r^4
\end{align}$$
- b) $\iint_C\sqrt{x^2+y^2}\ dxdy$ $$\begin{align} \\
&\begin{cases} x=\rho\cos\theta \\ y=\rho\sin\theta \end{cases} \\ \\
\\
&\iint_C f(x,y)\ dxdy=\iint_R f(r+\rho\cos\theta,\rho\sin\theta)\underset{\rho}{|\det DT|} \\
& C\rightsquigarrow A=\left\{ (\rho,\theta):\ 0\le\rho\le 2\pi\cos\theta, \ 0\in\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right] \right\} \\
&\iint_C\sqrt{x^2+y^2}=\int_{-\frac{\pi}{2}}^{\pi/2}\left(\int_0^{2\pi\cos\theta}\underset{\sqrt{x^2+y^2}}{\rho} \underset{|\det DT|}{\rho} d\rho\right)d\theta=\ldots= \frac{32}{9}r^3
\end{align}$$
### Equazioni Differenziali Parziali
$$\begin{align}
&Du=\{u_{x_1},\ldots,u_{x_n}\} \\
&D^2u=\{u_{x_ix_j}, \ i,j=1,\ldots,n\}
\end{align}$$
EDP di ordine $Z(k)$ è nella forma $$F(x,u(x),Du(x),D^2u(x))=0$$ $u:A\subseteq\mathbb{R}^n\to\mathbb{R}$ incognita, $F:A\times\mathbb{R}\times\mathbb{R}^n\times\mathbb{R}^{n\times n}\to\mathbb{R}$.
Si definisce soluzione classica $u\in C^2(C^k)$ t.c. $F$ è soddisfatta punto per punto
### Esempio
$u_{x_n}$ $$u(x_1,\ldots,x_n)=g(x_1,\ldots,x_{n-1})$$ $g\in C'$ ok

- **Lineari** 
	- $u_t(x,t)+b(x,t)\cdot\nabla u(x,t)=0$ (trasporto)
	- $\Delta u(x)=0=\sum_{i=1}^n u_{x_ix_i(x)}$ (Laplace)
	- $u_t(x,t)-\Delta u(x,t)=0$ (calore)
	- $u_{tt}(x,t)-\Delta u=0$ (onde)
- **Non lineari**
	- $u_t^{(x,t)}+u\cdot u_x^{(x,t)}=0$ (Burger)
	- $u_t+H(x_1\nabla u)=0$ (Hamilton-Jacobi)
	- $\det(D^2u)=f$ (Monge-Ampere)
**Sistemi**
$\begin{cases} u_t+u\cdot\nabla u=-\nabla p \\ div(u)=0 \\ div(u)=\sum_{i=1}^n u_{x_i}\end{cases}$ Eulero per fluidi comprimibili
$\underset{velocità}{u=(u_1,u_2,u_2)}$ $p=$ pressione
$\begin{cases} u_t+u\cdot\nabla u-\Delta u=-\nabla p \\ div(u)=0\end{cases}$ Meccanica dei fluidi (Navier-Stokes)
$u_t-\Delta u=f(u)$ Reazione-Diffusione
**Problemi**
- Determinare delle formule analitiche per le soluzioni, esatte o approssimate
- Sviluppare metodi numerici "veloci" ed "accurati"
- Sviluppare una teoria rigorosa e generale 
- N.B Spesso le soluzioni non sono esplicite e si cerca di sviluppare una teoria per dedurre indirettamente proprietà della soluzione