---
sticker: emoji//0036-fe0f-20e3
Order: "5"
---
- [[#Concetti Preliminari|Concetti Preliminari]]
- [[#Approccio Frequentista|Approccio Frequentista]]
	- [[#Approccio Frequentista#Media e Varianza della Media Campionaria di Osservazioni iid|Media e Varianza della Media Campionaria di Osservazioni iid]]
- [[#Teorema del Limite Centrale|Teorema del Limite Centrale]]
	- [[#Teorema del Limite Centrale#Dimostrazione|Dimostrazione]]
	- [[#Teorema del Limite Centrale#Binomiale|Binomiale]]
		- [[#Binomiale#Correzione di Continuità|Correzione di Continuità]]
	- [[#Teorema del Limite Centrale#Distribuzione della Media Campionaria|Distribuzione della Media Campionaria]]
- [[#Varianza Campionaria|Varianza Campionaria]]
- [[#Distribuzione di $\overline X$ per Popolazioni Gaussiane|Distribuzione di $\overline X$ per Popolazioni Gaussiane]]
- [[#Distribuzione di $S^2$ per Popolazioni Gaussiana|Distribuzione di $S^2$ per Popolazioni Gaussiana]]
- [[#Distribuzione di $\overline X$ e $S^2$ per Popolazioni Gaussiane|Distribuzione di $\overline X$ e $S^2$ per Popolazioni Gaussiane]]
- [[#Distribuzione $\overline X$ stimando $\sigma^2$ tramite $S^2$ per Popolazioni Gaussiane|Distribuzione $\overline X$ stimando $\sigma^2$ tramite $S^2$ per Popolazioni Gaussiane]]


## Concetti Preliminari
- **Popolazione:** Ci si riferisce ad una popolazione sui cui membri è possibile operare delle osservazioni di alcune caratteristiche (come per esempio un tempo di durata prima di una rottura o i pezzi buoni/non buoni prodotti da una macchina). Ognuna delle caratteristiche avrà una sua distribuzione nella popolazione.
- **Contesto:** Si estrae un campione della popolazione di interesse, prima di osservare una caratteristica si ha incertezza sulla sua determinazione. Si assume allora che il campione sia tratto con ripetizione in modo probabilistico e si assume anche nota la v.a. parametrica che regola l'incertezza dei parametri

> [!info] v.a. 
> Le variabili aleatorie sottostanti le osservazioni campionarie sono iid.

L'obiettivo con le statistiche campionarie è quello di fare inferenza sui parametri, fare previsioni, inferire sui dati mancanti e fare selezione fra i possibili modelli alternativi alle osservazioni.

## Approccio Frequentista
L'approccio frequentista all'inferenza parametrica si basa sulla distribuzione di alcune statistiche campionarie, ovvero l'incertezza con cui si osservano queste statistiche al variare del campione estratto.

> [!gray] Approccio Frequentista
> Se le osservazioni di una caratteristica hanno una cera distribuzione, quale sarà la distribuzione delle medie, se queste ultime fossero valutate su tutti i campioni della popolazione?


> [!example]+ Esempio:
> Si considera una popolazione $\{A,B,C,D\}$ e si considera la caratteristica $X=\#\text{numero di libri letti in un anno}$. 
>
> | Individui | Libri Letti |
> | --------- | ----------- |
> | A         | 0           |
> | B         | 1           |
> | C         | 1           |
> | D         | 3           |
> Se si potesse osservare tutta la popolazione si conoscerebbe la media della caratteristica sull'intera popolazione, tuttavia ciò non è possibile in quanto si ha solo un campione e allora si valuta la caratteristica solo su quest'ultimo: $$\overline X = \frac{5}{4}=1.25$$
>
> Si assume adesso di disporre solo di un campione di numerosità 2, estratto con ripetizione, per un totale di $4^2=16$ campioni:
>
> ![[Pasted image 20251204181312.png|center|400]]


### Media e Varianza della Media Campionaria di Osservazioni iid
Un carattere $X$, nella popolazione, ha media $\mu$ e varianza $\sigma^2$.
- La *Media della Distribuzione della Media Campionaria* è:
$$\begin{align}
E[\overline X]= E \left[ \frac{X_{1}+X_{2}+\ldots+X_{n}}{n} \right]= \frac{E[X_{1}]+E[X_{2}]+\ldots+E[X_{n}]}{n}= \frac{n\mu}{n}= \mu
\end{align}$$
- La *Varianza della distribuzione delle Medie Campionarie* è:
$$
Var[\overline X]= Var \left( \frac{X_{1}+X_{2}+\ldots+X_{n}}{n} \right)= \frac{Var[X_{1}]+Var[X_{2}]+\ldots+Var[X_{2}]}{n_{2}}= \frac{n\sigma^2}{n^2}= \frac{\sigma^2}{n}
$$

> [!hint] Osservazione 
> - La distribuzione delle medie campionarie è sempre centrata su $\mu$
> - La sua varianza si contrae all'aumentare di $n$ e il suo ammontare è proporzionale alla varianza della popolazione.
> - $\mu$ non è conosciuta ma si sa che, all'aumentare di $n$ le medie campionare che vengono estratte da tutti i possibili campioni di numerosità $n$, esse si concentrerebbero attorno a $\mu$ (all'aumentare $n$).
> - Usare la media campionarie valutata su un singolo campione come singolo campione di stima di $\mu$ appare poco rischioso se $Var(\overline X)$ è piccola.
> - La varianza delle medie campionarie è chiamata *Errore Standard*, in quanto sintetizza l'ammontare dell'errore di campionamento dovuto all'impiego di un singolo campione di numerosità $n$.

---

## Teorema del Limite Centrale
Il teorema del limite centrale aggiunge informazioni sulla forma della distribuzione delle medie campionarie

> [!gray] Teorema del Limite Centrale
> Siano $X$ delle v.a. iid, tutte con media $\mu$ e varianza $\sigma^2$. Allora se $n$ è grande, la somma delle variabili aleatorie $$X_{1}+X_{2}+\ldots X_{n}$$ è rappresentativamente distribuita come una *Normale* con:
> - Media = $n\mu$
> - Varianza = $n\sigma^2$

Il TLC assicura la riproducibilità (asintotica) di v.a. iid qualsiasi.

> [!gray] TLC Standard
> IL TLC in forma standardizzata è:
> $$\begin{gather}
> \frac{X_{1}+X_{2}+\ldots+X_{n}-n\mu}{\sigma \sqrt{ n }}\dot\sim N(0,1) \\
> p\left( \frac{X_{1}+X_{2}+\ldots+X_{n}-n\mu}{\sigma \sqrt{ n }}<x \right)\approx \Phi(x)
> \end{gather}$$
> Ovvero, quando $n\to \infty$, la funzione di ripartizione (CDF) della somma di v.a. qualsiasi standardizzate converge ad una normale $N(0,1)$.

### Dimostrazione
Si considerano $n$ v.a. indipendenti standardizzate $Y_{1},\ldots Y_{n}$, allora $S_{n}= \frac{Y_{1}+\ldots+Y_{n}}{\sqrt{ n }}$
 ha media 0 e varianza 1, allora 
 $$
 \phi_{S_{n}}(t)= \prod^n_{i=1}\phi_{\frac{Y_{i}}{\sqrt{ n }}}(t)= \left[ \phi_{\frac{Y_{1}}{\sqrt{ n }}}(t) \right]^n
 $$
 In generale $\phi_{x}(0)=1$ e nel caso di distribuzioni standardizzate varrà
 $$\begin{align}
 &\phi'_{\frac{Y_{1}}{\sqrt{ n }}}(0)=0 \\
&\phi''_{\frac{Y_{1}}{\sqrt{ n }}}(0)= \frac{1}{n}
 \end{align}$$
 Allora, sviluppando in serie di MacLaurin, $\phi_{S_{n}}(t)$ sarà
 $$\begin{align}
 \lim_{ n \to \infty } \left[ \phi_{\frac{Y_{1}}{\sqrt{ n }}}(t) \right]^2= \lim_{ n \to \infty }  \left[ \phi_{\frac{Y_{1}}{\sqrt{ n }}}(0)+t\phi'_{\frac{Y_{1}}{\sqrt{ n }}}(0)+ \frac{t^2}{2}\phi''_{\frac{Y_{1}}{\sqrt{ n }}}(0)+o(t^2) \right]^2=\lim_{ n \to \infty } \left[ 1+0+ \frac{t^2}{2n}+o(t^2) \right]^2\approx \exp\left( \frac{t^2}{2} \right)
 \end{align}$$
Si ricorda che la FGM(?) della Normale è 
$$
\phi(t)= \exp\left\{ \mu t+ \frac{\sigma^2t^2}{2} \right\}
$$
Allora la FGM della $N(0,1)$ è
$$
\phi(t)=\exp\left( \frac{t^2}{2} \right)
$$
Quindi 
$$
\lim_{ n \to \infty } S_{n}\approx N(0,1)
$$

> [!example]+ Esempio:
> In un ascensore possono salire 5 persone, che potrebbe rompersi se il peso complessivo $X$ è superiore ai 300 kg. 
> Con quale probabilità avviene questo evento se salgono 5 persone il cui il peso ha $\mu=55$ e $\sigma^2=9$?
> - Dal TLC: $$\sum^n_{i=1}X_{i}\approx N(n\mu,n\sigma^2)= N(275,45)$$ quindi si valuta $$ P\left( Z> \frac{300-275}{\sqrt{ 45 }}=3.72 \right)=9.961139e-05 $$
>  

### Binomiale
Il TLC fornisce anche un'approssimazione della binomiale:
Sia $X=\{0,1\}$ e $Y=\sum^n_{i=1}X_{i}$
$$\begin{gather}
E[Y]=n\pi\qquad Var(Y)=n\pi(1-\pi) \\ \\

\frac{Y-n\pi}{\sqrt{ np(1-\pi) }}\dot\sim N(0,1)
\end{gather}$$
#### Correzione di Continuità
Se $X\sim Bin(\pi=0.3,n=450)$, $E[X]=135$, $Var(X)=94.5$
$$\begin{align}
P(Y>150)&= \sum^{450}_{i=151} \begin{pmatrix}
450 \\ i
\end{pmatrix}\pi^i(1-\pi)^{450-i}=\underline{0.0565} \\
&\approx \sum^\infty_{i=151}P[i-0.5<X<i+0.5]\quad\text{correzzione} \\
&= p[X>150.5]= 1-\phi\left( \frac{150.5-135}{9.72} =1.59\right) \\
&\approx 1-0.9441=\underline{0.0559}
\end{align}$$
- Non introducendo la correzione: $$\begin{align}p[X>150]&= 1-\phi\left( \frac{150-135}{9.72} =1.54\right)\end{align}\approx 1-0.9382=\underline{0.0618}$$

### Distribuzione della Media Campionaria
Se per il TLC: $X_{1}+\ldots+X_{n}\dot\sim N(n\mu,n\sigma^2)$, allora
$$
\overline X = \frac{X_{1}+X_{2}+\ldots+X_{n}}{n}\dot\sim N\left( \mu, \frac{\sigma^2}{n} \right)
$$
e anche 
$$
\frac{\overline Z-\mu}{\frac{\sigma}{\sqrt{ n }}}\dot\sim N(0,1)
$$

Si deve misurare una nicchia nel muro, ma a misure ripetute risultano sempre leggermente diverse. 
Si stima $\sigma=2mm$, si decide di usare la media aritmetica come misura $d$ della nicchia.
Quante misure si devono fare per ottenere che la media $\overline X$ calcolata con i dati del campione sia compresa con un probabilità del $95\%$ nell'intervallo $d\pm 0.5mm$ centrato sulla misura vera?

$$\begin{gather}
\overline X\sim N\left( d,\sigma= \frac{2}{\sqrt{ n }} \right) \\
\begin{aligned} \\
p[-0.5<\overline X<0.5]&= P\left( -\frac{0.5}{\frac{2}{\sqrt{ n }}}< \frac{\overline X-d}{\frac{2}{\sqrt{ n }}}< \frac{0.5}{\sqrt{ n }} \right) \\
&\approx P\left[ -\frac{\sqrt{ n }}{4}<Z< \frac{\sqrt{ n }}{4} \right]
\end{aligned} \\
 \\
1-2P\left[ Z< \frac{\sqrt{ n }}{4} \right]\ge 0.95
\end{gather}$$
Poiché si vuole 
$$P\left[ Z<- \frac{\sqrt{ n }}{4} \right]\ge 0.025$$
Siccome $P[Z<-1.96]\approx 0.025$ allora 
$$
-\frac{\sqrt{ n }}{4}\ge -1.961 \to n\ge 62
$$


---
## Varianza Campionaria
Si considerano nuovamente delle variabili aleatorie $X_{1},\ldots,X_{n}$, tratte da una popolazione la cui caratteristica $X$ ha media $\mu$ e varianza $\sigma^2$.
Si considera ora la distribuzione di 
$$S^2:= \frac{1}{n-1}\sum^n_{i=1}(X_{i}-\overline X)^2$$
Per calcolare $E(S^2)$ considera che in generale
$$\begin{gather}\sum^n_{i=1}(x_{i}-\overline x)=\sum^n_{i=1}x_{i^2}-n \overline x^2 \\
S^2= \frac{1}{n-1}\left( \sum^n_{i=1}X_{i}^2-n \overline X^2 \right)\end{gather}$$
ovvero che
$$
(n-1)S^2=\sum^n_{i=1}X_{i}^2-n \overline X^2
$$

Poiché, una generica variabile aleatoria $W$
$$Var[W]=E[W^2]-E[W]^2\longrightarrow E[W^2]=Var[W]+E[W]^2$$
il valore atteso di $S^2$ si valuta considerando:
$$\begin{align} (n-1)E[S^2]&= E\left( \sum^n_{i=1}(X_{i}-\overline X)^2 \right)=E\left( \sum^n_{i=1} X_{i}^2+n \overline X^2-2\overline X^2 n \right)=E\left[ \sum^n_{i=1}X_{i}^2 \right]-E[n \overline X^2]= \\
&=nE[X^2]+nE[\overline X^2]=n Var[X]+nE[X]^2-nVar[\overline X]-nE[\overline X]^2= \\
&=n\sigma^2+n\mu^2- \frac{n\sigma^2}{n}-n\mu^2=\sigma^2 \\
E[S^2]&=\sigma^2 \end{align}$$
---
## Distribuzione di $\overline X$ per Popolazioni Gaussiane
Se la caratteristica $X$ osservata è distribuita gaussianamente, $X_{i}\sim N(\mu,\sigma^2)$, si ottengono risultati circa la distribuzione di $\overline X$ e di $S^2$. 
$\overline X= \frac{1}{n}(X_{1}+\ldots+X_{n})$ è la somma di $N(\mu,\sigma^2)$ indipendenti ed è quindi 
$$
\overline X\sim N\left(  \frac{1}{n} n\mu=\mu,\ \frac{n\sigma^2}{n}=\frac{\sigma^2}{n} \right)
$$
## Distribuzione di $S^2$ per Popolazioni Gaussiana
$$S^2:= \frac{1}{n-1}\sum^n_{i=1}(X_{i}-\overline X)^2$$
$$\begin{align}\sum^n_{i=1}(X_{i}-\overline X)^2&= \sum^n_{i=1}(X_{i}-\mu)^2+n(\overline X-\mu)^2-2\sum^n_{i=1}(X_{i}-\mu)(\overline X-\mu)\cdot \frac{n}{n}= \\
&= \sum^n_{i=1}(X_{i}-\mu)^2+n(\overline X-\mu)^2-2n(\overline X-\mu) \frac{\sum^n_{i=1} X_{i}}{n}- \frac{n\mu}{n}= \\
&= \sum^n_{i=1}(X_{i}-\mu)^2-n(\overline X-\mu)^2= \\
\text{si divide per }\sigma^2&\to \frac{\sum^n_{i=1}(X_{i}-\overline X)^2}{\sigma^2}=\frac{\sum^n_{i=1}(X_{i}-\mu)}{\sigma^2}- \frac{n(\overline X-\mu)^2}{\sigma^2} \end{align}$$

$$\underset{\chi^2_{n}}{\sum^n_{i=1}\left( \frac{X_{i}-\mu}{\sigma} \right)^2}= \underset{\chi^2_{n-1}}{\frac{\sum^n_{i=1}(X_{i}-\overline X)}{\sigma^2}}+ \underset{\chi^2_{1}}{\left[ \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}} \right]^2}$$

> [!info] Nota
> Il termine di destra e l'ultimo di sinistra sono distribuiti in forma nota. Si può congetturare che il termine ${\frac{\sum^n_{i=1}(X_{i}-\overline X)}{\sigma^2}}$ sia indipedente da $\left[ \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}} \right]^2$ e pertanto distribuito come un $\chi^2_{n-1}$ con $n-1$ gradi di libertà.
> La congettura è dimostrabile.

## Distribuzione di $\overline X$ e $S^2$ per Popolazioni Gaussiane
Concludendo
$$\begin{gather}\overline X\sim N\left( \mu, \frac{\sigma^2}{n} \right) \\
\frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}\dot\sim N(0,1) \\
\frac{(n-1)S^2}{\sigma^2}\sim \chi^2_{n-1} 
\end{gather}$$
Oppure
$$\frac{S^2}{\sigma^2}\sim \frac{\chi^2_{n-1}}{n-1}$$
$\overline X$ e $(n-1)S^2$ sono v.a. indipendenti perché dipendono solo da $\mu$, $\sigma^2$ e $n$.

> [!example]+ Esempio:
> La temperatura di una componente dopo 10 ore di funzionamento è assunta gaussaina. Se si effettuano 5 misurazioni, qual'è:
> - La probabilità che il rapporto fra la varianza campionaria delle osservazioni $S^2$ e $\sigma^2$ superi $20\%$ quella reale? 
> 	- Poiché $\frac{(n-1)S^2}{\sigma^2}\sim \chi_{4}^2$, ovvero $\frac{S^2}{\sigma^2}\sim \frac{\chi^2_{4}}{(n-1)}$ allora $$p\left( \frac{S^2}{\sigma^2}>1.2 \right)=p(\chi_{4}^2>1.2*4=4.8)=0.3084$$
> - La probabilità che il rapporto fra la varianza campionaria delle osservazioni $S^2$ e $\sigma^2$ sia compreso fra $0.80$ e $1.20$?
> 	- $$p\left( 0.8\le \frac{S^2}{\sigma^2}\le 1.2 \right)=p(\chi_{4}^2<1.2 * 4=4.8)-p(\chi_{4}^2<0.8*4=3.2)=0.21$$

## Distribuzione $\overline X$ stimando $\sigma^2$ tramite $S^2$ per Popolazioni Gaussiane
Per la determinazione della distribuzione di $\overline X$ si possono non conoscere $\sigma^2$. Si vuole quindi conoscere la distribuzione di
$$\frac{\overline X-\mu}{\frac{S}{\sqrt{ n }}}$$
Poiché
$$\frac{Z}{\frac{\sqrt{ \chi^2_{m} }}{m}}\sim t_{m-1}$$
Allora moltiplicando per $\sqrt{ \frac{\sigma^2}{\sigma^2} \frac{n-1}{n-1} }$ si ottiene
$$
\frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}\sqrt{ \frac{\sigma^2}{S^2} \frac{n-1}{n-1} }= \frac{\frac{\overline X-\mu}{\frac{\sigma}{\sqrt{  n }}}}{\sqrt{ \frac{S^2(n-1)}{\sigma^2}  \frac{1}{n-1}}}= \frac{Z}{\sqrt{  \frac{\chi_{n-1}^2}{n-1} }}\sim t_{n-1}
$$