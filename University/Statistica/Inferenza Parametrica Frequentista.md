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
## Valutazione degli Stimatori
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
 