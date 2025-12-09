---
sticker: emoji//0037-fe0f-20e3
Order: "6"
---
## Introduzione
Si restringe l'attenzione all'inferenza parametrica, ovvero si assume di aver scelto un modello parametrico per descrivere l'incertezza sulle variabili osservate. L'obiettivo è quello di saper dire qualcosa circa la specifica distribuzione di probabilità che genere le osservazioni di una caratteristica in una popolazione. Questo significa saper dire qualcosa sui parametri $\theta$.

Scelta quindi una famiglia di variabili aleatorie parametriche $f(X|\theta)$, si raccoglie un campione di soggetti con incertezza sulla caratteristica $X$, regolata dalle v.a. $X_{1},X_{2},\ldots,X_{n}$ (tutte identiche). Si assume $X_{i}\perp \!\!\! \perp X_{j}|\theta$, $\forall i,j$ cioè la condizione di iid, questo significa assumere che tutta l'incertezza su $X$ è individuata dal modello e dalla conoscenza di $\theta$.
Gli obiettivi sono quindi:
- La valutazione puntale di $\theta$, *Maximum Likelihood Estimate, MLE*
- Valutazione intervallare di $\theta$, *cd* intervalli di confidenza
- Valutazione delle probabilità degli stimatori
---
## Stimatori
Uno stimatore è una funzione delle variabili aleatorie che generano le osservazioni, e quindi esso stesso è una variabile aleatoria.

> [!example]+ Esempio:
> $$\overline X = \sum^n_{i=1} \frac{X_{i}}{n}$$
> La v.a. media aritmetica delle variabili aleatorie $X_{i}$ è una variabile aleatoria che si origina dalla somma di altre, che rappresentano l'incertezza sulle osservazione divise per $n$.
> Qualora per fornire una stima della media di una caratteristica della popolazione si utilizzi la media aritmetica delle osservazioni del campione, diventa allora rilevante studiare la v.a. $\overline X$.
> $\overline X$ è una media aritmetica di osservazioni ed è una stima valutata sul campione disponibile.

## Funzione di Verosomiglianza
Si considera la v.a. congiunta delle $X_{i}$ che descrive l'incertezza del piano di osservazione
$$
f(X_{1},\ldots,X_{n}|\theta)= \prod^n_{i=1}f(X_{i}|\theta)
$$
Prima di effettuare le osservazioni, l'argomento della funzione sono le v.a. $X_{i}$. Dopo aver osservato, le $X_{i}$ si materializzano in $x_{i}$ e si può riconsiderare la funzione con argomento $\theta$.
Al variare di $\theta$:
$$
l(\theta;x_{1},\ldots,x_{n})= \prod^n_{i=1}f(x_{i}|\theta)
$$
diventa una funzione *punteggio* valutabile per tutti i possibili $\theta$.

> [!gray] MLE
> Il valore $\hat{\theta}$ che massimizza la funzione $l$ è la **Maximum Likelihood Estimate** (MLE) di $\theta$.

