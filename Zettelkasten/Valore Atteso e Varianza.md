Tags: [[Analisi 2 e Probabilità]] [[University]]
### Definizione
Una v.a. è una funzione a variabili reali definita sullo spazio combinatorio. Una variabile aleatoria è discreta se assume un'infinità al più numerabile di valori $x_1,x_2,\ldots,x_n$ $$F(a)=P\{X\le a\}\quad -\infty<a<\infty$$*Funzione di ripartizione o distribuzione* 
- $F$ non è decrescente $$\begin{align}
&p(a)=P\{X\le a\} \\
&F(a)=\sum_{x\le a}p(x)
\end{align}$$*Funzione di Densità*
## Valore Atteso
### Definizione
$X$ v.a. discreta con densità discreta $p(x)$. Si definisce *Valore Atteso* (o *Speranza Matematica*) $$E[X]=\sum_{x:p(x)>0}x\cdot p(x)$$Media pesata di tutti i possibili valori che $X$ può assumere, ognuno pesato con la rispettiva probabilità
### Esempio
Calcolare $E[X]$, $X=$ lancio di un dado equilibrato $$\begin{align}
&p(1)=p(2)=\ldots=p(6)=\frac{1}{6} \\
&E[X]=1\cdot \frac{1}{6}+2\cdot \frac{1}{6}+3\cdot \frac{1}{6}\cdot\ldots= \frac{7}{2}
\end{align}$$

v.a. $X$, $p(x)$ densità discreta $E[g(x)]$
### Esempio
$X$ assume i valori $-1,0,1$ con probabilità $P=\{X=-1\}=0,2;\ P=\{X=0\}=0,5;\ P=\{X=1\}=0,3$ $$\begin{align}
&E[X^2]\quad Y=X^2\begin{cases}
0 \\
1
\end{cases} \\
&P\{Y=1\}=P\{X=-1\}+P\{X=1\}=0,2+0,3=0,5 \\
&P\{Y=0\}=P\{X=0\}=0,5
\end{align}$$pertanto $$E[Y](=E[X^2])=1\cdot0,5+0\cdot0,5=0,5$$
### Osservazione
$\underset{=0,5}{E[X^2]}\ne(E[X])^2=(-1\cdot0,2+1\cdot0,3)^2=0,01$ vale la seguente proprietà
### Proposizione
$X$ v.a. discreta che assume i valori $x_i,\ i\ge 1$ con probabilità $p(x_i)(=P\{X=x_i\})$, allora per ogni funzione a valori reali $g$ $$E[g(x)]=\sum_ig(x_i)p(x_i)$$
### Corollario
Siano $a,b\in \mathbb{R}$, $E[aX+b]=aE[X]+b$ $$\begin{align}
E[aX+b]&=\sum_i(ax_i+b)p(x_i)=\sum_iax_ip(x_i)+\sum_ibp(x_i) \\
&=a\underset{def\ E[X]}{\underline{\sum_ix_ip(x_i)}}+b \underset{=1}{\underline{\sum_ip(x_i)}}
\end{align}$$$E[X]=$ media pesata
$Var(X)=$ *Varianza* (indica la variabilità o la dispersione dei valori)
### Definizione
$X$ v.a. a valori discreti con media $\mu=E[X]$ $$Var(X)=E[(X-\mu)^2]$$
### Osservazione
$$\begin{align}
Var(X)&\overset{def. \ di\ varianza}{=} E[(X-\mu)^2]\overset{def.\ valore\ atteso}{=}\overset{\sum_i(x_i-mu)^2p(x_i)}{\sum_x(x-\mu)^2p(x)} \\
&=\sum_x(x^2-2\mu x+\mu^2)p(x)=\sum_xx^2p(x)-2\mu\sum_x x p(x)+\mu^2\sum_xp(x) \\
&= \overset{=\sum_ix_i^2p(x_i)}{E[X^2]}-2\mu \overset{\mu}{E[X]}+\mu^2\cdot1=E[X^2]-2\mu^2+\mu^2=E[X^2]-\mu^2 \\
&= E[X^2]-(E[X])^2
\end{align}$$
### Osservazione
$E[X^2]\ne(E[X])^2$
### Esempio
Calcolare $Var(X)$ $X=$ lancio del dado $$\begin{align}
&E[X]=\frac{7}{2} \\
&E[X^2]\overset{def}{=}\sum^6_{i=1}x_i^2p(x_i)=1^2 \frac{1}{6}+2^2 \frac{1}{6}+\ldots=\frac{91}{6} \\
&Var(X)\overset{OSS}{=}E[X^2]-(E[X])^2=\frac{91}{6}-\left( \frac{7}{2} \right)^2=\frac{35}{12}
\end{align}$$
#### Proprietà
Dati $a,b\in\mathbb{R}$ $$Var(aX+b)=a^2Var(X)$$
### Definizione
Si dice *Deviazione Standard* $\sigma_x=\sqrt{Var(X)}$ 
- Momenti di ordine $k$: $E[X^k]=\sum_i x_i^kp(x_i)$
- Momenti centrati di ordine $k$: $E[(X-E[X])^k]$
Per $K=2$ momento centrato di ordine $2$ e la varianza $$\overset{=g(x)=(x-\mu)^k}{E[(X-E[X])^k]}=\sum_i(x_i-\mu)^kp(x_i)\quad \mu=E[X]$$
### Osservazione
$E[(X-E[X])^2]$ se $X$ prende valori lontani dalla media $(X-E[X])^2$ assumerà valori "grandi", e quindi anche le varianze.
Se $X$ è costante, $E[X]=C$, $Var(X)=0\ ((X-E[X])^2=0)$
![[Pasted image 20250106191708.png]]
Questa proprietà è espressa da una disuguaglianza, nota come *Disuguaglianza di Chebyshev*.
### Proposizione (Disuguaglianza di Chebyshev)
$$P\{|X-E[X]|>y\}\le \frac{Var(X)}{y^2}\quad y>0$$
Interpretazione: misura della dispersione
	Se $Var(X)$ è "piccola", la probabilità che $X$ assuma valori lontani della media "è piccola"
