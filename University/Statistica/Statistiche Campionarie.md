---
sticker: emoji//0036-fe0f-20e3
---
n## Varianza Campionaria
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
## Distribuzione di $S^2$ per Popolazioni Gaussiane
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

La temperatura di una componente dopo 10 ore di funzionamento è assunta gaussaina. Se si effettuano 5 misurazioni, qual'è:
- La probabilità che il rapporto fra la varianza campionaria delle osservazioni $S^2$ e $\sigma^2$ superi $20\%$ quella reale? 
	- Poiché $\frac{(n-1)S^2}{\sigma^2}\sim \chi_{4}^2$, ovvero $\frac{S^2}{\sigma^2}\sim \frac{\chi^2_{4}}{(n-1)}$ allora $$p\left( \frac{S^2}{\sigma^2}>1.2 \right)=p(\chi_{4}^2>1.2*4=4.8)=0.3084$$
- La probabilità che il rapporto fra la varianza campionaria delle osservazioni $S^2$ e $\sigma^2$ sia compreso fra $0.80$ e $1.20$?
- $$p\left( 0.8\le \frac{S^2}{\sigma^2}\le 1.2 \right)=p(\chi_{4}^2<1.2 * 4=4.8)-p(\chi_{4}^2<0.8*4=3.2)=0.21$$
## Distribuzione $\overline X$ stimando $\sigma^2$ tramite $S^2$ per Popolazioni Gaussiane
Per la determinazione della distribuzione di $\overline X$ si possono non conoscere $\sigma^2$. Si vuole quindi conoscere la distribuzione di
$$\frac{\overline X-\mu}{\frac{S}{\sqrt{ n }}}$$
Poiché
$$\frac{Z}{\frac{\sqrt{ \chi^2_{m} }}{m}}\sim t_{m-1}$$
Allora moltiplicando per $\sqrt{ \frac{\sigma^2}{\sigma^2} \frac{n-1}{n-1} }$ si ottiene
$$
\frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}\sqrt{ \frac{\sigma^2}{S^2} \frac{n-1}{n-1} }= \frac{\frac{\overline X-\mu}{\frac{\sigma}{\sqrt{  n }}}}{\sqrt{ \frac{S^2(n-1)}{\sigma^2}  \frac{1}{n-1}}}= \frac{Z}{\sqrt{  \frac{\chi_{n-1}^2}{n-1} }}\sim t_{n-1}
$$