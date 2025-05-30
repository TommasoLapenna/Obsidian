---
Order: "8"
sticker: emoji//0038-fe0f-20e3
---
## Quantizzazione di Segnali Campionati
L'operazione di campionamento trasforma un segnale tempo-continuo in un segnale tempo-discreto. L'ampiezza dei campioni, tuttavia, rimane sotto forma di un numero reale rappresentabile, in generale, con un numero infinito di cifre. Questo crea problemi per l'elaborazione del segnale mediante tecniche numeriche, che possono trattare solo quantità esprimibili con numero finito di cifre.

L'operazione di *Quantizzazione* rende discreta l'ampiezza dei campioni associando loro un valore di ampiezza scelto da un insieme finito di possibili livelli (di quantizzazione).

![[Pasted image 20250529171628.png|center|500]]

L'operazione di campionamento e di quantizzazione sono alla base della conversione A/D.
Si indicando con:
- $Q[\cdot]$ l'operazione di quantizzazione 
- $\hat{x}(nT)$ il valore quantizzato
Si ha quindi
$$
\hat{x}(nT)=Q[x(nT)]
$$

> [!hint] Reversibilità della Quantizzazione
> La quantizzazione è un'operazione non reversibile, in quanto una volta che un segnale viene quantizzato l'informazione originale non può essere recuperata.

La quantizzazione è un ==processo lossy==, e l'errore commesso nell'operazione di quantizzazione è 
$$
e(nT)=\hat{x}(nT)-x(nT)
$$

Per effettuare la quantizzazione di un segnale occorre dividere l'intervallo di varizione di ampiezza per i suoi campioni in *Intervalli di Quantizzazione Contigui* $(x_{i},x_{i+1})$, gli estremi $x_{i}$ rappresentano le soglie di quantizzazione.
In ogni intervallo di quantizzazione $(x_{i},x_{i+1})$, viene selezionato un valore $\hat{x}_{i}$, detto ==*Livello di quantizzazione*==.

![[Pasted image 20250529173213.png|center|500]]

L'operazione di quantizzazione consiste nel selezionare per ogni campione $x(nT)$, l'intervallo di quantizzazione a cui il campione appartiene e nell'associare as esso il livello di quantizzazione dell'intervallo selezioanto.
Il progetto di un quantizzatore consiste nel fissare i valori delle sogli e dei livelli di quantizzazione. È possibile scegliere soglie e livelli di quantizzazione in modo da minimizzare la potenza dell'errore di quantizzazione (*Algoritmo di Max-Lloyd*).
- La procedura si basa sulla conoscenza della funzione densità di probabilità dei campioni da quantizzare. Gli intervalli di quantizzaione risultano di dimensioni ridotte in corrispondenza dei valori più probabili e, di conseguenza, i livelli di quantizzazione si addensano intorno ai punti di massimo della funzione di probabilità.

### Quantizzatori Uniformi
Una classe di quantizzatori più semplici è quella dei *Quantizzatori Uniformi*, ottenuti imponendo una distanza costante tra le soglie di quantizzazione e tra i livelli di quantizzazione, cioè:
$$
x_{i+1}-x_{i}=\Delta\qquad \hat{x}_{i+1}-\hat{x}_{i}=\Delta
$$
Normalmente, i livelli di quantizzazione vengono rappresentati mediante una notazione binaria, con un ==numero di bit $B$== (fissato), per cui il numero di possibili livelli di quantizzazione è $2^B$. La ==dinamica $D$== del quantizzatore rappresentata l'ampiezza dell'intervallo di valori che i livelli di quantizzazione riescono a coprire.

> [!hint] Approssimazione
> Per avere una buona rappresentazione del segnale, la dinamica deve coincidere, approssimativamente, con l'intervallo di variazione di ampiezza dei campioni del segnale.

Indicando l'intervallo di variazione di ampiezza dei campioni del segnale con $(x_{min}, x_{max})$, si deve avere $D>x_{max}-x_{min}$.

> [!example]+ Esempio:
> Un segnale sinusoidale di ampiezza $A$ assume valori tra $-A$ e $A$ e quindi $D>2A$
> ![[Pasted image 20250529174439.png|center|400]]

Se invece si desidera quantizzare i campioni di un processo aleatorio le cui ampiezze seguono una distribuzione di probabilità Gaussiana, si riscontra un problema con l'intervallo di variazione illimitato di una variabile aleatoria Gaussiana (servirebbe una dinamica infinita).

