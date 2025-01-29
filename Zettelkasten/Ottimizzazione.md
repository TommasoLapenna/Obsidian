Tags: [[Analisi 2 e Probabilità]] [[University]] 

OBIETTIVO: max/min una certa quantità sotto opportune condizioni
	- Ricerca di estremi all'interno del dominio $A$ di $f$ (si chiamano *estremi liberi* se $A$ è aperto)
	- Ricerca estremi assunti su un sottoinsieme di $A$ o sulla frontiera $\partial A$ (*estremi vincolati*) 
	
### Definizione
$A\subseteq\mathbb{R}^n$, $x_0\in A$, $f:A\to\mathbb{R}$. Si dice che $x_0$ è un punto di massimo(minimo) locale per $f$ $$\exists r>0 \ t.c.\quad f(x)\le f(x_0) \ \forall x\in A \cap B_r(x_0)$$
Rispettivamente $f(x)\ge f(x_0)$
Si dice stretto se le disuguaglianze valgono con $<$ e $>$

# Condizioni Necessarie del Primo Ordine
Ricerca di max/min liberi locali e/o locali per funzioni sufficientemente regolari.
### Teorema (di Fermat)
$f:A\subseteq\mathbb{R}^n\to\mathbb{R}$ con $A$ aperto $x_0$ punto di max/min per $f$. Se $f$ è derivabile in $x_0$, allora $$\nabla f(x_0)=0$$
### Dimostrazione 
$x_0$ minimo. Da mostrare che $f_{xj}(x_0)=0 \ \forall j$. $e_1,\ldots,e_n$, si definisce 
$$g(t)=f(x_0+te_j)$$
- $g$ è ben definita in un un intorno di $t=0$ 
- $x_0$ minimo locale per $f$ $\overset{per \ ipotesi}{ \Longrightarrow }t=0$ ($g(0)=f(x_0)$
- $f$ derivabile in $x_0\Longrightarrow g$ derivabile in $t=0$
- $g'(0)=\partial_{x_j}f(x_0)$
Per il Teorema di Fermat (su $g$) $\longrightarrow \partial_{x_j}f(x_0)=g'(0)=0$
### Definizione
Un punto critico (o stazionario) che non è né di massimo né di minimo si dice *Punto di Sella*.
### Osservazione
$f(x,y)=\sqrt{x^2+y^2}$ in $(0,0)$ ha minimo globale (è un cono con vertice $(0,0)$). Però le derivate parziali vanno studiati a parte.
# Richiami di Algebra Lineare
$M$ matrice $n\times n$, $M$ simmetrica
### Definizione
Si chiama *Forma Quadratica* associata a $M$ la funzione
$$\begin{gather}
q_M:\mathbb{R}^n\to\mathbb{R}\\
q_M(x)=<Mx,x>=\sum^n_{i,j=1}m_{ij}x_ix_j
\end{gather}$$
- $q_m\in C^{\infty}(\mathbb{R}^n)$
- $q_M(0)=0$
- $q_M$ è omogenea di grado $2$
### Definizione
Si dice che $M$ è *Definita Positiva(Negativa)* e si scrive $M>0$($M<0$) se
$$\sum_{i,j=1}^nm_{ij}x_ix_j=q_M(x)>0(<0)\quad\forall x\in\mathbb{R}^n\backslash\{0\}$$
$M$ è *Semidefinita Positiva(Negativa)* e si scrive $M\ge0$($\le0$)
$$\begin{align}
q_M(x)&\ge0\quad\forall x\in\mathbb{R}^n \\
(&\le0)\quad \forall x\in\mathbb{R}^n
\end{align}$$
$M$ è *Indefinita* se $M$ non è né $\ge 0$ né $\le0$ (cioè non esistono $x_-,x_+\in\mathbb{R}^n\{0\}$ t.c. $q_M(x_-)<0$, $q_M(x_+)>0$)
### Esercizio
- $M=-I_3=\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}\quad I_3>0$

$$\begin{align}
q_m(x,y,z)&=\left<I_3\begin{pmatrix} x  \\
y \\
z
\end{pmatrix},
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}\right>=\left<\begin{pmatrix}
x \\
y \\
x \\
\end{pmatrix},
\begin{pmatrix}
x \\
y \\
z \\

