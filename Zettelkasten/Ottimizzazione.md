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
2