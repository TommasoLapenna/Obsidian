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
$X=$ numero di vite difettose in confezioni da $10$, $n=10$, $p=0,01$ 
$$\begin{align} \\
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
#### Riassunto 
- **v.a. di Bernulli**
	Prova con successo/insuccesso
	$X=1$ in caso di successo, $X=0$ in caso di insuccesso $$P\{X=0\}=1-p\qquad P\{X=1\}=p$$
- **v.a. binomiale $n,p$**
	$n$ prove indipendenti con $\overset{p}{\text{successo}}$ / $\overset{1-p}{insuccesso}$ 
	$X=$ numero di successi $$P\{X=i\}=\begin{pmatrix}
n \\
i
\end{pmatrix}p^i(1-p)^{n-i}\quad E[X]=np\quad Var(X)=np(1-p)$$
### Proposizione
$X$ v.a. binomiale di parametri $n$ e $p$ $X\sim B(n,p)$, $p\in(0,1)$. Per $k$ che varia tra $0$ e $n$, $P\{X=k\}$ sarà inizialmente strettamente crescente e successivamente decrescente, raggiungendo il massimo nel più grande intero $k\le(n+1)p$
### Dimostrazione
$$\frac{P\{X=K\}}{P\{X=k-1\}}\ge1$$(crescente $P\{X=k\}\ge P\{X=k-1\}$)
Si determina per quali valori di $k$ vale il precedente: $$\begin{align}
&\frac{\begin{pmatrix}
n \\
k
\end{pmatrix}p^k(1-p)^{n-k}}{\begin{pmatrix}
n \\
k-1
\end{pmatrix}p^{k-1}(1-p)^{n-k+1}}=\frac{\frac{n!}{k!(n-k)!}p^k(1-p)^{n-k}}{\frac{n!}{(k-1)!(n-k+1)!}p^{k-1}(1-p)^{n-k+1}}=\frac{p}{1-p} \frac{(n-k+1)}{k}\ge1 \\
&p(n-k+1)\ge(1-p)k \\
&k(1-\cancel{p})+\cancel{kp}\le np+p \\
&k\le(n+1)p
\end{align}$$
### Osservazione
$$\begin{align}
&F_x(a)=\sum_{x\le a,\ p(x)>0}p(x)=\sum_{x\le a,\ p(x)>0}p\{X=x\} \\
&P\{X\le i\}=\sum_{k=0}^i\begin{pmatrix}
n \\
k
\end{pmatrix}p^k(1-p)^{n-k} \\
&P\{X=k+1\}= \frac{p}{1-p} \frac{n-k}{k+1}P\{X=k\}
\end{align}$$
## Variabile di Poisson
### Esempio
Il numero medio di persone che prende il tram in una città è $\lambda=12000$. Qual'è la probabilità che in un dato giorno $k=11900$ persone prendono il tram, sapendo che $n=500000$
$p_n=\frac{\lambda}{n}$ probabilità che ciasxuno prenda il tram (indip. l'uno dall'altro)
$X_n$ = numero di persone che prendono il tram
$X_n\sim B(n,p_n)$ $$\begin{align}
P\{X_n=k\}&=\begin{pmatrix}
n \\
k
\end{pmatrix}\overset{=\frac{n!}{k!(n-k)!}\begin{pmatrix}
\frac{\lambda}{n}
\end{pmatrix}^n\left( 1-\frac{\lambda}{n} \right)^{n-k}}{p_n^k}(1-p_n)^{n-k} \\
&=\begin{pmatrix}
500000 \\
11900
\end{pmatrix}\begin{pmatrix}
\frac{12}{500}
\end{pmatrix}^{11900}\begin{pmatrix}
1-\frac{12}{500}
\end{pmatrix}^{488100}
\end{align}$$Calcolo complicato. Soluzione:$$\begin{align}
&\lim_{n\to+\infty}P\{X_n=k\} \\
&P\{X_n=k\}=\left[ \frac{\lambda^k}{k!}\left( 1-\frac{\lambda}{n}^{-k} \right) \right] \frac{\overset{\frac{n!}{(n-k)!}}{n(n-1)\ldots(n-k+1)}}{n^k}\left( 1-\frac{\lambda}{n} \right)^n\quad n\to+\infty \\
&\lim_{n\to+\infty}\left( 1-\frac{\lambda}{n} \right)^{-k}=1\quad\lim_{n\to+\infty} \frac{n(n-1)\ldots(n-k+1)}{n^k}=1 \\
&\lim_{n\to+\infty}\left( 1-\frac{\lambda}{n} \right)^n=\lim_{n\to+\infty}\left[ \left( 1-\frac{\lambda}{n} \right)^{\frac{n}{-\lambda}} \right]^{-\lambda}=e^{-\lambda} \\
&\lim_{n\to+\infty}P\{X_n=k\}=e^{-\lambda} \frac{\lambda^k}{k!}
\end{align}$$
$n$ grande, $np=\lambda$
### Definizione
v.a. *di Poisson* approssimano le v.a. $B(n,p)$, $n$ grande, $p$ piccolo perché $np$ tende ad un valore finito $\lambda=np$
Alcuni esempi di v.a di Poisson
1) Il numero di errori di stampa in una pagina di un libro
2) Il numero di persone ultracentenarie in una comunità
3) Il numero di numeri di telefono sbagliati in un giorno
### Esempio
$X=$ errori tipografici di una pagina $X\sim Po\left( \frac{1}{\underset{\lambda}{2}} \right)$. Si calcoli la probabilità che ci sia almeno un errore nella pagina $$\begin{align}
&P\{X\ge1\}=1-P(\{x\ge1\}^c)=1-P\{x=0\}\overset{P\{X=i\}=e^{-\frac{\lambda^i}{i!}}}{=}1-e^{\frac{1}{2}} \\
&\overset{B(n,p)}{E[X]=np}\overset{n\to+\infty,\ np=\lambda}{\longrightarrow}E[X]=\lambda \\
&Var(X)=\underset{\lambda}{np}\underset{p\to0}{(1-p)}\quad Var(X)=\lambda \\
\end{align}$$ $$\begin{align}
E[X]&\overset{def}{=}\sum_{i=0}^\infty iP\{X=i\}=\sum_{i=0}^\infty i e^{-\lambda} \frac{\lambda^i}{i!}=e^{-\lambda}\sum_{i=0}^\infty \frac{\lambda^i}{i(i-1)!}=\lambda e^{-\lambda}\sum_{i=1}^\infty \frac{\lambda^{i-1}}{(i-1)!} \\
&\overset{j=i-1}{=}\lambda e^{-\lambda}\underset{e^\lambda}{\sum_{j=0}^\infty \frac{\lambda^j}{j!}}=\lambda e^{-\lambda}e^\lambda=\lambda
\end{align}$$$\sum_{n=0}^\infty \frac{x^n}{n!}=e^x$
$Var(X)=E[X^2]-(E[X])^2$ $$\begin{align}
E[X^2]&\overset{def}{=}\sum^\infty_{i=0}i^2P\{X=i\}=\sum_{i=0}^\infty i^2 e^{-\lambda} \frac{\lambda^i}{i!}=\lambda\sum^\infty_{i=1}ie^{-\lambda} \frac{\lambda^{i-1}}{(i-1)!}\overset{j=i-1}{=}\lambda\sum^\infty_{j=0}(j+1)e^{\lambda} \frac{\lambda^j}{j!} \\
&=\underset{E[X]}{\lambda\sum_{j=0}^\infty je^{-\lambda} \frac{\lambda^j}{j!}}+\underset{=1}{\lambda\sum_{j=0}^\infty e^{-\lambda} \frac{\lambda^j}{j!}}\overset{E[X]=\lambda}{=} \lambda\cdot\lambda+\lambda\cdot e^{-\lambda}\underset{e^\lambda}{\sum_{j=0}^\infty \frac{\lambda^j}{j!}}=\lambda^2+\lambda e^{-\lambda}e^\lambda \\
&=\lambda^2+\lambda
\end{align}$$$Var(X)=E[X^2]-(E[X])^2=\cancel{\lambda^2}+\lambda-\cancel{\lambda^2}=\lambda$ $$\begin{align}
&\sum^\infty_{i=0}P\{X=i\}=1 \\
&\sum_{i=0}^\infty e^{-\lambda} \frac{\lambda^i}{i!}=e^{-\lambda}\sum^\infty_{i=0} \frac{\lambda^i}{i!}=e^{-\lambda}e^\lambda=1
\end{align}$$
#### Ulteriore Utilizzo delle Variabili di Poisson
Un altro utilizzo delle variabili aleatorie di Poisson si ha nelle situazioni in cui gli "eventi" si verificano in certi istanti di tempo
- Verificarsi di un terremoto
- Arrivo di una persona allo sportello postale
### Definizione (Processo di Poisson)
Processo di Poisson di intensità $\lambda$ quando si ha $\{x_t:\ t>0\}$ con le seguenti caratteristiche
1) La probabilità che si verifichi esattamente in un intervallo di lunghezza $t$ è $\lambda t+o(t)$ $$P\{X_t=1\}=\lambda t+o(t)\quad f(t)=o(t)\iff \lim_{t\to0} \frac{f(t)}{t}=0$$
2) La probabilità che 2 o più eventi si verifichino è $o(t)$ $$P\{X_t>1\}=o(t)$$
3) Ciò accade in un intervallo temporale non influenza probabilisticamente ciò che accade in un intervallo di tempo disgiunto dal primo $$P_{X_t}(x)= \frac{(\lambda t)^x}{X!}e^{-\lambda t}\quad x=0,1,2\ldots$$
### Esempio
Si suppone che i terremoti nella parte occidentale degli Stati Uniti si verifichino sotto le ipotesi 1) 2) 3), con una intensità di $\lambda=2$ considerando come unità di tempo 1 settimana. Trovare la probabilità che avvengano almeno 3 terremoti nelle prossime 2 settimane 
$N(t)\quad N_t=$ numero di terremoti nell'unità di tempo $$\begin{align}
&P\{N(t)=k\}= \frac{(\lambda t)^k}{k!} e^{-\lambda t}\quad k=0,1,2\ldots\quad \lambda=2 \\
&P\{N(2)\ge3\}=1-P(\{N(2)\ge 3\}^c) \\
&=1-(P\{N(2)=0\}+P\{N(2)=1\})
+P\{N(2)=2\} \\
 &=1- \frac{(2\cdot 2)^0}{0!}e^{-2\cdot 2}-\frac{(2\cdot2)^1}{1!}e^{-2\cdot 2}- \frac{(2\cdot 2)^2}{2!}e^{-4} \\