### Dimostrazione
Si prende la v.a. $Y=y^2\mathcal X_{\{|X-E[X]>y|\}}$ $$\begin{align}
&\mathcal X_E=\begin{cases}
1& se \text{ si verifica }E \\
0& \text{altrimenti}
\end{cases} \\
&Y=\begin{cases}
y^2 & se\ |X-E[X]|>y \\
0& \text{altrimenti}
\end{cases} \\
&(X-E[X])^2\ge Y
\end{align}$$Infatti, sull'evento $\{|X-E[X]|>y\}$ $$Y\overset{def}{=}y^2\le(X-E[X])^2$$
Sull'evento $\{|X-E[X]|>y\}^c$ $$Y=0\le(X-E[X])^2$$
Si prende la media in $(X-E[X])^2\ge Y$ $$\begin{align}
Var(X)\overset{def}{=}E[(X-E[X])^2]\ge &E[Y] \\
=& E[y^2\mathcal X_{\{|X-E[X]|>y\}}] \\
=& y^2E[\mathcal X_{\{|X-E[X]|>y\}}] \\
=& y^2P\{|X-E[X]|>y\}
\end{align}$$$Var(X)\ge y^2P\{|X-E[X]|>y\}$
$P\{|X-E[X]|>y\}\le \frac{Var(X)}{y^2}$
## Esempi di Variabili Aleatorie Discrete
1) **Bernulloni e Binomiali**
	Si suppone di eseguire una prova o un esperimento i cui esiti possono essere classificati come successo o insuccesso 
		$X=1$ in caso di successo
		$X=0$ in caso di insuccesso $$(*)\ \begin{align}
