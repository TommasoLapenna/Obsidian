Tags: [[Analisi 2 e Probabilità]] [[University]]

Una variabile aleatoria è una funzione a valori reali definita nello spazio campionario
### Esempio
Lancio di 3 monete equilibrate
$Y=$ il numero di teste che si ottengono
$Y=0,1,2,3$ $$\begin{align}
&P\{Y=0\}=P(\{C,C,C\})=\frac{1}{8} \\
&P\{Y=1\}=P(\{C,C,T\},\{C,T,C\},\{T,C,C\})=\frac{3}{8} \\
&P\{Y=2\}=P(\{C,T,T\},\{T,T,C\},\{T,CT\})=\frac{3}{8} \\
&P\{Y=3\}=P(\{T,T,T\})=\frac{1}{8}
\end{align}$$Dato che $Y$ deve assumere almeno uno dei valori $0,1,2,3$ $$1=P(\cup_{i=0}^3\{Y=i\})=\sum_{i=0}^3P\{Y=i\}$$
### Definizione
Data una v.a., si definisce $$F(X)=P\{X\le x\}$$*Funzione di Ripartizione o Distribuzione*
Rappresenta la probabilità che, per ogni $x$, la v.a. sia minore o uguale a $x$
- $a\le b\Longrightarrow\{X\le a\}$ è contenuto in $\{X\le b\}$, $F(a)=P\{X\le a\}\le F(b)=P\{X\le b\}$, $F$ è non decrescente
### Definizione
Una v.a. si dice *Discreta* se può assumere un'infinità al più numerabile di valori
$X$ v.a. discreta, si definisce *Densità Discreta* $$P(a)=P\{X=a\}$$se $a$ assume i valori $x_1,x_2,\ldots,x_n$
- $P(\underset{X=X_i}{X_i})\ge0\quad i=1,\ldots,n$, $P(X)=0$ altrimenti
- $\sum_{i=1}^\infty P(X_i)=1$
### Esempio
![[Pasted image 20250104171951.png]]
### Esempio
La densità discreta di una v.a. $X$ $$p(i)=P\{X=i\}=c \frac{\lambda^i}{i!},\ c>0,\ i=0,1,2,\ \lambda>0 \ costante$$Calcolare:
1) $P\{x=0\}$
	Si determina $c>0$ $$\begin{align}
&\sum^\infty_{i=0}p(i)=1\iff\sum_{i=0}^\infty c \frac{\lambda^i}{i!}=1 \\
&\sum^\infty_{i=0} \frac{\lambda^i}{i!}=e^\lambda\qquad c\sum^\infty_{i=0} \frac{\lambda^i}{i!}=1 \\
&\qquad\qquad\qquad\quad \ ce^\lambda=1,\ c=e^{-\lambda} \\
&P\{X=0\}=e^{-\lambda} \frac{\lambda^0}{0!}=e^{-\lambda} \\
&P\{X>2\}=1-P\{X\le 2\}=1-(P\{X=0\}+P\{X=1\}+P\{X=2\}) \\
& \qquad\qquad \   = 1-e^{-\lambda}-e^{-\lambda} \frac{\lambda^1}{1!}-e^{-\lambda} \frac{\lambda^2}{2!}-e^{-\lambda}=1-e^{-\lambda} -\lambda e^{-\lambda}- \frac{\lambda^2e^{-\lambda}}{2}
\end{align}$$
### Osservazione
$$F(a)=\sum_{x\le a}p(x)$$
$F(X)=P\{X\le x\}$, $p(x)=P\{X=x\}$
$X$ assume i valori $x_1,x_2,\ldots,x_n$, $x_1<x_2<\ldots x_n$ allora $F$ è costante a tratti (negli intervalli $[x_{i-1},x_i)$) e ha un salto pari a $p(x_i)$ in $x_i$
### Esempio
$X$ v.a. discreta $$\begin{align}
&p(1)=\frac{1}{4}\quad p(2)=\frac{1}{2}\quad p(3)=\frac{1}{8}\quad p(4)=\frac{1}{8} \\
&F(a)=\begin{cases}
0 & se \ a<1 \\
\frac{1}{4} & se\ 1\le a< 2 \\
\frac{1}{4}+\frac{1}{2}+\frac{3}{4} & se \ 2\le a<3 \\
\frac{3}{4}+\frac{1}{8}=\frac{7}{8} & se \ 3\le a<4 \\
\frac{7}{8}+\frac{1}{8} & se\ a\ge 4
\end{cases}
\end{align}$$
```graph
bounds: [-1,3,3,-1]
keepAspectRatio: true
elements: [
	{type: point, def: [1,1/4], att: {name: ""}},
	{type: point, def: [2,1/4], att: {name: ""}},
	{type: point, def: [2,3/4], att: {name: ""}},
	{type: point, def: [3,3/4], att: {name: ""}},
	{type: point, def: [3,7/8], att: {name: ""}},
	{type: point, def: [4,7/8], att: {name: ""}},
	{type: point, def: [4,1], att: {name: ""}},
	{type: point, def: [5,1], att: {name: ""}},
	{type: segment, def: ["e0", "e1"]},
	{type: segment, def: ["e2", "e3"]},
	{type: segment, def: ["e4", "e5"]},
	{type: segment, def: ["e6", "e7"]},
]
```
### Esempio
I componenti prodotti da una ditta possono presentare 2 tipi di difetti, con percentuale del 3% e del 7% rispettivamente. I due tipi di divetti si possono produrre in maniera indipendente l'uno dall'altro in momenti diversi della produzione
1) Qual'è la probabilità che un componente presenta entrambi i difetti?
	$A_1=$ {Componente ha difetto 1}, $A_2=$ {Componente ha difetto 2}, $A_1$ e $A_2$ sono indipendenti per ipotesi
	$p(A_1\cap A_2)\overset{def. \ indip.}{=}p(A_1)\cdotp(A_2)=0,03\cdot0,07=0,0021$
2) Qual'è la probabilità che in componente sia difettoso (cioè che presenti almeno uno dei 2 difetti)
	$p(A_1\cup A_2)=p(A-1)+p(A_2)-p(A_1\cap A_2)=0,03+0,07-0,0021=0,0979$
3)  Qual'è la probabilità che il componente presenti il difetto 1, sapendo che esso è difettoso
	$p(A_1|A_1\cup A_2)\overset{def}{=} \frac{p(A_1\cap(A_1\cup A_2))}{p(A_1\cup A_2)}=\frac{p(A_1)}{p(A_1\cup A_2)}=\frac{0,03}{0,0979}=30,6\%$ 
4) Qual'è la probabilità che il componente presenti solo uno dei difetti sapendo che è difettoso
	$p((A_1^c\cap A_2)\cup (A_1\cap A_2^c)|A_1\cup A_2)$
	$p(F^c)=1-p(F)$
	$1-p(A_1\cap A_2|A_1\cup A_2)$
	Sapendo che il componente è difettoso si può calcolare la probabilità come 1 meno la probabilità che presenti entrambi i difetti
	$\overset{def}{=} \frac{p((A_1\cap A_2)\cap (A_1\cup A_2))}{p(A_1\cup A_2)}=1- \frac{p(A_1\cap A_2)}{p(A_1\cup A_2)}=1- \frac{0,0021}{0,0979}=97,8\%$