![[Pasted image 20250529175526.png|center|400]]

Quindi, per una realizzazione pratica del quantizzatore, l'intervallo di variazione delle ampiezze dei campioni viene ipotizzato di estensione finita, ma di dimensione tale che la probabilità che il segnale esca da tale intervallo (*Overflow*) sia sufficientemente piccola.
Per una variabile gaussiana a media nulla, sono note le probabilità che essa assuma valori nell'intervallo $[-k\sigma,k\sigma]$, con $k$ intero:

![[Pasted image 20250529175925.png|center|400]]

Risulta allora evidente che si commette un errore trascurabile se si assume che $x$ possa assumere valori (se a media nulla) nell'intervallo $[-3\sigma,3\sigma]$ oppure in $[-4\sigma,4\sigma]$

![[Pasted image 20250529180144.png|center|400]]


Se $D$ è eccessivamente grande rispetto a $x_{max}-x_{min}$, allora i livelli di quantizzazione effettivamente usati per rappresentare il segnale sono molto minori di quelli a disposizione. Viceversa, se $D$ è eccessivamente piccolo rispetto a $x_{max}-x_{min}$, allora vengono commessi errori rilevanti quando si quantizzano campioni al di fuori della dinamica del quantizzatore (*Errori di Overflow*).

![[Pasted image 20250529185545.png|center|450]]

Si deduce allora che il passo di quantizzazione $\Delta$, la $D$ e il numero di bit $B$ non possono essere arbitrariamente scelti, ma devono verificare la relazione
$$
\Delta= \frac{D}{2^B}
$$
Si ipotizza che d'ora in poi l'ipotesi che il campione da quantizzare abbia ampiezza distribuita simmetricamente rispetto all'origine, quindi anche l'insieme di soglie e livelli di quantizzazione dovrà rispettare, almeno approssimativamente, tale simmetria.

Per evitare problemi di overflow e mancato uso di alcuni livelli, è necessario quindi fare in modo che $D\simeq x_{max}-x_{min}$. Ci sono due soluzioni:
1. L'intervallo $x_{max}-x_{min}$ è fissato, di scelgono allora i parametri del quantizzatore in modo da ottenere un valore di $D$ pari a $x_{max}-x_{min}$.
2. I parametri del quantizzatore, e quindi $D$, sono già fissati e si deve allora scalare l'ampiezza del segnale in modo da riportare $x_{max}-x_{min}$ a un valore pari a $D$ (questa operazione non introduce perdite o distorsioni).

> [!example]+ Esempio:
> Si suppone che la dinamica del quantizzatore sia $(-1,1)$ e che il segnale in ingresso $x[n]$ abbia una dinamica $(-2,2)$. Occorre allora moltiplicare $x[n]$ per un fattore di scala $A$ che adatti i l segnale a quella del quantizzatore, in modo tale che il segnale scalato 
> $$
> x'[n]=Ax[n]
> $$
> abbia una dinamica in $(-1,1)$. In questo caso sarà $A=\frac{1}{2}$

Nella progettazione di quantizzatori uniformi, sono possibili diverse scelte:
- In base alla scelta dei livelli di quantizzazione
	1. **Midtread Quantizer** 
	![[Pasted image 20250529191427.png||400]]
	2. **Midrise Quantizer**
	![[Pasted image 20250529191520.png|400]]
	
- In base alla scelta della regola si associazione tra il campione $x(nT)$ e il valore quantizzato $\hat{x}(nT)$
	1. **Arrotondamento**$$\hat{x}(nT)=\{\hat{x}_{i}:i=\text{arg}\text{ min}_{k}(|x(nT)|-\hat{x}_{k})\}$$Si associa a $x(nT)$ il livello di quantizzazione $\hat{x}_{i}$ ad esso più vicino. Le soglie di quantizzazione risultano essere posizionate nel punto medio tra due livelli di quantizzazione, l'errore commesso soddisfa la disuguaglianza $$0\le|e(nT)|\le \frac{\Delta}{2}$$![[Pasted image 20250529193426.png|500]]
	2. **Troncamento** $$\hat{x}(nT)=\{\hat{x}_{i}:i=\text{arg}\text{ max}_{k}(\hat{x}_{k},\ \hat{x}_{k}\le x(nT))\}$$ Si associano a $x(nT)$ il livello $\hat{x}_{i}$ as esso più vicino tra quelli minori o uguali a $x(nT)$. Se le soglie di quantizzazione coincidono con i livelli di quantizzazione, l'errore commesso soddisfa la disuguaglianza $$0\le|e(nT)|<\Delta$$ ![[Pasted image 20250529193946.png|300]]



