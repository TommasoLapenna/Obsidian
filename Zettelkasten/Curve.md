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
$f:A\subset\mathbb{R}\to\mathbb{R}^m, \ m>1$  ($f_1(t),\ldots,f_m(t)$)
$m=2,3$ 
$\underset{\gamma}{r}:I\subset\mathbb{R}\to\mathbb{R}^m$, $I$ intervallo, $t_0\in I$, $l\in\mathbb{R}^m$
### Definizione
$\lim_{t\to t_0}r(t)=l\in\mathbb{R}^m$ se $\lim_{t\to t_0}|r(t)-l|=0$
$t\mapsto|\underset{\in\mathbb{R}^m}{r(t)-l}|$ è una funzione di variabile reale
$r(t)\to l \iff r_i(t)\to l_i\quad i=1,\ldots,m$
(es. $(\Rightarrow)$ $|\underset{\to0}{r_i(t)-l_i|}\le|\underset{\sqrt{(r_1(t)-l_1)^2+\ldots}}{r(t)-l}|\to0$)
$$\begin{align}
\lim_{t\to t_0}r(t)&=\lim_{t\to t_0}(r_1(t),\ldots,r_m(t)) \\
&=(\lim_{t\to t_0}r_1(t),\ldots, \lim_{t\to t_0}r_m(t))
\end{align}$$
### Definizione 
$I\subset\mathbb{R}$ (limitato o meno, aperto o chiuso). Si dice *Arco di Curva* o *Cammino di $\mathbb{R}^n$* una funzione $r:I\to\mathbb{R}^m$ continua (ovvero se ciascuna $r_i$ è continua) $$\begin{align}
&r:[t_1,t_2]\to\mathbb{R}^3 \\
&r(t)\to(x,y,z)\quad \begin{cases}
x=x(t) \\
y=y(t) \\
z=z(t)
\end{cases} \ t\in[t_1,t_2]
\end{align}$$![[Pasted image 20241227181333.png]]
### Definizione (Sostegno)
L'immagine di $r$ (l'insieme dei punti percorsi dal punto mobile)
- *Chiusa* se $r(a)=r(b)$ con $I=[a,b]$
- *Semplice* se $t_1\neq t_2\Longrightarrow r(t_1)\neq r(t_2)$ con l'eccezione $(t_1,t_2=(a,b)$
(una curva semplice può essere chiusa, ma non può intrecciarsi)
### Esempio
$\begin{cases}x=2\cos t \\ y=3\sin t\end{cases} \ t\in[0,\pi]$ è un arco si ellisse $\frac{x^2}{4}+\frac{y^2}{9}=1$  
```graph
bounds: [-5, 5, 5, -5]
keepAspectRatio: true
elements: [
	{type: curve, def: ["f:2*Math.cos(x)", "f:3*Math.sin(x)", 0, "f:Math.PI"]}
]
```
L'arco di curva è continua, non chiusa e semplice.
Se fosse $t\in[0,2\pi]$ allora sarebbe chiusa, semplice e il sostegno è tutta l'ellisse
## Derivate di Funzioni Vettoriali
$r:I\subset\mathbb{R}\to\mathbb{R}^m\quad f:A\subset\mathbb{R}^2\to\mathbb{R}$
### Definizione
$t_0\in I$, $r:I\subset\mathbb{R}\to\mathbb{R}^m$, $r$ è derivabile in $t_0$ se $$r'(t_0)=\lim_{t\to t_0} \frac{\overset{\in\mathbb{R}^n}{r(t_0+h})-\overset{\in\mathbb{R}^m}{r(t_0)}}{\underset{\in\mathbb{R}}{h}}$$esiste finito.
Se $r$ è derivabile in $I$ con derivata continua $r\in C'(I)$ $$r'(t_0)=\left(\lim_{h\to0} \frac{r_1(t_0+h)-r_1(t_0)}{h},\ldots\right)$$
### Definizione (Arco di Curva Regolare)
$r:I\to\mathbb{R}^m$ si dice *Regolare* se $$\begin{align}
&r\in C'(I) \\
&r'(t)\neq0\quad \forall t\in I
\end{align}$$*Versore Tangente* $T= \frac{r'(t)}{|r'(t)|}$
### Esempio
$r'(t)=(-\sin t, 3\cos t)\neq(0,0)\ \forall t$ $$T=\frac{(-2\sin t,3\cos t)}{\sqrt{4\sin^2 t+9\cos^2 t}}$$
#### Alcune Proprietà utili
$I\subseteq\mathbb{R}$, $u,v:I\to\mathbb{R}^m$
- $(u+v)'=u'+v'$
- $c\in\mathbb{R}$, $(cu)'=cu'$
- $\begin{matrix}f:I\to\mathbb{R} \\ u:I\to\mathbb{R}^m\end{matrix}$ derivabile $(fu)'=f'u+fu'$
- Se $g:\mathbb{R}\to\mathbb{R}$ derivabile $(u(g(t))'=u'(g(t))g'(t)\quad Img\subseteq I$
- $(u\cdot v)'=u'\cdot v+ u\cdot v'$ prodotto scalare
- Se $r:[a,b]\to\mathbb{R}^m$
	$\int^b_a r'(t)=(\int^b_ar_1(t)dt,\ldots, \int^b_a r_m(t)dt)$
- $r:[a,b]\to\mathbb{R}^m\in C'([a,b])$
	$\int^b_ar'(t)dt=r(b)-r(a)$
- Se $r$ è chiusa $\int^b_a r'(t)dt=0$
### Esempi
- **Retta, Segmento, Semiretta**
	Dati $x_1,x_2\in\mathbb{R}^n$ $$r(t)=x_1+t(x_2-x_1) \quad\small{\begin{cases} t\in[0,1] \ segmento \\
t\in\mathbb{R} \ retta \\
t\in[0,+\infty] \ semiretta
\end{cases}}$$
- **Circonferenza**
	$r:[0,2\pi]\to\mathbb{R}^2$ $$r(t)=(R\cos t, R\sin t)$$
- **Ellisse**
- **Poligonale** 
	Dati $x_0,\ldots,x_n\in\mathbb{R}^n$, si dice poligonale l'unione $[x_{i-1},x_i] \ i=0,\ldots,k$ $$\begin{align}
&r(t)=x_{i-1}+(kt-i+1)(x_i-x_{i-1}) \\
& \frac{i-1}{k}\le t\le \frac{i}{k}
\end{align}$$
- **Curve Piane**
	- $y=f(x) \ x\in[a,b]$ $$\begin{cases}
x=t \\
y=f(t)
\end{cases} \ t\in[a,b]$$
	- Equazione in forma polare
## Lunghezza di un Arco di Curva
$r:[a,b]\to\mathbb{R}^m$ parametrizzazione $$\mathcal P=\{a=t_0,t_1,\ldots,t_n=b\} \ di \ [a.b] $$ $t_i$ non necessariamente equidistanti.
La poligonale di estremi $[r(t_{j-1}),r(t_j)]$ $$l(\mathcal P)=\sum^n_{j=1}|r(t_j)-r(t_{j-1})|$$$l(\mathcal P)$ approssima per difetto la lunghezza di $\gamma$.
### Definizione
Si dice che $\gamma$ è *Rettificabile* se $$\sup_{\mathcal P}l(\mathcal P)=l(\gamma)<+\infty$$
### Osservazione (Caso Regolare)
$r'$ è il vettore velocità lungo la curva.
La lunghezza è lo spazio percorso in $[a,b]$ $$\begin{align}
&spazio = vel\cdot tempo \\
&l(\gamma)=\int^b_a|r'(t)|dt
\end{align}$$
### Teorema
$r:[a,b]\to\mathbb{R}^m$ parametrizza un arco di curva regolare $\Longrightarrow\gamma$ è rettificabile e $$l(\gamma)=\int_a^b|r'(t)|dt$$
### Esempi 
1) Lunghezza di un grafico
	$\gamma:\begin{cases} x=t \\ y=f(t)\end{cases} \ t\in[a,b]\quad \gamma'(t)=(1, f'(t))$ $$l(\gamma)=\int_a^b\sqrt{1+(f'(t))^2}dt$$
2) Curve in forma polare
	$\rho=f(\theta)\quad\theta\in[\theta_1,\theta_2]$ $$\begin{align}
&r:\begin{cases}
x=f(\theta)\cos\theta \\
y=f(\theta)\sin\theta
\end{cases}\ \theta\in[\theta_1,\theta_2] \\
& r'(\theta)=(f'(\theta)\cos\theta-f(\theta)\sin\theta,f'(\theta)\sin(\theta)+f(\theta)\cos\theta) \\
&|r'(\theta)|=\sqrt{(f'(\theta)^2+(f(\theta))^2} \\
&l(\gamma)=\int_{\theta_1}^{\theta_2}\sqrt{(f'(\theta))^2+(f(\theta))^2}d\theta
\end{align}$$
## Cambiamenti di Parametrizzazioni 
$r=r(t)$ regolare $t\in[a,b]$ $$\begin{align}
&t=g(u)\quad g:[c,d]\to[a,b]  \ derivabile \ e \ invertibile \\
&r=r(g(u)), \ u\in[c,d] \\
&\begin{cases}
x=R\cos t \\
y=R\sin t
\end{cases} \quad t\in[0,2\pi] \quad \begin{cases}
x=R\cos(2u) \\
y=R\sin(2u)
\end{cases}\quad u\in[0,\pi]\quad\begin{cases}
x=R\cos(-u) \\
y=R\in(-u)
\end{cases}\quad u\in[0,2\pi]
\end{align}$$
### Definizione
La lunghezza di un arco di curva regolare $r(\tau)$ per $\tau\in[t_0,t]$ è una funzione di $t$ $$S(t)=\int_{t_0}^t|r'(\tau)|d\tau$$Se si sa calcolare la funzione $S(t)$ e poi invertirla in funzione di $S$, si ottiene una parametrizzazione, detta *Parametro d'arco (Ascissa Curvilinea)* $$\begin{align}
&\begin{cases}
x=R\cos\theta \\
y=R \sin\theta
\end{cases}\quad\theta\in[0,2\pi] \\
&S(\theta)=\int^{\theta_2}_{\theta_1}\sqrt{R^2\sin^2\theta+R^2\cos^2\theta} \ d\theta=\int^{\theta}_{0}R\ d\theta= \int^{\theta}_{0} R \ d\theta = R\theta
\end{align}$$$\theta= \frac{S}{R}$ $$\begin{cases}
x=R\cos\left( \frac{S}{R} \right) \\
y=R\sin\left( \frac{S}{R} \right)
\end{cases}\quad S\in[0,2\pi R]$$
## Integrale di Linea (di 1° Specie)
### Definizione
Sia $r:[a,b]\to\mathbb{R}^m$ un arco di una curva regolare con sostegno $\gamma$, $f$ una funzione a valore reali definita su $A\subseteq\mathbb{R}^m$ contenente $\gamma$ $$f:A\subseteq\mathbb{R}^m\to\mathbb{R} \ con \ A \supset\gamma$$Si dice *Integrale di Linea* $$\int_\gamma f \ dS \equiv\int_a^b f(r(t))|r'(t)| \ dt$$
#### Significato Geometrico
$m=2$, $f$ positiva e continua, $\gamma$ sostegno
![[Pasted image 20241228161931.png]]

$S=$ superficie formata dai segmenti verticali che congiungono i punti di $\gamma$ con quelli di $f$.
$\int_\gamma f\ dS$ misura dell'area $S$
### Esempio
Parametrizzare il tratto del grafico della funzione $e^x$ compreso tra $x=0$ e $x=1$. Detta $\gamma$ tale curva, calcolare l'integrale su $\gamma$ di $f(x,y)=ye^x$ e la funzione di lunghezza di $\gamma$
$$\begin{align}
&\gamma:\begin{cases}
x=t \\
y=e^t
\end{cases}\quad t\in[0,1] \\
&\gamma'(t)=(1,e^t) \\
&|\gamma'(t)|=\sqrt{1+e^{2t}} \\
&f(\gamma(t))=\underset{y}{e^t}e^{\overset{x}{t}}=e^{2t} \\
&\int_\gamma f= \frac{1}{2}\int_0^1 2\underset{f(\gamma(t))}{e^{2t}}\underset{|\gamma'(t)|}{\sqrt{1+e^{2t}}}\ dt= \frac{1}{2} \frac{(1+e^{2t})^{\frac{3}{2}}}{\frac{3}{2}}\big|^1_0=\ldots \\
&l(\gamma)=\int^1_0|\gamma'(t)| \ dt=\int_0^1\sqrt{1+e^{2t}}\ dt
\end{align}$$
### Osservazione
$r$ generica $l(\gamma)=\sup_{\mathcal P}l(\mathcal P)$. Esistono curve non rettificabili
- L'integrale di linea non dipende dalla parametrizzazione di $\gamma$.
