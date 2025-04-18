---
Order: "6"
sticker: emoji//0036-fe0f-20e3
---
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
La cadenza con cui l'interruttore si chiude (cioè con la quale il segnale viene campionato) è $$f_{c}= \frac{1}{T}$$ed è*Frequenza di Campionamento* ($Hz$ o $\frac{\text{campioni}}{s}$)
Nella pratica, il campionamento viene effettuato dai convertitori A/D (Analogico/Digitale). Questi dispositivi sono controllati da un clock a frequenza $f_{c}$ che fornisce gli impulsi di comando al circuito per le operazioni di campionamento.
Il campionatore ideale estrae il valore del segnale $x(t)$ in corrispondenza di ogni impulso di clock, il convertitore A/D invece rende una rappresentazione finita del numero reale estratto (solitamente in aritmetica binaria 8 o 16 bit), introducendo un *Errore di Quantizzazione*.

L'elaborazione del segnale viene eseguita sui valori digitali estratti dal segnale attraverso la conversione A/D, e si risolve con l'esecuzione di un programma da parte di microprocessori specializzati, chiamati DSP (Digital Signal Processor).

![[Pasted image 20250417182141.png]]

<sup>Struttura flessibile, le funzioni di elaborazione possono essere realizzate cambiando semplicemente software (invece dell'hardware)</sup>

Il segnale $y[n]$ risultante viene successivamente riconvertito in un segnale analogico $y(t)$ attraverso una conversione D/A (Digitale/Analogico). Il dispositivo responsabile di questa operazione di chiama *Interpolatore*
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
u[n]=\sum^n_{i=-\infty}\delta[i]\qquad u[n]=\delta[-\infty]+\ldots+\delta[n-1]+\delta[n]
$$
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
\overline{X}(F+1)=\sum_{n=-\infty}^\infty [n]e^{-j 2\pi n(F+1)}=\sum_{n=-\infty}^\infty e^{j 2\pi nF}\underset{\text{Vale }1\text{ per }n\text{ intero} }{e^{-j 2\pi n}}=\sum_{n=-\infty}^\infty x[n]e^{-j 2\pi nF}=\overline{X}(F)
$$
Quindi $\overline{X}(F)$ è completamente nota se è noto il suo andamento in un intervallo delle frequenze normnalizzate di ampiezza unitaria (per esempio $F\in\left[ -\frac{1}{2}, \frac{1}{2} \right]$), chiamato *Intervallo Base*.

La definizione della trasformata è molto esaustiva dal punto di vista matematico, ma è poco conveniente quando la sequenza $x[n]$ proviene da un'operazione di campionamento di un segnale analogico $x(t)$.
La presenza della frequenza normalizzata infatti non consente di stabilire un legame con la frequenza delle componenti della trasformata $X(f)$ del segnale analogico di partenza. Se allora il periodo di campionamento è $T$, si può definire la variabile
$$
f= \frac{F}{T}= F\cdot f_{c}
$$
che viene ottenuta denormalizzando la frequenza normalizzata, misurabile in $Hz$.
Sostituendo nella definizione iniziale di trasformata $F=fT$, si ottiene una funzione complessa della frequenza misurabile in $Hz$ (nuova definizione).
$$
\overline{X}(f)=\sum_{n=-\infty}^\infty x[n]e^{-j 2\pi nfT}=TFS[x[n]]
$$
Anche per la trasformata di una sequenza si introducono lo spettro si ampiezza $\overline A(f)=|\overline X(f)|$ e lo spettro di fase $\overline \theta(f)=\angle \overline X(f)$.
Poiché la funzione $\overline X(f)$ è periodica di periodo $1$, è allora periodica in ambito frequenziale di un periodo pari alla frequenza di campionamento $f_{c}=\frac{1}{T}$:
$$
\overline X(f)= \overline X \left( f+ \frac{1}{T} \right)
$$
Questa periodicità è caratteristica delle trasformate di sequenza, che diventa evidente nella relazione di *Antitrasformata*.
Si introduce quindi la relazione di antitrasformazione
$$
x[n]=ITFS[\overline X(f)]= T \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\overline X(f)e^{j 2\pi nfT}\ df
$$
Permette di esprimere la sequenza attraverso un integrale di Fourier.

Procedimento per ottenere l'Antitrasformata
Si parte dalla definizione di trasformata
$$
\overline X(f)=\sum_{n=-\infty}^\infty x[m]e^{-j 2\pi mfT}=TFS[x[m]]
$$
Si moltiplicano entrambi i membri per un'oscillazione complessa alla frequenza $f$ e si integra sull'intervallo frequenziale $\left[ -\frac{1}{2T}, \frac{1}{2T} \right]$
$$
\int_{-\frac{1}{2T}}^{\frac{1}{2T}}e^{j 2\pi nfT}\ df = \int_{-\frac{1}{2T}}^{\frac{1}{2T}}\sum_{m=-\infty}^\infty x[m]e^{-j 2\pi mfT}e^{j 2\pi nfT}\ df = \sum_{m=-\infty}^\infty x[m]\int_{-\frac{1}{2T}}^{\frac{1}{2T}} e^{-j 2\pi(m-n)fT}\ df
$$