### MLE di $\theta$ di una Bernoulliana
Siano $x_{i}\in\{0,1\}$ osservazioni tratte da una $B(\pi)$. La funzione di verosimiglianza sarà:
$$\begin{align}  l(\pi;x_{1},\ldots,x_{n})&\propto \pi^{x_{1}}(1-\pi)^{1-x_{1}}\ldots \pi^{x_{n}}(1-\pi)^{1-x_{n}} \\
&\propto  \pi^{\sum_{i}x_{i}}(1-\pi)^{n-\sum_{i}x_{i}}\qquad x_{i}=0,1\quad \pi\in[0,1] \end{align}$$
passando poi ad una notazione logaritmica:
$$\begin{align}
&\log l(\pi;x_{1},\ldots,x_{n})= \sum_{i}x_{i}\log(\pi)+\left( n-\sum_{i}x_{i} \right)\log(1-\pi)\qquad \pi\in[0,1] \\
& \frac{d}{d\pi}\log l(\pi;x_{1},\ldots,x_{n})= \frac{1}{\pi}\sum^n_{i=1}x_{i}- \frac{1}{1-\pi}\left( n- \sum^n_{i=1}x_{i} \right)=0\to \hat{\pi}= \frac{\sum^n_{i=1}x_{i}}{n}
\end{align}$$
Quindi:
- La stima MLE di $\pi$ è$$\hat{\pi}= \frac{\sum^n_{i=1}x_{i}}{n}$$
- Lo stimatore di massima verosimiglianza di $\pi$ è$$\Pi = \frac{\sum^n_{i=1}X_{i}}{n}$$
*(la prima è numero, la seconda è una variabile aleatoria).*
### MLE di $\theta$ di una Poisson
Siano $x_{i}\in\{0,1,\ldots\}$ osservazioni tratte da una $Po(\lambda)$
$$\begin{align}
l(\lambda;x_{1},\ldots,x_{n})&= \prod^n_{i=1} \frac{\lambda^{x_{i}}e^{-\lambda}}{x_{i}!}= \frac{\lambda^{\sum_{i}x_{i}}e^{-n\lambda}}{\prod^n_{i=1}x_{i}} \\ 
\log l(\lambda;x_{1},\ldots,x_{n})&= \sum^n_{i=1}x_{i}\log\lambda-n\lambda-\log c \\
\frac{\delta \log l(\lambda;x_{1},\ldots,x_{n})}{\delta\lambda}&= \frac{\sum^n_{i=1}x_{i}}{\lambda}-n=0\to \hat{\lambda}= \frac{\sum^n_{i=1}x_{i}}{n}
\end{align}$$
### MLE di $\mu$ e $\sigma^2$ di una Normale
Siano $x_{i}\in R$ osservazioni tratte da una $N(\mu,\sigma^2)$.
$$\begin{align}
f(\mu,\sigma;x)&= \prod^n_{i=1} \frac{1}{\sqrt{ 2\pi }\sigma}\exp\left\{  - \frac{(x_{i}-\mu)^2}{2\sigma^2}  \right\}= \left( \frac{1}{2\pi} \right)^{\frac{n}{2}} \frac{1}{\sigma^n} \exp\left\{ -\frac{1}{2\sigma^2}\sum^n_{i=1}(x_{i}-\mu)^2 \right\} \\
\log l(\mu,\sigma;x)&= - \frac{n}{2}\log(2\pi)-n\log\sigma-\frac{1}{2\sigma^2} \sum^n_{i=1}(x_{i}-\mu)^2 \\
 \frac{\partial}{\partial \mu}\log l(\mu,\sigma;x)&= \frac{1}{\sigma^2}\sum^n_{i=1}(x_{i}-\mu)=0\to \hat{\mu}= \frac{\sum^n_{i=1}x_{i}}{n} \\
\frac{\partial}{\partial\sigma}\log l(\mu,\sigma;x)&=-\frac{n}{\sigma}+\frac{1}{\sigma^3}\sum^n_{i=1}(x_{i}-\mu)^2=0\to \hat\sigma^2= \frac{\sum^n_{i=1}(x_{i}-\hat{\mu})^2}{n}
\end{align}$$
Quindi:
- $$\hat{\mu}= \frac{\sum^n_{i=1}x_{i}}{n}\qquad \hat{\sigma}^2= \frac{\sum^n_{i=1}(x_{i}-\hat{\mu})^2}{n}$$
Lo stimatore MLE della varianza $\frac{\sum^n_{i=1}(X_{i}-\overline X)^2}{n}$ è detto un operatore distorto, nel senso che
$$
E\left( \frac{\sum^n_{i=1}(X_{i}-\mu)^2}{n} \right)\ne \sigma^2
$$
### Proprietà Asintotiche degli Stimatori MLE
Gli stimatori MLE sono
- Asintoticamente non distorti
- Asintoticamente consistenti: la varianza dello stimatore diminuisce al crescere di $n$
- Asintoticamente efficaci: la varianza dello stimatore è la minima rispetto ad altri stimatori al crescere di $n$
- Asintoticamente hanno distribuzione Normale
In sintesi, asintoticamente $$\Theta \sim N\left( \theta, \frac{1}{I(\theta)} \right)$$dove la quantità $I(\theta)$ è la derivata dall'espansione in serie di Taylor della distribuzione dello stimatore che a sua volta, essendo spesso una media, per il TLC è approssimata da una normale.
Per osservazioni condizionatamente indipendenti vale 
$$
I(\theta)= nE_{y}\left[ \left( \frac{\delta \log f(\theta;y)}{\delta \theta} \right)^2 \right]
$$
Alternativamente
$$
I(\theta)= -E_{y}\left( \frac{\delta^2\log l(\theta;y)}{\delta\theta^2} \right)=-nE_{y}\left( \frac{\delta^2\log f(\theta;y)}{\delta\theta^2} \right)
$$
### Varianza degli Stimatori MLE
$I(\theta)$è detta *Indormaione Attesa di Fisher* e corrisponde al reciproco della varianza della distribuzione normale che approssima la distribuzione dello stimatore.
Nel caso si conosca la distribuzione dello stimatore, $I(\theta)^{-1}$ coincide con la varianza della sua distribuzione.
Spesso $I(\theta)$ è approssimata attraverso l'informazione osservata di Fisher $I(\hat{\theta})$ che, invece di prendere il valore atteso rispetto ad $Y$, la valuta nel punto $\hat{\theta}_{MLE}$.