\end{pmatrix}\right>= \\
&=x^2+y^2+z^2=|(x,y,z)|^2>0\quad \forall(x,y,z)\ne0_{\mathbb{R}^3}
\end{align}$$
- $M=-I_3, \ -I_3<0 \quad q_m(x,y,z)=-x^2-y^2-z^2<0\quad \forall(x,y,z)\ne0_{\mathbb{R}^3}$
- $M=\begin{pmatrix}1 & 0 \\ 0 & 0\end{pmatrix}\quad M\le0$
$$\begin{align}
q_M(x,y)&=\left< \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} \begin{pmatrix}
x \\
y
\end{pmatrix},\begin{pmatrix}
x \\
y
\end{pmatrix}\right>= \\
&=\left<\begin{pmatrix}
x \\
0
\end{pmatrix}, \begin{pmatrix}
x \\
y
\end{pmatrix}\right>=x^2\ge0\quad \forall(x,y,z)\in\mathbb{R}^2
\end{align}$$
- $M=\begin{pmatrix}-1 & 0 \\ 0 & 0\end{pmatrix}\le0$
- $M=\begin{pmatrix} 1 & 0 \\ 0 & -1\end{pmatrix}$
$$\begin{align}
&q_M(x,y)=\left<\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}\begin{pmatrix}
x \\
y
\end{pmatrix},\begin{pmatrix}
x \\
y
\end{pmatrix}\right>=\left<\begin{pmatrix}
x \\
-y
\end{pmatrix},\begin{pmatrix}
x \\
y
\end{pmatrix}\right>=x^2-y^2 \\
&q_M(1,0)=1>0\quad q_M(0,1)=-1<0\Longrightarrow M \ indefinita
\end{align}$$
### Definizione
Si chiama *Minore(Principale)* di ordine $k$ $k\in\{1,2,\ldots,n\}$ di $M$, una sottomatrice di $M$ ottenuta selezionando $k$ righe e $k$ colonne aventi lo stesso indice
### Esercizio
$\begin{pmatrix}a & b \\ b & c\end{pmatrix}$
Ordine $1\quad(a)\quad(c)$
Ordine $2\quad \begin{pmatrix}a & b \\ b & c\end{pmatrix}$
- $\begin{pmatrix} a & b & c\\ b & d & e \\ c & e & f\end{pmatrix}$ 
	i minori principali si ottengono sopprimendo un numero arbitrario di righe e colonne aventi lo stesso indice
Ordine $1\quad(a)\quad(d)\quad(f)$
Ordine $2\quad \begin{pmatrix} a & b \\ b & d\end{pmatrix}, \begin{pmatrix} a & c \\ c & f\end{pmatrix}, \begin{pmatrix}d & e \\ e & f\end{pmatrix}$
Ordine $3 \begin{pmatrix}a & b & c \\ b & d & e \\ c & e & f\end{pmatrix}$

# Riassunto
$M$ matrice simmetrica $n\times n$ 
$$\begin{align}
&q_M:\mathbb{R}^n\to\mathbb{R} \\
&q_M(x)
=<Mx,x>=\sum^n_{i,j=1}m_{ij}x_ix_j\end{align}$$
- $q_M$ definita positiva(negativa) se $q_M(x)>0$($<0$) $\forall x\in \mathbb{R}^n$ 
- $q_M$ semidefinita positiva(negativa) se $q_M\ge0$($\le0$) $\forall x\in\mathbb{R}^n$ 
### Definizione (Minore Principale)
$M\in\mathbb{R}^{n\times n}$, si dice *Minore Principale* $M_k$ di ordine $k$ una sottomatrice di $M$ ottenuta selezionando $k$ righe e $k$ colonne aventi lo stesso indice
### Proposizione 1)
Le seguenti affermazioni sono equivalenti:
	- a) $M\ge0$
	- b) tutti gli autovalori di $M$ sono $\ge0$ (ne esiste uno nullo)
	- c) $\det(M_k)\ge 0$ per ogni minore $M_k$ di ordine $k$, $k\in\{1,2,\ldots,n\}$