| Caratteristica Ingresso-Uscita |                                           |
| ------------------------------ | ----------------------------------------- |
| Midtread, Arrotondamento       | ![[Pasted image 20250530103521.png\|250]] |
| Midtread, Troncamento          | ![[Pasted image 20250530103744.png\|250]] |
| Midrise, Arrotondamento        | ![[Pasted image 20250530103819.png\|250]] |
| Midrise, Troncamento           | ![[Pasted image 20250530103901.png\|250]] |
### Modello dell'Errore di Quantizzazione
Si considera il problema della modellazione dell'errore di quantizzazione. Questo può essere visto come una sequenza che si somma (modello adattivo) al segnale campionato, essendo
$$
e(nT)=\hat{x}(nT)-x(nT)
$$
![[Pasted image 20250530104305.png|center|300]]
E quindi
$$\hat{x}(nT)=e(nT)+x(nT)$$
![[Pasted image 20250530104554.png|center|300]]
Si modella $e(nT)$ come un processo aleatorio, indicato come *Rumore di Quantizzazione*. Le ipotesi che vengono assunte per $e(nT)$ sono le seguenti:

1. $\{e(nT)\}$ è un processo stazionario in senso lato (wide sense stationary, WSS).
	- Implica che la media, potenza e la varianza di $\{e(nT)\}$ sono costanti, non dipendenti quindi dall'indice $n$.
2. La funzione densità di probabilità dell'ampiezza dell'errore di quantizzazione è di tipo uniforme.
	- Permette di valutare tali costanti, distinguendo i casi di quantizzazione per troncamento e per arrotndamento.
3. $\{e(nT)\}$ è incorrelato col processo $\{e(nT)\}$ con il processo $\{x(nT)\}$.
	- $E[x(nT)\cdot e(nT)]=E[x(nT)]\cdot E[e(nT)]$
	- Nel caso dell'arrotondamento vale $E[x(nT)\cdot e(nT)]=0$
4. I campioni del processo $\{e(nT)\}$ sono incorrelati tra loro.
	- Per la quantizzazione con troncamento si ha $$E[e(nT)\cdot e((n+m)T)]=\begin{cases}E[e^2(nT)]=\frac{\Delta^2}{3} & m=0 \\E[e(nT)]\cdot E[e((n+m)T)]= \frac{\Delta^2}{4} & m\ne 0\end{cases}$$
	- Per la quantizzazione con arrotondamento si ha $$E[e(nT)\cdot e((n+m)T)]=\begin{cases}E[e^2(nT)]=\sigma^2_{e}=\frac{\Delta^2}{12} & m=0 \\ 0 & m\ne 0\end{cases}$$ In questo caso l'errore di quantizzazione è un <u>processo bianco</u>
	
> [!gray] Densità di Probabilità, Caso del Troncamento
> Nel caso del troncamento, la pdf dell'errore di quantizzazione è data da 
> $$
> p_{e}(e)=\begin{cases}
> \frac{1}{\Delta} & -\Delta<e\le0 \\
> 0 & altrove
> \end{cases}
> $$
> In tal caso è facile verificare che
> $$\begin{align}
> & E[e(nT)]=\int_{-\Delta}^0 ep_{e}(e)\ de=-\frac{\Delta}{2}= \frac{1}{\Delta}\cdot \left. \frac{e^2}{2}\right|^0_{-\Delta} \\
> & E[e^2(nT)]=\int_{-\Delta}^0 e^2p_{e}(e)\ de= \frac{\Delta^2}{3}= \frac{1}{\Delta}\cdot \left . \frac{e^3}{3}\right|^0_{-\Delta} \\
> & \underset{\text{varianza?}}{\sigma^2_{e}}=\int^0_{-\Delta}\left( e+ \frac{\Delta}{2} \right)^2p_{e}(e)\ de = \frac{\Delta^2}{12}= E[e^2]-E[e]^2
> \end{align}$$