### Calcolo di $I(\theta)$ usando la Likelihood, Poisson

![[Pasted image 20251209162402.png|center|600]]

### Calcolo di $I(\theta)$ usando la Probabilità di una sola prova

![[Pasted image 20251209162449.png|center|600]]

---
## Stimatori
### Valutazione di Stimatori
 Sia $\mathbf{x} = \{x_{1},\ldots,x_{n}\}$ un campione tratto da una popolazione per una caratteristica $X\sim f(X|\theta)$. La v.a. congiunta da cui originano le osservazioni campionarie, $\mathbf{X}=(X_{1},\ldots,X_{n})$ è costituita da v.a. iid e $\theta$ è il parametro su cui fare inferenza.
 Uno stimatore è una v.a. funzione delle $\mathbf{X},\ T(\mathbf{X})$.

 Si deve determinare, per ogni possibile valore del parametro, qual'è la perdita *loss "l"* che subisce utilizzando la stima campionaria derivante dalla scelta dello stimatore, in generale:
 $$\begin{align}
 I(T(\mathbf{x}),\theta)&> 0\text{ se }T(\mathbf{x})\ne\theta \\
&=0\text{ se } T(\mathbf{x})=\theta
 \end{align}$$
 Per la valutazione degli stimatori si utilizza spesso la funzione quadratica di *loss*
 $$
 I(T(\mathbf{x}),\theta)=\begin{cases}
0 & \text{se }T(\mathbf{x})=\theta \\
(T(\mathbf{x})-\theta)^2 & \text{se }T(\mathbf{x})\ne\theta
\end{cases}
 $$
 Per un certo stimatore e per un certo valore di $\theta$, l'ammontare del danno dipenderà dalla stima del parametro per il campione osservato.
 Considerate nel loro insieme, le stime assumeranno valori con probabilità determinata dalla distribuzione di probabilità dello stimatore, una sintesi si ottiene considerando il valore atteso del danno (rispetto ala distribuzione delle $X$) denominato *rischio*.
 
 Se si è adottata una funzione di danno quadratica, il rischio è denominato *MSE* (Mean Square Error):
 $$
 MSE_{T}(\theta)=E_{\mathbf{x}}(T(\mathbf{ X})-\theta)^2= \int_{\mathbf{ X}}(T(\mathbf{ X})-\theta)^2f(T(\mathbf{ X})|\theta)\ d(\mathbf{X}) \quad \forall \theta$$

> [!example]+ Esempio:
>  Siano $X\sim Po(\lambda)$
>  Proposte di stimatori per l parametro $\lambda$ di una Poisson 
> 
> |         |      $T(X_{1},\ldots,X_{n})$      | Commento |
> | :-----: | :-------------------------------: | :------: |
> | $T_{1}$ | $$\frac{1}{n} \sum^n_{i=1}X_{i}$$ | Sensato  |
> | $T_{2}$ |             $$X_{1}$$             | Sprecone |
> | $T_{3}$ |               $$3$$               | Ridicolo |
> I commenti siano espressi ricordando che, in una Poisson, $\lambda$ coincide con la media della variabile.
Si immagina di  valutare il $MSE(\lambda)$ per $0\le\lambda\le 5$, allora usando gli stimatori 
$T_{1}$, $T_{2}$ e $T_{3}$ si ottiene:
>$$\begin{align}
MSE_{T_{1}}(\lambda)&=E(\overline X-\lambda)^2=Var(\overline X)= \frac{\lambda}{n} \\
MSE_{T_{2}}(\lambda)&= E(X_{1}-\lambda)^2=Var(X)= \lambda \\
MSE_{T_{3}}(\lambda)&=E(3-\lambda)^3= (3-\lambda)^2
\end{align}$$
**Osservazioni:**
>- $T_{3}$ è *observation free*
>- Se $\lambda_{1}\le\lambda\le\lambda_{2}$ il suo MSE sarebbe inferiore a quello degli altri due stimatori per $\lambda_{1,2}= \frac{6n+1}{n}\pm \frac{\sqrt{ \left( \frac{6n+1}{n} \right)^2 }-36}{2}$
>- $T_{1}$ ha rischio sempre inferiore a $T_{2}$
>
>![[Pasted image 20251209183614.png|center|400]]