### Proposizione 2) 
Le seguenti affermazioni sono equivalenti
1) $M\le0$
2) Tutti gli autovalori sono $\le0$ (ne esiste almeno uno nullo)
3)   $\det(M_k)\le0$ per ogni minore $M_k$ di ordine dispari, $\det(M_k)\ge0$ per ogni minore di ordine pari.
### Definizione
Si dice *Minore Principale di Nord-Ovest* di ordine $k$ la matrice $M^{(k)}\in\mathbb{R}^{k\times k}$ ottenuta selezionando le prime $k$ righe e $k$ colonne di $M$
### Esempio
$A=\begin{pmatrix}3 & 0 & 1 \\ 0 & 2 & 4 \\ 1 & 4 & 5\end{pmatrix}\quad\begin{pmatrix}a & b \\ c & d\end{pmatrix}$
$$A^{(1)}=(3)\quad A^{2}=\begin{pmatrix}
3 & 0 \\
0 & 2
\end{pmatrix}\quad A^{(3)}=A$$
### Teorema (di Sylvester)
$M\in\mathbb{R}^{n\times n}$ simmetrica
1) $M$ definita positiva $\iff \det M^{(k)}>0\quad\forall k$
2) $M$ definita negativa $\iff(-1)^k\det(M^{(k)})>0\quad\forall k=1,\ldots,n$
### Osservazione
1)  $M$ definita positiva $\iff$ tutti gli autovalori sono $>0$
2) $M$ definita negativa $\iff$ tutti gli autovalori sono $<0$
2) $M$ è indefinita se esiste almeno un autovalore positivo e uno negativo
### Esempio
$N=2$ $M=\begin{pmatrix}a & b \\ b & c\end{pmatrix}$ simmetrica $\det M=ac-b^2$
- $\det M>0\Longrightarrow M$ è definita 
- $\det M=0\Longrightarrow M$ è semidefinita
-  $\det M<0\Longrightarrow M$ è indefinita
$\det M=\lambda_1\lambda_2\quad T_r(M)=\lambda_1+\lambda_2$
- se $\det M=ac-b^2<0\Longrightarrow M$ è indefinita
- se $\det= \begin{matrix}ac-b^2 \\ ac>b^2\end{matrix}>0 \ \begin{matrix} \underset{c>0}{a>0}\end{matrix}\underset{Sylvester}{\Longrightarrow}M>0$
- se $\det M=ac-b^2=0 \ \begin{matrix} a,c\ge0\Longrightarrow M\ge0 \\ a,c \le\Longrightarrow M\le0\end{matrix}$
### Proposizone
$M\in \mathbb{R}^{2\times 2}$ simmetrica, $\det M=\lambda_1\lambda_2$ $T_2(M)=\lambda_1+\lambda_2$
1) $M\ge 0 \iff \det M=0$ e $T_r(M)\ge0$
2) $M\le0\iff\det M=0$ e $T_r(M)\le0$
3) $M\ge0\iff\det M>0$ e $T_r(M)>0$
4) $M<0\iff\det M>0$ e $T_r(M)<0$
5) $M$ è indefinita se $\det M<0$
### Teorema (Condizione necessaria per estremi locali 2° ordine)
$A$ aperto, $f:A\to\mathbb{R}$, $f\in C^2(A)$, $x_0\in A$
- Se $x_0$ è massimo locale $\Longrightarrow \begin{cases}\nabla f(x_0)=0 \\ H f(x_0)\le0\end{cases}$
- Se $x_0$ è minimo locale $\Longrightarrow\begin{cases}\nabla f(x_0)=0 \\ H f(x_0)\ge0\end{cases}$
### Dimostrazione
$x_0$ minimo per $f$, $v\in\mathbb{R}^n$ fissato $$F(t)=f(x_0+tv)$$$t=0$ minimo per $F$, $F''(0)\ge0$
$$\begin{align}
&F''(t)\overset{verificare}{=}\sum^n_{i,j=1}f_{x_ix_j}(x_0+tv)v_iv_j \\
&F''(0)\ge0\iff\sum^n_{i,j=1}\overset{q_{Hf}(x_0)}{f_{x_ix_j}(x_o)}v_iv_j\ge0
\end{align}$$
### Osservazione (Corollario)
- Max) $f_{x_ix_i}(x_0)\le0$
- Min) $f_{x_ix_i}(x_0)\ge0$
Infatti $\sum^n_{i,j=1}f_{x_ix_j}(x_0)v_iv_j\le0(\ge0)$ prendendo $v=(0,\ldots,\overset{i}{1},0,\ldots,0)=e_i$
### Osservazione
Come in Analisi I, La condizione non è sufficiente: $$\begin{align}
&f(x)=x^3\quad\begin{matrix} f'(0)=0 \\
f''(0)=0
\end{matrix}\quad x=0 \text{ non è né massimo né minimo} \\
&f(x)=x^4\quad\begin{matrix} f'(0)=0 \\
f''(0)=0
\end{matrix}\quad x=0 \text{ non è un massimo}
\end{align}$$
### Teorema (Condizioni Sufficienti del 2° Ordine per Estremi Locali)
$A$ aperto, $f:A\to\mathbb{R}$, $\\f\in C^2(A)$, $x_0\in A$
- Max) Se $\begin{cases}\nabla f(x_0)=0 \\ Hf(x_0)<0\end{cases}\Longrightarrow x_0$ è un massimo locale
- Min) Se $\begin{cases}\nabla f(x_0)=0 \\ Hf(x_0)>0\end{cases}\Longrightarrow x_0$ è un minimo locale
Se $x_0$ è critico e $Hf(x_0)$ è indefinita $\Longrightarrow x_0$ è un punto di sella
### Esempi
1) $f:\mathbb{R}^2\to\mathbb{R}$, $f(x,y)=x^2+y^2$
	Si determina $(x,y)$ t.c. $\nabla f(x,y)=0$ $$\begin{cases}