> [!gray] Densità di Probabilità, Caso dell'Arrotondamento
> Nel caso dell'arrotondamento, la pdf dell'errore di quantizzazione è data da  
> $$
> p_{e}(e)=\begin{cases}
> \frac{1}{\Delta} & -\frac{\Delta}{2}<e\le \frac{\Delta}{2} \\
> 0 & altrove
> \end{cases}
> $$
> da cui si ricava
> $$\begin{align}
> &E[e(nT)]=\int^{\frac{\Delta}{2}}_{-\frac{\Delta}{2}}ep_{e}(e)\ de=0 = \frac{1}{\Delta}\cdot \left. \frac{e^2}{2}\right|^{\frac{\Delta}{2}}_{{- \frac{\Delta}{2}}} \\
> &E[e^2(nT)]=\sigma^2_{e} =\int^{\frac{\Delta}{2}}_{-\frac{\Delta}{2}}e^2p_{e}(e)\ de = \frac{\Delta^2}{12}=\frac{1}{\Delta}\cdot \left . \frac{e^3}{3}\right|^{\frac{\Delta}{2}}_{\frac{\Delta}{2}}
> \end{align}$$

Le ipotesi fatte sul rumore di quantizzazione risultano valide quando il segnale campionato varia da campione a campione in maniera sufficientemente complessa, con differenze di diversi livelli di quantizzazione tra un campione  el'altro.
Sebbene per i segnali deterministici l'errore di quantizzazione sia una sequenza deterministica, anche per tali segnali la sequenza $\{e(nT)\}$ viene trattata come un processo aleatorio. 
In casi particolari però le ipotesi del modello possono non risultare più valide, per esempio quantizzando i campioni di una funzione costante: si ottiene un errore di quantizzazione costante e non un processo aleatorio.

Un parametro fondamentale per valutare la perdita di informazione derivante dall'operazione di quantizzazione è il rapporto tra la potenza del segnale e la potenza dell'errore di quantizzazione, usualmente indicato con $SNR_{q}$ (*Signal Noise Reduction*).

> [!info] Ipotesi
> Si ipotizza d'ora in poi che il quantizzatore operi secondo la legge di arrotondamento, in tal caso la potenza e varianza dell'errore di quantizzazione coincidono e sono uguali a $\sigma^2_{e}=\frac{\Delta^2}{12}$

Indicando con $S$ la potenza del segnale e ricordando che $\Delta= \frac{D}{2^B}$ 
$$
SNR_{q}=\frac{S}{\sigma^2_{e}}= \frac{S}{\frac{1}{12}\Delta^2}=\frac{S}{12\left( \frac{D}{2^B} \right)^2}= \frac{12\cdot S\cdot 2^{2B}}{D^2}
$$
Se si esprime $SNR_{q}$ in scala logaritmica:
$$\begin{align}
SNR_{q\ db}=& 10\log_{10}SNR_{q}=10\log_{10}\left( \frac{12\cdot S\cdot 2^{2B}}{D^2} \right)=(20\log_{10}2)B+10 \log_{10}\left( \frac{12S}{D^2} \right)  \\
\simeq& 6.02B+10\log_{10}\left( \frac{12S}{D^2} \right)\ dB
\end{align}$$

Per valutare il rapporto $SNR_{q}$ è necessario conoscere la potenza del segnale oltre ai parametri del quantizzatore.

Si vuole ottenere un segnale sinusoidale di ampiezza $A$.
Sia $\alpha$ il rapporto tra l'escursione picco-picco della sinusoide ($2A$, ovvero da $-A$ a $+A$) e la dinamica $D$ del quantizzatore. Quindi
- $\alpha=\frac{2A}{D}$, $0<\alpha\le 1$ (visto che $D\ge 2A$)
- $D\cdot\alpha=2A$, quindi $A=\alpha  \frac{D}{2}$
- La potenza del segnale è $S=\frac{A^2}{2}=\frac{\alpha^2D^2}{8}$
In scala logaritmica si ottiene
$$\begin{align}
SNR_{q}&\simeq 6.02B+10\log_{10}\left( \frac{12\cdot \frac{\alpha^2D^2}{8}}{D^2} \right)=6.02B+10\log_{10}\left( \frac{3}{2}\alpha^2 \right)= \\
&=6.02B+10\log_{10}\left( \frac{3}{2} \right)+20\log_{10}\alpha=6.02B+1.76+20\underset{<0\text{ perché }\alpha<1}{\log_{10}\alpha}\ dB
\end{align}$$
Il massimo $SNR_{q}$