### Bias
Sia il *bias* di $T(\cdot)$ se assunto come stimatore di $\theta$ definito da 
$$
b_{\theta}(d):= E[T(X)]-\theta
$$
Se il bias è nullo, si dice che $T(\cdot)$ è uno stimatore *corretto* o *non distorto*.
Fra gli stimatori corretti esiste la possibilità di individuare quello a varianza minima, $\forall \theta$.
### Proprietà
Se $X\sim f(X|\theta)$ e $E(X)=\theta$ allora:

1. $T(X)=\sum^n_{i=1}\lambda_{i}X_{i}$ è corretto per $\theta$ se $\sum^n_{i=1}\lambda_{i}=1$ $$E\left[ \sum^n_{i=1}\lambda_{i}X_{o} \right]= \sum^n_{i=1}\lambda_{i}E[X_{i}]=\sum^n_{i=1}\lambda_{i}\theta=\theta$$
2. Se $T(X)$ è uno stimatore corretto, allora il suo errore quadratico medio è $$\begin{align}
MSE_{T}(\theta)&= E_{X}[(T(X)-\theta)^2]=E_{X}[(T(X)-E[T])^2]=Var[T(X)]
\end{align}$$Quindi l'errore quadratico medio di uno stimatore corretto è pari alla sua varianza
### Stimatori Distorti
Si determina il MSE per uno stimatore distorto
$$
\begin{align}
MSE_{T}(\theta)&= E[(T-\theta)^2] \\
&=E[(T-E[T]+E[T]-\theta)^2] \\
&= E[(T-E[T]^2)]+2(E[T]-\theta)E[(T-E[T])+(E[T]-\theta)^2] \\
&=E[(T-E[T])^2]+2(E[T]-\theta)[E[T]-E[T]]+E[(E[T]-\theta)^2] \\
&=Var[T]+0+E[b_{\theta}(T)^2] \\
&=Var[T]+b_{\theta}(T)^2
\end{align}
$$
con $b_{\theta}(T)^2=(E[T]-\theta)^2$

> [!example]+ Esempio:
> Un'urna contiene due palle con impresso un numero ciascuna $(X)$. Si sa che il più piccolo dei due numeri vale $\theta$ ed è la metà dell'altro. Si vuole stimare il valore più piccolo dei $\theta$ sulla base di una singola estrazione di $X$, essendo
> $$
> Pr(X=\theta)=Pr(X=2\theta)=\frac{1}{2}
> $$
> Considerando $T_{1}=X$ e $T_{2}=\frac{2}{3}X$, allora
> $$
> \begin{align}
> E(T_{1})&=E(X)=\frac{1}{2}\theta+\frac{1}{2} 2\theta=\frac{3}{2}\theta&\text{distorto}& \\
> E(T_{2})&=E\left( \frac{2}{3}X \right)=\frac{2}{3}E(X)=\frac{2}{3} \frac{3}{2}\theta=\theta &\text{corretto}&
> \end{align}
> $$
> Il primo stimatore, seppur distorto, fornisce il valore esatto del parametro una volta su due, il secondo invece se esce il numero più piccolo dirà che $\theta$ vale $\frac{2}{3}\theta$, se esce il più grande valuterà $\theta$ pari a $\frac{4}{3}\theta$.
> Si valutano gli MSE:
> $$
> \begin{align}
> MSE_{T_{1}}(\theta)&= \frac{1}{2}\left( \theta-\frac{3}{2}\theta \right)^2+\frac{1}{2}\left( 2\theta-\frac{3}{2}\theta \right)^2+ \left( \frac{1}{2}\theta \right)^2= \frac{1}{2}\theta^2 \\
> MSE_{T_{2}}(\theta)&= \frac{1}{2}\left( \frac{2}{3}\theta-\theta \right)^2+\frac{1}{2}\left( \frac{2}{3}2\theta-\theta \right)^2=\frac{1}{9}\theta^2
> \end{align}
> $$
> ![[Pasted image 20251209185730.png|center|400]]
> 
> Cioè $T_{2}$ è sempre migliore di $T_{1}$ in termini di MSE.

