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
![[Pasted image 20241229114810.png]]
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
![[Pasted image 20241229130735.png]]

**N.B** $D\subseteq\mathbb{R}^n$ misurabile. Si definisce ill volume $n-dim$ di $D$ $$Vol_n(D)=\int_D1 \ dx$$($Vol_1(D)=$ lunghezza, $Vol_2(D)=$ area, $Vol_3(D)=$volume)
