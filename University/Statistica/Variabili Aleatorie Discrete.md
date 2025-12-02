---
sticker: emoji//0034-fe0f-20e3
Order: "3"
---
- [[#Variabile Aleatoria di Bernoulli|Variabile Aleatoria di Bernoulli]]
	- [[#Variabile Aleatoria di Bernoulli#Valore Atteso e Varianza|Valore Atteso e Varianza]]
- [[#Variabile Aleatoria Binomiale|Variabile Aleatoria Binomiale]]
	- [[#Variabile Aleatoria Binomiale#Coefficiente Binomiale|Coefficiente Binomiale]]
	- [[#Variabile Aleatoria Binomiale#Valore Atteso e Varianza|Valore Atteso e Varianza]]
- [[#Variabile Aleatoria di Poisson|Variabile Aleatoria di Poisson]]
	- [[#Variabile Aleatoria di Poisson#Valore Atteso e Varianza|Valore Atteso e Varianza]]
	- [[#Variabile Aleatoria di Poisson#Proprietà della v.a. di Poisson|Proprietà della v.a. di Poisson]]
- [[#Variabile Aleatoria Ipergeometrica|Variabile Aleatoria Ipergeometrica]]
	- [[#Variabile Aleatoria Ipergeometrica#Valore Atteso e Varianza|Valore Atteso e Varianza]]
	- [[#Variabile Aleatoria Ipergeometrica#Calcolo della Covarianza|Calcolo della Covarianza]]
	- [[#Variabile Aleatoria Ipergeometrica#Varianza della Ipergeometrica|Varianza della Ipergeometrica]]

## Variabile Aleatoria di Bernoulli
- **Esperimento Causale:** Esperimento di tipo successo/insuccesso, vero/falso
- **Spazio degli Eventi:** $\Omega=\{V,F\}$
- La variabile aleatoria $X$ assume valori in $\mathcal X=\{0,1\}$
- **Funzione di Massi di Probabilità:** $$P(X=0)=1-p\qquad P(X=1)=p$$
- $p$ è il parametro della distribuzione e corrisponde alla probabilità di successo
### Valore Atteso e Varianza
Se $X\sim Ber(p)$ si ha:
- **Valore Atteso:** $$E[X]=1\cdot P(X=1)+0\cdot P(X=0)=p$$
- **Varianza:** $$\begin{align}Var(X)&=(1-E[X])^2P(X=1)+(0-E[X])^2P(X=0)=(1-p)^2p+p^2(1-p)= \\
&=[p(1-p)][(1-p)+p]=p(1-p)\end{align}$$
---
## Variabile Aleatoria Binomiale
- **Esperimento Causale:** $n$ ripetizioni condizionatamente indipendenti di esperimenti di tipo successo/insuccesso, vero/falso
- **Spazio degli Eventi:** $\Omega=\{\underset{n}{(F,F,\ldots,F)},\underset{n}{(F,V,\ldots,V)},\ldots,\underset{n}{(V,V,\ldots,V)}\}$
- La variabile aleatoria $Y$ indica il numero di successi nelle $n$ prove e assume valori in $\mathcal Y=\{0,1,\ldots,n\}$. Essa è la somma di $n$ variabili di Bernulli condizionatamente indipendenti
- Se $Y_{1}\sim Bin(n_{1},\pi)$ e $Y_{2}\sim Bin(n_{2},\pi)$, allora $Y_{Y_{1}+Y_{2}}=Y_{1}+Y_{2}\sim Bin(n_{2}+n_{2},\pi)$
- **Funzione Massa di Probabilità:** $$P(Y=i)=\begin{pmatrix}
n \\ i
\end{pmatrix}\pi^i(1-\pi)^{n-i}\quad i=0,1,\ldots,n$$
- $\pi$ è il parametro del modello, $n$ in genere è assunto noto
### Coefficiente Binomiale
Il coefficiente biomiale rappresenta il numero di combinazioni semplici di $n$ in classe $i$:
$$\begin{pmatrix}
n \\
i
\end{pmatrix}=\frac{n!}{i!(n-i)!}$$
Esso è anche il rapporto tra le disposizioni semplici di $n$ in classe $i$ e il numero di permutazioni $i!$
$$
\underset{\text{possono essere scelti per primo}}{n}\cdot \underset{\text{possono essere scelti per secondo}}{(n-1)}\cdot(n-2)\cdot \ldots\cdot \underset{\text{possono essere scelti per }i-esimo}{(n-i+1)}= \frac{n!}{(n-i)!}
$$

- Se si ha $i=0$, allora $\begin{pmatrix} n \\ 0\end{pmatrix}=1$ 

> [!example]+ Esempio:
> Si suppone di lanciare una moneta truccata (con probablità test: $\frac{2}{3}$ e di croce: $\frac{1}{3}$) per $n=4$ volte. Si calcoli la probabilità che esca 2 volte testa.
> $X_{1},X_{2},X_{3},X_{4}$ sono variabili di Bernoulli iid, $Y=\sum^4_{i=1}X_{i}$
> $$P(Y=2)= \frac{4!}{2!2!}\left( \frac{2}{3} \right)^2 \left( \frac{1}{3} \right)^2$$

### Valore Atteso e Varianza

Se $X_{i}\sim Ber(p)$, $Y=X_{1}+X_{2}+\ldots+X_{n}$; $Y\sim Bin(n,\pi)$
- **Valore Atteso:** $$E[Y]=E[X_{1}]+\ldots+E[X_{n}]=n\pi$$
- **Varianza:** $$\begin{align}Var(Y)&=Var(X_{1})+\ldots+Var(X_{n})+\underset{=0}{Cov(X_{1},X_{2})}+\ldots+Cov(X_{n-1},X_{n})=n\pi(1-\pi)\end{align}$$
---
## Variabile Aleatoria di Poisson
- **Esperimento Aleatorio:** Ripetizione indipendenti di esperimenti di tipo successo/insuccesso, vero/falso in uno spazio o tempo limitato e determinato
- **Spazio degli Eventi:** $\Omega=\{(F,F,\ldots),(F,V,\ldots),\ldots,(V,V,\ldots)\}$
- La variabile aleatoria $X$ è una variabile di conteggio. Essa indica il numero di volte in cui si verifica un certo evento (successo)
- **Funzione di Massa di Probabilità:** $$P(X=i|\lambda)=\frac{\lambda^i}{i!}e^{-\lambda}\quad i=0,1,\ldots$$Dove $\lambda>0$ è il parametro della distribuzione
- Per essere una misura di probabilità propria, $\sum^\infty_{i=0}P(X=i)=1=e^{-\lambda}e^{\lambda}=1$
### Valore Atteso e Varianza
Si determina la funzione generatrice dei momenti:
$$
\phi(t)=E[e^{tX}]=\sum^{\infty}_{i=0}e^{ti}P(X=i)=\sum^\infty_{i=0}e^{ti} \frac{\lambda^i}{i!}e^{-\lambda}=e^{-\lambda}\underset{\text{serie nota}}{\sum^\infty_{i=0} \frac{(\lambda e^{t})^i}{i!}}=e^{-\lambda}e^{\lambda e^t}=\exp[\lambda(e^t-1)]
$$
$$\begin{gather} 
 \frac{d\phi(t)}{dt}=\exp[\lambda(e^t-1)]\lambda e^t \\
\frac{d^2\phi(t)}{dt^2}=\exp[\lambda(e^t-1)]\lambda e^t+\exp[\lambda(e^t-1)](\lambda e^t)^2
\end{gather}$$
- **Valore Atteso:** $$E[X]=\exp[\lambda(e^0-1)]\lambda e^0=\lambda$$
- **Varianza:** $$Var[X]=\exp[\lambda(e^0-1)\lambda] e^0+\exp[\lambda(e^0-1)](\lambda e^0)^2-E[X]^2=\lambda$$
### Proprietà della v.a. di Poisson
- La variabile aleatoria di Poisson con $\lambda=np$ approssima una distribuzione $Bin(n,\pi)$ quando $n$ è molto grande e $\pi$ è molto piccolo. Infatti, il numero di successi in un gran numero di ripetizioni, con una piccola probabilità di successo, è approssimativamente Poisson con $\lambda=np$.
- La somma di v.a. di Poisson indipendenti:  $$X_{1}\sim Pois(\lambda_{1}),\ X_{2}\sim Pois(\lambda_{2})\qquad (X_{1}+X_{2})\sim Pois(\lambda_{1}+\lambda_{2})$$infatti $$\phi_{X_{1}+X_{2}}(t)=\exp[\lambda_{1}(e^t-1)]\exp[\lambda_{2}(e^t-1)]=\exp[(\lambda_{1}+\lambda_{2})(e^t-1)]$$
---
## Variabile Aleatoria Ipergeometrica
- **Esperimento:** $n$ ripetizioni non indipendenti con risultato vero/falso
- Si immagina un'urna in cui c'è un numero finito di palline nere $N$ e palline marroni $M$, ad ogni estrazione ogni pallina ==non viene rimessa nell'urna==. La variabile aleatoria $X$ indica il numero di palline nere in $n$ estrazioni e $\mathcal X=\{\max(0,n-M),\ldots,\min(n,N)\}$
- **Funzione di Massa di Probabilità:** $$P(X=i)= \frac{\begin{pmatrix} N \\ i\end{pmatrix}\begin{pmatrix}M \\ n-i \end{pmatrix}}{\begin{pmatrix}N+M\\ n \end{pmatrix}}\qquad i=\max(0,n-M),\ldots,\min(n,N)$$
### Valore Atteso e Varianza
Ciascuna estrazione presa per se determina una variabile di Bernoulli $$X_{i}=\begin{cases}
0 &  se \ falso \\ 1 & se \ vero
\end{cases}$$
- **Valore Atteso:** $$\begin{align}&E[X_{i}]=\frac{N}{N+M},\ \forall i \\
&E[X]=E\left[ \sum^n_{i=1} X_{i} \right]=n \frac{N}{N+M} \end{align}$$
- **Varianza:** $$\begin{align}&Var(X_{i})=\frac{N}{N+M} \frac{M}{N+M}=\frac{NM}{(N+M)^2} \\
&Var(X)=Var\left( \sum^n_{i=1}X_{i} \right)=n \frac{NM}{N+M}+2 \sum^n_{j=2}\sum_{i<j}Cov(X_{i},X_{j})\end{align}$$
### Calcolo della Covarianza
Presa una coppia $X_{i},X_{j}$, si sa che
$$\begin{align}
&P(X_{i}=1,X_{j}=1)=\frac{N}{\underset{P(X_{i}=1)}{N+M}} \frac{N-1}{\underset{P(X_{j}=1|X_{i}=1)}{N+M-1}} \\
&\begin{aligned}E[X_{i}X_{j}]&=1\cdot P(X_{i}=1,X_{j}=1)+0\cdot [P(X_{i}=0,X_{j}=1)+P(X_{i=1},X_{j}=0)+P(X_{i}=0,X_{j}=0)]= \\
&= \frac{N}{N+M} \frac{N-1}{N+M-1}\end{aligned} \\
&Cov(X_{i},X_{j})=E[X_{i}X_{j}]-E[X_{i}]E[X_{j}]= \frac{N}{N+M} \frac{N-1}{N+M-1} - \frac{N^2}{(N+M)^2}=- \frac{NM}{(N+M)^2(N+M-1)}
\end{align}$$
### Varianza della Ipergeometrica
Sostituendo il risultato della covarianza in ciascune degli $\frac{n(n-1)}{2}$ addendi (e moltiplicando per 2) si ottiene:
$$
Var(X)=\frac{nNM}{(N+M)^2}+n(n-1) \frac{NM}{(N+M)^2(N+M-1)}$$