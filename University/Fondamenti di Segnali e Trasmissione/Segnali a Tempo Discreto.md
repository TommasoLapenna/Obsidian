---
Order: "6"
sticker: emoji//0036-fe0f-20e3
---
- [[#Campionamento dei Segnali a Tempo Continuo|Campionamento dei Segnali a Tempo Continuo]]
- [[#Segnali Notevoli|Segnali Notevoli]]
	- [[#Sequenza Gradino Unitario|Sequenza Gradino Unitario]]
	- [[#Sequenza Esponenziale Unilatero|Sequenza Esponenziale Unilatero]]			- [[#Sequenza $\delta$ o Impulsiva|Sequenza $\delta$ o Impulsiva]]
	- [[#Sequenza Impulso Rettangolare Causale di Durata $N$|Sequenza Impulso Rettangolare Causale di Durata $N$]]
	- [[#Oscillazione Complessa Discreta alla Frequenza Normalizzata $F_{0}$|Oscillazione Complessa Discreta alla Frequenza Normalizzata $F_{0}$]]
- [[#Rappresentazione dei Segnali Aperiodici a Tempo Discreto nel Dominio della Frequenza|Rappresentazione dei Segnali Aperiodici a Tempo Discreto nel Dominio della Frequenza]]
- [[#Teoremi sulla Trasformata di Fourier di una Sequenza|Teoremi sulla Trasformata di Fourier di una Sequenza]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema di Linearità|Teorema di Linearità]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema del Ritardo|Teorema del Ritardo]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema della della Modulazione (o Traslazione in Frequenza)|Teorema della della Modulazione (o Traslazione in Frequenza)]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema della Somma di Convoluzione|Teorema della Somma di Convoluzione]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema del Prodotto|Teorema del Prodotto]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema dell'incremento|Teorema dell'incremento]]
	- [[#Teoremi sulla Trasformata di Fourier di una Sequenza#Teorema della Sequenza Somma|Teorema della Sequenza Somma]]
- [[#Esempi|Esempi]]
- [[#Condizione di Nyquist e Teorema del Campionamento|Condizione di Nyquist e Teorema del Campionamento]]
	- [[#Condizione di Nyquist e Teorema del Campionamento#Campionamento|Campionamento]]
	- [[#Condizione di Nyquist e Teorema del Campionamento#Interpolazione|Interpolazione]]
	- [[#Condizione di Nyquist e Teorema del Campionamento#Interpolazione a Mantenimento|Interpolazione a Mantenimento]]
	- [[#Condizione di Nyquist e Teorema del Campionamento#Interpolazione Cardinale e Teorema del Campionamento|Interpolazione Cardinale e Teorema del Campionamento]]
- [[#Trasformata Discreta di Fourier|Trasformata Discreta di Fourier]]
- [[#Proprietà della DFT|Proprietà della DFT]]
	- [[#Proprietà della DFT#Proprietà di Linearità|Proprietà di Linearità]]
	- [[#Proprietà della DFT#Proprietà di Traslazione Circolare|Proprietà di Traslazione Circolare]]
	- [[#Proprietà della DFT#Proprietà della Traslazione in Frequenza|Proprietà della Traslazione in Frequenza]]
	- [[#Proprietà della DFT#Proprietà di Inversione Temporale|Proprietà di Inversione Temporale]]
	- [[#Proprietà della DFT#Proprietà di Coniugazione|Proprietà di Coniugazione]]
	- [[#Proprietà della DFT#Proprietà di Simmetria per Sequenze Reali|Proprietà di Simmetria per Sequenze Reali]]
	- [[#Proprietà della DFT#Teorema di Parseval|Teorema di Parseval]]
	- [[#Proprietà della DFT#Teorema del Prodotto|Teorema del Prodotto]]
	- [[#Proprietà della DFT#Teorema della Convoluzione|Teorema della Convoluzione]]
	- [[#Proprietà della DFT#Relazioni tra Convoluzione Lineare e Convoluzione Circolare|Relazioni tra Convoluzione Lineare e Convoluzione Circolare]]
- [[#Complessità di Calcolo della Trasformata Discreta|Complessità di Calcolo della Trasformata Discreta]]
	- [[#Complessità di Calcolo della Trasformata Discreta#Fast Fourier Transform (FFT)|Fast Fourier Transform (FFT)]]
- [[#Tavola Sinottica|Tavola Sinottica]]

## Campionamento dei Segnali a Tempo Continuo

> [!info]
> Un segnale a tempo discreto è una successione $x_{n}$ o sequenza di numeri $x[n]$, ed è quindi rappresentabile con una funzione di variabile intera che assume valori reali o complessi

Un caso tipico nell'elaborazione dei segnali è quello in cui il segnale a tempo discreto $x[n]$ viene ottenuto a partire da un segnale a tempo continuo attraverso un'operazione di campionamento.
Campionare un segnale $x(t)$ significa estrarre dal segnale i valori che esso assume assume a istanti di temporali equidistanti (multipli di un intervallo $T$ detto *Periodo di Campionamento*)

![[Pasted image 20250417180713.png|center|400]]

Con questa operazione si crea una sequenza il cui l'$n-$esimo valore è il valore assunto dal segnale a tempo continuo all'istante $nT$
$$
x[n]=x(nT)
$$
L'operazione di campionamento viene effettuata da un dispositivo chiamato *Campionatore*

![[Pasted image 20250417181020.png|center|250]]

La cadenza con cui l'interruttore si chiude (cioè con la quale il segnale viene campionato) è $$f_{c}= \frac{1}{T}$$ed è *Frequenza di Campionamento* ($Hz$ o $\frac{\text{campioni}}{s}$).

Nella pratica, il campionamento viene effettuato dai convertitori A/D (Analogico/Digitale). Questi dispositivi sono controllati da un clock a frequenza $f_{c}$ che fornisce gli impulsi di comando al circuito per le operazioni di campionamento.
Il campionatore ideale estrae il valore del segnale $x(t)$ in corrispondenza di ogni impulso di clock, il convertitore A/D invece rende una rappresentazione finita del numero reale estratto (solitamente in aritmetica binaria 8 o 16 bit), introducendo un *Errore di Quantizzazione*.

L'elaborazione del segnale viene eseguita sui valori digitali estratti dal segnale attraverso la conversione A/D, e si risolve con l'esecuzione di un programma da parte di microprocessori specializzati, chiamati DSP (Digital Signal Processor).


![[Pasted image 20250417182141.png]]

<sup>Struttura flessibile, le funzioni di elaborazione possono essere realizzate cambiando semplicemente software (invece dell'hardware)</sup>

Il segnale $y[n]$ risultante viene successivamente riconvertito in un segnale analogico $y(t)$ attraverso una conversione D/A (Digitale/Analogico). Il dispositivo responsabile di questa operazione di chiama *Interpolatore*.

![[Pasted image 20250417182550.png|center|400]]
## Segnali Notevoli
##### Sequenza Gradino Unitario
$$u[n]=\begin{cases}
1 & n\ge 0 \\
0 & n<0
\end{cases}$$
![[Pasted image 20250417183214.png|center|300]]
A differenza del caso continuo, in $0$ non presenta discontinuità.
##### Sequenza Esponenziale Unilatero
$$
x[n]=a^n u[n]
$$
![[Pasted image 20250417183410.png|center|300]]
##### Sequenza $\delta$ o Impulsiva
$$
\delta[n]=\begin{cases}
1 & n= 0 \\
0 & \text{altrimenti}
\end{cases}
$$
![[Pasted image 20250417183427.png|center|300]]
In modo analogo al caso continuo, le funzioni $\delta$ e gradino sono funzioni tra loro legate
$$
u[n]=\begin{cases}
1 & n\ge 0  \\
0 & n<0
\end{cases}\qquad \delta[n]=\begin{cases}
1 & n=0 \\ 0 & \text{altrimenti}
\end{cases}
$$
Il gradino è la sequenza somma della $\delta[n]$ $$
u[n]=\sum^n_{i=-\infty}\delta[i]\qquad u[n]=\delta[-\infty]+\ldots+\delta[n-1]+\delta[n]$$
Solo se $n\ge 0$ almeno un termine fa $1$, altrimenti sono tutti $0$.
Inoltre $\delta[n]=u[n]-u[n-1]$

![[Pasted image 20250417184641.png|center|350]]
##### Sequenza Impulso Rettangolare Causale di Durata $N$
$$
x[n]=\begin{cases}
1 & 0\le n\le N-1 \\
0 & \text{altrimenti}
\end{cases}
$$
Si ottiene come differenza tra un $u[n]$ e una sua versione ritardata

![[Pasted image 20250417185307.png|center|400]]
##### Oscillazione Complessa Discreta alla Frequenza Normalizzata $F_{0}$
$$
x[n]=\exp(j 2\pi F_{0}n)
$$
È la versione a tempo discreto della oscillazione complessa analogica $\exp(j 2\pi f_{0}t)$ alla frequenza $f_{0}$. La frequenza $F_{0}$ è normalizzata perché rappresenta un numero puro (adimensionale). Rispetto alla variabile temporale $n$, questo segnale è periodico se s solo se $F_{0}$ è un numero razionale (cioè se $F_{0}=\frac{p}{q}$).

---
## Rappresentazione dei Segnali Aperiodici a Tempo Discreto nel Dominio della Frequenza
Come per i segnali continui nel tempo, si può sviluppare una rappresentazione nel domino della frequenza del segnale, partendo però all'inverso (ovvero dal caso aperiodico).

Data una sequenza aperiodica $x[n]$, si definisce la *Trasformata di Fourier della Sequenza* $x[n]$ (il segno serve a distinguerla dalla trasformata continua)
$$
\overline{X}(F)= \sum_{n=-\infty}^\infty x[n]e^{-j 2\pi nF}
$$
funzione della variabile $F$ (frequenza normalizzata).

Si osserva che la trasformata di una sequenza è una funzione periodica in $F$ di periodo $1$ $$
\overline{X}(F+1)=\sum_{n=-\infty}^\infty [n]e^{-j 2\pi n(F+1)}=\sum_{n=-\infty}^\infty e^{j 2\pi nF}\underset{\text{Vale }1\text{ per }n\text{ intero} }{e^{-j 2\pi n}}=\sum_{n=-\infty}^\infty x[n]e^{-j 2\pi nF}=\overline{X}(F)$$
Quindi $\overline{X}(F)$ è completamente nota se è noto il suo andamento in un intervallo delle frequenze normalizzate di ampiezza unitaria (per esempio $F\in\left[ -\frac{1}{2}, \frac{1}{2} \right]$), chiamato *Intervallo Base*.

La definizione della trasformata è molto esaustiva dal punto di vista matematico, ma è poco conveniente quando la sequenza $x[n]$ proviene da un'operazione di campionamento di un segnale analogico $x(t)$.
La presenza della frequenza normalizzata infatti non consente di stabilire un legame con la frequenza delle componenti della trasformata $X(f)$ del segnale analogico di partenza. Se allora il periodo di campionamento è $T$, si può definire la variabile
$$
f= \frac{F}{T}= F\cdot f_{c}
$$
che viene ottenuta denormalizzando la frequenza normalizzata, misurabile in $Hz$.
Sostituendo nella definizione iniziale di trasformata $F=fT$, si ottiene una funzione complessa della frequenza misurabile in $Hz$ (nuova definizione).

> [!gray] ==Trasformata di Fourier di una Sequenza==
> $$
> \overline{X}(f)=\sum_{n=-\infty}^\infty x[n]e^{-j 2\pi nfT}=TFS[x[n]]
> $$

Anche per la trasformata di una sequenza si introducono lo spettro si ampiezza $\overline A(f)=|\overline X(f)|$ e lo spettro di fase $\overline \theta(f)=\angle \overline X(f)$.
Poiché la funzione $\overline X(f)$ è periodica di periodo $1$, è allora periodica in ambito frequenziale di un periodo pari alla frequenza di campionamento $f_{c}=\frac{1}{T}$:
$$
\overline X(f)= \overline X \left( f+ \frac{1}{T} \right)
$$
Questa periodicità è caratteristica delle trasformate di sequenza, che diventa evidente nella relazione di *Antitrasformata*.
Si introduce quindi la relazione di antitrasformazione

> [!gray] ==Antitrasformata di Fourier di una Sequenza==
> $$
> x[n]=ITFS[\overline X(f)]= T \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline X(f)e^{j 2\pi nfT}\ df
> $$

Permette di esprimere la sequenza attraverso un integrale di Fourier.

> [!gray] Procedimento per ottenere l'Antitrasformata
> Si parte dalla definizione di trasformata
> $$
> \overline X(f)=\sum_{n=-\infty}^\infty x[m]e^{-j 2\pi mfT}=TFS[x[m]]
> $$
> Si moltiplicano entrambi i membri per un'oscillazione complessa alla frequenza $f$ e si integra sull'intervallo frequenziale $\left[ -\frac{1}{2T}, \frac{1}{2T} \right]$
> $$
> \int_{-\frac{1}{2T}}^{\frac{1}{2T}}e^{j 2\pi nfT}\ df = \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\sum_{m=-\infty}^\infty x[m]e^{-j 2\pi mfT}e^{j 2\pi nfT}\ df = \sum_{m=-\infty}^\infty x[m]\int_{-\frac{1}{2T}}^{\frac{1}{2T}} e^{-j 2\pi(m-n)fT}\ df
> $$
> ^496717
> 
> Si osserva che
> $$
> \int_{-\frac{1}{2T}}^{\frac{1}{2T}}e^{-j 2\pi(m-n)fT}\ df= \begin{cases}
> 0 & m\ne n \\ \frac{1}{T} & m=n
> \end{cases}
> $$
> La serie del secondo membro della relazione su riduce in un unico termine per cui $m=n$, in cui vale l'integrale $\frac{1}{T}$: 
> $$
> \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline{X}(f)e^{j 2\pi fT}\ df= \frac{1}{T}x[n]
> $$
> Da cui si ottiene la relazione di antitrasformazione ^f0871d
> $$
> x[n]=ITFS[\overline X(f)]= T \int_{-\frac{1}{2T}}^{\frac{1}{2T}} \overline X(f)e^{j 2\pi fT}\ df
> $$
> La serie al secondo membro della relazione [[#^496717|precedente]] si riduce all'unico termine per cui $m=n$, in cui l'integrale vale $\frac{1}{T}$.

Il significato dell'espansione della frequenza $x[n]$ è la solita della trasformata di Fourier:
- Il segnale viene espresso come sovrapposizione di un continuo di componenti frequenziali di ampiezza e fase regolate da $\overline X(f)$. 

> [!info] Componenti Necessarie
> Per un segnale analogico servono tutte le componenti a tutte le frequenze sull'asse reale (da $-\infty$ a $+\infty$). Invece per esprimere una frequenza in ambito frequenziale bastano le componenti aventi frequenze comprese nell'intervallo $\left[ -\frac{1}{2T}, \frac{1}{2T} \right]$.
Questo fatto è giustificato dalla periodicità

Questo fatto è giustificato dalla periodicità della trasformata di una sequenza (solo le componenti veramente significative sono quelle nel periodo di base).

> [!hint] Periodicità della Trasformata di una Sequenza
> La periodicità e/o limitatezza della trasformata di una sequenza sono conseguenze di un fenomeno che si verifica nei segnali a tempo discreto:
> - Due oscillazioni sinusoidale (complesse) alle rispettive frequenze $f_{0}+\frac{m}{T}$ e $f_{0}$ sono indistinguibili.
>
> Infatti
> $$
> \exp\left[ j 2\pi\left( f_{0}+\frac{m}{T} \right)nT \right]=\exp(j 2\pi f_{0}nT)\exp (j 2\pi mn)= \exp(j 2\pi f_{0}nT)
> $$
> ![[Pasted image 20250419152654.png|center|425]]
> Quindi non ha senso pensare a componenti significative nello spettro del segnale discreto fuori di un intervallo base di ampiezza pari alla frequenza di campionamento (in quanto queste componenti sono indistinguibili da quelle presenti nel periodo base).
> Questa è proprio la definizione di periodicità della trasformata.

<br>
Per la serie della TFS si possono porre problemi di convergenza.

> [!gray] Condizione Sufficiente per l'Esistenza della trasformata
> Una condizione sufficiente è l'assoluta sommabilità:
> $$
> \sum_{n=-\infty}^\infty |x[n]|<+\infty
> $$
> Infatti si ha che
> $$
> |\overline{X}(f)|=|\sum_{n=-\infty}^\infty x[n]e^{-j 2\pi fT}|\le\sum_{n=-\infty}^\infty |x[n]e^{-j 2\pi nfT}|= \sum_{n=-\infty}^\infty|x[n]|
> $$
> Per cui se $\sum_{n=-\infty}^\infty |x[n]|<\infty$ allora è vero che $|\overline X(f)|<+\infty$ (il verificarsi di questa condizione assicura la convergenza per tutti i valori della sequenza).
> 

Le proprietà della trasformata di Fourier di una sequenza relativamente a quelle del segnale temporale sono identiche a quelle ricavate per la trasformata di Fourier di un segnale continuo (simmetria Hermitaina, segnale pari o dispari, segnale reale ecc..). Queste proprietà si ricavano delle seguenti relazioni (ricavate precedentemente)
- ==*Analisi*:== $$\overline X(f)=\sum_{n=-\infty}^\infty x[m]e^{-j 2\pi mfT}=TFS[x[m]]$$
- ==*Sintesi:*== $$x[n]=ITFS[\overline X(f)]= T \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline X(f)e^{j 2\pi nfT}\ df$$

> [!info] N.B.
> Il segnale nel tempo è discreto, ma la trasformata è continua.

> [!example]+ Esempio: Calcolo della trasformata della sequenza $\delta[n]$
> ![[Pasted image 20250419155821.png]]

> [!example]+ Esempio: Calcolo della trasformata dell'impulso rettangolare discreto:
> ![[Pasted image 20250419161036.png]]
> 

> [!example]+ Esempio: Calcolo della Trasformata della Sequenza Esponenziale Discreto
> ![[Pasted image 20250419162448.png]]

---
## Teoremi sulla Trasformata di Fourier di una Sequenza
Alcune proprietà della trasformata di una sequenza sono analoghe a quelle della trasformata di un segnale continuo, mentre altre sono radicalmente diverse.
### Teorema di Linearità
> [!gray] ->
> Si considera la seguente combinazione lineare:
> $$
> x[n]=a\cdot x_{1}[n]+b\cdot x_{2}[n]
> $$
> Allora
> $$
> \overline X(f) = a\cdot \overline X_{1}(f)+b\cdot\overline X_{2}(f)
> $$
> dove $\overline X_{1}(f)=TFS[x_{1}[n]]$ e $\overline X_{2}(f)=TFS[x_{2}[n]]$.
> 

Questa proprietà è una banale conseguenza della definizione di trasformata di Fourier di una sequenza, si dimostra in modo analogo al caso continuo
### Teorema del Ritardo

> [!gray] ->
> Si considera una sequenza $x[n]$ con trasformata $\overline X(f)$. la trasformata della sequenza $x[n-k]$ (ottenuta ritardando $x[n]$ di $k$ passi) è espressa nel seguente modo:
> $$
> x[n-k]\iff \overline X(f)e^{-j 2\pi kft}
> $$
> <br>**Dimostrazione:**
> Basta osservare che
> $$
> \begin{align}
> TFS[x[n-k]]&=\sum_{n=-\infty}^\infty x[n-k]e^{-j 2\pi nfT}=\sum_{n=-\infty}^\infty x[m]e^{-j 2\pi(m+k)fT}=e^{-j 2\pi kfT} \sum_{m=-\infty}^\infty x[m]e^{-j 2\pi mfT} \\
> &= \overline X(f)e^{-j 2\pi kfT}
> \end{align}
> $$
> avendo effettuato il cambio di variabile $m=n-k$.

### Teorema della della Modulazione (o Traslazione in Frequenza)

> [!gray] ->
> La trasformata della sequenza $x[n]e^{j 2\pi nf_{0}T}$ (ottenuta modulando $x[n]$ con la sequenza $e^{j 2\pi nf_{0}T}$) è espressa da
> $$
> x[n]e^{j 2\pi nf_{0}T}\iff \overline X(f-f_{0})
> $$
> <br> **Dimostrazione:**
> Infatti si ha
> $$
> TFS[x[n]e^{j 2\pi nf_{0}T}] = \sum_{n=-\infty}^\infty x[n]e^{j 2\pi nf_{0}T}e^{-j 2\pi nfT}= \sum_{n=-\infty}^\infty x[n]e^{-j 2\pi n(f-f_{0})T}=\overline X(f-f_{0})
> $$

### Teorema della Somma di Convoluzione
> [!info] Somma di Convoluzione tra Sequenza Aperiodiche
> Si definisce la sequenza $z[n]$ come somma di convoluzione tra le sequenze (aperiodiche) $x[n]$ e $y[n]$: 
> $$
> z[n]=x[n]\otimes y[n]=\sum_{k=-\infty}^\infty x[k]y[n-k]=\sum_{k=-\infty}^\infty y[k]x[n-k]
> $$
> - Gode delle stesse proprietà commutativa, associativa e distributiva dell'integrale di convoluzione.

> [!gray] ->
> La trasformata di Fourier della sequenza $z[n]=x[n]\otimes y[n]$ è espressa da
> $$
> z[n]=x[n]\otimes y[n] \iff \overline Y(f)\cdot \overline X(f)= \overline Z(f)
> $$
> <br>**Dimostrazione:**
> $$
> \overline Z(f)=\sum_{n=-\infty }^\infty \sum_{k=-\infty}^\infty x[k]y[n-k]e^{-j 2\pi nfT}
>  = \sum_{k=-\infty}^\infty x[k]\sum_{n=-\infty}^\infty y[n-k]e^{-j 2\pi nfT}$$
> Invertendo l'ordine delle due sommatorie, si osserva che (teorema del ritardo)
> $$
> \sum_{n=-\infty}^\infty y[n-k]e^{-j 2\pi nfT} = \overline Y(f)e^{-j 2\pi kfT}
> $$
> Allora si può scrivere
> $$
> \overline Z(f)=\sum_{k=-\infty}^\infty x[k]\ \overline Y(f)e^{-j 2\pi kfT} =\overline Y(f)\sum_{k=-\infty}^\infty x[k]e^{-j 2\pi kfT}=\overline Y(f)\overline X(f)
> $$

### Teorema del Prodotto

> [!gray] ->
> Si considera la frequenza $p[n]$ data dal prodotto fra la sequenza $x[n]$ e la sequenza $y[n]$, ovvero $p[n]=x[n]\cdot y[n]$, e se ne calcola la trasformata:
> $$
> \overline P(f)=\sum_{n=-\infty}^\infty p[n]e^{-j 2\pi nfT} =\sum_{n=-\infty}^\infty x[n]y[n]e^{-j 2\pi nfT}=\sum_{n=-\infty}^\infty \left( T \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline X (v)e^{j 2\pi nvT}\ dv \right)y[n]e^{-j 2\pi nfT}
> $$
> (avendo espresso $x[n]$ come antitrasformata di $\overline X(f)$).
> Con questa trasformata si ricava (invertendo l'ordine delle operazione di somma e intergale):
> $$
> \overline P(f)=T\int_{-\frac{1}{2T}}^{\frac{1}{2T}} \overline X(v)\sum_{n=-\infty}^\infty y[n]e^{-j 2\pi n(f-v)T}\ dv = T\int_{-\frac{1}{2T}}^{\frac{1}{2T}} \overline X(v) \overline Y(f-v)\ dv
> $$
> che permette di stabilire la relazione
> $$
> p[n]=x[n]y[n]\iff\overline P(f)=T\int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline X(v)\overline Y(f-v)\ dv
> $$

Poiché le funzioni $\overline X(v)$ e $\overline Y(f-v)$ sono periodiche di periodo $\frac{1}{T}$, l'integrazione può esere svolta su un qualsiasi intervallo frequenziale di ampiezza $\frac{1}{T}$. Questo integrale rappresenta la *Convoluzione Ciclica* (o periodica) fra le trasformate $\overline X(v)$ e $\overline Y(v)$

La convoluzione ciclica p un'operazione che si definisce tra funzioni periodiche come le trasformate delle sequenze. Si noti come la funzione integranda è analoga a quella nella convoluzione lineare (o aperiodice), ma viene calcolato su un solo periodo, e il risultato viene poi diviso per l'ampiezza del periodo stesso ($\frac{1}{T}$).
### Teorema dell'incremento

> [!gray] ->
> La derivata di un segnale a tempo continuo $x(t)$ può essere approssimata con il rapporto incrementale
> $$\left.\frac{dx(t)}{dt}\right |_{t=nT}\simeq \frac{x(nT)-x(nT-T)}{T}=\frac{x[n]-x[n-1]}{T}$$
> avendo definito la sequenza $x[n]=x(nT)$ ottenuta per campionamento del segnale continuo $x(t)$.
> Si introduce l'operatore *Incremento* $\Delta$ definito dalla relazione 
> $$\Delta x[n]=x[n]-x[n-1]$$
> Si può immaginare la sequenza degli incrementi $\Delta x[n]$ di $x[n]$ come il corrispondente a tempo discreto della derivata del segnale a tempo continuo $\frac{dx(t)}{dt}$.
> Infine, usando il teorema del ritardo si può scrivere
> $$
> \Delta x[n]\iff \overline X(f)-\overline X(f)e^{-j 2\pi fT}=\overline X(f)(1-e^{-j 2\pi fT})
> $$

### Teorema della Sequenza Somma

> [!gray] ->
> Si considera la *Sequenza Somma* $y[n]$ di una sequenza $x[n]$:
> $$
> y[n]=\sum_{k=-\infty}^n x[k]
> $$
> La trasformata della sequenza è espressa da 
> $$
> \overline Y(f)= \frac{\overline X (f)}{1-e^{-j 2\pi fT}}\qquad \text{se }\overline X(0)=0
> $$
> <br> **Dimostrazione:**
> per il teorema dell'incremento si può scrivere 
> $$
> \Delta y[n]\iff \overline Y(f)(1-e^{j 2\pi fT})
> $$
> D'altronde 
> $$
> \Delta y[n]=y[n]-y[n-1] = \sum_{k=-\infty}^n x[k]-\sum^{n-1}_{k=-\infty} x[k]=x[n]
> $$
> e quindi
> $$
> \overline X(f)=\overline Y(f)(1-e^{-j 2\pi fT})
> $$
>
> ^poopo
> 
> e si conclude con
> $$
> y[n]= \sum_{k=-\infty}^n x[k]\iff \overline Y(f)= \frac{\overline X(f)}{1-e^{-j 2\pi fT}}
> $$
> Se si considera però [[#^poopo|(*)]], per $f=0$ si ottiene
> $$\overline X(0)=\overline Y(0)(1-e^{-j0})$$
> che non può essere valida se $\overline X(0)\ne0$. Quindi, la condizione per l'applicabilità di questo teorema nella forma appena espressa è che valga
> $$
> \overline X(0)=\sum_{n=-\infty}^\infty x[n]=0
> $$

## Esempi

> [!example]+ Esempio:
> ![[Pasted image 20250419175156.png]]
> ![[Pasted image 20250419175224.png]]
> ![[Pasted image 20250419175248.png]]

> [!example] Esempio:
> ![[Pasted image 20250419175344.png]]
> ![[Pasted image 20250419175403.png]]
> ![[Pasted image 20250419175425.png]]
> ![[Pasted image 20250419175446.png]]
> ![[Pasted image 20250419175512.png]]

---
## Condizione di Nyquist e Teorema del Campionamento
### Campionamento
Si prende in considerazione il campionamento di un segnale a tempo continuo $x(t)$:
$$x[n]=x(nT)$$
Si determinano ora le conseguenza in ambito frequenziale di questa relazione (già validata in ambito temporale).

Ovviamente si ha:
$$
\overline X(f)=\sum_{n=-\infty}^\infty x[n]e^{-j 2 \pi nfT}=\sum_{n=-\infty}^\infty x(nT)e^{-j 2\pi nfT}
$$
^ddd

Si esprimono i campioni del segnale a tempo continuo $x(t)$ attraverso l'integrale di Fourier (antitrasformata) all'istante $t=nT$ (usando la variabile ausiliare $v$)
$$
x(t)=\int_{-\infty}^\infty X(v)e^{j 2\pi vnT}\ dv\Longrightarrow x[n]=x(nT)=\int_{-\infty}^\infty X(v)e^{j 2\pi vnT}\ dv 
$$
Sostituendo alla relazione [[#^ddd|precedente]] si ottiene
$$
\overline X(f)=\sum_{n=-\infty}^\infty \left(\int_{-\infty}^\infty X(v)\ e^{j 2\pi vnT}\ dv\right)e^{-j 2\pi nfT}=\int_{-\infty}^\infty X(v)\sum_{n=-\infty}^\infty e^{-j 2\pi n(f-v)T}\ dv
$$
avendo scambiato l'ordine di somma e integrazione. 

Per semplificare questo risultato, si considera lo sviluppo in serie di Fourier del segnale pettine di Dirac, con coefficienti tutti uguali a $\frac{1}{T}$
$$x(t)=\sum_{n=-\infty}^{\infty} \delta(t-nT)=\sum_{k=-\infty}^\infty X_{k}e^{k \frac{2\pi kt}{T}}= \frac{1}{T}\sum^\infty_{k=-\infty}e^{j \frac{2\pi kt}{T}} $$![[Pasted image 20250419182257.png|center|250]]
Se si calcola la trasformata di Fourier dei due membri della relazione:
$$\sum_{n=-\infty}^\infty e^{ -j 2\pi n }= \frac{1}{T}\sum_{k=-\infty}^\infty \delta \left( f- \frac{k}{T} \right)$$
![[Pasted image 20250419182502.png|center|250]]

Si sostituisce questa espressione in $\overline X(f)=\int_{-\infty}^\infty X(v)\sum_{n=-\infty}^\infty e^{ -j 2\pi n(f-n)T }\ dv$ e si ottiene 
$$
\begin{align}
\overline{X}(f)&= \int_{-\infty}^\infty X(v) \frac{1}{T}\sum_{k=-\infty}^\infty \delta\left( f-v- \frac{k}{T} \right)\ dv = \frac{1}{T}\sum_{k=-\infty}^\infty \int_{-\infty}^\infty X(v)\delta \left( v-\left( f- \frac{k}{T} \right) \right)\ dv 
\end{align}
$$
Infine, per la proprietà campionatrice della funzione $\delta$ si ottiene:
$$
\overline{X}(f)=\frac{1}{T}\sum_{k=-\infty}^\infty X\left( f- \frac{k}{T} \right)
$$

> [!hint] Trasformata di una Sequenza di Campionamento
> Questa relazione mostra che la trasformata di una sequenza ottenuta tramite campionamento di un segnale analogico $x(t)$ si ricava come periodicizzazione della trasformata di $x(t)$, con un periodo di ripetizione in frequenza pari alla frequenza di campionamento $\frac{1}{T}$.

Si considera come esempio lo spettro seguente segnale analogico $x(t)$ (a). Si considerano successivamente i due spettri di $x[n]$ (b e c), ottenute con due frequenze di campionamento diverse.

![[Pasted image 20250506171841.png]]

Nel caso b) si ottiene una banda $B$ sufficientemente larga, si ha così che le replice della trasformata di $x(t)$ siano separate e non sovrapposte.
Lo stesso non si può dire nel caso c), dove la frequenza di campionamento minore da origine ad una banda $B$ non sufficientemente grande, il risultato è la sovrapposizione delle repliche della trasformata di $x(t)$, le quali si sommano e creano un'interferenza.

La conseguenza di una frequenza di campionamento non sufficientemente grande è quella dell'introduzione di un ==*Errore di Aliasing*== nell'intervallo $\left[ - \frac{1}{2T}, \frac{1}{2T} \right]$, creato dalle repliche dello spettro-base, che porta ad una distorsione del segnale.

Se il segnale è a banda limitata, è dunque possibile trovare una condizione che garantisce l'assenza di aliasing. La banda del segnale analogico di partenza $B$ deve essere più piccola dell'estremo superiore dell'intervallo base $\left[ - \frac{1}{2T}, \frac{1}{2T} \right]$, cioè $B\le \frac{1}{2T}$.

> [!gray] Condizione di Nyquist
> Fissata la banda del segnale $B$, la frequenza di campionamento deve essere scelta in modo che valga la seguente condizione
> $$
> f_{c}= \frac{1}{T}\ge 2B
> $$

Tornando al caso precedente, in b si ha che la condizione è rispettata ($f_{c}= .5 B >2B$), perciò l'intervallo base contiene una replica indistorta dello spettro del segnale analogico di partenza.

> [!example]+ Esempio:
> ![[Pasted image 20250506180024.png]]

La condizione di Nyquist pone alcuni vincoli sulla scelta della frequenza di campionamento se si desidera ricostruire un segnale a tempo continuo utilizzandone i campioni. In particolare, il periodo di campionamento deve essere scelto in funzione della banda del segnale analogico.
L'informazione portata da un segnale è data dalla sua forma, ovvero il suo andamento del tempo, quindi i campioni per poter rappresentare questa informazione devono seguire nel modo più fedele possibile questi andamento.

> [!example]+ Esempio:
> ![[Pasted image 20250506181118.png]]

> [!hint] Corrispondenza tra Dominio del Tempo e della Frequenza
> Se si aumenta $f_{c}$, le repliche in frequenza si allontanano. Ovvero se si diminuisce $T$, i campioni si avvicinano

> [!example]+ Esempio: Trasformata di $x[n]=1$
> Ricavare la trasformata di Fourier della sequenza costante $x[n]=1$.
> Si può pensare $x[n]$ come risultante da un campionamento con intervallo $T$ arbitrario del segnale costante a tempo continuo $x(t)=1$.
> Poiché
> $$
> x(t)=1\iff X(f)=\delta(f)
> $$
> Applicando la relazione del campionamento
> $$
> \overline{X}(f)= \frac{1}{T}\sum_{k=-\infty}^\infty X\left( f- \frac{k}{T} \right)
> $$
> Si trova
> $$
> \overline{X}(f)= \frac{1}{T}\sum_{k=-\infty}^\infty \delta \left( f- \frac{k}{T} \right)
> $$
> ![[Pasted image 20250506182513.png]]
> Ricordando che la trasformata per sequenze è periodica, si può limitare il risultato all'intervallo $\left[ -\frac{1}{2T}, \frac{1}{2T} \right]$.

> [!example]+ Esempio: 
> Trovare la trasformata di Fourier delle sequenze
> - $z[n]=\cos(2\pi nf_{0}T)$
> - $y[n]=\sin(2 \pi nf_{0}T)$
> Dalla trasformata della sequenza costante dell'esempio precedente e dal teorema della modulazione si ottiene
> $$
> x[n]=e^{j 2\pi n_{0}T}\iff \overline{X}(f-f_{0})
> $$
> Si ha che, rispetto alla sequenza costante $x[n]=1$
> $$
> e^{j 2\pi n_{0}T}\iff \frac{1}{T}\sum_{k=-\infty}^\infty \delta\left( f-f_{0}- \frac{k}{T} \right)
> $$
> Per cui, utilizzando le formule di Eulero, si trova immediatamente
> $$
> \begin{aligned}
> &\overline{Z}(f)= \frac{1}{2T}\delta(f-f_{0})+\frac{1}{2T}\delta(f+f_{0}) \\
> &\overline{Y}(f) \frac{1}{2jT}\delta(f-f_{0})- \frac{1}{2jT}\delta(f+f_{0})
> \end{aligned} \qquad -\frac{1}{2T}\le f\le \frac{1}{2T}
> $$
> Limitato all'intervallo base della trasformata.

> [!example]+ Esempio:
> La trasformata di Fourier $\overline X(f)$ di una sequenza $x[n]$ è rappresentata nella seguente figura.
> ![[Pasted image 20250507120631.png|center|400]]
> Attraverso la relazione di antitrasformata si trova
> $$
> x[n]=T\int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline X(f)e^{j 2\pi nfT}
> \ df= T\int_{-B}^B e^{j 2\pi nfT}\ df= T \left[ \frac{e^{j 2\pi nfT}}{j 2\pi nT} \right]^B_{-B}=2BT\text{sinc}(2BnT)$$
> Si può ottenere lo stesso risultato pensando a $\overline X(f)$ come  derivante della periodicizzazione di una singola funzione $\text{rect}$:
> $$
> \overline X(f)= \frac{1}{T}\sum_{k=-\infty}^\infty T\cdot \text{rect}\left( \frac{f-\frac{k}{T}}{2B} \right)
> $$
> Quindi la sequenza $x[n]$ si può ricavare come campionamento del segnale a tempo continuo 
> $$
> x(t)=ITCF\left[ T\cdot\text{rect}\left( \frac{f}{2B} \right) \right]=2BT\text{sinc}(2Bt)
> $$
> ![[Pasted image 20250507122423.png|center|450]]

### Interpolazione
La ricostruzione di un segnale a tempo continuo a partire da una sequenza di campioni viene e viene realizzata attraverso un *Interpolatore*.
L'nterpolazione è da considerarsi come una generalizzazione dell'operazione compiuta in pratica da un convertitore D/A in uscita.

Il sistema che esegue l'operazione di campionamento e la successiva interpolazione (senza elaborazioni intermedie) è composto da due blocchi A/D e D/A in cascata:

![[Pasted image 20250507124719.png]]

Ci sono vari tipi di operazione di interpolazione.
### Interpolazione a Mantenimento
L'operazione di *Interpolazione a Mantenimento* da questo componente è la seguente:
- Per costruire il segnale anologico in iscita, il valore $n-$esimo della sequenza di ingresso $x[n]$ viene mantenuto a partire dall'istante $nT$ fino a che non sia disponibile, all'istante $(n+1)T$, il successivo valore $n[n+1]$

![[Pasted image 20250520150919.png]]

Si può quindi scrivere facilmente l'espressione del segnale interpolato $\hat{x}(t)$ in funzione dei valori della sequenza $x[n]$.
$\hat{x}(t)$ è costuito da una successione di impulsi rettangolari di durata $T$, applicata agli istanti $nT$ e di ampiezza pari al relativo valore $n-$esimo:
$$
\hat{x}=\sum^\infty_{n=-\infty} x[n]p(t-nT)
$$
con $p(t)$ impulso rettangolare o più in generale l'impulso di mantenimento.
$$
p(t)=\text{rect}\left( \frac{t-\frac{T}{2}}{T} \right)
$$
![[Pasted image 20250520152613.png]]

Il segnale ricostruito dall'interpolatore a mantenimento è quindi un onda costante a tratti non è una replica indistorta del segnale analogico $x(t)$.

> [!info] Sample & Hold
> L'operazione che direttamente conduce da $x(t)$ al segnale costante a tratti $\hat{x}(t)$ viene indicata in elettronica con il nome *Sample and Hold*

Si calcola adesso la trasformata di Fourier del segnale interpolato per espandere sul comportamento dell'interpolatore a mantenimento nel dominio dell frequenza.
$$
\hat{x}(t)=\sum_{n=-\infty}^\infty x[n]p(t-nT)\Longrightarrow \hat{X}= \sum_{n=-\infty}^\infty x[n]P(f)e^{-j 2\pi nfT}= P(f)\sum_{n=\infty}^\infty x[n]e^{-j 2\pi nfT}=P(f)\overline X (f)
$$
Questa relazione mostra che la trasformata di Fourier di un segnale interpolato è data dal prodotto della trasformata continua dell'impulso di mantenimento $p(t)$ con la trasformata della sequenza $x[n]$.

> [!hint] ->
> Si ricorda che in generale, considerando che 
> $$
> \text{Segnale Continuo }x(f)\iff X(f)
> $$
> Avendo inoltre dimostrato che la trasformata di $F$ della sequenza $x[n]$ è legata a quella del segnale $x(f)$:
> $$
> \text{Segnale campionato discreto }x[n]\iff \overline X(f)=\frac{1}{T}\sum_{k=-\infty}^\infty X\left( f-\frac{k}{T} \right)
> $$
> e
> $$
> \text{Segnale ricostruito continuo }\hat{x}(t)\iff \hat{X}(f)=P(f)\hat{X}(f)=P(f)=\frac{1}{T}\sum_{k=-\infty}^\infty X\left( f-\frac{k}{T} \right)
> $$

Essendo poi $p(t)$ espresso da $p(t)=\text{rect}\left( \frac{t-\frac{T}{2}}{T} \right)$ si ha che
$$
P(f)=T\text{sinc}(fT)e^{-j \pi fT}
$$
e siccome la trasformata della sequenza $x[n]$ è legata a quella del segnale a tempo continuo $x(t)$ ($\overline X(f)= \frac{1}{T}\sum_{k=-\infty}^\infty X\left( f-\frac{k}{T} \right)$), con le opportune sostituzioni si ottiene:
$$
\hat{X}(f)=P(f)\overline X(f)=T\text{sinc}(fT)e^{-j \pi fT}
\frac{1}{T}\sum_{k=-\infty}^\infty X\left( f-\frac{k}{T} \right)$$
Considerando solo lo spettro delle ampiezze:
$$
|\hat{X}(f)|=T\text{sinc}(fT) \frac{1}{T}\sum^\infty_{k=-\infty} X\left( f- \frac{k}{T} \right)$$
![[Pasted image 20250520161251.png|center|400]]

Per esempio, si suppone che la trasformata di Fourier del segnale $x(t)$ di banda $B$ sia espressa da
$$
X(f)= \frac{1}{2B}\cdot \frac{|f|}{B}\text{rect}\left( \frac{f}{2B} \right)$$
(Spettro del segnale continuo)

![[Pasted image 20250520164517.png|center|400]]

Si suppone inoltre che si campioni il segnale con $f_{c}=\frac{1}{T}=2.5B\ge 2B$, ovvero che soddisfi la condizione di Nyquist, e che poi si ricostruisca con il sample & hold.

![[Pasted image 20250520165411.png|center|400]]

Lo spettro di ampiezza della sequenza $x[n]$, formato dalle repliche dello spettro originale con un periodo $f_{c}=2.5B$ (lo spettro NON è normalizzato per $\frac{1}{T}$)
$$
T\hat{X}(f)=\sum_{k=-\infty}^\infty X\left( f- \frac{k}{T} \right)
$$
![[Pasted image 20250520165809.png]]
<sup>La linea grigia indica $T|\hat{X}(f)|$, mentre quella tratteggiata indica $|\text{sinc}(fT)|$ </sup>

![[Pasted image 20250520170321.png]]
![[Pasted image 20250520170446.png]]

Si può risolvere questo problema usando un filtro *Anti-Immagine* all'uscita dell'interpolatore (convertitore D/A). Questo filtro è un passa banda, con banda B, che elimina le immagini dello spettro del segnale interpolato, riducendo il segnale nella banda originaria.

![[Pasted image 20250521103951.png|center|459]]

![[Pasted image 20250521104039.png|center|500]]

L'effetto del filtro anti-immagine in ambito temporale è quello di smussare il segnale costante a tratti (quindi con discontinuità) e ridurlo quindi ad un andamento più simile a quello del segnale analogico originale:

![[Pasted image 20250521104632.png|center|400]]

> [!example]+ Esempio: Segnale Cinematografico
![[Pasted image 20250521110742.png]]
Il procedimento di interpolazione con mantenimento è efficace, cioè non si ha apparente percezione della "granularità" del movimento effettivamente ricostruito, perché l'occhio umano svolge la funzione di filtro anti-immagine.
Il dato, spesso citato, di "tempo di permanenza delle immagini sulla retina" pari a circa $0.1s$ porta a valutare la "banda" dell'occhio umano in circa $10\ Hz$. e quindi l'effetto anti-immagine filtrante è adeguato vista la frequenza di campionamento di $24\ Hz$.
Tuttavia, nelle proiezioni cinematografiche si notano spesso artefatti.
### Interpolazione Cardinale e Teorema del Campionamento
Le fonti di distorsione dell'interpolatore a mantenimento posso essere attribuite alla particolare scelta dell'impulso $p(t)$ utilizzato nella formula di interpolazione. Le discontinuità di questo impluso inducono infatti infiniti punti di discontinuità nel segnale inetrpolato $\hat{x}(t)$. Queste discontinuità causano l'allargamento illimitato della banda di $\hat{x}(t)$ stesso.
Analogamente, la distorsione di ampiezza è da attribuire al fatto che nell'intervallo $\left[ -\frac{1}{2T}, \frac{1}{2T} \right]$ la trasformata $P(f)$ dell'impulso interpolante non assume un valore costante.
Queste osservazioni suggeriscono la possibilità di generalizzare l'operazione di interpolazione, scegliendo un diverso tipo di impulso interpolante $p(t)$.

![[Pasted image 20250521112046.png|center|400]]

Scelte diverse di $p(t)$ corrisponderanno a formule di interpolazione diverse e andamenti temporali e frequenaziali del segnale interpolato $\hat{x}(t)$. 

Lo spettro del segnale interpolato è espresso dalla formula 
$$
\hat{X}(f)=\sum_{n=-\infty}^\infty x[n]P(f)e^{-j 2\pi nfT}=P(f)\sum_{n=-\infty}^\infty x[n]e^{-j 2\pi nfT}=P(f)\overline X(f)
$$
valida per qualunque forma di $p(t)$.
Si sceglie adesso un impulso interpolante tale che la sua trasformata sia costante nell'intervallo $\left[ - \frac{1}{2T}, \frac{1}{2T} \right]$ e nulla al di fuori, cioè $$P(f)=T\text{rect}(fT)$$allora
$$
\hat{X}(f)=P(f)\overline X(f)=T\text{rect}(fT)\cdot \frac{1}{T}\sum_{k=-\infty}^\infty X\left( f- \frac{k}{T} \right)=X(f)
$$
valida ovviamente in assenza di aliasing, ovvero se $x(t)$ ha banda limitata $B$ e se è rispettata la condizione di Nyquist $f_{c}\ge 2B$:

![[Pasted image 20250521112900.png|center|350]]

Questo risultato è di fondamentale importanza, ed è universalmente noto com *Sampling Theorem (C. Shannon)*

> [!gray] Teorema del Campionamento
Un segnale il cui spettro è limitato nella banda $B$ può essere ricostruito esattamente a partire dai propri campioni, purché la frequenza di campionamento non sia inferiore a $2B$

In particolare, pocihé
$$
T\text{rect}(fT)=P(f)\iff p(t)=\text{sinc}\left( \frac{t}{T} \right)
$$
la formula di interpolazione risultante dalla scelta di $p(t)$ è
$$
\hat{x}=\sum_{n=-\infty}^\infty x[n]\text{sinc}\left( \frac{t-nT}{T} \right)
$$
che è nota come ==*Formula di Interpolazione Cardinale*==.

> [!info] Significato di $\text{sinc}(\cdot)$
> Il nome $\text{sinc}$, assegnato a suo tempo alla funzione $\frac{\sin(\pi\alpha)}{\pi\alpha}$ significa infatti *Seno Cardinale*, con riferimento al ruolo cardine assunto nella formula precedente dall'interpolazione stessa.

![[Pasted image 20250521115718.png]]

Se il ricampionamento del segnale interpolato al generico istante $t=kT$, per le proprietà della funzione $\text{sinc}$, solo il $k-$esimo fra tutti gli impulsi della sommatoria produce contributo non nullo, e pari proprio al valore $x[k]=x(kT)$ del campione del segnale di partenza. si ha infatti:
$$
\hat{x}(kT)=\sum_{n=-\infty}^\infty x[n]\text{sinc}(k-n)=\sum_{n=-\infty}^\infty x[n]\delta[k-n]=x[k]=x(kT)
$$
==Questo risultato conferma che il segnale interpolato coincide con il segnale di partenza negli istanti di campionamenti==

Se si considera un qualunque altro istante non coincidente con uno di quelli di campionamento, si nota che il valore del segnale interpolato viene ottenuto combinando linearmente tutti gli infiniti campioni $x[n]$ del segnale $x(t)$
$$
\hat{x}(t)=\sum^\infty_{n=-\infty}x[n]\text{sinc} \left( \frac{t-nT}{T} \right)
$$

> [!hint] ->
> In  altre parole, la ricostruzione di un segnale a banda limitata a un certo istante richiede la conoscenza di tutta la sequenza di campioni del segnale stesso, in istanti sia precedenti a quello considerato, sia successivi.
> 

Pertanto la formula di interpolazione cardinale, sebbene abbia una grande rilevanza teorica, è inutilizzabile bella sua forma esatta nelle applicazioni pratiche:
1. Sono in teoria richiesti infiniti termini di una sommatoria per ricostruire il segnale originario.
2. Una ricostruzione in tempo reale è impossibile perché richiederebbe la conoscenza di valori del segnale in istanti successivi a quello di interpolazione (interpolatore non causale).

> [!example]+ Esempio: Interpolazione Lineare
> Si suppone che l'impulso $p(t)$ dell'interpolatore sia
> $$
> p(t)=\left( 1- \frac{|t|}{T} \right)\text{rect}\left( \frac{t}{2T} \right)= \text{tr}\left( \frac{t}{T} \right)
> $$
> Questo impulso rettangolare è caratteristico della formula di *Interpolazione Lineare*.
> ![[Pasted image 20250521123654.png|center|400]]
> 
> Il segnale interpolato $\hat{x}(t)$ è costituito da una spezzata che collega i punti corrispondenti a campioni consecutivi del segnale $x(t)$, $\hat{x}(t)$ rappresenta la cosiddetta interpolazione lineare della sequenza si campioni.
> 
> ![[Pasted image 20250521124021.png|center|450]]
> 
> Infatti, osservando che in un generico intervallo $[(k-1)T,\ kT)$ compreso fra due campioni consecutivi $x[k-1]$ e $x[k]$, solo due addendi della sommatoria danno contributo non nullo cioè quelli con $n=k-1$ e $n=k$. In questo intervallo il segnale interpolato vale allora
> $$
> \begin{align}
> \hat{x}(t)&=x[k-1]p(t-(k-1)T)+x[k]p(t-kT) \\
> &=x[k-1]\left( 1- \frac{t-kT+T}{T} \right)+x[k]\left( 1+ \frac{t-kT}{T} \right) \\
> &= x[k]+\{x[k]-x[k-1]\}\left( \frac{t-kT}{T} \right)
> \end{align}
> $$
> ![[Pasted image 20250521124452.png|center|250]]
> La quale rappresenta l'equazione del segmento di retta che collega i punti ai campioni $x[k-1]$ e $x[k]$.
> 
> La trasformata di Fourier del segnale $\hat{x}(t)$ è data ancora da:
> $$
> \hat{X}(f)=P(f)\overline X(f)
> $$
> con 
> $$
> P(f)=T\text{sinc}^2(fT)
> $$
> Lo spettro del segnale interpolato ha un andamento qualitativamente non dissimile da quello relativo all'interpolatore con mantenimento.
> 
> ![[Pasted image 20250521124814.png|center|500]]
> 
> Il segnale interpolato linearmente ha un lo spettro di ampiezza con immagini più attenuate rispetto al caso dell'interpolatore con mantenimento.
> Lo spettro $P(f)$ dell'impulso interpolatore decresce più rapidamente al crescere della frequenza nel caso di interpolazione lineare che nel caso del mantenimento
> 
> ![[Pasted image 20250521125049.png|center|500]]
> 
> Se si confronta il segnale generato da un interpolatore a mantenimento con quello generato da un interpolatore lineare si osserva che:
> - Il primo presenta discontinuità di prima specie, il secondo è un segnale continuo
> - Il primo segnale avrà un maggiore contenuto di componenti ad alte frequenza rispetto al secondo
> 
> ![[Pasted image 20250521125321.png|center|500]]
> 
> Si nota che la distorsione di banda è abbastanza evidente. Questo deriva dalla particolare forma dello spettro del segnale di partenza in cui sono più ampie le componenti vicine al limite di banda $B$.
> 
> Se lo spettro di partenza è invece più decisamente passa-basso (ovvero con componenti via via digradanti all'aumentare della frequenza), la trasforata del segnale interpolato linearmente presenterà una distorsione di banda piuttosto ridotta.
> 
> ![[Pasted image 20250521125619.png|center|500]]

___

## Trasformata Discreta di Fourier
Una sequenza $x[n]$ è periodica se esiste un numero intero positivo $N_{0}$ (periodo della sequenza) tale che
$$
x[n]=x[n+N_{0}]\quad \forall n
$$
Una sequenza $x[n]$ periodica di periodo $N_{0}$ è individuata quindi da $N_{0}$ numeri reali (o complessi) che rappresentano i valori assunti da $x[n]$ in un periodo , as  esempio nell'intervallo $n=0,1,\ldots,N_{0}-1$.

Si osserva che il campionamento di un segnale periodico a tempo continuo di periodo $T_{0}$ non genera necessariamente una sequenza periodica di periodo $N_{0}$:
- Se $T$ è il periodo di campionamento, affinché si ottenga una sequenza periodica è necessario che un numero intero $N_{0}$ di intervalli di campionamento sia esattamente pari a un qualunque numero intero $M_{0}$ di periodi di ripetizione del segnale originario: $$N_{0}T=M_{0}T_{0}$$ Ciò significa che il rapporto $\frac{T}{T_{0}}$ deve essere un numero razionale.

In pratica, gli impulsi di campionamento del convertitore $A/D$ devono essere sincronizzati con il segnale periodico analogico, ovvero avere legame preciso con il periodo di ripetizione del segnale $x(t)$. ==Quindi se il rapporto $\frac{T}{T_{0}}$ non è un numero razionale, l'operazione di campionamento non da origine ad una sequenza periodica.==

![[Pasted image 20250526122032.png|center|450]]

> [!gray] Trasformata e Antitrasforamata Discreta di Fourier
> - Si suppone che $x[n]$ sia una sequenza periodica di periodo $N_{0}$. Essa può essere rappresentata mediante uno sviluppo del tutto analogo alla serie di Fourier per i segnali periodici a tempo continuo, chiamato ==*Serie Discreta* o *Antitraformata Discreta di Fourier*== $$x[n]=\frac{1}{N_{0}}\sum_{k=0}^{N_{0}-1}\overline X_{k}e^{j \frac{2\pi kn}{N_{0}}}\quad \forall n\in[0,N_{0}-1]$$
> - La sequenza dei coefficienti discreti di Fourier è chiamata ==*Trasformata Discreta di Fourier* (*DTF*)== della sequenza periodica$$
> \overline X_{k}=\sum_{n=0}^{N_{0}-1}x[n]e^{-j \frac{2\pi kn}{N_{0}}}\quad \forall k\in[0,N_{0}-1]
> $$

> [!info] NB
> Il fattore di normalizzazione $\frac{1}{N_{0}}$ può essere messo indifferentemente nella trasformata diretta o nella trasformata inversa. È importante quindi essere consistenti con la notazione scelta. Verrà successivamente applicata la seguente notazione:
> $$
> IDTF:\ x[n]=\frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k} e^{j \frac{2\pi kn}{N_{0}}}\qquad DTF:\ \overline X_{k}=\sum^{N_{0}-1}_{n=0} x[n]e^{-j \frac{2\pi kn}{N_{0}}}
> $$

Si notano le analogie tra queste relazioni e le corrispondenti relazione di sintesi e analisi per i segnali periodici a tempo continuo:
- Per i segnali periodici a tempo continuo la rappresentazione mediante serie di Fourier comporta una somma infinita di termini $$x(t)=\sum^\infty_{k=-\infty} X_{k}e^{j \frac{2\pi kt}{T_{0}}}\quad X_{k}=\frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)e^{-j \frac{2\pi kt}{T_{0}}}\ dt$$
- Nel caso di sequenze periodiche, la rappresentazione mediante antitrasformata discreta consiste in una somma con un numero finito di addendi $$ x[n]= \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k}e^{j \frac{2\pi kn}{N_{0}}}\quad \overline X_{k}=\sum_{n=0}^{N_{0}-1}x[n]e^{-j \frac{2\pi kn}{N_{0}}}$$
Infatti, la trasformata di una sequenza periodica di periodo $N_{0}$ è essa stessa con il medesimo periodo:
$$\begin{align}
&\overline X_{k+N_{0}} = \sum^{N_{0}-1}_{n=0}x[n]e^{-j \frac{2\pi(k+N_{0})n}{N_{0}}}=\sum^{N_{0}-1}_{n=0}x[n]e^{-j \frac{2\pi kn}{N_{0}}}\underset{=1}{e^{-j 2\pi n}}= \sum^{N_{0}-1}_{n=0}x[n]e^{-j \frac{2\pi kn}{N_{0}}}=\overline X_{k} \\
&\Longrightarrow \overline X_{k+N_{0}}=\overline X_{k}
\end{align}$$
La sequenza periodica è espressa, come nel caso del segnale periodico a tempo continuo, da una somma di oscillazioni sinusoidali a frequenza armoniche (cioè multiple di una frequenza fondamentale).
Si riscrive l'equazione di sintesi nel seguente modo:
$$
x[n]=\frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k} e^{j \frac{2\pi kn}{N_{0}}}=\frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k}e^{\frac{j2\pi k}{N_{0}T}nT}= \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0} \overline X_{k}e^{j 2\pi f_{k}nT}
$$
I valori esponenziali complessi nella scomposizione oscillano alle frequenze $f_{k}= \frac{k}{N_{0}T},\ k=0,\ldots,N_{0}-1$ che si chiamano *Armoniche Relative al Periodo di Ripetizione $N_{0}$*, ovvero la frequenza dondamenrale $\frac{1}{N_{0}T}$ (essendo $N_{0}T$ il periodo del segnale, numero di campioni per passo di campionamento).

Anche in questo caso si possono osservare le analogie tra le corrispondenti relazioni di sintesi e analisi per i segnali periodici:
$$\begin{align}
& x[n]=\sum^{N_{0}-1}_{k=0}\overline X_{k}e^{j \frac{2\pi kn}{N_{0}}}& &x(t)=\sum^\infty_{k=-\infty} \overline X_{k}e^{j \frac{2\pi kt}{T_{0}}}& \\
& X_{k}=\frac{1}{N_{0}}\sum^{N_{0}-1}_{n=0}x[n]e^{-j \frac{2\pi jn}{N_{0}}}& &X_{k}=\frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{{-\frac{T_{0}}{2}}}x(t)e^{-j \frac{2\pi kt}{T_{0}}}\ dt&
\end{align}$$
- La differenza principale tra le equazioni di analisi a tempo continuo e discreto consiste nell'integrale per ricavare il coefficiente di Fourier, che viene calcolato sull'insieme simmetrico $\left( -\frac{T_{0}}{2}, \frac{T_{0}}{2} \right)$, mentre la trasformata viene calcolata come sommatoria di un intervallo asimmetrico $[0, N_{0}-1]$. 

> [!info] Motivazione
> Questo perché quando $N_{0}$ è un numero dispari, è semplice calcolare la trasformata discreta anche sull'intervallo simmetrico $\left[ \frac{-N_{0}-1}{2} ,\frac{N_{0}-1}{2}\right]$, ma se $N_{0}$ è un numero pari non è possibile  trovare un intervallo simmetrico di ampiezza pari a $N_{0}$. Si preferisce quindi unificare i due casi usando l'intervallo asimmetrico destro $[0,N_{0}-1]$

> [!gray] ->
> Si dimostra adesso che dalla relazione di sintesi, ovvero l'antitrasformata discreta, discende la relazione di analisi ($\overline X_{k}=\sum^{N_{0}-1}_{n=0}e^{-j \frac{2\pi kn}{N_{0}}}$) (trasformata discreta). Si parte quindi dall'equazione
> $$
> x[n]=\frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}e^{j \frac{2\pi kn}{N_{0}}}
> $$
> e si moltiplicano entrambi i membri per il fattore $e^{-j \frac{2\pi nm}{N_{0}}}$ (con $0\le m\le N_{0}-1$) e si effettua l'operazione di somma sul periodo rispetto all'indice $n$:
> $$
> \Longrightarrow \sum^{N_{0}-1}_{{n=0}}x[n]e^{-j \frac{2\pi nm}{N_{0}}}= \frac{1}{N_{0}} \sum^{N_{0}-1}_{n=0}\sum^{N_{0}-1}_{k=0} \overline X_{k}e^{j \frac{2\pi nk}{N_{0}}}e^{-j \frac{2\pi nm}{N_{0}}}
> $$
> Sviluppando poi il secondo membro e scambiando le due sommatorie si ricava
> $$
> \sum^{N_{0}-1}_{n=0}\sum^{N_{0}-1}_{k=0}\overline X_{k} e^{-j \frac{2\pi mn}{N_{0}}}e^{j \frac{2\pi nk}{N_{0}}}=\sum^{N_{0}-1}_{k=0}\overline X_{k} \sum^{N_{0}-1}_{n=0} e^{j \frac{2\pi n(k-m)}{N_{0}}}
> $$
> La seconda sommatoria al secondo membro diviene (usando la formula $\sum^{N-1}_{n=0}q^n= \frac{1-q^N}{1-q}$)
> $$
> \sum^{N_{0}-1}_{n=0} e^{j \frac{2\pi n(k-m)}{N_{0}}}=\sum^{N_{0}-1}_{n=0}\left( e^{j \frac{2\pi(k-m)}{N_{0}}} \right) = \frac{1-e^{j 2\pi
> (k-m)}}{1-e^{j \frac{2\pi(k-m)}{N_{0}}}}=0\quad k\ne m
> $$
> Essendo $e^{j2\pi(k-m)}=1$, mentre per $k=m$ si ha
> $$
> \sum^{N_{0}-1}_{n=0} \overline X_{k}e^{-j \frac{2\pi mn}{N_{0=}}}=\sum^{N_{0}-1}_{n=0}1=N_{0}$$
> Pertanto, esprimendo la condizione $$\sum^{N_{0}-1}_{n=0}e^{j \frac{2\pi n(k-m)}{N_{0}}}=\begin{cases}N_{0}& \text{per }n=m \\ 0 & \text{per } n\ne m\end{cases}= \delta[k-m]N_{0}$$
> si trova 
> $$
> \frac{1}{N_{0}}\sum^{N_{0}-1}_{n=0}\sum^{N_{0}-1}_{k=0} \overline X_{k}e^{-j \frac{2\pi mn}{N_{0}}}e^{j \frac{2\pi nk}{N_{0}}}= \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k} \delta[k-m]N_{0}= \frac{1}{N_{0}}N_{0}\overline X_{m}
> $$
> e per sostituzione si ricava infine 
> $$
> \sum^{N_{0}-1}_{n=0} x[n]e^{-j \frac{2\pi mn}{N_{0}}}= \overline X_{m}
> $$
> Da cui segue immediatamente l'equazione di analisi.

> [!example]+ Esempio:
> Calcolare la trasformata discreta della sequenza $x[n]$ periodica di periodo $N_{0}=8$, definita sul periodo-base come
> $$
> x[n]=\begin{cases}
> 1 & 0\le n\le 3 \\
> 0 & 4\le n\le 7
> \end{cases}
> $$
> Questa sequenza è un treno di impulsi rettangolari a tempo discreto
> 
> ![[Pasted image 20250527144045.png|center|400]]
> 
> La trasformata discreta è
> $$
> \overline X_{k}=\sum^{N_{0}-1}_{n=0}x[n]e^{-j \frac{2\pi kn}{N_{0}}}= \sum^{3}_{n=0}e^{-j \frac{2\pi kn}{8}}=\sum^{3}_{n=0}\left( e^{-j \frac{\pi k}{4}} \right)^n
> $$
> Si può applicare la formula della somma di una progressione geometrica quando $k\ne 0$, mentre quando $k=0$ si ha banalmente $\overline X_{0}=4$.
> Quindi riassumendo si ha:
> $$
> \overline X_{k}=\begin{cases}
> 4 & k=0 \\
> \frac{1-e^{-jk\pi}}{1-e^{-j \frac{\pi}{4}}} & k\ne 0
> \end{cases}
> $$
> Si può verificare che 
> $$\begin{align} 
> &\overline X_{2}=\overline X_{4}=\overline X_{6}=0 \\
> &|\overline X_{1}|=|\overline X_{7}|= \frac{1}{8\sin\left( \frac{\pi}{8} \right)}\simeq 0.327\cdot 8 \\
> &|\overline X_{3}|=|\overline X_{5}|= \frac{1}{8\sin\left( \frac{3\pi}{8} \right)}\simeq 0.135\cdot 8
> \end{align}$$
> e lo spettro di ampiezza è
> 
> ![[Pasted image 20250527144908.png|center|400]]

## Proprietà della DFT
Analogamente alla trasformata di Fourier per sequenze, anche per la DTF è possibile dimostrare delle proprietà importanti. Verrà usata la notazione 
$$
DTF_{N_{0}}\{X[n]\}=\overline X_{k}\quad 0\le n, \ k\le N-1
$$
### Proprietà di Linearità

> [!gray] ->
> $$
> DTF_{N_{0}}\{a x[n]+by[n]\}=a \overline X_{k}+b \overline Y_{k}
> $$
### Proprietà di Traslazione Circolare

> [!gray] ->
> $$
> DTF_{N_{0}}\{x[n-n_{0}]\}=e^{-j \frac{2\pi kn_{0}}{N_{0}}}\overline X_{k}
> $$
> **Dimostrazione:**
> $$\begin{align}
> DTF_{N_{0}}\{x[n-n_{0}]\}&= \sum^{N-1}_{n=0}x[n-n_{0}]e^{-j \frac{2\pi}{N_{0}}kn}\overset{\small{p=n- n_{0}\Rightarrow n=p+n_{0}}}{=}\sum^{N_{0}-1-n_{0}}_{p=-n_{0}}x[p]e^{-j \frac{2\pi}{N_{0}}k(p+n_{0})} \\
> &= e^{-j \frac{2\pi}{N_{0}}kn_{0}}\sum^{N_{0}-1-n_{0}}_{p=-n_{0}}x[p]e^{-j \frac{2\pi}{N_{0}}kp}= e^{-j \frac{2\pi}{N_{0}}kn_{0}}\sum^{N-1}_{p=0}x[p]e^{-j \frac{2\pi}{N_{0}}kp} \\
> &=e^{-j \frac{2\pi kn_{0}}{N_{0}}}\overline X_{k}
> \end{align}$$
> Nel penultimo passaggio viene sfruttata la periodicità della sequenza $x[n]$ e della funzione esponenziale all'interno della sommatoria.
> ![[Pasted image 20250526172244.png|center|300]]
> Questo fatto permette di sostituire il termine relativo a $p=-n_{0}$ con quello relativo a $p=N_{0}-n_{0}$, il termine relativo a $p=-n_{0}+1$ con quello relativo a $p=N-n_{0}+1$ etc. in modo tale che la sommatoria da $-n_{0}$ a $N_{0}-1-n_{0}$ è uguale alla sommatoria da $0$ a $N_{0}-1$.
> 
> Poiché sia la sequenza $x[n]$ che la sua versione traslata $x[n-n_{0}]$ sono sequenze periodiche, è interessante ricavare la relazione esistente tra i due periodi delle due sequenze.
> ![[Pasted image 20250526172529.png|center|500]]
> Dall'osservazione di questi, si nota che, a causa della periodicità, i campioni che escono a destra dell'intervallo $[0,5]$, a causa della traslazione, rientrano a sinistra in tale intervallo. Tale effetto giustifica la denominazione di traslazione circolare data all'operazione

### Proprietà della Traslazione in Frequenza
> [!gray] ->
> $$
> DTF_{{N_{0}}} \left\{ x[n]e^{j \frac{2\pi k_{0}n}{N_{0}}} \right\}=\overline X_{k-k0}
> $$pru
### Proprietà di Inversione Temporale

> [!gray] ->
> $$\begin{align}
> &DTF_{N_{0}}\{x[-n]\}=\overline X_{-k}=\overline X_{N_{0}-k} \\
> & DTF_{N_{0}}\{x[-n]\}= \overline X^*_{k}\text{ se } x[n] \text{ è reale}
> \end{align}$$
> ![[Pasted image 20250526173135.png|center|500]]
> $$
> DTF_{N_{0}}\{x[-n]\}=\overline{X}_{-k}= \overline X_{{N_{0}-k}}
> $$
> **Dimostrazione:**
> $$\begin{align}
> DTF_{N_{0}}\{x[-n]\}=& \sum^{N_{0}-1}_{n=0}x[-n]e^{-j \frac{2\pi}{N_{0}}kn}= \overset{\begin{aligned}
> &n=N_{0}-p \\
> &p=N_{0}-m
> \end{aligned}}{\sum^{N-1}_{n=0}x[N_{0}-n]e^{-j \frac{2\pi}{N_{0}}kn}}=\overset{\overset{=1}{e^{-j \frac{2\pi k\cancel{N_{0}}}{\cancel{N_{0}}}}}\cdot e^{+j \frac{2\pi kp}{N_{0}}}}{\sum^{N_{0}}_{p=1}x[p]e^{-j \frac{2\pi}{N_{0}}k(N_{0}-p)}} \\
> =& \overset{=e^{-j \frac{2\pi}{N_{0}}(-k)\cdot p}}{\sum^{N-1}_{p=0}x[p]e^{j \frac{2\pi}{N_{0}}kp}}=\overline X_{-k}=\overline X_{N_{0}-k}
> \end{align}$$
> Dove nel primo passaggio è stata usata la periodicità della sequenza $x[n]$ e nel penultimo passaggio, per cambiare gli indici della sommatoria, è stata usata la proprietà di periodicità della sequenza e della funzione esponenziale.
### Proprietà di Coniugazione

> [!gray] ->
> $$
> DTF_{N_{0}}\{x^*[n]\}=\overline X^*_{-k}=\overline X^*_{N_{0}-k}
> $$
### Proprietà di Simmetria per Sequenze Reali

> [!gray] ->
> Per una sequenza reale $x[n]$, si ha:
> $$
> DTF_{N_{0}}\{x[n]\}=DTF_{N_{0}}\{x^*[n]\}\longrightarrow \overline X_{k}= \overline X^*_{-k} = \overline X^*_{N_{0}-k}
> $$
> da cui derivano le seguenti proprietà di simmetria di modulo e la fase di $X[k]$:
> $$
> |\overline X_{k}|= |\overline X_{-k}|= |\overline X_{N_{0-k}}|\qquad \angle \overline X_{k}=-\angle \overline X_{-k}=-\angle \overline X_{N_{0}-k}
> $$
> Tali relazioni implicano che il modulo della sequenza $X[k]$ è simmetrico rispetto al valore $k=\frac{N}{2}$, mentre la fase è antisimmetrica a tala valore.
> - Per sequenze di lunghezza pari, il centro di simmetria coincide con un campione della lunghezza della sequenza![[Pasted image 20250527142512.png|center|400]]<sup>In questo cao per $N_0=6$, si ha che $k=3$</sup>
> - Per sequenze di lunghezza dispari, invece il centro di simmetria coincide con un punto equidistante tra due campioni ![[Pasted image 20250527142716.png|center|400]]

### Teorema di Parseval
> [!gray] ->
> $$
> \sum^{N_{0}-1}_{n=0}x[n]y^*[n]=\frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k}\overline Y^*_{k}\qquad \sum^{N_{0}-1}_{n=0}|x[n]|^2= \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0} |\overline X_{k}|^2
> $$
> **Dimostrazione:**
> $$\begin{align}
> \sum^{N_{0}-1}_{n=0}x[n]y^*[n]=&\sum^{N_{0}-1}_{n=0}x[n]\left( \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0} \overline Y_{k} e^{j \frac{2\pi kn}{N_{0}}} \right)^*= \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline Y^*_{k}\sum^{N_{0}-1}_{n=0}x[n]e^{-j \frac{2\pi kn}{N_{0}}}= \frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k}\overline Y^*_{k}
> \end{align}$$
> Ponendo $x[n]=y[n]$ si ottiene la seconda relazione

### Teorema del Prodotto

> [!gray] ->
> Si considera adesso una sequenza periodica $p[n]$ data dal prodotto fra le sequenza $x[n]$ e la sequenza $y[n]$ entrambe periodiche di periodo $N_{0}$
> $$
> p[n]=x[n]y[n]
> $$
> e si calcola poi la sua trasformata discreta di Fourier
> $$\begin{align}
> \overline P_{k}=& \sum^{N_{0}-1}_{n=0}p[n]e^{-j \frac{2\pi nk}{N_{0}}}=\sum^{N_{0}-1}_{n=0}x[n]y[n]e^{-j \frac{2\pi nk}{N_{0}}}= \sum^{N_{0}-1}_{n=0} \frac{1}{N_{0}}\sum^{N_{0}-1}_{m=0}\overline X_{m} e^{j \frac{2\pi nm}{N_{0}}}\cdot y[n]e^{-j \frac{2\pi nk}{N_{0}}} \\
> \end{align}$$
> Dove $x[n]$ è stata composta in serie discreta di Fourier. In questo passaggio è stata usata una variabile muta $m$ nell'operazione di antitrasformazione per non creare ambiguità con la variabile $k$ da cui dipende la trasformata.
> Invertendo l'ordine delle sommatorie si ricava
> $$
> \overline P_{k}= \sum^{N_{0}-1}_{m=0}\overline X_{m} \frac{1}{N_{0}}\sum^{N_{0}-1}_{n=0}y[n]e^{-j \frac{2\pi n(k-m)}{N_{0}}}= \frac{1}{N_{0}}\sum^{N_{0}-1}_{m=0}\overline X_{m} \overline Y_{{k-m}}= \frac{1}{N_{0}} \cdot \overline X_{k}\otimes \overline Y_{k}
> $$
> In cui la convluzione fra le trasformate discrete è una somma di concoluzione ciclica tra sue sequenze periodiche $\overline X_{k}$ e $\overline Y_{k}$ in ambito frequenziale. 
> 
> ==In conclusione:==
> $$
> p[n]=x[n]y[n]\iff \overline P_{k}= \frac{1}{N_{0}} \sum^{N_{0}-1}_{m=0}\overline X_{m}\overline Y_{k-m}= \frac{1}{N_{0}}\cdot \overline X_{k}\otimes \overline Y_{k}
> $$

### Teorema della Convoluzione

> [!gray] ->
> Si considera la sequenza $z[n]$ come somma di convoluzione ciclica o circolare tra le due sequenze $x[n]$ e $y[n]$, periodiche di periodo $N_{0}$
> $$
> z[n]=x[n]\otimes y[n] = \sum^{N_{0}-1}_{m=0} x[m] y[n-m]=\sum^{N_{0}-1}_{m=0}y[m]x[n-m]
> $$
> Questa somma di convoluzione gode delle stesse proprietà della somma di convoluzione tra sequenze aperiodiche (commutativa, associativa, distributova).
> Si calcola la trasformata discreta di $z[n]$
> $$\begin{align}
> \overline Z_{k}&=\sum^{N_{0}-1}_{n=0}z[n]e^{-j \frac{2\pi nk}{N_{0}}}=\sum^{N_{0}-1}_{n=0}\sum^{N_{0}-1}_{m=0}x[m]y[n-m] e^{-j \frac{2\pi nk}{N_{0}}}= \sum^{N_{0}-1}_{m=0}x[m]\sum^{N_{0}-1}_{n=0}y[y-m]e^{-j \frac{2\pi nk}{N_{0}}} \\
> &=\sum^{N_{0}-1}_{m=0}x[m]\overline Y_{k}e^{-j \frac{2\pi mk}{N_{0}}}=\overline Y_{k}\sum^{N_{0}-1}_{m=0}x[m]e^{-j \frac{2\pi mk}{N_{0}}}=\overline X_{k}\cdot \overline Y_{k}
> \end{align}$$

In conclusione, si può enunciare il teorema della convoluizione (ciclica) nella forma
$$
x[n]\otimes y[n]\iff \overline X_{k}\cdot \overline Y_{k}
$$
### Relazioni tra Convoluzione Lineare e Convoluzione Circolare
Si studiano adesso le relazioni che esistono tra convoluzione discreta, lineare e concoluzione circolare di due sequenze di lunghezza finita.
Siano data $x[n]$ e $h[n]$ due sequenze di lunghezza $L$ e $M$, ovvero il supporto sul quale le sequenze hanno campioni nulli, è rispettivamente $[0,L-1]$ e $[0,M-1]$

![[Pasted image 20250527152223.png|center|450]]

- Per quanto riguarda la convoluzione circolare, considerando che le due sequenze hanno lunghezza diversa, è necessario fissare un periodo comune $N$, con il quale eseguire l'estensione periodica delle sequenze. L'unico vincolo che si pone è che $N\ge \text{max}(L,M)$. Fissato $N$, è necessario appendere in fondo alle sequenze un certo numero di zeri ($N-L$ e $N-M$, rispettivamente per $x[n]$ e $h[n]$) prima di estendere periodicamente le due sequenze.

La convoluzione circolare tra due sequenze è quindi data da 
$$
y_{c}[n]=x[n]\otimes h[n]=\sum^{N-1}_{k=0}x[k]h[n-k]
$$
È importante stabilire la relazione esistente tra $y_{l}[n]$ e $y_{c}[n]$. Senza ambiguità, si assume $L>M$
$$
\begin{align}
&y_{c}[n]=x[n]\otimes h[n]=\sum^{N-1}_{k=0}x[k]h[n-k] \\
& y_{l}[n]=x[n]*h[n]=\sum^{\infty}_{k=-\infty} x[k]h[n-k]
\end{align}
$$
Poiché tale relazione dipende dalla scelta di $N$, si distinguono due casi
...
ESERCIZI...
## Complessità di Calcolo della Trasformata Discreta 
Si considera di avere in generale $x[n]$ a valori complessi, cioè $z=a+jb$, e che gli esponenziali complessi siano precalcolati, cioè già in memoria. Per il calcolo di un singolo campione $X[k]$ è necessario eseguire
$$
\overline X_{k}=x[0]e^{-j0}+ x[1]e^{-j \frac{2\pi k}{N_{0}}}+x[2]e^{-j \frac{2\pi 2k}{N_{0}}}+\ldots+x[N_{0}-1]e^{-j \frac{2\pi(N_{0}-1)k}{N_{0}}}
$$
con:
- $N_{0}$ moltiplicazioni complesse
- $N_{0}-1$ addizioni complesse
La maggior parte degli elaboratori traducono le operazioni nel campo complesso in operazioni nel campo reale, eseguite tra le parti reali e immaginarie dei numeri complessi coinvolti, cioè
- Per eseguire un'addizione complessa è necessario eseguire $2$ addizioni reali:
$$(a+jb)+(c+jd)=(a+c)+j(b+d)$$
- Per eseguire una moltiplicazione complessa è necessario eseguire $4$ moltiplicazioni reali e $2$ addizioni reali
$$
(a+jb)\cdot(c+jd)= (a\cdot c- b\cdot d)+j(a\cdot d+ b\cdot c)
$$
Per eseguire il calcolo di un singolo campione $X[k]$
- Occorre eseguire $N_{0}-1$ addizioni complesse, e $N_{0}$ moltiplicazioni complesse
	- Addizione complessa: 2 addizioni reali
	- Moltiplicazione complessa: 4 moltiplicazioni reali + 2 addizioni reali = 6 operazioni reali
- Sono necessarie complessivamente 
	- $(N_{0}-1)*2= 2N_{0}-2$ addizioni reali
	- $4N_{0}$ moltiplicazioni reali e $2N_{0}$ addizioni reali
In tutto $2N_{0}-2+4N_{0}+2N_{0}=8N_{0}-2$ operazioni reali per ogni valore di $k$.

Poiché la sequenza è costituita da $N_{0}$ coefficienti DFT, il numero complessivo di operazioni da compiere per calcolare la trasformata discreta di Fourier (TDF) di una sequenza periodica di periodo $N_{0}$ è pari a 
$$
N_{TDF}(N_{0})=(8N_{0}-2)N_{0}=8N_{0}^2-2N_{0}\simeq 8N^2_{0}
$$
**Complessità Quadratica Rispetto al Numero di Campioni**

Riassumendo:
![[Pasted image 20250527155325.png]]

Se $N_{0}=1024=2^{10}$ e, supponendo di avere in processore con frequenza di clock $f_{{clk}}=1 \ GHz$, il tempo per il calcolo della DTF è:
$$
T_{calcolo}=\frac{NTDF(N_{0})}{f_{clk}}= 8\cdot 2^{20}\cdot 10^{-9}\simeq 8\cdot 10^6\cdot 10^{-9}= 8ms
$$
Un deciso miglioramento della velocità di elaborazione è stato raggiunto utilizzando un algoritmo veloce di calcolo che sfrutta le simmetrie dei fattori esponenziali riduce la complessità.
Tale algoritmo, noto come *Fast Fourier Transform (FFT)* a parità di clock permette di ridurre notevolmente i tempi di calcolo. Si applica se $N_{0}=2^M$
### Fast Fourier Transform (FFT)
FFT è un algoritmo a decimazione nel tempo: si ottiene suddividendo gli addendi in 2 gruppi
$$\begin{align}
\overline X_{k}&= \sum^{\frac{N_{0}}{2}-1}_{m=0}x[2m]e^{-j \frac{2\pi(2m)}{N_{0}}}+\sum^{\frac{N_{0}}{2}-1}_{m=0} x[2m+1]e^{-j \frac{2\pi(2m+1)}{N_{0}}} \\
&=\overset{\overline P_{k}}{\overline{\sum^{\frac{N_{0}}{2}-1}_{m=0}x[2m]e^{-j \frac{2\pi km}{\frac{N_{0}}{2}}}}}+e^{-j \frac{2\pi k}{N_{0}}}\cdot \overset{\overline D_{k}}{\overline{\sum^{\frac{N_{0}}{2}-1}x[2m+1]e^{-j \frac{2\pi km}{\frac{N_{0}}{2}}}}}
\end{align}$$
- Il primo termine è la trasformata della sequenza ottenuta dai $\frac{N_{0}}{2}$ campioni di indice pari a $x[n]$.
- Il secondo termine è la trasformata della sequenza ottenuta dai $\frac{N_{0}}{2}$ campioni di indici dispari di $x[n]$.
Questa scomposizione è ricorsiva nell'ordine, cioè la trasformata di ordine $N_{0}$ è espressa come combinazione lineare di due trasformate di ordine $\frac{N_{0}}{2}$.
Il numero di operazioni $N_{FFT}(N_{0})$ necessarie a calcolare la trasformata di ordine $N_{0}$ secondo questo criterio può allora essere espresso in maniera ugualmente ricorsiva sulla base di questa scomposizione
$$
N_{FFT}(N_{0})=N_{FFT}\left( \frac{N_{0}}{2} \right)+N_{FFT}\left( \frac{N_{0}}{2} \right)+6N_{0}+2N_{0}
$$
Avendo tenuto conto del fatto che, per ogni valore di $k$, è necessario moltiplicare $D_{k}$ per un esponenziale complesso precalcolato (6 operazioni reali) e quindi effettuare la somma con $P_{k}$ (2 operazioni reali $\overset{\overline P_{k}}{\overline{\sum^{\frac{N_{0}}{2}-1}_{m=0}x[2m]e^{-j \frac{2\pi km}{\frac{N_{0}}{2}}}}}+e^{-j \frac{2\pi k}{N_{0}}}\cdot \overset{\overline D_{k}}{\overline{\sum^{\frac{N_{0}}{2}-1}x[2m+1]e^{-j \frac{2\pi km}{\frac{N_{0}}{2}}}}})$).
Questo procedimento di scomposizione può essere poi ripetuto in modo ricorsivo
$$
N_{FFT}(N_{0})=N_{FFT}\left( \frac{N_{0}}{2} \right)+N_{FFT}\left( \frac{N_{0}}{2} \right)+6N_{0}+2N_{0}= 2\left[ N_{FFT}\left( \frac{N_{0}}{2}+4N_{0} \right) \right]
$$
essendo $N_{FFT}\left( \frac{N_{0}}{2} \right)=2\left[ N_{FFT}\left( \frac{N_{0}}{4}+ \frac{4N_{0}}{2} \right) \right]$ risulta
$$
N_{FFT}(N_{0})=2\left\{ 2\left[ N_{FFT}\left( \frac{N_{0}}{4} \right)+\frac{4N_{0}}{2} \right]+4N_{0} \right\}= 4N_{FFT}\left( \frac{N_{0}}{4} \right)+2\cdot 8N_{0}
$$
Iterando
$$\begin{align}
&N_{FFT}(N_{0})=8N_{FFT}\left( \frac{N_{0}}{8} \right)+3\cdot 8N_{0}
  \\
&N_{FFT}(N_{0})=16N_{FFT}\left( \frac{N_{0}}{16} \right)+4\cdot 8N_{0}
 \\
&\vdots \\
&N_{FFT}(N_{0})=N_{0}\cdot N_{FFT}\left( \frac{N_{0}}{N_{0}} \right)+\log_{2}N_{0}\cdot 8N_{0}
\end{align}$$
Dove $N_{0}\cdot N_{FFT}(1)=N_{0}\cdot 6$, dove $6$ è il numero di operazioni per una moltiplicazione complessa.

Si ottiene in conclusione
$$
N_{FFT}(N_{0})=6N_{0}+8N_{0}\log_{2}N_{0}\simeq 8N_{0}\log_{2}N_{0}
$$
Questa relazione indica una complessità per l'algoritmo di FFT notevolmente inferiore alla complessità quadratica dell'algoritmo di trasformata discreta secondo la definizione.
Il rapporto tra il numero di operazioni necessarie nei due casi è pari a 
$$
\frac{N_{TDF}(N_{0})}{N_{FFT}(N_{0})}= \frac{\cancel 8N_{0}^{\cancel 2}}{\cancel 8 \cancel{N_{0}}\log_{2}N_{0}}= \frac{N_{0}}{\log_{2}N_{0}}= \frac{1024}{10}\simeq 100$$
Se si usa il medesimo elaboratore per calcolare una FFT di ordine $1024$, si otterrà un tempo di calcolo inferiore a quello prima calcolato del fattore $\frac{1024}{10}\simeq 100$. Il vantaggio che si consegue utilizzando l'algoritmo di calcolo FFT invece della trasformata classica aumenta al crescere di $N_{0}$.

L'algoritmo di FFT fu pubblicato nel 1965 da Cooley e Tukey. a questa data si fa risalire la nascita della moderna elaborazione dei segnali. Attraverso la FFT, infatti, possono essere effettuate in maniera efficiente alcune operazioni fondamentali di analisi ed elaborazione dei segnali. Tali operazioni non furono realizzabili in pratico fino al momento di introduzione dell'algoritmo veloce, vista la ridotta velocità dei componenti elettronici e quindi dei calcolatori dell'epoca.
Questo giustifica l'importanza centrale attribuita alla FFT nello sviluppo delle tecniche di elaborazione numerica
## Tavola Sinottica
![[Pasted image 20250527162623.png|center|500]]

Ogniqualvolta il segnale è periodico nel tempo, esso possiede uno spettro discreto. Se il segnale è discreto nel tempo, esso possiede uno spettro periodico (dualità dei domini di tempo e frequenza).