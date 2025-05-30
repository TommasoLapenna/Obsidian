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

> [!example]+ Esempio: Sinusoide di Ampiezza $A$:
> Si vuole ottenere un segnale sinusoidale di ampiezza $A$.
> Sia $\alpha$ il rapporto tra l'escursione picco-picco della sinusoide ($2A$, ovvero da $-A$ a $+A$) e la dinamica $D$ del quantizzatore. Quindi
> - $\alpha=\frac{2A}{D}$, $0<\alpha\le 1$ (visto che $D\ge 2A$)
> - $D\cdot\alpha=2A$, quindi $A=\alpha  \frac{D}{2}$
> - La potenza del segnale è $S=\frac{A^2}{2}=\frac{\alpha^2D^2}{8}$
> In scala logaritmica si ottiene
> $$\begin{align}
> SNR_{q}&\simeq 6.02B+10\log_{10}\left( \frac{12\cdot \frac{\alpha^2D^2}{8}}{D^2} \right)=6.02B+10\log_{10}\left( \frac{3}{2}\alpha^2 \right)= \\
> &=6.02B+10\log_{10}\left( \frac{3}{2} \right)+20\log_{10}\alpha=6.02B+1.76+20\underset{<0\text{ perché }\alpha<1}{\log_{10}\alpha}\ dB
> \end{align}$$
> Il massimo $SNR_{q}$ si ha quando il segnale sinusoidale occupa tutta la dinamica del quantizzatore ($\alpha=1$).
> Se $\alpha=1$, cioè $D=2A$, la potenza del segnale è $S= \frac{A^2}{2}$
> $$\begin{align}
> &\sigma^2_{e}=\frac{\Delta^2}{12}=\frac{1}{12} \left( \frac{D}{2^B}^2 \right)=\frac{1}{12} \frac{4A^2}{2^{2B}}= \frac{1}{3}A^22^{-2B} \\
> &SNR_{q}= \frac{S}{\sigma^2_{e}}= \frac{\frac{A^2}{2}}{\frac{1}{3}A^22^{-2B}}= \frac{3}{2}2^{2B}=6.02B+1.76\ dB
> \end{align}$$

> [!example]+ Esempio:
> Si vuole quantizzare un segnale rappresentato tramite un processo aleatorio con campioni aventi distribuzione di ampiezza di tipo Gaussiano, con media nulla e varianza $\sigma^2_{x}$. 
> L'intervallo di variazione delle ampiezze dei campioni viene ipotizzato di estensione finita, tale che la probabilità che il segnale esca da tale intervallo (overflow) sia sufficientemente piccola.
> Solitamente si sceglie la dinamica del quantizzatore tale che $\frac{D}{2}=k\sigma_{x}$, dove $k$ è una costante dell'ordine delle unità. Per esempio, per $k=4$, è noto che $Prob\{|x(nT)|>4\sigma_{x}\}=6.3\cdot 10^{-5}$. Scegliendo $\frac{D}{2}=4\sigma_{x}$, si ha che $\frac{D}{8}=\sigma$
> $$
> S=\sigma^2_{x}=\frac{D^2}{64}
> $$
> Si ottiene quindi:
> $$\begin{align}
> SNR_{q\ db}&=6.02B+10\log_{10}\left( \frac{12S}{D^2} \right)\ dB\simeq 6.02B+10\log_{10}\left( \frac{12 \frac{D^2}{64}}{D^2} \right)= 6.02B+10\log_{10}\left( \frac{3}{16} \right)= \\
> &= 6.02B-7.27 \ dB
> \end{align}$$

### Quantizzazione in Presenza di Disturbi
Occorre considerare che in ingresso al quantizzatore in realtà non ci sarà ,ao solo il segnale utile $x(t)$, ma anche eventuali disturbi (rumore adattivo $r(t)$).
Lo schema di conversione A/D è perciò

![[Pasted image 20250530120154.png]]

La quantizzazione introduce una nuova fonte di rumeore $e[n]$ in uscita, la quale diventa $y[n]=x[n]+r[n]+e[n]$. Il rapporto tra potenza di segnale e di rumore all'uscita è dato da
$$
SNR_{u}= \frac{E[(x[n])^2]}{E[(r[n]+e[n])^2]}
$$