f_x=2x=0 \\
f_y=2y=0
\end{cases}\iff\begin{cases}
x=0 \\
y=0
\end{cases}$$$(0,0)$ punto critico $$Hf(x,y)=\begin{pmatrix}
f_{xx} & f_{xy} \\
f_{yx} & f_{yy}
\end{pmatrix}=\begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}>0$$$\Longrightarrow(0,0)$ punto di minimo locale
	Metodo alternativo: $(0,0)$ è l'unico punto critico e $f(0,0)=0$ e $f(x,y)=x^2+y^2\ge0=f(0,0)$ $\forall(x,y)\in\mathbb{R}^2$ 
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:x*x+y*y", [-5, 5], [-5, 5]]}
]
```
2) $f(x,y)=-x^2-y^2$ $$Hf(0,0)=\begin{pmatrix}
-2 & 0 \\ 0 & -2
			\end{pmatrix}$$$(0,0)$ massimo locale (anche globale) $f=-x^2-y^2\le0$
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:-x*x+-y*y", [-5, 5], [-5, 5]]}
]
```
3) $f(x,y)=x^2-y^2$ $$Hf=\begin{pmatrix}
2 & 0 \\ 0 & -2
\end{pmatrix}\Longrightarrow\det Hf(0,0)=-4<0$$
$(0,0)$ è un punto di sella
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:x*x-y*y", [-5, 5], [-5, 5]]}
]
```

4) $f(x,y)=xy$ $$Hf(0,0)=\begin{pmatrix}
0 & 1 \\ 1 & 0
\end{pmatrix}\Longrightarrow \det Hf(0,0)=-1$$
$(0,0)$ è un punto di sella
```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: functiongraph3d, def: ["f:x*y", [-5, 5], [-5, 5]]}
]
```
### Esempio
$f(x,y)=3x^2+y^2-x^3y$ determinare i punti critici
$$\begin{align}
&\begin{cases}
f_x=0 \\
f_y=0
\end{cases}\Longrightarrow\begin{cases}
6x-3x^2y=0 \\
2y-x^3=0
\end{cases}\Longrightarrow\begin{cases}
6x-\frac{3}{2}x^5=0 \\
y=\frac{x^3}{2}
\end{cases} \\
&\begin{cases}
3x( 2-\frac{x^4}{2})=0 \\
y=\frac{x^3}{2}
\end{cases}\iff\begin{cases}
x=0 \\
y=0
\end{cases}\lor\begin{cases}
x=-\sqrt{2} \\
y=-\sqrt{2}
\end{cases}\lor\begin{cases}
x=\sqrt{2} \\
y=\sqrt{}2
\end{cases} \\
\end{align}$$
$$Hf(x,y)=\begin{pmatrix}
\overset{f_{xx}}{6-6xy} & \overset{f_{xy}}{-3x} \\
\underset{f_yx}{-3x^2} & \underset{f_{yy}}{2}
\end{pmatrix} \quad Hf(0,0)=\begin{pmatrix}
6 & 0 \\
0 & 2
\end{pmatrix}>0$$
$(0,0)$ punto di minimo locale
### Osservazione
$f(x,1)=3x^2+1-x^3\overset{x\to+\infty}{\longrightarrow}-\infty$
- $(\sqrt{2},\sqrt{2})$ 
$$\begin{align}
&Hf(\sqrt{2}, \sqrt{2})=\begin{pmatrix}
-6 & -6 \\
-6 & 2
\end{pmatrix} \\
& \det Hf(\sqrt{2}, \sqrt{2})<0
\end{align}$$
$\Longrightarrow Hf(\sqrt{2}, \sqrt{2})$ è indefinita $\Longrightarrow(\sqrt{2}, \sqrt{2})$ è punto di sella
- $(-\sqrt{2}, -\sqrt{2})$ punto di sella (stesso modo)
### Ricorda:
$f\in C^2(A)$, $(x_0,y_0)\in A$ punto critico $$Hf(x_0,y_0)=\begin{pmatrix}
f_{xx}(x_0,y_0) & f_{xy}(x_0,y_0) \\
f_{yx}(x_0,y_0) & f_{yy}(x_0,y_0)
\end{pmatrix}$$
1) Se $\det Hf(x_0,y_0)>0$ e
	- $f_{xx}(x_0,y_0)>0$ allora $(x_0,y_0)$ è minimo locale
	- $f_{xx}(x_0,y_0)<0$ allora $(x_0,y_0)$ è massimo locale
	($\det Hf=f_{xx}f_{yy}-f_{xy}^2>0$, $f_{yy}$ ha lo stesso segno di $f_{xx}$)
2) Se $\det Hf(x_0,y_0)<0\Longrightarrow(x_0,y_0)$ è punto di sella
3) Se $\det Hf(x_0,y_0)=0$ occorre un'analisi ulteriore
### Osservazione
In 3) $Hf(x_0,y_0)\ge0(\le0)$
## Strategia per cercare Max e Min per $f:A\to\mathbb{R}^2$
###### Step 1)
Si isolano i punti in cui $f$ non è regolare (ad esempio non derivabile una o due volte. Questi punti vanno esaminati a parte)
###### Step2)
Tolti i punti anomali, si determinano i punti critici risolvendo $$\nabla f(x)=0$$
###### Step 3)
Si studia la natura dei punti critici analizzando il segno della f.q. associata a $Hf$
- Se f.q. è definita o indefinita si usano i Teoremi di prima
- Se f.q. è nulla o semidefinita, per esempio:
	1) Incremento
		$$f(x_0+h)-f(x_0)=\underset{=0}{\overset{=0}{\nabla f(x_0)}\cdot h}+\frac{1}{2}\sum^n_{i,j=1}f(x_0)h_ih_j+o(|h|^2)$$
		es. $f(x_0+h)\ge f(x_0)$
	2) Tecnica delle restrizioni per provare che un punto è di sella
### Esempio (per 2))
Studiare max e min locali di $f(x,y)=x^4-6x^2y^2+y^4$ $$\begin{align}
&\begin{cases}
f_x=4x^3-12xy^2=0 \\
f_y=4y^3-12x^2y=0
\end{cases} \\
& \begin{cases}
x=0 \\
y=0
\end{cases}\quad (0,0)\qquad Hf(0,0)=\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix} \\
& f(x,0)=x^4\rightsquigarrow x=0 \ \text{min} \\
& f(0,y)=y^4\rightsquigarrow y=0 \ \text{min} \\
& f(x,x)=-4x^4\rightsquigarrow x=0 \ \text{max}
\end{align}$$ $\Longrightarrow(0,0)$ non è né di ma né di min 
## Esercizi 
##### $f(x,y)=2(x^4+y^4+1)-(x+y)^2$
$(0,0)$ critico con $\det Hf=0$ ($Hf(0,0)=\begin{pmatrix} -2 & -2 \\ -2 & -2\end{pmatrix}$)
$$\begin{align}
g(x)&=f(x,mx)=2(x^4+m^4x^4)+2-(x+mx)^2 \\
&= 2(1+m^4)x^4-(1+m)^2x^2+2 \\
g'(x)&=8(1+m^4)x^3-2(1+m)^2x=0
\end{align}$$
Si annulla in $x=0$
$$\begin{align}
g''(x)&=24(1+m^4)x^2-2(1+m)^2 \\
g''(0)&=-2(1+m)^2<0\quad m\neq-1
\end{align}$$
In $x=0$ per $m\neq-1$ $g''(0)<0$ e in $x=0$ massimo relativo
In $x=0$ per $m=-1$ $g''(0)=0$ $$\begin{align}
&g^{(iii)}(x)=48(1+m^4)x\quad g^{(iii)}(0)=0 \\
&g^{(iv)}(x)=48(1+m^4)\quad g^{(iv)}(0)\overset{m=-1}{=}96>0
\end{align}$$ $x$ minimo locale $$\begin{align}
&g(x)=\overset{2}{g(0)}+\cancel{g'(0x)}+\cancel{\frac{1}{2}g''(0)x^2}+\cancel{\frac{1}{3!}g^{(iii)}(0)x^3}+\overset{>0}{\frac{1}{4}g^{(iv)}(x)}+\ldots \\
&g(x)=2+\overset{>0}{kx^4}+o(x^5)>2=g(0)
\end{align}$$ $g(x)>g(0) \ \ x=0$ minimo locale
- RIASSUNTO 
	per $m\neq1\quad x=0$ max locale
	per $m=-1\quad x=0$ min locale
	$(0,0)$ non è né di max né di min 
##### $f(x,y)=\frac{x^3y}{3}+\frac{1}{2}x^2y+\frac{1}{2y^2}$
Determinare i punti critici e studiare la natura. Uno dei punti critici è un caso "dubbio", per studiarlo si deve valutare il segno di $f$ in un intorno di $(0,0)$
$$\begin{align}
&\nabla f(x,y)=0\qquad xy(x+1)=0 \ (1) \\
&\begin{cases}
f_x=0 \\
f_y=0
\end{cases} \ \begin{cases}
x^2y+xy=0 \\
\frac{x^3}{3}+\frac{1}{2}x^2+y=0
\end{cases} \ (2)
\end{align}$$
Da $(1)\Longrightarrow x=0 \lor y=0\lor x=-1$
- $x=0\overset{(2)}{\Longrightarrow}g=0\quad (0,0)$
- $y=0\overset{(2)}{\Longrightarrow} \frac{x^3}{3}+\frac{1}{2}x^2=0\iff x^2(\frac{x}{3}+\frac{1}{2})=0$
- $x=-1\overset{(2)}{\Longrightarrow}y=-\frac{1}{6}\quad (-1,-\frac{1}{6})$
$(0,0), \ \left( -\frac{3}{2},0 \right), \ (-1, -\frac{1}{6})$ punti critici
$$Hf(x,y)=\begin{pmatrix}
2xy+y & x^2+x \\ x^2+x & 1
\end{pmatrix}$$
- $Hf(0,0)=\begin{pmatrix} 0 & 0 \\ 0 & 1\end{pmatrix} \ \det Hf(0,0)=0$ caso dubbio
- $Hf\left( -\frac{3}{2},0 \right)=\begin{pmatrix}0 & -\frac{3}{4} \\ -\frac{3}{4} & 1\end{pmatrix} \ \det Hf\left( -\frac{3}{2},0 \right)<0 \ (-\frac{3}{2},0)$ punto di sella 
- $Hf\left( -1,-\frac{1}{6} \right)=\begin{pmatrix} \frac{1}{6} & 0 \\ 0 & 1\end{pmatrix} \ \det Hf\left( -1,-\frac{1}{6} \right)=\frac{1}{6>0}, \ f_{xx}\left( -1,-\frac{1}{6} \right)=\frac{1}{6}>0$ minimo relativo
Nel caso dubbio:
$$\begin{align}
f(0,0)&=0\qquad f(x,y)-\overset{=0}{f(0,0)}\ge0 (\le 0) \\
f(x,y)&=\overset{1}{y} \overset{(2) \ f(x,y)>0(<0)}{\underset{\ge0}{\frac{1}{2}y+\frac{1}{2}x^2+\frac{1}{3}x^3}} \\
(2)&\ge0\quad y\ge-x^2-\frac{2}{3}x^3
\end{align}$$
In prima approssimazione $(2)\ge0$ per $y\ge-x^2$
```graph
bounds: [-10, 10, 10, -10]
keepAspectRatio: true
elements: [
	{type: functiongraph, def: ["0"]},
	{type: inequality, def: ["e0"], att: {inverse: true, fillOpacity: 0.1}},
	{type: functiongraph, def: ["f:-x*x"]},
	{type: inequality, def: ["e2"], att: {fillOpacity: 0.1}},
]
```
$f$ cambia segno in un intorno di $(0,0)$, quindi $(0,0)$ non è né di max né di min $$f(x_0+h)=f(x_0)+\underset{=0}{\cancel{\nabla f(x_0)\cdot h}}+\frac{1}{2}+\sum f_{x_ix_j}\ldots$$$g(ax+by)\rightsquigarrow g(t)$
$g(\sqrt{x^2+y^2})\rightsquigarrow g(t)$ 