Tags: [[Analisi 2 e Probabilità]] [[University]] 

# Funzioni Convesse
**Segmento:** $x,y\in\mathbb{R}^n \quad [x,y]=\{ty+(1-t)x: \ t\in[0,1]\}$
### Definizione
Un insieme $A$ si dice *Convesso* se per ogni $x,y\in A$ il segmento $[x,y]$ è contenuto in $A$.
### Definizione
$A\subset\mathbb{R}^n$ convesso, $f:A\to\mathbb{R}$ si dice *Convessa* se per ogni coppia di punti $x_1,x_2\in A$ si ha $$f(tx_1+(1-t)x_2)\le tf(x_1)+(1-t)f(x_2) \ \forall t\in[0,1]$$se $<$ si dice *Strettamente Convessa*, se $-f$ convessa  si dice *Concava*.
### Esempio
$f(x)=|x|\quad x\in\mathbb{R}^n\quad t\in[0,1]$ $$\begin{align}
f(tx_1+(1-t)x_2)&=|tx_1+(1-t)x_2|
 \\ &\le t|x_1|+(1-t)|x_2| \\
& =tf(x_1)+(1-t)f(x_2) \\
f(x)=|x|^p \ su \ \mathbb{R}^n
\end{align}
$$ $f(x)=g(|x|)$  $\overset{g(t)=t^p}{g}$ convessa e crescente è convessa $$\begin{align}
f(tx_1+(1-t)x_2)&=g(|tx_1+(1-t)x_2|) \\
&\overset{g \ crescente}{\le}g(t|x_1|+(1-t)|x_2|) \\
&\overset{g \ comvessa}{\le}tg(|x_1|)+(1-t)g(|x_2|)
\end{align}$$ $f(x,y)=h(x)$
### Proprietà
$A$ aperto e convesso
1) $f\in C'(A)$. $f$ convessa $\iff$ per ogni $x_0\in A$ vale
	$f(x)\ge f(x_0)+\nabla f(x_0)\cdot(x-x_0) \ \forall x\in A$
2) $f\in C^2(A)$. $f$ convessa $\iff Hf(x)\ge0 \ \forall x \in A$
#### Conseguenza di 1)
- Se $f$ è strettamente convessa e $x_0$ critico ($\nabla f(x_0)=0$)$\Longrightarrow x_0$ minimo assoluto
- $f$ convessa in $A\iff \forall x\in A$ e $\forall v\in \mathbb{R}^n\quad g(t)=f(x+tv)$ è convessa nel dominio $\{t:x+tv\in A\}$
## Applicazione
### Rifrazione della Luce o legge di Snell
![[Pasted image 20241227174327.png]]
$AC$ raggio a velocità $v_1$
$CB$ raggio a velocità $v_2$
#### Principio di Fermat
La luce segue il percorso di tempo minimo $$\begin{align}
&d_1=|AC|=\sqrt{(x-x_1)^2+y_1^2} \\
&d_2=|CB|=\sqrt{(x-x_2)^2+y_2^2}
\end{align}$$$f(x)= \frac{d_1}{v_1}+ \frac{d_2}{v_2}$ tempo che la luce impiega per andare da $A$ a $B$ $$\begin{align}
f'(x)&=0 \\
 f'(x)&= \frac{1}{\cancel 2 \sqrt{(x-x_1)^2+y_1^2}}\cdot \frac{\cancel 2(x-x_1)}{v_1}+ \frac{x-x_2}{\sqrt{(x-x_2)^2+y^2_2}} \\
&= \frac{\sin\alpha_1}{v_1}- \frac{\sin\alpha_2}{v_2}=0
\end{align}$$ $\frac{\sin\alpha_1}{v_1}= \frac{\sin\alpha_2}{v_2}$ Legge di Snell
# Calcolo Infinitesimo per le Curve 