Supponendo che $r[n]$ e $e[n]$ siano staticamente indipendenti (ed entrambi a media nulla), vale $E[(r[n]+e[n])^2]=E[r^2[2]]+E[e^2[n]]$
$$
SNR_{u}= \frac{E[(x[n])^2]}{E[(r[n])^2]+E[(e[n])^2]}= \frac{P_{x}}{P_{r}+P_{e}}
$$
$SNR_{i}$ e $SNR_{u}$ sono legati fra loro: se si definisce il rapporto tra potenza del segnale e potenza dell'errore di quantizzazione
$$
SNR_{q}=\frac{P_{x}}{P_{e}}
$$
essendo $SNR_{i}= \frac{P_{x}}{P_{r}}$ si ha
$$
\frac{1}{SNR_{u}}= \frac{P_{r}+P_{e}}{P_{x}}= \frac{P_{r}}{P_{x}}+ \frac{P_{e}}{P_{x}}= \frac{1}{SNR_{i}}+ \frac{1}{SNR_{q}}
$$

> [!hint] Osservazione
> Si osserva che la relazione vale in scala lineare. Se si hanno i valori in $dB$, occorre convertirli in scala lineare per effettuare i calcoli.

---

Sia $x(t)$ un processo aleatorio, con distribuzione di ampiezza Gaussiana, a media nulla, affetto da un rumore additivo $r(t)$ incorrelato con il segnale. Il rapporto tra potenza di segnale e di rumore (nella banda di interesse) è $SNR_{i}=30\ dB$. Determinare il fattore di scala $A$ che adatta la dinamica del segnale a quella del quantizzatore che si suppone pari a $(-1,1)$. Determinare poi il rapporto tra potenza di segnale e di rumore all'uscita $SNR_{u}$ quando i campioni acquisiti vengono quantizzati a $B=9$ bit, nell'ipotesi che i processi siano stazionari in senso lato.