---
## Intervalli di Confidenza per $\mu$, $X\sim N(\mu,\sigma)$
Si vuole dare un intervallo di valori su $\theta$ al $95\%$ invece che una stima puntuale.
Si sa che: $\overline X\sim N\left( \mu, \frac{\sigma^2}{n} \right)$
$$\begin{gather}
P\left( -1.96< \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}<1.96 \right)\approx 0.95 \\
P\left( -1.96 \frac{\sigma}{\sqrt{ n }}< \overline X -\mu < 1.96 \frac{\sigma}{\sqrt{ n }}\right)\approx 0.95 \\
P\left( 1.96 \frac{\sigma}{\sqrt{ n }}>\mu-\overline X>-1.96 \frac{\sigma}{\sqrt{  n }} \right) \approx 0.95 \\
P\left( \overline X-1.96 \frac{\sigma}{\sqrt{ n }}<\mu<\overline X +1.96 \frac{\sigma}{\sqrt{ n }}\right)\approx 0.95
\end{gather}$$
Le v.a. $\overline X$ producono intervalli (tramite estrazioni campionarie) che includono $\mu$ con probabilità $0.95$.
![[Pasted image 20251209190349.png|center|400]]

Il campione genera un solo intervallo di confidenza al $95\%$ del parametro $\mu$.

È nell'intervallo
$$\left[ \overline x-1.96 \frac{\sigma}{\sqrt{ n }},\ \overline x+1.96 \frac{\sigma}{\sqrt{  n }} \right]$$
con che probabilità $0.95$ è contenuto in $\mu$?
$\to$ No, non si può solo dire che se si fossero generati molti campioni, questi al $95\%$ avrebbero prodotto un CI che conteneva $\mu$. Che l'unico intervallo a disposizione sia uno di quelli "verdi" o "neri" non si può sapere.

> [!example]+ Esempio
> Si pesa un oggetto 5 volte:
> 
> | $x$ | 3.142 | 3.163 | 3.155 | 3.150 | 3.141 |
> | --- | ----- | ----- | ----- | ----- | ----- |
> 
> $$\overline x=3.1502$$
> Si ritiene che il peso osservato, per la presenza di un errore di misura, sia una v.a.a $X\sim N(\mu,\sigma=0.01)$.
> Si deterimina il CI:
> $$
> CI:\ \overline x\pm 1.96* \frac{0.01}{\sqrt{ 5 }}= [3.1493,\ 3.1510]
> $$
> 

#### Determinazione della Numerosità del Campione
Ci si può assegnare il compito di determinare la numerosità campionaria che determini un intervallo di confidenza di ampiezza e livello di confidenza prefissati, poiché
$$
\begin{align}
A_{CI}&= 2 Z_{\frac{\sigma}{2}} \frac{\sigma}{\sqrt{ n }} \\
n&=\left( \frac{2 Z_{\frac{\sigma}{2}}\sigma}{A_{CI}} \right)^2
\end{align}
$$

> [!example]+ Esempio:
> Nell'esempio precedente. se si avesse preteso $A_{CI}=0.001$ (estremamente piccolo) e livello di confidenza $1-\alpha=0.95$, allora
> $$
> n=\left( \frac{2*1.96*0.01}{0.01} \right)^2=54.32^2\approx 1536
> $$

