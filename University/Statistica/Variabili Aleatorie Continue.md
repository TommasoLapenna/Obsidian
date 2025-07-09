---
sticker: emoji//0035-fe0f-20e3
---
- [[#Variabile Uniforme Continua|Variabile Uniforme Continua]]
	- [[#Variabile Uniforme Continua#Media e Varianza|Media e Varianza]]
	- [[#Variabile Uniforme Continua#Numeri Pseudo-Casuali|Numeri Pseudo-Casuali]]
	- [[#Variabile Uniforme Continua#Metodo dell'Inversione|Metodo dell'Inversione]]
- [[#Variabile Normale o Gaussiana|Variabile Normale o Gaussiana]]
	- [[#Variabile Normale o Gaussiana#Caratteristiche|Caratteristiche]]
	- [[#Variabile Normale o Gaussiana#Media e Varianza|Media e Varianza]]
	- [[#Variabile Normale o Gaussiana#Variabile Normale Standardizzata|Variabile Normale Standardizzata]]
	- [[#Variabile Normale o Gaussiana#Riproducibilità|Riproducibilità]]
- [[#Variabile Aleatoria Esponenziale|Variabile Aleatoria Esponenziale]]
	- [[#Variabile Aleatoria Esponenziale#Media e Varianza|Media e Varianza]]
- [[#Esponenziale|Esponenziale]]
- [[#Variabile Beta|Variabile Beta]]
	- [[#Variabile Beta#Media e Varianza|Media e Varianza]]
- [[#Variabile Gamma|Variabile Gamma]]
	- [[#Variabile Gamma#Media e Varianza|Media e Varianza]]
	- [[#Variabile Gamma#Riproducibili|Riproducibili]]
- [[#Variabile $\chi^2$|Variabile $\chi^2$]]
- [[#Variabile $t$ di Student|Variabile $t$ di Student]]
	- [[#Variabile $t$ di Student#Media e Varianza|Media e Varianza]]
- [[#Variabile $F_{n,m}$ di Fisher-Snedecor|Variabile $F_{n,m}$ di Fisher-Snedecor]]

## Variabile Uniforme Continua
Il modello uniforme continuo consiste nell'assumere egualmente probabile la realizzazione della variabile $X\in{\alpha,\beta}$ in due intervalli della stessa ampiezza inclusi nel campo di definizione. I parametri della variabile uniforme continua determinano il suo campo di definizione e, indirettamente la media e la varianza della stessa.
Fare inferenza sui parametri della uniforme continua serve ad apprendere quale sia il campo di osservazione della variabile.

Formalmente, se $X\sim Unif(\alpha,\beta)$:
$$
f(x|\alpha,\beta)= \frac{1}{\beta-\alpha} \quad \alpha,\beta\in \mathbb{R}\quad \mathcal X=[\alpha,\beta]
$$
e la sua funzione di ripartizione sarà
$$
P[X\le x|\alpha,\beta]=\int_{\alpha}^x \frac{1}{\beta-\alpha}\ ds = \frac{x-\alpha}{\beta-\alpha}
$$
quindi
$$P[a\le X\le b|\alpha,\beta]=\int_{a}^b \frac{1}{\beta-\alpha}\ ds= \frac{b-a}{\beta-\alpha}$$
![[Pasted image 20250707182022.png|center|450]]

> [!example]+ Esempio:
> Se si arriva alla fermata dell'autobus alle 10 e si sa solo che ne passerà un altro entro le 10:30. Qual'è la probabilità che si debba aspettare più di 20 minuti?
> $$
> P(X>20)=1- \frac{1}{30-0}\int^{20}_{0}dx=1- \frac{20}{30}=\frac{1}{3}
> $$
### Media e Varianza 
$$\begin{align}&E[X]:=\int_{\alpha}^\beta x  \frac{1}{\beta-\alpha}\ dx=\frac{\beta^2-\alpha^2}{2(\beta-\alpha)}=\frac{(\beta-\alpha)(\beta+\alpha)}{2(\beta-\alpha)}=\frac{\alpha+\beta}{2} \\
&E[X^2]=\int_{\alpha}^\beta x^2 \frac{1}{\beta -\alpha}\ dx= \frac{\beta^3-\alpha^3}{3(\beta-\alpha)}=\frac{\alpha^2+\alpha\beta+\beta^2}{3} \\
&Var[X]=\frac{\alpha^2+\alpha\beta+\beta^2}{3}-\left( \frac{\alpha+\beta}{2} \right)^2=\frac{\alpha^2-2\alpha\beta+\beta^2}{12}= \frac{(\beta-\alpha)^2}{12} \end{align}$$
### Numeri Pseudo-Casuali
Le variabili uniformi hanno un ruolo fondamentale nella pratica: le loro realizzazioni sono direttamente generabili da un computer.
- **Numeri Casuali:** 
	- Hanno distribuzione uniforme su un intervallo specifico
	- Sono indipendenti tra loro
	- Più lungo è il periodo, migliore è la qualità della sequenza
Esistono diversi algoritmi per la generazioni di numeri casuali, tutti vengono inizializzati con un seed ed ogni volta che si uso lo stesso seed verrà prodotta la stessa sequenza.
### Metodo dell'Inversione
Il metodo dell'inversione è un metodo per generare realizzazioni da una variabile aleatoria continua che abbia una data funzione di ripartizione (strettamente crescente). Il metodo si basa sul fatto che:
- Se $X$ ha una funzione di ripartizione $F_{X}(x)$
- Se $U=f_{X}(x)$ è  una variabile aleatoria uniforme su $[0,1]$ indipendentemente dalla densità della variabile $X$
Allora un campione di valori da $X$ può essere ottenuto prima campionando $U\sim Unif(0,1)$, poi valutando $x=F^{-1}_{X}(u)$.
---
## Variabile Normale o Gaussiana
La distribuzione normale fu introdotta da Gauss e riproposta da Laplace per trattare misure affette da errore e inerenti alla traiettoria di corpi celesti.
L'ipotesi era che, misure ripetute dovessero essere rilevate con maggiore probabilità attorno ad un valore rappresentato dal valore effettivo della misura stessa. 
La ragione delle diverse misure è attribuibile a molti piccoli disturbi intercorsi tra un osservazione e l'altra.

Si assume che la variabilità delle misure sia finita e che gli errori stessi siano indipendenti tra loro (non essendoci alcuna informazione sulla tendenza degli errori ad essere maggiori o minori della misura effettiva). Il rispetto di questi vincoli permette di formulare la **Densità di Probabilità** della variabile aleatoria normale:
$$f(x|\mu,\sigma^2)=\frac{1}{\sqrt{  2\pi\sigma^2 }}\exp\left( - \frac{1}{2\sigma^2}(x-\mu)^2 \right)$$
Con $\mu\in \mathbb{R}$, $\sigma^2\in \mathbb{R}^+$, $\mathcal X=\mathbb{R}$. $\mu$ e $\sigma^2$ sono i due parametri della varianza della variabile.

![[Pasted image 20250708112906.png|center|400]]

### Caratteristiche
- La distribuzione è unimodale e simmetrica, ovvero media, mediana e modo coincidono
- L'asse delle ordinate è l'asse di simmetria
- Il massimo della funzione di densità è per $x=\mu$ ed è pari a $(\sigma \sqrt{ 2\pi })^{-1}$
### Media e Varianza
Si determina la funzione generatrice dei momenti:
$$\begin{align}\phi(t)&:=E[\exp(tX)] =\frac{1}{\sqrt{ 2\pi }\sigma}\int^\infty_{-\infty} \exp[tx]\exp\left\{ - \frac{(x-\mu)^2}{2\sigma^2} \right\}\ dx \\
&=\frac{1}{\sqrt{ 1\pi }} \frac{\sigma}{\sigma}\int_{-\infty}^\infty \exp[t(\sigma y+\mu)]\exp\left[ - \frac{y^2}{2} \right]\ dy, \quad \small{y= \frac{x-\mu}{\sigma},\ x=y\sigma+\mu}  \\
&= \frac{\exp[\mu t]}{\sqrt{ 2\pi }}\int_{-\infty}^\infty \exp\left\{ \frac{2\sigma ty-y^2}{2} \right\}\ dy \\
&=\frac{\exp[\mu t]}{\sqrt{ 2\pi }}\exp\left[ \frac{\sigma^2t^2}{2} \right]\int_{-\infty}^\infty \exp\left\{ - \frac{y^2-2\sigma ty+\sigma^2t^2}{2} \right\}\ dy \\
&=\exp\left\{ \mu t+ \frac{\sigma^2t^2}{2} \right\}\int^\infty_{-\infty} \frac{1}{\sqrt{ 2\pi }}\exp\left\{ - \frac{(y-\sigma t)^2}{2} \right\}\ dy \\
&=\exp\left\{ \mu t+\frac{\sigma^2t^2}{2} \right\}
\end{align}$$
Quindi 
$$\begin{gather} \phi(t)=\exp\left\{ \mu t+\frac{\sigma^2t^2}{2} \right\}  \\
\phi'(t)=(\mu+\sigma^2t)\exp\left\{ \mu t+ \frac{\sigma^2t^2}{2} \right\}\to \phi'(0)=\mu \\
\phi''(t)=[\sigma^2]+(\mu+\sigma^2t)^2\exp\left\{ \mu t+ \frac{\sigma^2t^2}{2} \right\}\to \phi''(0)=\sigma^2+\mu^2 \\
\end{gather}$$
Con $E[X]=\mu$ e $Var(X)=\sigma^2$
Al contrario della binomiale e della Poisson, la posizione della dispersione della distribuzione nella normale possono essere vantaggiosamente regolate in modo separato.
### Variabile Normale Standardizzata

> [!info] Trasformata Lineare di una Normale
> La trasformata lineare di una normale è anch'essa una trasformata normale, cioè se $X\sim N(\mu,\sigma^2)$ allora
> $$Y=\alpha+\beta X\sim N(\alpha +\beta \mu,\ \beta^2\sigma^2)$$
> Infatti: 
> $$\begin{align}
> E[\exp(t(\alpha+\beta X))]&=\exp[\alpha t]E[\exp(\beta tX)]=\exp[\alpha t]\phi_{x}(\beta t)=\exp[\alpha t]\exp\left\{ \mu\beta t+ \frac{\sigma^2\beta^2t^2}{2}  \right\} \\
> &=\exp\left\{ (\alpha+\beta \mu)t+ \frac{(\beta^2\sigma^2)t^2}{2} \right\}
> \end{align}$$

In particolare, se $Z= \frac{X-\mu}{\sigma}$ allora
$$Z\sim N\left( \frac{\mu-\mu}{\sigma}=0,\ \frac{1}{\sigma^2}\sigma^2=1 \right)$$
Una qualsiasi v.a. normale che subisce la trasformazione $Z= \frac{X-\mu}{\sigma}$ è detta standardizzata, e la sua funzione di ripartizione è
$$
\phi_{(x)}:=\frac{1}{\sqrt{ 2\pi }}\int^x_{-\infty} \exp\left[ -\frac{z^2}{2} \right]\ dz,\quad \forall x\in \mathbb{R}
$$
 Non sapendo valutare l'integrale della normale, si ricorre a delle *approssimazioni tabulate* per $\phi(\cdot)$, infatti se $X\sim N(\mu,\sigma^2)$ allora
$$P[X<b]=P\left( \frac{X-\mu}{\sigma}< \frac{b-\mu}{\sigma} \right)=P\left( Z< \frac{b-\mu}{\sigma} \right)=:\phi\left( \frac{b-\mu}{\sigma} \right)$$

> [!hint] Forme Tavole
> Le tavole hanno forme diverse e si deve sempre considerare la  figura/formula riportata per utilizzarle

> [!example]+ Esempio: Valutare $Pr(z\le 1.64)$:
> ![[Pasted image 20250708122429.png|center|550]]

### Riproducibilità
La somma di $n$ variabili aleatorie normali indipendenti è $$N\left( \mu=\sum^n_{i=1}\mu_{i},\ \sigma^2=\sum^n_{i=1}\sigma^2_{i} \right)$$
La FGM di $\sum^n_{i=1}X_{i}$ è data da 
$$\begin{align}\phi(t)&=E[\exp\{tX_{1}+tX_{2}+\ldots+tX_{n}\}]=E[\exp(tX_{1})\exp(tX_{2})\ldots \exp(tX_{n})]=\prod^n_{i=1}E[\exp(tX_{i})]= \\
&=\prod^n_{i=1}\exp\left\{ \mu_{i}t+ \frac{\sigma^2_{i}t}{2} \right\}=\prod_{i=1}^2 \exp\left\{ \mu_{i}t+\frac{\sigma^2_{i}t^2}{2} \right\}=\exp\left\{ \overline \mu t+ \frac{\overline \sigma^2t^2}{2} \right\}\end{align}$$
Con $\overline \mu:= \sum^n_{i=1}\mu_{i}$ e $\overline \sigma^2=\sum^n_{i=1}\sigma^2_{i}$

> [!example]+ Esempio
> Si assume che il reddito degli impiegati pubblici è distribuito normalmente. Si sa anche che il $25\%$ guadagna meno di $180$ e il $25\%$ più di 320. Quale frazione guadagna meno di $250$ e quale fra $260$ e $300$?
> $$\begin{gather}
> P(X<180)=P\left( Z< \frac{180-\mu}{\sigma} \right)=0.25 \\
> P(X>320)=P\left( Z> \frac{320-\mu}{\sigma} \right)=0.25
> \end{gather}$$
> Dalla tavola $x_{0.25}=-0.675$ e $z_{0.75}=0.675$, quindi $$P(Z<-0.675)=0.25\quad e \quad P(Z>0.675)=0.25$$
> Quindi, mettendo a sistemi
> $$
> \frac{180-\mu}{\sigma}=-0.675 \quad e \quad \frac{320-\mu}{\sigma}
> $$
> Si ottiene
> $$\mu=250\quad e \quad \sigma=103.70$$
> Per cui
> $$\begin{gather}P(X<250)=\phi\left( \frac{250-250=0}{103.70} \right)=0.5 \\
> P(260<X<300)=\phi\underset{0.684}{\left( \frac{300-250}{103.70} \right)}-\underset{0.096}{\phi\left( \frac{260-250}{103.70} \right)}=0.147\end{gather}$$

La larghezza con cui è prodotta la scalanatura di un trafilato è $N(\mu=0.9,\sigma=0.0030)$, le specifiche impongono il limite $0.9\pm 0.005$, che percentuali di difetti è prevista?
$$2P(X>0.905)=2\left( 1-\phi\underset{1.67}{\left( \frac{0.905-0.9}{0.0030} \right)} \right)=2(1-0.953)=2\times 0.047=0.094$$
Quale $\sigma$ è compatibile con una percentuale di difetti $\le 1\%$?
Se deve essere $P(Z\le 0.895\cup X\ge 0.905)=0.01$ allora deve essere anche $$P\left( Z\ge \frac{0.905-0.9}{\sigma} =\frac{0.005}{\sigma}\right)=0.005$$
Quindi $\phi\left( \frac{0.005}{\sigma} \right)=0.995$. Infine, poiché
$$\phi^{-1}(0.995)=2.57=\frac{0.005}{\sigma}\Longrightarrow \sigma= \frac{0.005}{2.57}=0.001945$$
## Variabile Aleatoria Esponenziale
La variabile aleatoria esponenziale è la più semplice forma di modellazione del tempo di durata/attesa di un evento.
**Funzione di Densità** e di **Ripartizione:**
$$\begin{align}&f(x|\lambda)\begin{cases}
\lambda \exp[-\lambda x] & se\ x\ge 0 \\ 0 & se \ x< 0
\end{cases} \\
&F(x)=P[X\le x]=\int_{0}^x\lambda \exp[-\lambda y]\ dy = \lambda\left(\left . - \frac{1}{\lambda}\exp(-\lambda y)\right|_{0}^x \right)=1-\exp[-\lambda x]\quad x\ge 0\end{align}$$
![[Pasted image 20250708125659.png|center|400]]

### Media e Varianza
$$\begin{align} 
\phi(t)&:=E[\exp(tX)]\lambda \exp[-\lambda x] \ dx \\
&=\lambda \int_{0}^\infty \exp[-(\lambda-t)x]\ dx \\
&= \lambda \int_{0}^\infty \exp[-(\lambda-t)x]\ dx \\
&=\frac{\lambda}{\lambda-t},\quad t<\lambda
\end{align}$$
$$\begin{gather}\phi'(t)= \frac{\lambda}{(\lambda-t)^2} \\
\phi''(t)= \frac{2\lambda}{(\lambda-t)^3} \\
E[X]=\phi'(0)= \frac{1}{\lambda}\quad E[X^2]=\phi''(0)=\frac{2}{\lambda^2}\quad Var[X]=\frac{1}{\lambda^2}\end{gather}$$
---
## Esponenziale
La esponenziale è una variabile senza memoria, ovvero la probabilità di una durata maggiore di $t+s$ non è influenzata dalla conoscenza che l'evento ha già raggiunto la durata $t$, ovvero
$$
P[X>s+t|X>t]= \frac{P[X>s+t,\ X>t]}{P[X>t]}= \frac{\exp[-\lambda(s+t)]}{\exp[-\lambda(t)]}=P[X>s]
$$
E quindi anche 
$$P[X>s+t]=P[X>s]P[X>t]$$
Che per l'esponenziale risulta
$$\exp[-\lambda(s+t)]=\exp[-\lambda s]\exp[-\lambda t]$$
Nel caso di una distribuzione con memoria la probabilità di tempo residuo, sapendo che si è già vissuto $t$ è
$$
P[\text{vita residua}>s]=P[\text{vita totale}>t+s|\text{vita vissuta}=t]= \frac{1-F(t+s)}{1-F(t)}
$$

Il tempo di vita di un'auto è una $Exp\left( \frac{1}{20} \right)$
- Qual'è la probabilità che faccia almeno altri $20(000)$ km avendone già fatte $10(000)$? $$1-F\left( 20|\lambda=\frac{1}{20} \right)=\exp[-\lambda 20]=\exp\left( -\frac{20}{20} \right)=0.3678$$
- Come cambia la risposta se la durata di vita dell'auto è $U(0,40)$? $$\begin{align}P(X>\underset{t+s}{30}|X\ge \underset{t}{10})= \frac{1-F(t+s)}{1-F(t)}=\frac{1-P(X\le 30)}{1-P(X\le 10)}=\frac{1- \frac{3}{4}}{1- \frac{1}{4}}=0.33\ne 0.5\end{align}$$
---
## Variabile Beta
La variabile $X$ beta è definita su un intervallo finito $\mathcal X=[a,b]$. I parametri della distribuzione sono $(\alpha,\beta)$, con $\alpha>0$ e $\beta>0$. Si usa per esprimere l'incertezza.
È di interesse il caso $\mathcal X=[0,1]$, cosicché la sua funzione di densità è $$f(x)=\frac{\lceil(\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}x^{\alpha-1}(1-x)^{\beta-1}$$
se $0\le x\le 1$, dove $\frac{\lceil(\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}$ è l'integrale di Eulero del $1°$ tipo, ovvero 
$$\frac{\lceil(\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}=\int_{0}^1 x^{\alpha-1}(1-x)^{\beta-1}\ dx$$
![[Pasted image 20250709005318.png|center|400]]
### Media e Varianza
$$
E[X]= \frac{\alpha}{\alpha+\beta}\qquad Var[X]= \frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}
$$
---
## Variabile Gamma
La variabile aleatoria gamma con parametri $(\alpha,\lambda)$, $\alpha>0$ e $\lambda>0$, è definita dall'integrale di Eulero di secondo tipo: 
$$
\lceil(\alpha):=\int_{0}^\infty \lambda^\alpha x^{\alpha-1}\exp[-\lambda x]\ dx
$$
Pertanto la funzione di densità è 
$$
f(x)=\begin{cases}
\frac{\lambda^\alpha}{\lceil(\alpha)x^{\alpha-1}}\exp[-\lambda x] & se\ x>0 \\
0 & se \ x\le 0
\end{cases}
$$
Si può dimostrare che $\lceil(n)=(n-1)!$: Se $n\in \mathbb{N}$ con $\alpha=1$ la distribuzione gamma coincide con l'esponenziale.

![[Pasted image 20250709010005.png|center|400]]

### Media e Varianza
Si calcola la FGM:
$$\begin{align}
\phi(t)&:= \int^\infty_{0} \exp[tx] \frac{\lambda^\alpha}{\lceil (\alpha)}x^{\alpha-1}\exp[-\lambda x]\ dx \\
&= \frac{\lambda^\alpha}{\lceil(\alpha)}\int_{0}^\infty x^{\alpha-1}\exp[-(\lambda-t)x]\ dx \\
&=\left( \frac{\lambda}{\lambda-t} \right)^\alpha  \frac{1}{\lceil (\alpha)}\int_{0}^\infty y^{\alpha-1}\exp[-y]\ dy\qquad con \ y=(\lambda-t)x \\
&= \left( \frac{\lambda}{\lambda-t} \right)^\alpha
\end{align}$$
$$\begin{gather} 
\phi'(t)= \frac{\alpha\lambda^\alpha}{(\lambda-t)^{\alpha+1}} \\
\phi''(t)=\frac{\alpha(\alpha+1)\lambda^\alpha}{(\lambda-t)^{\alpha+2}}
\end{gather}$$
$$E[X]=\phi'(0)=\frac{a}{\lambda}\qquad E[X^2]=\phi''(0)= \frac{\alpha(\alpha+1)}{\lambda^2}\qquad Var[X]=E[X^2]-E[X]^2=\frac{\alpha}{2}$$

- Per $\alpha=1$, la gamma coincide con l'esponenziale
- La somma di esponenziali di parametro ($\lambda$) iid è una gamma di parametri $(n,\lambda)$

> [!example]+ Esempio:
> La durata di un esponenziale $\left( \frac{1}{30} \right)$. Se si hanno $5$ toner, si ha un'autonomia espressa da una gamma $\left( \frac{5,1}{30} \right)$
> ![[Pasted image 20250709011616.png|center|400]]

### Riproducibili
Se due variabili aleatorie gamma indipendenti condividono il parametro $\lambda$ allora sono riproducibili, ovvero
$$X_{1}+X_{2}\sim Gamma(\alpha_{1}+\alpha_{2},\ \lambda)$$
Infatti
$$\begin{align}\phi_{X_{1}+X_{2}}(t)&=E[\exp^{t(X_{1}+X_{2})}]=E[\exp^{tX_{1}}\exp^{tX_{2}}]=\underset{\text{per l'indipendenza}}{E[\exp^{tX_{1}}]E[\exp^{tX_{2}}]}= \\
&=\left( \frac{\lambda}{\lambda-t} \right)^{\alpha_{1}}\left( \frac{\lambda}{\lambda-t} \right)^{\alpha_{2}}=\left( \frac{\lambda}{\lambda-t} \right)^{\alpha_{1}+\alpha_{2}}\end{align}$$
---
## Variabile $\chi^2$
Se $Z\sim N(0,1)$ allora
$$Z^2\sim \chi_{1}^2$$
Ovvero se 
$$
P(-0.5\le Z\le 0.5)= \phi(0.5)-\phi(-0.5)=0.695-(1-0.695)=0.39
$$
Allora
$$P(\chi_{1}\le 0.5^2=0.25)=0.3829249$$

Per $Z_{1},\ldots Z_{n}\sim N(0,1)$ indipendenti
$$\sum^n_{i=1}Z_{i}^2\sim \chi_{n}^2$$
La distribuzione è quindi riproducibile:
$$
\chi^2_{n}+\chi_{m}^2=\sum^n Z_{i}^2+\sum^mZ_{i}^2 = \sum^{n+m} Z_{i}^2=\chi^2_{n+m}
$$
![[Pasted image 20250709012203.png|center|400]]

**Variabile $\chi^2$, $P[X\ge \chi_{\alpha ,n}]=\alpha$:**

![[Pasted image 20250709012502.png|center|500]]

Si spara ad un bersaglio bidimensionale e si commette un errore in vertical $X_{1}$ ed orizzontale $X_{2}$ che seguono indipendentemente una distribuzione $N(\mu=0,\sigma=2)$. Qual'è la probabilità che il bersaglio venga mancato di più di $3$cm?

Si sa che la distanza fra il bersaglio e il colpo è 
$$D^2=X_{1}^2+X_{2}^2$$Quindi 
$$\frac{D^2}{4}=\left( \frac{X_{1}}{2} \right)^2+\left( \frac{X_{2}}{2} \right)^2$$
![[Pasted image 20250709012900.png|center|300]]
$$P[D>3]=P[D^2>9]=P[X^2_{1}+X_{2}^2>9]=P\left[ Z_{1}^2+Z_{2}^2> \frac{9}{4} \right]=P\left[ \frac{\chi_{2}>9}{4} \right]\approx 0.3246525$$
Avendo ottenuto $Z_{i}=\frac{1}{\sigma}$, $X_{i}\sim N(0,1)$, $i=1,2$.

---
## Variabile $t$ di Student
La variabile $t$ è anche detta $t$ di student.
Data una v.a. normale standard $Z$ e una chi-quadro $C_{n}$ si ha
$$
T_{n}= \frac{Z}{\sqrt{ \underset{\text{radice di una varianza}}{\frac{C_{n}}{n}} }}
$$
che è una $t$ di student con $n$ gradi di libertà

![[Pasted image 20250709013550.png|center|400]]

- La distribuzione $t$ scende a $0$ più lentamente di una normale, è caratterizzata quindi da code più pesanti
- Al crescere di $n$ la varianza decresce
- $t_{\alpha,n}$ è definito come quel valore t.c. $P(T_{n}\ge t_{\alpha,n})=\alpha$
- Anche i valori $t_{\alpha ,n}$ sono tabulati

**Distribuzione $t$, $P[T_{n}\ge t_{\alpha ,n}]=\alpha$:**
![[Pasted image 20250709013916.png|center|500]]
### Media e Varianza
$$E[T_{n}]=0\quad per\ n\ge 2\qquad Var[T_{n}]= \frac{n}{n-2}\quad per\ n\ge 3$$
??? MGF di $X\sim X_{1}^2$ non c'è nelle slide???

---
## Variabile $F_{n,m}$ di Fisher-Snedecor
Serve per confrontare la distribuzione di due varianza.
Date una v.a. $C_{n}\sim \chi_{n}$ e una v.a. $C_{m}\sim \chi_{m}$ indipendenti, allora
$$\frac{\frac{C_{n}}{n}}{\frac{C_{m}}{m}}\sim F_{n,m}\qquad P(F_{n,m}>f_{n,m,\alpha})=\alpha$$
![[Pasted image 20250709014143.png|center|400]]
