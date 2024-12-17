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
### 