&=1-e^{-4}-4e^{-4}-8e^{-4}=1-13e^{-4}
\end{align}$$
## Variabile Aleatoria Geometrica
$n$ prove indipendenti con probabilità $0<p<1$ di avere successo. Si ripetono le prove finché non si ottiene un successo $$P\{X=n\}=\underset{n-1\text{ insuccessi}}{\underline{(1-p)^{n-1}}}\cdot \underset{\text{successo n-esima prova}}{\underline p}$$$X=$ numero di prove per ottenere un successo.
Vale $$\sum^\infty_{n=1}P\{X=n\}=\sum^\infty_{n-1}(1-p)^{n-1}p=p\sum^\infty_{n=1}=p \frac{1}{1-(1-p)}= \frac{p}{p}=1$$
### Esempio
Un urna contiene $N$ palline bianche e $M$ palline nere, estrazioni con reimmisione.Si estrae una pallina alla volta fino a che non si ottiene una pallina nera. Probabilità che si debbano estrarre $n$ palline?
$p=\frac{M}{N+M}$ probabilità del successo $$P\{X=n\}=(1-p)^{n-1}p=\left( \overset{\frac{N}{N+M}}{1-\frac{M}{N+M}} \right)^{n-1} \frac{M}{N+M}= \frac{N^{n-1}M}{(N+M)^2}$$$P\{X\ge n\}=(1-p)^{n-1}=\left( 1-\frac{M}{N+M} \right)^{n-1}=\frac{M}{M+N}\sum^{+\infty}_{k=n}\left( \frac{N}{M+N} \right)^{k=1}$
### Proprietà $X\sim G(p)$
### Proposizione (Assenza di memoria della variabile geometrica) 
$$P\{X=r+s|X>r\}=P\{X=s\}$$
### Dimostrazione
$$\begin{align}
P\{X=r+s|X>r\}&\overset{def}{=} \frac{P(\{X=r+s\}\cap\{X>r\})}{P\{X>r\}}= \frac{P\{X=r+s\}}{P\{X>r\}} \\
&\overset{P\{X=r+s\}\overset{X\sim G(p)}{=}(1-p)^{r+s-1}p}{=} \frac{(1-p)^{\cancel r+s-1}p}{\cancel{(1-p)^r}}=(1-p)^{s-1}p=P\{X=s\}
\end{align}$$
**Nota:** La $P\{X>n\}$ indica la probabilità che siano necessarie $n+1$ estrazioni per ottenere il primo successo. Questa è uguale alla probabilità che le prime $n$ estrazioni siano risultate tutte degli insuccessi  

