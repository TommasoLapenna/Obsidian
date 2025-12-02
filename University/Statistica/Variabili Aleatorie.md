---
sticker: emoji//0033-fe0f-20e3
Order: "2"
---
- [[#Introduzione|Introduzione]]
- [[#Variabili Aleatorie Discrete e Continue|Variabili Aleatorie Discrete e Continue]]
- [[#Funzione di Ripartizione|Funzione di Ripartizione]]
	- [[#Funzione di Ripartizione#Per Variabili Aleatorie Discrete|Per Variabili Aleatorie Discrete]]
		- [[#Per Variabili Aleatorie Discrete#Coppie di Variabili Aleatorie Discrete|Coppie di Variabili Aleatorie Discrete]]
	- [[#Funzione di Ripartizione#Per Variabili Aleatori Continue|Per Variabili Aleatori Continue]]
		- [[#Per Variabili Aleatori Continue#Coppie di Variabili Aleatorie Continue|Coppie di Variabili Aleatorie Continue]]
- [[#Variabili Aleatorie Indipendenti|Variabili Aleatorie Indipendenti]]
- [[#Distribuzioni Condizionate|Distribuzioni Condizionate]]
- [[#Valore Atteso|Valore Atteso]]
	- [[#Valore Atteso#Per $X$ Discreta|Per $X$ Discreta]]
	- [[#Valore Atteso#Per$X$ Continua|Per$X$ Continua]]
	- [[#Valore Atteso#Proprietà|Proprietà]]
- [[#Varianza|Varianza]]
	- [[#Varianza#Varianza della Somma di v.a.|Varianza della Somma di v.a.]]
- [[#Covarianza|Covarianza]]
	- [[#Covarianza#Generalizzazione|Generalizzazione]]
- [[#Caso di Indipendenza, $X\perp\!\!\!\perp Y$|Caso di Indipendenza, $X\perp\!\!\!\perp Y$]]
- [[#Caso di Indipendenza, $X\perp\!\!\!\perp Y$#Mediana|Mediana]]
- [[#Entropia per Variabili Discrete|Entropia per Variabili Discrete]]
	- [[#Entropia per Variabili Discrete#H(p) Come Quantità Media di Informazione|H(p) Come Quantità Media di Informazione]]
- [[#Funzione Generatrice dei Momenti|Funzione Generatrice dei Momenti]]
- [[#Disuguaglianza di Markov|Disuguaglianza di Markov]]
- [[#Legge Debole dei Grandi Numeri|Legge Debole dei Grandi Numeri]]

## Introduzione
Spesso non sono di interesse tutti gli eventi elementari associati ad un esperimento aleatorio. Spesso è di interesse solo una certa riduzione degli stessi, quindi:
1. Si può passare dallo spazio degli eventi $\Omega$ ad uno derivato $\mathcal X$, assegnando ai punti di $\Omega$ un valore in $\mathcal X$
2. Si possono assegnare ai valori in $\mathcal X$ una probabilità derivata da quelle assegnate ai punti in $\Omega$
3. Si può specificare una funzione che descriva le probabilità trovate nel nuovo spazio

Una **Variabile Aleatoria** $X$ è una funzione che associa un numero reale ad ogni evento elementare $\omega \in \Omega$
$$
X:\Omega\longrightarrow \mathcal X\subseteq \mathbb R \qquad X(\omega)=x \in \mathbb{R}
$$

> [!example]+ Esempio:
> Esperimento originario: Lancio di due dadi $\Omega=\{(1,1),\ldots,(6,6)\}$. 
> Quantità di interesse: Somma dei risultati $\mathcal X={2,3,\ldots,12}$ 
> $$\begin{align}
> P_{\mathcal X}(X=2)&=P_{\Omega}((1,1)) \\
> P_{\mathcal X}(X=3)&=P_{\Omega}((1,2))+P_{\Omega}((2,1)) \\
> \ldots&=\ldots
> \end{align}$$

Esperimento originario: Pezzi difettosi su due acquisti $\Omega=\{(d,d),(a,d),(d,a),(a,a)\}$.
Quantità di interesse: Almeno un componente accettabile $\mathcal X=\{\text{non accettabile: }0,\ \text{accettabile: }1\}$
$$\begin{align}
P_{\mathcal X}(X=0)&=P_{\Omega}((d,d)) \\
P_{\mathcal X}(X=1)&=P_{\Omega}((a,a))+P_{\Omega}((a,d))+P_{\Omega}(d,a)
\end{align}$$
## Variabili Aleatorie Discrete e Continue
Le variabili aleatoria si possono classificare in base alla cardinalità del loro supporto $\mathcal X$:
- **Discrete:** Possono assumere al più una quantità finita o numerabile di valori, $\mathcal X \subseteq \mathbb{N}$
- **Continue:** Possono assumere valori in tutto l'insieme dei numeri reali, $\mathcal X\subseteq \mathbb{R}$

---

## Funzione di Ripartizione
La funzione di ripartizione di una variabile aleatoria è definita come
$$
F(X):=P(X\le x)
$$
Essa consente la valutazione della probabilità di qualunque evento derivabile da $X$.

> [!example]+ Esempio
> $$P(a<X\le b)=F(b)-F(a)$$
> Infatti $\{X\le b\}=\{X\le a\}\cup \{a<X\le b\}$

### Per Variabili Aleatorie Discrete
**Funzione di Massa di Probabilità:**
$$P(x):=P(X=x)$$
- $P(x)>0,\ x \in \mathcal X$
- $P(x)=0,\ x\notin\mathcal X$
- $\sum_{x\in \mathcal X}P(x)=1$

**Funzione di Ripartizione:** 
$$F(a)=\sum_{x\le a}P(x)$$
![[Pasted image 20250706124927.png|center|500]]

> [!example]+ Esempio: Lancio della moneta:
> - $\Omega=\{T,C\}$
> - $X$ è la variabile binaria associata all'esito del lancio
> - $X\in\mathcal X=\{0,1\}$
>
> Oppure:
> - $n$ lanci ripetuti e indipendenti della stessa moneta
> - Lo spazio degli eventi è $\Omega \times\ldots \times\Omega=\Omega^n$, $|\Omega^n|=2^n$
> - $X$ è il numero di croci sulle $n$ prove
> - $X\in\mathcal X=\{0,1,\ldots,n\}$
> - $|\mathcal X|=n+1$
#### Coppie di Variabili Aleatorie Discrete
- **Funzione di Ripartizione:** $$\begin{align}F(x,y)&:=P(X\le x,Y\le y) \\
F(x)&:=P(X\le x,Y<\infty) \\
F(y)&:= P(X<\infty,Y\le y)\end{align}$$
- **Funzione di Massa di Probabilità:**
$$\begin{align}p(x_{i},x_{j})&=P(X=x_{i},Y=y_{j}) \\
p(x_{i})&= \sum_{j}P(X=x_{i},Y=y_{j}) \\
p(y_{j})&=\sum_{i} P(X=x_{i},Y=y_{j})\end{align}$$

> [!info] Nota
> Dalla congiunta si possono ricavare le marginali ma non il viceversa

### Per Variabili Aleatori Continue
Una v.a. definita in $\mathbb{R}$ non consente una probabilizzazione per ogni possibile singleton del dominio. Tuttavia è possibile determinare la probabilità per sottoinsiemi di $\mathcal X$ usando la funzione di ripartizione
$$
F(x)=P(X\le x)
$$
Per descrivere l'incertezza su $X$ si utilizza la ==**Funzione di Densità**==
$$
f_{X}(x)=\frac{d}{dx}F(x)
$$
![[Pasted image 20250706125736.png|center|400]]
$$\begin{align}
P(X\in B)&=\int_{B}f(x)\ dx\quad B\subseteq \mathbb{R} \\
P(X\in \mathbb{R})&=\int_{-\infty}^\infty f(x)\ dx = 1 \\
P(X\in a)&=\int_{a}^af(x)\ dx =0 \\
F(a)&=\int_{-\infty}^a f(x)\ dx \\
P(a\le X\le b)&= F(b)-F(a)=\int_{a}^b f(x)\ dx
\end{align}$$

> [!example]+ Esempio: Durata di una conversazione Telefonica
> - $X$ la lunghezza in minuti di una conversazione telefonica
> - $X\in\mathcal X=[0,+\infty]$
> $$\begin{align}
> &f(x|\lambda)=\lambda \exp(-\lambda x),\quad 0\le x<\infty,\ \lambda>0 \\
> &F(x)=\int^x_{0}\lambda \exp(-\lambda t)\ dt=-\exp(-\lambda t)|^x_{0}=-\exp (-\lambda x)+1
> \end{align}$$
> Se $\lambda=1$
> $$\begin{align}
> P(4.9\le x\le 5.1)&=\exp(-4.9\cdot 1)-\exp(-5.1\cdot 1)= 0.001249837 \\
> f(5)* 0.2&=0.006737947\cdot 2\approx 0.001347589
> \end{align}$$

#### Coppie di Variabili Aleatorie Continue
Due variabili aleatorie sono congiuntamente continue se esiste una funzione non negativa di ripartizione tale che
$$\begin{gather} \frac{d}{dxdy}F(x,y)=\underset{\text{densita' congiunta}}{f(x,y)} \\
P((X,Y)\in C)=\iint_{(x,y)\in C}f(x,y)\ dxdy\end{gather}$$
con
$$\begin{gather}C=\{x,y\in \mathbb{R}^2:x\in A,\ y\in B\} \\ P(X\in A,Y\in B)=\int_{B}\int_{A}f(x,y)\ dxdy \\
F(a,b)=P(X\le a, Y\le b)=\int_{-\infty}^b\int_{-\infty}^a f(x,y)\ dxdy\end{gather}$$
==Le marginali sono nuovamente ottenute per integrazione==
$$
f_{X}(x)\int_{\infty}^\infty f(x,y)\ dy\qquad f_{Y}(y)=\int_{-\infty}^\infty f(x,y)\ dx
$$

> [!example]+ Esempio:
> Sia $f(x,y)=\exp(-x)\exp(-y)$, $x>0$, $y>0$, si calcola
> $$\begin{align}
> P(0\le X\le 1,\ 1\le Y\le 2)&=\int_{0}^1 \int^2_{1} \exp(-x)\exp(-y)\ dxdy=\int_{0}^1 \exp(-x)\ dx \int_{1}^2 \exp(-y)\ dy= \\
> &=\int_{0}^1 \exp(-x)\ dx-\exp(-y)|^2_{1}=(-\exp(-y)|^1_{0})(\exp(-1-\exp(-2)))= \\
> &=(\exp(0)-\exp(-1))(\exp(-1)-\exp(-2))=0.1469
> \end{align}$$

---

## Variabili Aleatorie Indipendenti
Due variabili aleatorie indipendenti si dicono indipendenti se tutti gli eventi relativi alla prima sono indipendenti da tutti quelli relativi alla seconda. Quando per ogni coppia $A$ e $B$
$$
P(X\in A, \ Y\in B)=P(X\in A)P(Y\in B)$$
Se $A=(-\infty)$, $B=(-\infty,b)$ allora
$$
P(X\in A,\ Y\in B)=P(X\le a)P(Y\le b)=F_{X}(a)F_{Y}(b)
$$
- Nel caso discreto: $$p(x,y)=p_{X}(x)p_{Y}(y)$$
- Nel caso continuo $X$ e $Y$ sono indipendenti se: $$f(x,y)=f_{X}(x)f_{Y}(y)$$
---

## Distribuzioni Condizionate 
Per eventi
$$P(E|F)=\frac{P(E\cap F)}{P(F)}$$
- **Variabili Aleatorie Discrete:** $$\underset{\text{Funz. massa di prob. cond.}}{p_{X|Y}(x|y)}=\frac{P(X=x,\ Y=y)}{P(Y=y)}=\frac{p_{XY}(x,y)}{P_{Y}(y)}\quad p_{Y}(y)>0$$
- Nel caso di **Variabili Aleatorie Continue** si parla di *densità condizionale*:$$\underset{\text{Densita' cond.}}{f_{X|Y}(x|y)}=\frac{f(x,y)}{f(y)}\quad f_{Y}(y)>0$$
> [!example] Esempio:
> $$\begin{align}& f(x,y)=2-x-y,\qquad 0\le x\le 2\quad 0\le y\le 1 \\
> &f(x)=\int_{0}^1(2-x-y)\ dy=(2-x)y-  \left.\frac{y^2}{2}\right|^1_{0}=\frac{3}{2}-x \\
> &f(y|x)=\frac{2-x-y}{\frac{3}{2}-x}\quad 0\le y\le1\end{align}$$
> 

--- 
## Valore Atteso
Il concetto di valore atteso è uno dei più importanti della teoria della probabilità, esso è spesso detto media: infatti il valore atteso può essere pensato come una media pesata. 
Il concetto di valore atteso è analogo in fisica al concetto di gravità o baricentri
![[Pasted image 20250706164919.png|center|400]]

Se il fulcro è in $\mu=E[X]$ $$\sum_{i}P(x_{i})(x_{i}-\mu)=0$$
### Per $X$ Discreta
Se $X$ è discreta, il valore atteso di $X$, $E[X]$ è $$E[X]:= \sum_{i}x_{i}P(X=x_{i})$$

> [!example]+ Esempi
> - Il valore atteso della *funzione indicatrice* è la probabilità che $X=1$ $$E[X]=0*P(X=0)+1*P(X=1)=P(X=1)$$
> - Il calore atteso del numero $x$ di ragazzi che entra in un gruppo di 3, se il gruppo è scelto a caso fra 4 ragazzi e 3 ragazze è $$E[X]=\sum_{x=0}^3 x \frac{\begin{pmatrix}4\\ x\end{pmatrix} \begin{pmatrix}
> 3 \\ 3-x
> \end{pmatrix}}{\begin{pmatrix}
> 7 \\ 3
> \end{pmatrix}}$$

### Per$X$ Continua
Se $X$ è continua, il valore atteso di $X$, $E[X]$ è $$E[X]:=\int_{-\infty}^\infty xf(x)\ dx$$

> [!example]+ Esempio:
> La durata di una lampadina è espressa da una variabile aleatoria la cui densità è $$f(x)=\frac{1}{1000}\exp\left( - \frac{x}{1000} \right)$$
> Quanto dura in media una lampadina?
> $$\begin{align}
> E[X]&=\int^\infty_{0}x \frac{1}{1000}\exp\left( - \frac{x}{1000} \right)\ dx = uv|^\infty_{0}-\int_{0}^\infty u'v\ dx= \\
> &=\left.-x\exp\left( -\frac{x}{1000} \right)\right|^\infty_{0}-\int^\infty_{0}-\exp\left( -\frac{x}{1000} \right)\ dx= 0+1000=1000
> \end{align}$$
> avendo posto $u=x$ e $v=\int \frac{1}{1000}\exp\left( -\frac{x}{1000} \right)\ dx=-\exp\left( -\frac{x}{1000} \right)$.

### Proprietà
- Se $X$ è una variabile aleatoria, allora anche la funzione $g(X)$ è una variabile aleatoria.
	- Se $X$ è continua: $$E[g(X)]:=\int_{-\infty}^\infty g(x)f(x)\ dx$$
	- Se $X$ è discreta: $$E[g(x)]:=\sum_{x}g(x)P(X=x)$$
- Valore atteso di una trasformata lineare $X=aX+b$ $$E[aX+b]=aE[X]+b$$
- Valore atteso di potenze di variabili (momenti) $$M_{n}(X)=E[X^n]=\sum_{x}x^np(x)$$
- Valore atteso di una somma di variabili $$E[X_{1}+X_{2}+\ldots+X_{n}]=E[X_{1}]+E[X_{2}]+\ldots+E[X_{n}]$$

> [!example]+ Esempio:
> Siano $E[X]=2$ e $E[X^2]=8$
> - $E[2+4X^2]=2+4\times 8=34$
> - $E[X^2+(X+1)^2]=8+8+4+1=21$

Lettere in una busta: $N$ lettere e $N$ buste, buste e lettere cadono e si infilano a caso nella buste. Qual'è il numero medio di lettere che finisce nella busta giusta?
$X_{i}=1$ corrisponde all'evento *la busta $i$ riceve la lettera giusta*
$$
p(X_{i})=\begin{cases}
\frac{1}{N} & se\ X_{i}=1 \\ \frac{N-1}{N} & se \ X_{i}=0
\end{cases}\qquad E[X_{i}]=\frac{1}{N}\qquad E[X_{1}+\ldots X_{n}]=N\cdot \frac{1}{N}=1
$$
Cioè dipendente da $N$

--- 
## Varianza
Il valore atteso è il baricentro dei possibili valori di  $X$, tuttavia questo dato non fornisce informazioni sulla loro dispersione, quantificata come varianza.
$$Var(X):= E[X-E[X]]^2=E[X^2]-E[X]^2$$
- Varianza di trasformate lineari: $$\begin{align}Var(bX)&=b^2 Var(x) \\
Var(a+X)&= Var(X) \\
Var (a+bX) &= b^2 Var(X)\end{align}$$ 
### Varianza della Somma di v.a.
$$\begin{align}
Var\left( \sum^n_{i=1} X_{i} \right)&=Cov\left( \sum^n_{i=1}X_{i}, \sum^n_{j=1}X_{j} \right)=\sum^n_{i=1}\sum^n_{j=1}Cov(X_{i},X_{j})= \\
&= \sum^n_{i=1}Var(X_{i})+\sum^n_{i=1}\sum^m_{\begin{aligned}
j&=1 \\ j&\ne i 
\end{aligned}}Cov(X_{i},X_{j}) \\
Var(X_{1}+X_{2})&= Var(X_{1})+Var(X_{2})+2Cov(X_{1},X_{2})
\end{align}$$

## Covarianza
Siano $\mu_{X}=E[X]$, $\mu_{Y}= E[Y]$ e $\mu_{Z}=E[Z]$
$$\begin{gather}
Cov(X,Y):=E[(X-\mu_{X})(Y-\mu_{Y})]=E[XY]-E[X\cdot \mu_{Y}]-E[Y\cdot \mu_{X}]+\mu_{X}\mu_{Y}=E[XY]-\mu_{X}\mu_{Y} \\
Cov(aX,bY)= ab\ Cov(X,Y) \\
Cov(X+Y,Z)= Cov(XZ)+Cov(YZ)
\end{gather}$$
### Generalizzazione 
$$\begin{align}
Cov\left( \sum^n_{i=1} X_{i},Y \right)&:= \sum^n_{i=1}Cov(X_{i},Y) \\
Cov\left( \sum^n_{i=1}X_{i}, \sum^m_{j=1} Y_{j} \right)&= \sum^n_{i=1}\sum^m_{j=1}Cov(X_{i},Y_{j})
\end{align}$$

> [!example]+ Esempio:
> Quanto vale $Cov(X_{1}+X_{2},X_{1}-X_{2})$ se $X_{1}$ ha la stessa distribuzione di $X_{2}$?
> $$
> Cov(X_{1}+X_{2},X_{1}-X_{2})=Cov(X_{1},X_{1})-Cov(X_{1},X_{2})-Cov(X_{2},X_{2})+Cov(X_{1},X_{2})=0
> $$
> 

## Caso di Indipendenza, $X\perp\!\!\!\perp Y$
$$\begin{align}
E[XY]&=\int_{\mathcal Y}\int_{\mathcal X}xy\ f(x,y)\ dxdy= \int_{\mathcal Y}\int_{\mathcal X} xy\ f(x)f(y)\ dxdy=\int_{\mathcal x}xf(x\ dx)\int_{\mathcal y}yf(y)\ dy= E[X]E[Y]
\end{align}$$
Quindi:
- $Cov(XY)=E[XY]-E[X]E[Y]=0$
- $Var\left( \sum^n_{i=1} X_{i}\right)=\sum^n_{i=1}Var(X_{i})$

> [!example] Esempio:
> Calcolare la varianza del numero di successi su $n$ ripetizioni condizionatamente indipendenti di un esperimento con probabilità di successo $\pi$, $X_{i}=\{0,1\}$ 
> $$Var\left( \sum X_{i} \right)=\sum Var(X_{i})=n\pi(1-\pi)$$
> Questo perché
> $$Var(X_{i})=E(X_{i}^2)-E(X_{i})^2=\pi-\pi^2=\pi(1-\pi)$$

## Mediana
La mediana $m$ è quel valore della variabile tale che $F(m)=\frac{1}{2}$

---

## Entropia per Variabili Discrete
L'entropia costituisce una valutazione della variabilità della distribuzione di probabilità assegnata ad una variabile aleatoria.
Si considera una variabile dicotomica $X=\{0,1\}$, $P(X=0)=p$, tutta l'incertezza della v.a. è racchiusa nel valore $p$.
Si indica con $I(p)$ la quantità di incertezza della caratteristica $X=0$ a cui è stata assegnata la probabilità $p$. Questa quantità può essere anche intesa come il danno che si subisce nel fornire una probabilità $P(X=0)=p$ quando effettivamente $X=0$ è vero.

$I(p)$ deve avere rispondere ad alcuni criteri:
1. Se è vero $X=0$ e si indica $P(X=0)=p=1$ allora $I(p):=0$ 
2. Se è vero $X=0$, $I(p)$ deve essere crescente al diminuire di $p$ verso $0$
3. La informazione proveniente da due variabili indipendenti deve essere additiva, ovvero se si introduce la v.a. $Y=\{0,1\}$ e assegno $P(Y=0)=q$, allora$$I(P(X=0)=p,\ P(Y=0)=q)=I(p)+I(q)$$
Aggiungendo altri requirements si è giunti a formulare la proposta
$$I(p)=-\ln_{2}(p)$$
Infatti poiché $$\begin{gather}
p(X=0,Y=0)=p(X=0)p(Y=0)=pq \\
-\ln_{2}(pq)=-(\ln_{2}(p)+\ln_{2}(q))=I(p)
\end{gather}$$
In una v.a. l'entropia è la media dell'incertezza della distribuzione di distribuzione di probabilità misurata tramite $I(p)$ $$H(X):=-\sum^2_{i=1}\ln_{2}(p_{i})p_{i}=-(\ln_{2}(p)p+\ln_{2}(1-p)(1-p))$$

In una variabile dicotomica $H(X)=H(p)$ è una funzione concava con massimo $p=0.5$

![[Pasted image 20250707141507.png|center|300]]

### H(p) Come Quantità Media di Informazione
Si suppone che v.a. $X$ discreta descriva l'incertezza circa la prima lettera di una targa

| $X$    | $a$   | $b$    | $c$     | $d$     |
| ------ | ----- | ------ | ------- | ------- |
| $P(X)$ | $0.5$ | $0.25$ | $0.125$ | $0.125$ |
Se si calcola l'entropia emerge che la quantità media di informazione (incertezza) risulta
$$
H(X)=-(0.5\log_{2}0.5+0.25\log_{2}0.25+0.125\log_{2}0.125+0.125\log_{2}0.125)=1.75
$$
Si suppone che si voglia indovinare quale delle 4 lettere sia quella giusta per poter fare delle domande del tipo *è la lettera ... quella giusta?*. Si inizia da quella più probabile per poi andare a scalare, il numero medio di tentativi per arrivare a conoscere alla lettere che si cerca ($Y=\{1,2,3\}$) si calcola nel seguente modo
$$\begin{align}
E(Y)&=1p(a)+2p(\overline a)p(b|\overline a)+3p(\overline a)p(\overline b|\overline a)p(c|\overline a, \overline b)+3p(\overline a)p(\overline b|\overline a)p(d|\overline a, \overline b) \\
&=1\times 0.5+2\times 0.5+3\times 0.5\times 0.5 \times 0.5+3\times 0.5\times 0.5 \times 0.5 \\
&= 1.75
\end{align}$$
---

## Funzione Generatrice dei Momenti
- Data una v.a. *discreta* $X$, è definita la funzione generatrice dei momenti il valore atteso
$$
\phi(t):=E_{x}[e^{tX}]=\sum_{x}e^{tx}p(x)\quad \forall t\in \mathbb{R}
$$
- Data una v.a. *continua* $X$, è definita funzione generatrice dei momenti  il valore atteso $$\phi(t):=E[e^{tX}]=\int_{-\infty}^\infty e^{tx} f(x)\ dx \quad \forall t\in \mathbb{R}$$
Il nome deriva dal fatto che il momento $r-$esimo di $X$ può essere generato da $\phi(t)$ calcolando la derivata $r-$ esima rispetto a $t$ nel punto $t=0$, infatti:
$$
\frac{\delta^r\phi(t)}{\delta t}=\frac{\delta^r E(e^{tx})}{\delta t}=E\left( \frac{\delta^re^{tx}}{\delta t} \right)=E(X^re^{tx})=E(X^r)\quad se\ t=0
$$
Cioè 
$$
\phi^{(r)}(t)=\frac{d^r\phi(t)}{dt^r}= \frac{d^rE[e^{tX}]}{dt^r}
$$
e 
$$\phi^{(r)}(t=0)=E[X^r]$$
Se $X\perp\!\!\!\perp Y$ $$\phi_{X+Y}=E[e^{t(X+Y)}]=E[e^{t(X)}e^{t(Y)}]=E[e^{t(X)}]E[e^{t(Y)}]=\phi_{X}(t)\phi_{Y}(t)$$

> [!hint] La funzione generatrice dei momenti determina la distribuzione
>  Due variabili con la stessa funzione generatrice dei momenti hanno la stessa funzione di ripartizione e la stessa funzione di massa di probabilità o di densità

> [!example]+ Esempio:
> Si considera una $X\in\{0,1\}$ con $P(X=1)=p$ 
> $$\begin{gather}\phi=E[e^{tX}]=e^{t\cdot 0}P(X=0)+e^{t\cdot 1}P(X=1)=(1-p)+e^tp \\
> \frac{d\phi(t)}{dt}=e^tp \\
> \frac{d\phi(0)}{dt}=0\end{gather}$$
> 

Si considera una v.a. definita per $X>0$, tale che $f(x|\lambda)=\lambda \exp (-\lambda x)$, per $\lambda>0$
$$\begin{gather}
\phi(t)=E[e^{tX}]=\int_{0}^\infty \exp(ts)\cdot \lambda \exp(-s\lambda)\ ds=\int_{0}^\infty \lambda \exp(s(t-\lambda))\ ds= \frac{\lambda}{\lambda-t} \\
\frac{d\phi(t)}{dt}= \frac{\lambda}{(\lambda-t)^2} \\
\frac{d\phi(0)}{dt}= \frac{1}{\lambda}
\end{gather}$$
Si considera adesso $Y=\sum^n_{i=1}X_{i}$, dove tutte le $X_{i}$ sono iid
$$\begin{gather}\phi(Y)=\prod^n_{i=1}\phi(X_{i})=\left( \frac{\lambda}{\lambda-t} \right)^n \\
\phi(t)=E[e^{tY}]= \left( \frac{\lambda}{\lambda-t} \right)^n \\
\frac{d\phi(t)}{dt}= \frac{n\left( \frac{\lambda}{\lambda-t} \right)^{n+1}}{\lambda} \\
\frac{d\phi(0)}{dt}=\frac{n}{\lambda}\end{gather}$$
---

## Disuguaglianza di Markov
Sia $X$ una variabile aleatoria non negativa, allora
$$P(X\ge a)\le \frac{E[X]}{a}\quad \forall x,a>0$$
$$\begin{align}E[X]&=\int_{0}^\infty xf(x)\ dx=\int_{0}^axf(x)\ dx+\int_{a}^\infty xf(x)\ dx\ge\int^\infty_{a} xf(x)\ dx\ge a\int_{a}^\infty f(x)\ dx\ge aP(X\ge a) \end{align}$$
Sia $X$ una variabile aleatoria di media $\mu$ e varianza $\sigma^2$, allora $$P(|X-\mu|\ge k)\le \frac{\sigma^2}{k^2}\quad per \ ogni\ k>\sigma$$
$$\begin{align} 
\sigma^2&=\int_{-\infty}^\infty (x-\mu)^2f(x)f(x)\ dx=\int^{\mu-k}_{-\infty}(x-\mu)^2f(x)\ dx+\int^{\mu+k}_{\mu-k}(x-\mu)^2f(x)\ dx+\int_{\mu+k}^\infty (x-\mu)^2f(x)\ dx\ge \\
&\ge\int^{\mu-k}_{-\infty} (x-\mu)^2f(x)\ dx+\int^\infty_{\mu+k}(x-\mu)^2f(x)\ dx\ge k^2\left( \int_{-\infty}^{\mu-k}f(x)\ dx+\int_{\mu+k}^\infty f(x)\ dx \right)\ge \\
&\ge k^2Pr(x \in[-\infty,\ (\mu-k)]\cup [(\mu+k),\ +\infty])
\end{align}$$
---

## Legge Debole dei Grandi Numeri

> [!gray] Legge Debole dei Grandi Numeri
> Siano $(X_{1},\ldots, X_{n})$ $n$ variabili aleatorie iid (indipendenti e identicamente distribuite), tutte con media $\mu$ e varianza $\sigma^2$ (finita), allora la media aritmetica delle loro realizzazioni, al divergere di $n$ approssima il valore atteso di $\mu$ 
> $$\lim_{ n \to \infty } P\left( \left|\frac{X_{1}+\ldots+X_{2}}{n}-\mu\right|>k \right)\to 0$$
> Poiché $E\left( \frac{X_{1},\ldots,X_{n}}{n} \right)=\mu$ e $Var\left( \frac{X_{1},\ldots,X_{n}}{n} \right)=\frac{\sigma^2}{n}$ , applicando la disuguaglianza di Chebichev a $\frac{X_{1}+\ldots+X_{n}}{n}$ si ottiene
> $$
> P\left( \left|\frac{X_{1}+\ldots+X_{2}}{n}-\mu\right|>k \right)\le \frac{\sigma^2}{nk^2}
> $$
> Che tende a $0$ al divergere di $n$, per un $k$ piccolo a piacere

> [!example]+ Esempio:
> Quanto deve essere grande un campion di una variabile $X$ di media $\mu$ e varianza $\sigma^2$ affinché si abbia una probabilità di almeno il $99\%$ che a fronte di $n$ osservazioni la media campionaria osservata $\overline X_{n}$ sia un intorno di ampiezza $0.5\sigma$ da $\mu$?
> $$P(|\overline X_{n}-\mu|\le0-5\sigma)\ge 1-0.01=0.99$$
> Essendo in questo caso: $0.01=\frac{\sigma^2}{nk^2}$ e $k=0.5\sigma$ allora $$n=\frac{\sigma^2}{0.01(0.5\sigma)^2}$$

provaaaaaaaa