&p(1)=P\{X=1\}=p \\
&p(0)=P\{X=0\}=1-p
\end{align}$$$0\le p\le1$
### Definizione
Una variabile aleatoria discreta si dice di *Bernulli* se la densità discreta è definita come $(*)$.
Se vengono eseguite $n$ prove indipendenti ognuna delle quali abbai successo o insuccesso con probabilità $p$ e $1-p$
$X=$ numero di successi. $X$ si dice v.a. *Binomiale* di parametri $n$ e $p$ $$\begin{align}
&X\sim B(n,p) \\
&\underset{=P\{X=i\}}{p(i)}=\begin{pmatrix}
n \\
i
\end{pmatrix}p^i(1-p)^{n-i} \\
&\sum_{i=0}^\infty p(i)=\sum^n_{i=0}\begin{pmatrix}
n \\
i
\end{pmatrix}\underset{x}{p^i}\underset{y}{(1-p)}^{n-i}\overset{T. \ del\ binomio}{=}(p+(1-p))^n=1
\end{align}$$
### Esempio
Lancio di 5 monete equilibrate (gli esiti sono indipendenti). $X=$ conta il numero di teste ottenute, $n=5$, $p=\frac{1}{2}$. Determinare la densità discreta $X\sim B(\frac{5,1}{2})$ $$\begin{align}
&P\{X=0\}=\begin{pmatrix}
5 \\
0
\end{pmatrix}\begin{pmatrix}
\frac{1}{2}
\end{pmatrix}^0\begin{pmatrix}
\frac{1}{2}
\end{pmatrix}^5=\frac{1}{32} \\
&P\{X=1\}=\underset{\frac{5!}{1!4!}=5}{\begin{pmatrix}
5 \\
1
\end{pmatrix}} \begin{pmatrix}
\frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2}
\end{pmatrix}^4=\frac{5}{32} \\
&P\{X=2\}=\ldots
\end{align}$$
### Esempio
Fabbrica che produce viti, è noto che le viti prodotte presentano un difetto in maniera indipendente una dall'altra, con probabilità pari a $0,01$. La fabbrica vende le viti in confezioni da $10$ e sostituisce i pacchetti che contengono più di una vite difettosa. Qual'è la percentuale di pacchetti venduti che la fabbrica dovrà sostituire?
$X=$ numero di vite difettose in confezioni da $10$, $n=10$, $p=0,01$ $$\begin{align} \\
P\{X=i\}&=\begin{pmatrix}
10 \\
i
\end{pmatrix}(0,01)^i(1-0,01)^{10-i} \\

P\{X\ge0\}&=1-P(\{X\ge2\}^c)=1-(P\{X=0\}+P\{X=1\}) \\
&=1-\begin{pmatrix}
10 \\
0
\end{pmatrix}(0,01)^0(0,99)^{10}-\begin{pmatrix}
10 \\
1
\end{pmatrix}(0,01)^1(0,99)^9\approx 0,004\ (0,4\%)
\end{align}$$
### Proprietà delle Variabili Aleatorie Binomiali
$$\begin{align}
&X\sim B(n,p)\quad E[X]=np\quad Var(x)=np(1-p)=E[(X-E[X])^2]=E[X^2]-(E[X])^2 \\
&E[X^k]=\sum^n_{i=0}i^k\begin{pmatrix}
n \\
i
\end{pmatrix}p^i(1-p)^{n-i}=\sum_{i=0}^ni^{k-1}i\begin{pmatrix}
n \\
i
\end{pmatrix}p^i(1-p)^{n-i} \\
&=\sum^n_{i=1}i^{k-1}n\begin{pmatrix}
n-1 \\
i-1
\end{pmatrix}p^i(1-p)^{n-i}=n\sum^n_{i=1}i^{k-1}\begin{pmatrix}
n-1 \\
i-1
\end{pmatrix}p^{i-1}p(1-p)^{n-1} \\
&=np\sum_{i=1}^ni^{k-1}\begin{pmatrix}
n-1 \\
i-1
\end{pmatrix}p^{i-1}(1-p)^{n-i}=........... \\
\end{align}$$