$X\sim G(p)$
$P\{X=n\}=\underset{q}{(1-p)^{n-1}p\quad n=0,1,2\ldots}$
Valore atteso e varianza di $X\sim G(p)$ $$q=1-p\qquad E[X]\sum_xxp\{X=x\}$$
$$\begin{align}
E[X&]=\sum^\infty_{i=1} iq^{i-1}p=\sum_{i=1}^\infty(i-1+1)q^{i-1}p=\sum^\infty_{i=1}(i-1)q^{i-1}p+\sum^\infty_{i=1}q^{i-1}p \\
&\overset{j=i-1}{=}\sum^\infty_{j=0}jq^jp+1\overset{q^j=qq^{j-1}}{=}q\sum_{j=1}^\infty jq^{j-1}p+1=qE[X]+1
\end{align}$$
$$E[X]=qE[X]+1\Longrightarrow (1-q)E[X]=1$$dato che $q=1-p\quad pE[X]=1,\ E[X]=\frac{1}{p}$
.........
$Var(X)=E[X^2]-(E[X])^2=\frac{1-p}{p^2}$
# Serie di Funzioni (e Serie di Potenze)
$$\begin{align}
&\sum^\infty_{n=0}x^n= \frac{1}{1-x}\quad -1<x<1 \\
&\sum_{n=0}^\infty \frac{x^n}{n!}=e^y\quad \forall x\in\mathbb{R} \\
&f_n:I\to\mathbb{R}\quad I\subset\mathbb{R} \text{ intervallo} \\
&\forall x\in I\quad \sum^\infty_{n=1}f_n(x)
 \\
