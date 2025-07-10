---
sticker: emoji//0037-fe0f-20e3
---
- [[#Elementi Comuni fra Scuola Frequentista e Bayesiana|Elementi Comuni fra Scuola Frequentista e Bayesiana]]
- [[#Inferenza Statistica Bayesiana|Inferenza Statistica Bayesiana]]
	- [[#Inferenza Statistica Bayesiana#Elementi Fondamentali per Osservazioni iid|Elementi Fondamentali per Osservazioni iid]]
	- [[#Inferenza Statistica Bayesiana#Distribuzioni a Priori Coniugate|Distribuzioni a Priori Coniugate]]
- [[#Teorema di Fattorizzazione di Neyman Fisher|Teorema di Fattorizzazione di Neyman Fisher]]
	- [[#Teorema di Fattorizzazione di Neyman Fisher#Utilizzo Bayesiano e Distribuzione a Priori Coniugate|Utilizzo Bayesiano e Distribuzione a Priori Coniugate]]
	- [[#Teorema di Fattorizzazione di Neyman Fisher#Modello Binomiale|Modello Binomiale]]
	- [[#Teorema di Fattorizzazione di Neyman Fisher#Esponenziale|Esponenziale]]
	- [[#Teorema di Fattorizzazione di Neyman Fisher#Modello Uniforme|Modello Uniforme]]
- [[#Dalla Indipendenza Condizionata alla Scalabilità|Dalla Indipendenza Condizionata alla Scalabilità]]
- [[#Sintesi Intervallare: Credible Intervals|Sintesi Intervallare: Credible Intervals]]
	- [[#Sintesi Intervallare: Credible Intervals#Regioni HDP: High Posterior Density vs Credible Intervals|Regioni HDP: High Posterior Density vs Credible Intervals]]
- [[#Distribuzioni Predittive|Distribuzioni Predittive]]
- [[#Marginal Likelihood|Marginal Likelihood]]
	- [[#Marginal Likelihood#Caso Binomiale|Caso Binomiale]]

## Elementi Comuni fra Scuola Frequentista e Bayesiana
Lo schema di base dell'inferenza statistica è basato sul modello del campionamento ripetuto. Si assume cioè di avere a disposizione $n$ unità statistiche estratte in modo casuale (con rimpiazzo) da una popolazione, considerate rispetto ad una caratteristica $Z$.
Si assume inoltre che l'incertezza circa le determinazioni di $Z$ nella popolazione è interamente governata da un modello parametrico $$Z\sim p(Z|\theta),\ \theta\in \Theta$$
Le variabili aleatorie $Z_{1},\ldots, Z_{n}$ sono così assunte essere iid, quindi condizionatamente indipendenti dato il modello e i suoi parametri.
L'obiettivo è dire qualcosa circa i $\theta$ dopo avere osservato i dati campionari.

## Inferenza Statistica Bayesiana
### Elementi Fondamentali per Osservazioni iid
 Si considera un generico modello delle osservazioni
 $$
 (Z,p(Z|\theta),\ \theta\in \Theta)
 $$
 Condizionatamente al parametro, il processo di osservazione è descritto da 
 $$
 \left( Z^{(n)},\ \prod^n_{_{i=1}}p(z_{i}|\theta), \ \theta\in \Theta \right)
 $$
 L'approccio Bayesiano all'inferenza aggiunge un elemento, ovvero l'incertezza sui parametri
 $$\begin{gather}
 p(\theta) \\
\mathcal F=\{p(\theta):\ \theta\in \Theta\}
 \end{gather}$$
 Il modello sulle osservazioni e quello sui parametri formano il modello Bayesiano.
### Distribuzioni a Priori Coniugate
Sia $\mathcal F$ la classe delle distribuzioni di probabilità a priori su $\theta$ avente come cardinalità quella del parametro o il prodotto delle cardinalità dei parametri se il modello è multiparametrico.
Sia afferma che $\mathcal F$ è coniugata a $p(Z|\theta)$ se 
$$
p(\theta|\mathbf{z})= \frac{p(\mathbf{z}|\theta)p(\theta)}{\underset{p(\mathbf{z})}{\int_{\Theta}p(\mathbf{z}|\theta)p(\theta)\ d\theta}}
$$
è ancora un elemento di $\mathcal F$
## Teorema di Fattorizzazione di Neyman Fisher
Si definiscono $Z=Z_{1},\ldots, Z_{n}$ le variabili aleatorie che governano l'incertezza sull'osservazione campionaria $z=z_{1},\ldots,z_{n}$. Si considera la probabilità congiunta di $z_{1},\ldots,z_{n}$ dato $\theta$
$$p(\mathbf{z}|\theta)=p(z_{1},\ldots,z_{n}|\theta)$$

> [!gray] Teorema di Fattorizzazione
> Se
> $$p(\mathbf{z}|\theta)=g(t(\mathbf{z}),n,\theta)\phi(\mathbf{ z})$$
> allora $t(\mathbf{ z})$ è detta *statistica sufficiente* per $\theta$ e cale che
> $$
> z \perp\!\!\!\perp \theta|t(z)
> $$
> Cioè la conoscenza della statistica sufficiente $t(\mathbf{ z})$ rende la distribuzione di $Z$ indipendente da $\theta$
> 
> **Dimostrazione:**
> Se l'assunto è vero
> $$p(t(\mathbf{ z})|\theta)=\sum_{\mathcal Z^n:t=t(\mathbf{z})}= \sum_{\mathcal Z^n:t=t(\mathbf{z})}g(t(\mathbf{z}),n,\theta)\phi(\mathbf{z})=g(t(\mathbf{z}),n,\theta)\sum_{\mathbf{ z}\in \mathcal Z^n:t=t(\mathbf{z})}\phi(\mathbf{z})$$
> 

La distribuzione condizionata 
$$\begin{align}
p(\mathbf{ z}|t(\mathbf{z}),\theta)&= \frac{p(\mathbf{z},t(\mathbf{z})|\theta)}{p(t(\mathbf{ z}|\theta))}= \frac{p(\mathbf{z}|\theta)}{p(t(\mathbf{z})|\theta)}= \frac{g(t(\mathbf{z}),n,\theta)\phi(\mathbf{ z})}{g(t(\mathbf{ z}),n,\theta)\sum_{\mathbf{z}\in\mathcal Z^n\vartheta=t(\mathbf{ z})}\phi(\mathbf{ z})}= \\
&= \frac{\phi(\mathbf{z})}{\sum_{\mathbf{z}\in \mathcal Z^n\vartheta=t(\mathbf{ z})}\phi(\mathbf{ z})}\quad\perp\!\!\!\perp \theta 
\end{align}$$
Caso Binomiale:
- Sia $z_{i}=\{0,1\}$ $\forall i$, $t=t(\mathbf{z})=\sum^n_{i=1}z_{i}$  $$p(\mathbf{z}|t,\theta)= \frac{p(\mathbf{ z}|\theta)}{p(t|\theta)}= \frac{\theta^t(1-\theta)^{n-t}}{\begin{pmatrix}
n \\ t
\end{pmatrix}\theta^t(1-\theta)^{n-t}}= \frac{1}{\begin{pmatrix}
n \\ t
\end{pmatrix}}$$
### Utilizzo Bayesiano e Distribuzione a Priori Coniugate
Inferenza su $\theta$ tramite $t=t(\mathbf{ z})$
$$
p(\theta|z_{1},\ldots,z_{n})= \frac{\phi(z_{1},\ldots,z_{n})g(t,n,\theta)p(\theta)}{\phi(z_{1},\ldots,z_{n})\int_{\theta}g(t,n,\theta)p(\theta)\ d\theta}\propto g(t,n,\theta)p(\theta)
$$
Per questo motivo le statistiche sufficienti sono conosciute anche come *riassunti esaustivi*. 
Si immagina adesso di avere un gruppo di altre $m$ osservazioni $\mathbf{z}'=z_{n+1},\ldots, z_{n+m}$ essendo $s=t(Z_{n+1},\ldots,z_{n+m})$. Poiché le v.a. relative alle osservazioni sono condizionatamente indipendenti
$$\begin{gather}
p(\mathbf{ z},\mathbf{z}'|\theta)=\prod^n_{i=1}p(z_{i}|\theta)\prod^m_{i=1}p(z_{i}|\theta)=\prod^{m+n}_{i=n+1}p(z_{i}|\theta) \\
\propto g(t(z_{1},\ldots,z_{n},z_{n+1},\ldots,z_{n+m}),n+m,\theta) \\
\propto g(t(z_{1},\ldots,z_{n}),n,\theta)g(t(z_{1}',\ldots, z_{m}'),m,\theta) \\
\propto g(t,n,\theta)g(s,m,\theta)
\end{gather}$$
Quindi, interpretati $s$ e $m$ come iperparametri di una distribuzione a priori 
$$
g(t(z_{1},\ldots,z_{n},z_{1}',\ldots,z'_{m}),n+m,\theta)=\underset{\text{likelihood}}{g(t,n,\theta)}\underset{\text{prior}}{g(s,m,\theta)}
$$
Allora, se la a priori sui parametri ha lo stesso $kernel \ g(\cdot)$ della likelihod e la $g(\cdot)$ è esprimibile secondo il teorema di fattorizzazione, la posteriori di $\theta$ risulta coniugata.
In pratica, scritta la likelihood nella forma che soddisfa il teorema di fattorizzazione risulta conveniente identificare, come a priori per $\theta$, una variabile aleatoria che abbia il medesimo kernel.
### Modello Binomiale
1. Likelihood $$\mathscr l(\theta;x)\propto \theta^x(1-\theta)^{n-x}, \quad \theta\in [0,1]$$
2. Se si sceglie come a priori su $\theta$ una $Beta(\alpha,\theta)$, ovvero: $$p(\theta|\alpha,\beta)=\frac{\lceil (\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}\theta^{\alpha-1}(1-\theta)^{\beta-1}\quad \alpha,\beta>0,\ \theta\in[0,1] $$
3. $$\begin{align} p(\theta|x,n,\alpha,\beta)&\propto \theta^x(1-\theta)^{n-x}\theta^{\alpha-1}(1-\theta)^{\beta-1} \\
&\propto \theta^{x+\alpha-1}(1-\theta)^{n-x+\beta-1} \\
&\sim Beta(x+\alpha,n-x+\beta) \end{align}$$

> [!example]+ Esempio:
> Una medicina è testata su $n=21$ pazienti ed è stata trovata efficace su $x=18$. Qual'è la probabilità $\theta$ che la medicina sia efficace su un paziente?
> - Modello delle osservazioni $X\sim Bin(\theta;n)$
> - $\theta$ è la probabilità di successo della medicina su un paziente
> - La likelihood è $$\mathscr l(\theta;x)\propto \theta^{18}(1-\theta)^3$$
> - Il prior è $$Beta(\theta|\alpha,\beta)= \frac{\lceil (\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}\theta^{\alpha-1}(1-\theta)^{\beta-1}$$
> - Bayes: se si assume come una a priori una $Beta(1,1)=U(0,1)$ $$p(\theta|x,n)\propto l(\theta;x)p(\theta)\propto^{18+1-1}(1-\theta)^{3+1-1}\to Beta(19,4)$$
> - $E(\theta,x,n)=\frac{19}{19+4}=0.8260$
> - In generale  $$\begin{gather} \begin{aligned}
> p(\theta|x,n,\alpha,\beta)&\propto \theta^x(1-\theta)^{n-x}\theta^{\alpha-1}(1-\theta)^{\beta-1} \\
> &\sim Beta(x+\alpha,n-x+\beta) \end{aligned} \\
> \begin{aligned}
> p(x=1)&=\int_{\theta}p(x=1|\theta) \frac{\lceil (\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}\theta^{\alpha-1}(1-\theta)^{\beta-1}\ d\theta \\
> &=\int_{\theta} \theta\frac{\lceil(\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}\theta^{\alpha-1}(1-\theta)^{\beta-1}\ d\theta \\
> &=\int_{\theta} \frac{\lceil(\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)}\theta^\alpha(1-\theta)^{\beta-1}\ d\theta \\
> &= \frac{\lceil(\alpha+\beta)}{\lceil(\alpha)\lceil(\beta)} \frac{\lceil(\alpha+1)\lceil(\beta)}{\lceil(\alpha+1+\beta)}= \frac{\alpha}{\alpha+\beta}\end{aligned}\end{gather}$$

### Esponenziale
Modello delle osservazioni: esponenziale
$$\begin{gather}
p(z|\theta)=\theta \exp(-\theta z) \\
\mathscr l(\theta;\mathbf{ z})\propto \theta^n\exp\left( -\theta \sum z_{i} \right)
\end{gather}$$
A priori: gamma $$p(\theta)= \frac{\lambda_{2}^{\lambda_{1}}}{\lceil(\lambda_{1})}\theta^{\lambda_{1}-1}\exp(-\theta\lambda_{2})$$
A posteriori: gamma $$\begin{align}
p(\theta|\mathbf{ z})&\propto \theta^{\lambda_{1}+n-1}\exp\left( -\theta\left( \sum z_{i}+\lambda_{2} \right) \right) \\
&=Ga\left( \lambda_{1}^*=\lambda_{1}+n,\ \lambda_{2}^*=\sum z_{i+\lambda_{2}} \right)
\end{align}$$
Predittiva a posteriori: Sia sempre $\lambda_{1}^*=\lambda_{1}+n$, $\lambda_{2}^*=\sum z_{i}+\lambda_{2}$
$$\begin{align}
p(Z_{n+1}=z_{n+1}|\mathbf{z})&\propto \int \theta \exp(-\theta_{z_{n+1}})\theta^{\lambda_{1}^*}\exp(-\theta\lambda_{2}^*)\ d\theta \\
&= \frac{{\lambda_{2}^*}^{\lambda_{1}^*}}{\lceil(\lambda_{1}^*)}\int \theta^{\lambda_{1}^*+1}\exp(-\theta(\lambda_{2}^*+z_{n+1}))\ d\theta \\
&= \frac{{\lambda_{2}^*}^{\lambda_{1}^*}}{\lceil(\lambda_{1}^*)} \frac{\lceil(\lambda_{1}^*+1)}{(\lambda_{2}^*+z_{n+1})^{\lambda_{1}^*+1}}= Gg(\lambda_{1}^*,\lambda_{2}^*,1)
\end{align}$$
Marginal likelihood
$$\begin{align}
p(\mathbf{z}|\lambda_{1},\lambda_{2})&= \int_{\theta} \frac{\lambda^{\lambda^1}}{\lceil(\lambda_{1})}\theta^{\lambda_{1}-1}\exp(-\theta\lambda_{2})\theta^n\exp\left( -\theta \sum z_{i} \right)\ d\theta \\
&= \frac{\lambda_{2}^{\lambda_{1}}}{\lceil(\lambda_{1})} \frac{\lceil(\lambda_{1}+n)}{\left( \lambda_{2}+\sum z_{i} \right)^{\lambda_{1}+n}}
\end{align}$$
### Modello Uniforme
$$\begin{align} p(z|\theta)&= \frac{1}{\theta}I_{[0,\theta]}(z)  \\
I(\theta;\mathbf{ z})&= \left( \frac{1}{\theta} \right)^n \prod^n_{i=1}I_{[0,1]} \left( \frac{z_{i}}{\theta} \right) \\
&= \left( \frac{1}{\theta} \right)^n I_{[0,1]} \left( \frac{z_{(n)}}{\theta} \right) \\
&=\left( \frac{1}{\theta} \right)^2 I[1,\infty] \left( \frac{\theta}{z_{(n)}} \right) \\
&= \left( \frac{1}{\theta} \right)^n I_{[z_{(n)},\infty]}(\theta)
\end{align}$$
Si assume a priori per $\theta$ una $Pareto(z_{0},\alpha)$

![[Pasted image 20250709181937.png|center|400]]

Si ottiene come a posteriori ancora una Pareto
$$\begin{align} 
p(\theta|z_{0},\alpha)&=\frac{\alpha}{z_{0}}\left( \frac{z_{0}}{\theta} \right)^{\alpha+1}I_{[z_{0},\infty]}(\theta) \\
p(\theta|\mathbf{ z})&\propto \left( \frac{1}{\theta} \right)^{\alpha+n+1}I_{[\max(z_{(n),z_{0}}), \infty]}(\theta)
\end{align}$$
Cioè una $Pa(\alpha+n,\max(z_{(n)},z_{0}))$.
Predittiva a priori:
$$
(z,\theta)=p(z|\theta)p(\theta)= \frac{\alpha z_{0}^\alpha}{\theta^{\alpha+1}} \frac{1}{\theta}= \frac{\alpha z_{0}^\alpha}{\theta^{\alpha+2}}
$$
Per
$$
p(z)=\int_{0}^{z_{0}} \frac{\alpha z_{0}^\alpha}{\theta^{\alpha+2}}\ d\alpha = \frac{\alpha}{(\alpha+1)z_{0}}\quad se \ z\le z_{0}
$$
Per $z_{0}<z<\infty$ si ottiene invece
$$
p(z)=\int_{z}^\infty \frac{\alpha z_{0}^\alpha}{\theta^{\alpha+2}}\ d\theta= \frac{\alpha z_{0}^\alpha}{(\alpha+1)z^{\alpha+1}}
$$
## Dalla Indipendenza Condizionata alla Scalabilità
La scalabilità è la forma di indipendenza che si instaura fra le v.a. osservabili una volta marginalizzata la loro congiunta condizionata facendo uso dell'incertezza parametro.
$$
p(N_{1},\ldots,N_{n})=\int_{\theta}p(N_{1},\ldots,N_{n}|\theta)p(\theta)\ d\theta
$$

> [!example]+ Esempio:
> Sia $N$ la v.a. numero di arrivi in una unità di tempo
> $$
> N\sim Po(\theta)= \frac{\theta^m\exp(-\theta)}{m!}\quad m=0,1,\ldots
> $$
> Si verifica immediatamente che la a priori congiunta è 
> $$
> \theta\sim Ga(\alpha,\beta)= \frac{\beta^\alpha}{\Gamma(\alpha)}\theta^{\alpha-1}e^{-\beta}\quad \theta,\alpha,\beta>0
> $$
> La marginale (predittiva) di $N$ risulta essere una Binomiale negativa
> $$\begin{align}
> P(N_{h}=m)&=\int^\infty_{0} \frac{\theta^me^{-\theta}}{m!}
>  \frac{\beta^\alpha}{\Gamma(\alpha)}\theta^{\alpha-1}e^{\beta\theta} \\
> &= \frac{\beta^\alpha}{\Gamma(\alpha)m!}\int^\infty_{0}\theta^{m+\alpha-1}e^{-(\beta+1)^\theta}\ d\theta \\
> &=\frac{\beta^\alpha}{\Gamma(\alpha)m!}\cdot \frac{\Gamma(\alpha+m)}{(\beta+1)^{\alpha+m}}=\begin{pmatrix}
> \alpha+m-1 \\ \alpha-1
> \end{pmatrix} \left( \frac{\beta}{\beta+1} \right)^\alpha\left( \frac{1}{\beta+1} \right)^m\end{align}$$
> 

> [!example]+ Esempio: Congiunta non Condizionata
> $$\begin{align}
> P(N_{h}=m,N_{k}=k)&= \int_{0}^\infty \frac{\theta^me^{-\theta}}{m!} \frac{\theta^ke^{-\theta}}{k!}\cdot \frac{\beta^\alpha}{\Gamma(\alpha)}\theta^{\alpha-1}e^{\beta\theta}\ d\theta \\
> &= \frac{\beta^\alpha}{\Gamma(\alpha)m!k!}\int_{0}^\infty \theta^{m+k+\alpha-1}e^{-(\beta+2)\theta}\ d\theta \\
> &= \frac{\beta^\alpha}{\Gamma(\alpha)m!k!} \frac{\Gamma(m+k+\alpha)}{(\beta+2)^{m+k+\alpha}} \\
> &\ne \frac{\beta^\alpha}{\Gamma(\alpha)m!}\cdot \frac{\Gamma(\alpha+m)}{(\beta+1)^{\alpha+m}} \frac{\beta^\alpha}{\Gamma(\alpha)m!}\cdot \frac{\Gamma(\alpha+k)}{(\beta+1)^{\alpha+k}} \\
> &= \frac{\beta^{2\alpha}}{\Gamma(\alpha)^2m!k!} \frac{\Gamma(\alpha+m)\Gamma(\alpha+k)}{(\beta+1)^{2\alpha+m+k}}
> \end{align}$$

La congiunta marginalizzata rispetto al parametro non è uguale al prodotto fra le marginali, quindi le v.a. non sono più indipendenti se non si conosce il valore del parametro. Questa forma di dipendenza è chiamata **Scalabilità** in quanto le differenze nella sequenze delle osservazioni non alterano la congiunta: le osservazioni sono quindi scambiabili (di posizione).

## Sintesi Intervallare: Credible Intervals
Si impone
$$p(a\le\theta\le b)=1-\alpha$$
Si cercano i quantili della distribuzione con  probabilità che lascino a destra e a sinistra una probabilità ad $\frac{\alpha}{2}$, ricorda gli intervalli di confidenza.
### Regioni HDP: High Posterior Density vs Credible Intervals
- La regione $(1-\alpha)\%$ HDP è quella che sottende con probabilità $(1-\alpha)$ densità maggiori uguali o maggiori di quelle fuori dalla regione
- Le regioni HDP hanno il volume minore
- HDP $\overline =$intervalli di credibilità per distribuzioni concave unimodali e simmetriche
- Per la loro individuazione si ricorre a programmi iterativi-simulativi
- Per distribuzioni multimodali l'HDP tende a individuare regioni disgiunte
- In R, il package che calcola è HDInterval

> [!example]+ Esempio:
> Sia il risultato dell'inferenza una $B\eta(19,4)$ e $\alpha=0.05$, il credile interval è $\theta\in[0.6508,0.9481]$ (rosso, ampiezza $0.297$), l'HDP è $\theta\in(0.671,0.964)$ (verde, ampiezza $0.293$)
> 
> ![[Pasted image 20250709184856.png|center|350]]

## Distribuzioni Predittive
L'obiettivo è valutare l'incertezza circa la realizzazione di una ulteriore osservazione rispetto alle $n$ osservate:
$$
p(x_{n+1}|x)=\int_{\theta\in\Theta}p(x_{n+1}|\theta)p(\theta|x)\ d\theta
$$
Le predittive generano nuove classi di distribuzioni non indicate nei parametri e definite in $\mathcal X$. Esse forniscono la probabilità che la $n+1$ esima osservazione assuma valori puntuali o per intervallo nel suo campione di definizione.

Nel caso binomiale, dopo aver osservato $s$ successi su $n$ prove, la probabilità di osservare una $n+1$ esima osservazione sarà
$$\begin{align}
Pr(x_{n+1}|s,n)&= \int_{\theta\in \Theta}Pr(x_{n+1}=1|\theta)Pr(\theta|s,n)\ d\theta \\
&= \int_{\theta\in \Theta}\theta  \frac{\Gamma(\alpha+\beta+n)}{\Gamma(\alpha+s)\Gamma(\beta+n-s)}\theta^{\alpha+s-1}(1-\theta)^{\beta+n-s-1}\ d\theta \\
&=\frac{\Gamma(\alpha+\beta+n)}{\Gamma(\alpha+s)\Gamma(\beta+n-s)}\int_{\theta\in \Theta} \theta^{\alpha+s}(1-\theta)^{\beta+n-s-1}\ d\theta \\
&=\frac{\Gamma(\alpha+\beta+n)}{\Gamma(\alpha+s)\Gamma(\beta+n-s) \Gamma} \frac{\Gamma(\alpha+s+1)\Gamma(\beta+n-s)}{\Gamma(\alpha+\beta+n+1)}
\end{align}$$
La predittiva è chiamata Beta-Binomiale la cui forma generale è
$$Bb(x|\alpha,\beta ,n)= \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)\Gamma(\alpha+\beta+n)}\begin{pmatrix}
n \\ x
\end{pmatrix}\Gamma(\alpha+x)\Gamma(\beta+n-x)$$
Nel caso predittivo binomiale, $n=1$ e $x=\{0,1\}$
- Se la a priori su $\theta$ fosse stata uniforme, $\sigma,\beta=1$ $$\begin{align}
p(x_{n+1}=1|s,n)&= \frac{(n+1)}{s!(n-s)!} \frac{(s+1)!(n-s)!}{(n+2)!} \\
&= \frac{s+1}{n+2}\ne \frac{s}{n}
\end{align}$$
## Marginal Likelihood
La probabilità (o densità) coniugata delle variabili aleatorie sottostanti le osservazioni, valutata per il set di dati del campione, è denominata *marginal likelihood* e valuta:
- Il denominatore della formula di Bayes
- Costituisce la base per la scelta fra modelli in cui si valuta
- $BF= \frac{p(x_{1},\ldots,x_{n}|M_{1})}{p(x_{1},\ldots,x_{n}|M_{2})}$
La marginal likelihood è ottenuta marginalizzando rispetto a tutti i parametri del modello utilizzando la probabilità attribuita a priori ai parametri. Ovvero è la media dei valori delle likelihood valutate per tutti i possibili valori dei parametri con pesi pari alla probabilità (densità a priori) degli stessi.
### Caso Binomiale
$$\begin{align}
p(X=x|\alpha,\beta,n)&=\int_{0}^1 \begin{pmatrix}
n \\ x
\end{pmatrix}\theta^x(1-\theta)^x \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}\theta^{\alpha-1}(1-\theta)^{\beta-1}\ d\theta \\
&=\begin{pmatrix}
n \\ x
\end{pmatrix} \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}\int_{0}^1 \theta^{\alpha+x-1}(1-\theta)^{n+\beta-x-1}\ d\theta \\
&=\begin{pmatrix}
n \\ x
\end{pmatrix} \frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)} \frac{\Gamma(\alpha+x)\Gamma(n+\beta-x)}{\Gamma(n+a+\beta)}
\end{align}$$
È ancora una beta binomiale $(n\ge 1)$ valutata al valore di $x$ osservato nel campione, ad esempio si potrebbero confrontare due marginal likelihood ottenute con gli stessi dati ma specificate con due a priori differenti.

> [!info] Nota
> In statistica Bayesiana, cambiando a priori cambia il modello.