Nell'ipotesi di processi stazionari in senso lato, le potenze di segnale e di rumore sono costanti quindi non dipendono dall'istante di campionamento $nT$. Quindi è plausibile considerare costante $SNR_{i}$
$$
SNR_{i}= \frac{P_{x}}{P_{r}}= \frac{E[x^2(t)]}{E[r^2(t)]}= \frac{E[x^2(nT)]}{E[r^2(nT)]}= \frac{E[x^2[n]]}{E[r^2[n]]}=30 \ dB
$$
Nel caso in cui i campioni del segnale seguano una distribuzione di ampiezza di tipo Gaussiano a media nulla, la probabilità di overflow,  cioè che il segnale non rientri nella dinamica del quantizzatore, è prossima a zero considerando che il segnale assuma valori compresi tra $-4\sigma_{x}$ e $4\sigma_{x}$.
A differenza dell'esempio precedente, però, non è possibile modificare la dinamica del quantizzatore, fissata a $(-1,+1)$, occorre quindi scalare l'ampiezza del segnale per riportarlo nell'intervallo $(-1,1)$ tramite un fattore di scala $A=\frac{1}{4\sigma_{x}}$
![[Pasted image 20250530123619.png|center|400]]
Siano $x'$, $r'$, $y'$, i segnali $x$, $r$, $y$ scalati del fattore $A$. L'introduzione del fattore scala altera le potenze dei segnali, ma non ne altera il rapporto, infatti
$$
SNR_{i}= \frac{P_{x'}}{P_{r'}}= \frac{E[(x'[n])^2]}{E[(r'[n])^2]}= \frac{E[(Ax[n])^2]}{E[(Ar[n])^2]}
= \frac{A^2E[x^2[n]]}{A^2E[r^2[n]]}=\frac{P_{x}}{P_{r}}=30\ dB$$
La quantizzazione introduce una nuova fonte di rumore $e[n]$ sull'uscita, la quale diventa $y'[n]=x'[n]+r'[n]+e[n]$. Il rapporto tra potenza di segnale e di rumore all'uscita è dato da
$$
SNR_{u}= \frac{E[(x'[n])^2]}{E[(r'[n])^2]+E[(e[n])^2]}= \frac{P_{x'}}{P_{r'}+P_{e}}
$$
da cui
$$\begin{align}
&\frac{1}{SNR_{u}}= \frac{P_{r'}+P_{e}}{P_{x'}}= \frac{P_{r'}}{P_{x'}}+ \frac{P_{e}}{P_{x'}}= \frac{1}{SNR_{i}}+ \frac{1}{SNR_{q}} \\
&SNR_{i\ dB}= 30 \ dB\longrightarrow SNR_{i}=10^3\Longrightarrow \frac{1}{SNR_{i}}=10^{-3} \\
&SNR_{q}= \frac{S}{\sigma^2_{e}}= \frac{S}{\frac{1}{12} \Delta^2}= \frac{S}{\frac{1}{12} \left( \frac{D}{2^B} \right)^2}= \frac{12\cdot S\cdot 2^{2B}}{D^2}
\end{align}$$
ma $S=P_{x'}; \ x'=Ax$ processo Gaussiano, con $A=\frac{1}{4\sigma_{x}}$
$$\begin{align}
&P_{x'}=A^2\sigma^2_{x}= \frac{1}{16\sigma^2_{x}}\cdot \sigma^2_{x}= \frac{1}{16} \\
&SNR_{q}= \frac{12\cdot \frac{1}{16}\cdot 2^{2B}}{4}= \frac{3}{16}\cdot 2^{2B}= \frac{3}{16}\cdot 2^{18}=4.9152
\end{align}$$
È lo stesso risultato ottenuto tenendo fisso il segnale e scegliendo la dinamica $\frac{D}{2}=4\sigma_{x}$
$$\begin{align}
&SNR_{q\ dB}= 46.91\ dB\Longrightarrow \frac{1}{SNR_{q}}=2,03\cdot 10^{-5} \\
& \frac{1}{SNR_{u}}= \frac{1}{SNR_{i}}+ \frac{1}{SNR_{q}}= 10^{-3}+2,03\cdot 10^{-5} \\
&\Longrightarrow SNR_{u}=980,03\iff SNR_{u}= 29,91 \ dB
\end{align}$$
Ovviamente $SNR_{u}< SNR_{i}$.
Visto che la quantizzazione aggiunge una nuova fonte di rumore, la potenza del rumore aumenta e quindi il rapporto segnale rumore diminuisce

---

Sia  $x(t)$ un segnale sinusoidale, affetto da rumore adattivo incorrelato con il segnale. Il rapporto tra potenza di segnale e di rumore nella banda di interesse vale $SNR_{i}=30 \ dB$. Determinare il numero di bit $B$ con cui quantizzare il segnale affinché la degradazione introdotta dal quantizzatore sia, al massimo, $\Delta_{dB}=0.1\ dB$.

In questo tipo di esercizi, si devono determinare le caratteristiche del quantizzatore (numero di bit $B$) in base alla specifiche date. L'incogniita è $SNR_{q}$, mentre sono noti $SNR_{i}$ e $SNR_{u}$
$$\begin{align}
&SNR_{i}= 30\ dB& &SNR_{i}=10^3& \\
&SNR_{u}=SNR_{i}-\Delta_{dB}=30 \ dB-0,1\ dB= 29,9\ dB& &SNR_{u}=9977,237
\end{align}$$
$$\begin{align}
\frac{1}{SNR_{u}}=\frac{1}{SNR_{i}}+ \frac{1}{SNR_{q}}&\Longrightarrow \frac{1}{SNR_{q}}= \frac{1}{SNR_{u}}- \frac{1}{SNR_{i}} \\
\frac{1}{SNR_{q}}=\frac{1}{977,237}-\frac{1}{1000}&\Longrightarrow SNR_{q}= 42930,9 \\
&\Longrightarrow SNR_{q}=46,32\ dB
\end{align}$$
Non essendo specificato, si suppone che il segnale sinusoidale abbia ampiezza unitaria. In caso contrario, si può scalare il segnale di un fattore uguale all'inverso dell'ampiezza. 
Il segnale-rumore legato alla quantizzazione di un segnale sinusoidale di ampiezza unitaria è:
$$
SNR= \frac{S}{\sigma_{e}^2}= \frac{S}{\frac{1}{12}\Delta^2}= \frac{S}{\frac{1}{12} \left( \frac{\Delta}{2^B} \right)^2}= \frac{12\cdot S\cdot 2^{2B}}{D^2}
$$
Con $SNR_{q}=6.02B+1.76\ dB$ si ottiene
$$
SNR_{q}= \frac{12\cdot 2^{2B}}{2\cdot 4}= \frac{3}{2}\cdot 2^{2B}
$$
cioè $SNR_{q}=6.02B+1.76\ dB$.
Dato $SNR_{q}=46.32\ dB$, si deve assegnare al quantizzatore $B$ bit, con $B>7.98$, cioè $B=8$ bit.

> [!hint] N.B.
> Si sceglie l'intero superiore perché così la perdita è minore o uguale a quanto richiesto

---

Un segnale $s(t)$ è composto dalla somma di due sinusoidi di ampiezza unitaria. Il segnale è affetto da rumore adattivo $r(t)$ incorrelato con $s(t)$ e tale che il rapporto tra potenza di segnale e di rumore (nella banda di interesse) vale $60\ dB$. Il segnale viene quantizzato a 8 bit. Determinare $B$ affinché la grandezza del rapporto tra potenza di segnale e di rumore all'uscita del quantizzatore sia inferiore a $0.5\ dB$.
$$
s(t)=\cos(2\pi f_{1}t)+\cos(2\pi f_{2}t)
$$
La dinamica del segnale di ingresso è $(-2,2)$. Nell'ipotesi di utilizzare un quantizzatore con dinamica $(-1,1)$, per adattare la dinamica del segnale a quella del quantizzatore è necessario introdurre un fattore di scala $A=\frac{1}{2}$.
Indicando con $s'(t)$ il segnale dopo lo scalamento si ha:
$$
P_{s'}= \frac{A^2}{2}+\frac{A^2}{2}= \frac{\left( \frac{1}{2} \right)^2+\left( \frac{1}{2} \right)^2}{2}= \frac{1}{4}
$$
Inoltre
$$
P_{e}=\sigma_{e}^2= \frac{\Delta^2}{12}= \frac{1}{12}\left( \frac{D}{2^B} \right)^2= \frac{1}{12} \frac{4}{2^{2B}}= \frac{1}{3}2^{-2B}
$$
$$
\frac{1}{SNR_{q}}= \frac{1}{SNR_{u}}- \frac{1}{SNR_{i}}
$$
- $\frac{P_{s'}}{P_{r'}}=SNR_{i}=60 \ dB$ ovvero $10^6$
- $SNR_{u}=SNR_{i}-\Delta_{dB}= 60\ dB-0,5 \ dB=59,5 \ dB$ ovvero $891251$

Si ricava che
$$
SNR_{q}= \frac{1}{\frac{1}{SNR_{u}}-\frac{1}{SNR_{i}}}= \frac{1}{\frac{1}{891251}-10^{-6}}= \frac{P_{s'}}{P_{e}}= \frac{\frac{1}{4}}{\frac{1}{3}2^{-2B}}= \frac{3}{4}2^{2B}
$$
In questa espressione l'unica incognita è $B$, dalle specifiche date si ricava quindi $B=11.69$, cioè si devono usare 12 bit fi quantizzazione

--- 

Si deve campionare e quantizzare un segnale $x(t)$ dato dalla somma di due processi aleatori $x_{1}(t)$ e $x_{2}(t)$, stazionari, con distribuzione Gaussiana, incorrelati tra loro, a media nulla e con deviazione standard, rispettivamente $\sigma_{1}=2$ e $\sigma_{2}=1$. Il processo $x_{1}(t)$ è affetto da rumore adattivo $v_{1}(t)$, mentre $x_{2}(t)$ è affetto da rumore adattivo $v_{2}(t)$. I processi $v_{1}(t)$ e $v_{2}(t)$ sono incorrelati tra loro e con i segnali $x_{1}(t)$ e $x_{2}(t)$. I rapporti tra potenza di segnale e di rumore sono $SNR_{1}=\frac{E[x^2_{1}(t)]}{E[v^2_{1}(t)]}=40\ dB$ e $SNR_{2}=\frac{E[x^2_{2}(t)]}{E[v^2_{2}(t)]}=38\ dB$. 
Calcolare il fattore di scala necessario per  evitare il problema dell'overflow della dinamica del quantizzatore, supponendo che questa sia $(-1,1)$. Calcolare inoltre il rapporto tra potenza di segnale e di rumore all'uscita del quantizzatore quando i campioni vengono quantizzati a $B=10$ bit.

![[Pasted image 20250530163750.png|center|500]]


Il segnale $x(t)$ ha una distribuzione Gaussiana in quanto è la somma di due processi aleatori Gaussiani. La media e la varianza di $x(t)$ sono dati da
$$\begin{align}
&\mu_{x} = E[x(t)]= E[x_{1}(t)]+E[x_{2}(t)]=0 \\
&\sigma^2_{x}=E[x^2(t)]=E[x^2_{1}(t)]+E[x_{2}^2(t)]+2\underset{=0}{\cancel{E[x_{1}(t)x_{2}(t)]}}=\sigma_{1}^2+\sigma_{2}^2=5
\end{align}$$
Un fattore di scala appropriato affinché il processo $x(t)$ rispetti la dinamica del quantizzatore è dato da $A= \frac{1}{4\sigma_{x}}= \frac{1}{4\sqrt{ 5 }}$
$$P_{x'}=A^2\sigma^2_{x}= \frac{1}{16\cdot \sigma^2_{x}}\sigma^2_{x}=\frac{1}{16}$$
I rapporti tra potenza di segnale e di rumore sono $SNR_{1}=\frac{E[x^2_{1}(t)]}{E[v_{1}^2(t)]}=40 \ dB$ e $SNR_{2}=\frac{E[x_{2}^2(t)]}{E[v_{2}^2(t)]}=38\ dB$
$$\begin{align}
&SNR_{1}= \frac{E[x_{1}^2(t)]}{E[v_{1}^2(t)]}=\frac{\sigma_{1}^2}{P_{v_{1}}}=10^4 \Longrightarrow P_{v_{1}}=E[v_{1}^2]=\frac{\sigma^2_{1}}{10^4}=\sigma^2_{1}\cdot 10^{-4}= 4\cdot 10^{-4} \\
& SNR_{2}= \frac{E[x_{2}^2(t)]}{E[v_{2}^2(t)]}=\frac{\sigma_{2}^2}{P_{v_{2}}}=10^{3,8}\Longrightarrow P_{v_{2}}=E[v_{2}^2]=\frac{\sigma^2_{2}}{10^{3,8}}=\sigma_{2}^2\cdot 10^{-3,8}= 1\cdot 10^{-3,8}=1,58\cdot 10^{-4}
\end{align}$$
Con questi valori si ottiene quindi:
$$
SNR_{i}= \frac{\sigma_{1}^2+\sigma_{2}^2}{P_{v_{1}}+P_{v_{2}}}=39,52\ sB
$$

Calcolare inoltre il rapporto tra potenza di segnale e di rumore all'uscita del quantizzatore quando i campioni vengono quantizzati a $B=10$ bit

RIcordando che tali potenze risultano attenuate di un fattore $A^2$ all'uscita del quantizzatore
$$\begin{align}
&P_{x'}=\frac{1}{16} \\
&P_{e}=\sigma_{e}^2=\frac{1}{3}2^{-2}= \frac{1}{3}2^{-20}????? \\
&SNR_{u}= \frac{P_{x'}}{P_{v_{1}'}+P_{v_{2}'}+P_{e}}= \frac{P_{x'}}{A^2E[v_{1}^2]+A^2E[v_{2}^2]+P_{e}}
\end{align}$$
Usando i valori ricavati si ha
$$
SNR_{u}= 8571,03
$$
Ovvero $39,33\ dB$ e quindi $SNR_{u}<SNR_{i}$