&f_n=a_n(x-x_0)^n\quad \sum^\infty_{n=1} a_n(x-x_0)^n\ \text{serie di potenze}\end{align}$$
Problemi tipici: $\sum_{n=1}^\infty f_n(x)\quad f(x)\text{ somma della serie}$
1) se $f_n\in C^0(I)\Longrightarrow f\in C^0$ in $I$?
2) se $f_n$ derivabili $\Longrightarrow f$ è derivabile?
	Si può calcolare $f'$ derivando termine a termine le $f_n$
3) Vale $$\int_a^b\sum_{n=1}^\infty f_n(x)\ dx=\sum^\infty_{n=1}\int_a^b f_n(x)\ dx \ ?$$
### Esempio
$\sum_{n=0}^\infty x^n= \frac{1}{1-x}$ $$\begin{align}
& \sum^n_{k=0}x^k= \frac{x^{n+1}-1}{x-1}\text{ derivando termine a termine} \\
&\sum_{k=1}^nkx^{k-1}= \frac{nx^{n+1}-(n+1)x^n+1}{(x-1)^2}
\end{align}$$Per $|x|<1$ e $n\to+\infty$ $$\begin{align}
&nx^{x+1}\to0\quad (n+1)x^n\to0 \\
&\sum_{k=1}^\infty kx^{k-1}=\frac{1}{(x-1)^2}=f'(x) \\
& (\sum^\infty_{k=0}x^k)^1=\sum^\infty_{k=1}kx^{k-1}
\end{align}$$
Una serie non derivabile termine a termine $\sum^\infty_{k=1} \frac{\sin(3^nx)}{2^n}$ $$\begin{align}
&\left| \frac{\sin(3^nx)}{2^n} \right|\le \frac{1}{2^n}\text{ converge assolutamente} \\
&f_n(x)= \frac{\sin(3^nx)}{2^n}\in C^\infty(\mathbb{R})\rightsquigarrow \sum_{n=1}^\infty f'_n(x) \\
& \sum^\infty_{n=1} \frac{3^n\cos(3^nx)}{2^n}\text{ non converge }\forall x\in I \\
&x=0\quad \sum^\infty_{n=1}\left( \frac{3}{2} \right)^n\text{ divergente} 
\end{align}$$
Analizzando le serie di potenze $\sum^\infty_{n=0}a_nx^n\quad a_n(x-x_0)^n$ l'insieme degli $x$ per cui si ha convergenza è un intervallo, la metà di questo intervallo si chaima *Raggio di Convergenza*