#### CI per $\mu$ della Normale, non noto $\sigma$
Si ricorda che si è definita la va. $t-$student:
$$
\frac{Z}{\sqrt{ \frac{\chi^2_{n-1}}{n-1} }}\sim t_{n-1}
$$
e che 
$$
(n-1) \frac{S^2}{\sigma^2}\sim \chi^2_{n-1}
$$
Non disponendo di $\sigma^2$, si usa lo stimatore corretto $S^2= \frac{\sum^n_{i=1}(X_{i}-\overline X)^2}{n-1}$
$$
\begin{align}
\frac{\overline X-\mu}{\frac{S}{\sqrt{ n }}}&= \frac{\overline X-\mu}{\frac{S}{\sqrt{ n }}}\sqrt{  \frac{\sigma^2(n-1)}{\sigma^2(n-1)} } \\
&= \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}\sqrt{ \frac{\sigma^2(n-1)}{S^2(n-1)} } \\
&= \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{  n }}} / \sqrt{  \frac{S^2(n-1)}{\sigma^2(n-1)} } \\
&= N(0,1) / \sqrt{  \frac{\chi^2_{n-1}}{n-1} }\sim t_{n-1}
\end{align}
$$
Quindi 
$$P\left( -t_{\frac{\alpha}{2},n-1}< \frac{\overline X-\mu}{\frac{S}{\sqrt{ n }}} < t_{\frac{\alpha}{2},n-1} \right)=1-\alpha$$
o equivalentemente
$$
P\left( \overline X-t_{\frac{\alpha}{2},n-1} \frac{S}{\sqrt{ n }}< \mu < \overline X+t_{\frac{\alpha}{2},n-1} \frac{S}{\sqrt{ n }} \right)=1-\alpha
$$
Osservati $\overline X=\overline x$ e $S=s$, al livello di confidenza $1-\alpha$ 
$$
\mu\in\left( \overline x- t_{\frac{\alpha}{2},n-1} \frac{s}{\sqrt{ n }},\ \overline x+ t_{\frac{\alpha}{2},n-1} \frac{s}{\sqrt{ n }} \right)
$$
Cioè $\mu$ risulterà incluso con probabilità $1-\alpha$ in tutti gli intervalli che al variare del campione venissero prodotti.

Riprendendo l'esempio delle misure con errore:
- Primo calcolo $s=0.00920326$
- Si guarda poi sulle tavole $t_{0.025,4}=-2.776$, quindi si determina $$\overline x\pm t_{\frac{\alpha}{2},n-1} \frac{s}{\sqrt{ n }}=[3.1387,3.1616]$$
## Intervalli di Predizione
L'obiettivo è dire qualcosa circa la previsione sul prossimo valore di $X$ osservato dopo aver osservato $x_{1},\ldots,x_{n}$.
Si suppone $X\sim N(\mu,\sigma)$, $\mu$ e $\sigma$ parametri incogniti, sarà quindi
$$
\overline X\sim N\left( \mu, \frac{\sigma^2}{n} \right)\qquad \text{e}\qquad X_{n+1}\sim N(\mu,\sigma^2)
$$
Quindi:
$$
X_{n+1}-\overline X\sim N\left( 0,\sigma^2+\frac{\sigma^2}{2} \right)
$$
quindi
$$
\frac{X_{n+1}-\overline X}{\sigma \sqrt{ 1+ \frac{1}{n} }}\sim N(0,1)
$$
Non conoscendo $\sigma^2$, lo si sostituisce con $S^2$ e moltiplicando con $\sqrt{ \frac{\sigma^2(n-1)}{\sigma^2(n-1)} }$, il che produce 
$$
\frac{X_{n+1}-\overline X}{S\sqrt{ 1 + \frac{1}{n} }}\sim t_{n-1}
$$
$$
\begin{align}
1-\alpha&= P\left( - t_{\frac{\alpha}{2},n-2}< \frac{X_{n+1}-\overline X_{n}}{S_{n}\sqrt{ 1+ \frac{1}{n} }}<t_{\frac{\alpha}{2},n-1} \right) \\
&= P\left( \overline X_{n}-t_{\frac{\sigma}{2},n-1}S_{n}\sqrt{ 1+ \frac{1}{n} }< X_{n+1}< \overline X_{n}+t_{\frac{\alpha}{2},n-1} S_{n}\sqrt{  1+ \frac{1}{n} } \right)
\end{align}
$$
Passando ai valori campionari, con confidenza $1-\alpha$, l'intervallo
$$
\left( \overline x_{n}-t_{\frac{\alpha}{2},n-1}s_{n} \sqrt{ 1+ \frac{1}{n} },\ \overline x_{n}+t_{\frac{\alpha}{2},n_{1}}s_{n}\sqrt{  1+ \frac{1}{n} } \right)
$$
conterrà il valore da prevedere nell'$(1-\alpha)\%$ dei possibili intervalli che si sarebbero potuti derivare da tutti i possibili campioni.
## Intervalli di Confidenza per la Varianza