Vale una delle seguenti
1) $I=\{x_0\}$
2) $I$ è un intervallo centrato in $x_0$ ($(x_0-R,x_0+R),\ [x_0-R,x_0+R)\ldots$)
3) $I\equiv\mathbb{R}$
$R=$ raggio di convergenza $x_0=0\sum^\infty_{n=0}a_nx^n$
1) **$R$ positivo (finito o infinito)** 
	La somma della serie è derivabile in $(-R,R)$ e la serie può essere derivata termine a termine $$\frac{d}{dx}\left(\sum^\infty_{n=0} a_nx^n\right)=\sum^\infty_{n=1} na_nx^{n-1}\quad R\ne0,\ |x|<1$$
2) **$R$ positivo (finito o infinito)**
	La somma della serie ammette primitiva in $(-R,R)$ che può essere calcolata termine a termine $$\int_0^x\sum_{n=0}^\infty a_nt\ dt=\sum^\infty_{n=0}\int^x_0a_nt^n\ dt=\sum^\infty_{n=0} \frac{a_nx^{n+1}}{n+1}$$
$$\begin{align}
E[X]&\overset{|q|<1}{=}\sum^\infty_{i=1}iq^{i-1}p=p\sum_{i=1}^\infty iq^{i-1}=p\sum^\infty_{i=1} \frac{d}{dq}(q^i)=p \frac{d}{dq}\left(\sum^\infty_{i=1}q^i\right)=p \frac{d}{dq}\left( \frac{1}{1-q} \right) \\
&= p \frac{1}{(1-q)^2}\overset{q=1-p}{=} \frac{p}{p^2}= \frac{1}{p}
\end{align}$$
$$E[X^2]=\sum^\infty_{i=1} i^2q^{i-1}p=p\sum^\infty_{i=1} \frac{d}{dq}(iq^i)=\ldots= \frac{2}{p^2}-\frac{1}{p}$$
### Esempio
$X\sim G(p)$, provare che $E\left[ \frac{1}{X} \right]= \frac{-p\log p}{1-p}\quad q=1-p$ $$E[g(x)]=\sum_x g(x)P\{X=x\}=\sum_{x_i} g(x_i)= P\{X=x_i\}$$
$$\begin{align}
E\left[ \frac{1}{X} \right]&= \sum^\infty_{i=1} \frac{1}{i}q^{i-1} p \ \frac{q}{q}= \frac{p}{q}\sum^\infty_{i=1} \frac{q^i}{i}=\frac{p}{q} \sum^\infty_{i=1}\int_0^q x^{i-1}\ dx= \frac{p}{q}\int^q_0\left(\sum_{i=1}^\infty x^{i-1}\right)dx \\
&= \frac{p}{q}\int^q_0 \frac{1}{1-x}\ dx\overset{y=1-x}{=}-\frac{p}{q}\int^p_1 \frac{1}{y}\ dy \overset{0<p<1}{=}+\frac{p}{q}\int^1_p \frac{1}{y}\ dy \\
&=\overset{\begin{matrix}
x=0\Rightarrow y=1 \\
y=q\Rightarrow y=1-q=1-(1-p)=p
\end{matrix}}{\frac{p}{q}\log y |^1_p}= \frac{p}{q}(\log1-\log p)=-\frac{p\log p}{1-p}
\end{align}$$$\sum^\infty_{i=0} P\{X=i\}=1$
