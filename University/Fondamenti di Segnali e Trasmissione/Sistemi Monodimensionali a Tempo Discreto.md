---
Order: "7"
sticker: emoji//0037-fe0f-20e3
---
- [[#Caratterizzazione dei Sistemi a Tempo Discreto|Caratterizzazione dei Sistemi a Tempo Discreto]]
	- [[#Caratterizzazione dei Sistemi a Tempo Discreto#Proprietà dei Sistemi Monodimensionali a Tempo Discreto|Proprietà dei Sistemi Monodimensionali a Tempo Discreto]]
	- [[#Caratterizzazione dei Sistemi a Tempo Discreto#Sistemi Lineari e Stazionari a Tempo Discreto|Sistemi Lineari e Stazionari a Tempo Discreto]]
	- [[#Caratterizzazione dei Sistemi a Tempo Discreto#Risposta in Frequenza  di un SLS|Risposta in Frequenza  di un SLS]]
	- [[#Caratterizzazione dei Sistemi a Tempo Discreto#Filtri a Tempo Discreto|Filtri a Tempo Discreto]]

## Caratterizzazione dei Sistemi a Tempo Discreto
La maggior parte delle considerazioni che sono già state fatte per i sistemi a tempo continuo sono ancora valide quando si prendono in considerazioni i *Sistemi a Tempo Discreto*.
Un sistema monodimensionale a tempo discreto è un elemento che elabora una sequenza d'ingresso $x[n]$ e genera una sequenza in uscita $y[n]$. L'unica differenza notevole dal punto di vista concettuale riguarda la menzione esplicita di un *Programma Calcolatore*. Infatti, i segnali a tempo discreto possono essere elaborati da circuiti elettronici digitali programmabili, il cui funzionamento è regolato da un programma. Si può allora identificare il sistema che trasforma la sequenza d'ingresso in quella di uscita con il solo programma del circuito, piuttosto che con l'insieme di dispositivi che permette l'elaborazione.
### Proprietà dei Sistemi Monodimensionali a Tempo Discreto
Si identifica un sistema a tempo discreto con la trasformazione che viene eseguita sull'eccitazione $x[n]$ per fornire la risposta $y[n]$
$$
y[n]=T[x[m];n]
$$
![[Pasted image 20250527164957.png|center|350]]

o anche, quando non si corre alcun rischio di ambiguità
$$
y[n]=T[x[n]]
$$
Un generico sistema monodimensionale a tempo discreto è
- ==**Lineare**== se ad esso è applicabile il principio di sovrapposizione degli effetti cioè se $$T[\alpha \cdot x_{1}[n]+\beta \cdot x_{2}[n]]=\alpha \cdot T[x_{1}[n]]+\beta \cdot T[x_{2}[n]]$$ fissate le sequenze $x_{1}[n]$ e $x_{2}[n]$, i coefficienti $a$ e $b$ della loro combinazione lineare.
- ==**Stazionario o Invariante nel Tempo**== se una trslazione della sequenza in ingresso comport una traslazione della stessa entità della sequena di uscita, cioè $$
T[x-[n-n_{0}]]=y[n-n_{0}]
$$ per ogni valor del parametro intero $n_{0}$.
- ==**Causale**== se la sequenza di un uscita all'istante generico $n$ non dipende dai valori assunti dalla sequenza di ingresso ad istanti successivi a $n$ $$y[n]=T[x[m],m\le n; n]=T[x[m]u[n-m];n]$$
- ==**Stabile**== secondo il criterio BIBO (Bounded Input Bounded Output) se per qualunque sequenza d'ingresso a valori limitato, tale cioè che $$|x[n]|\le k\quad \forall n$$ si ottiene una sequenza di uscita a sua volta a valori limitati, cioè $$|x[n]|\le k\Longrightarrow |y[n]|\le m\quad \forall n$$
- ==**Istantaneo o Senza Memoria**== se la sequenza di uscita all'istante generico $n$ dipende solo dal valore assunto della sequenza di ingresso al medesimo istante $$y[n]=T[x[m],m=n;n]=T[x[m]\delta[n-m];n]$$
- ==**Invertibile**== se è possibile trovare un secondo sistema $T^{-1}[\cdot]$ tale che per qualunque segnale di ingresso $x[n]$, si abbia $$x[n]=T^{-1}[y[n]]$$

> [!example]+ Esempio:
> ![[Pasted image 20250527172535.png]]
> 

### Sistemi Lineari e Stazionari a Tempo Discreto
Si considerano adesso la classe dei *Sistemi Lineari e Stazionari* (*SLS*) a tempo discreto. Come già dimostrato per i sistemi analogici, un SLS a tempo discreto è caratterizzato completamente dalla conoscenza della *Risposta Impulsiva* $h[n]$, definita come
$$
h[n]=T[\delta[n]]
$$
Infatti, nota $h[n]$, la sequenza di uscita $y[n]$ del sistema avente in ingresso la sequenza $x[n]$ è 
$$
y[n]=T[x[n]]=T\left|\sum^\infty_{k=-\infty}x[k]\delta[n-k]\right|
$$
dalla quale, per la proprietà di linearità, si ricava
$$
y[n]=\sum^\infty_{k=-\infty} x[k]T[\delta[n-k]]
$$
Per la stazionarietà del sistema si ha che $T[\delta[n-k]]=h[n-k]$ e dunque la relazione precedente diventa
$$
y[n]= \sum^\infty_{k=-\infty} x[k]h[n-k]=x[n]\otimes[n]
$$
cioè la sequenza di uscita di un SLS è la somma di convoluzione fra la sequenza di ingresso e la risposta impulsiva del sistema stesso.

- Un sistema SLS è ==*FIR*== (*Finite Impulse Response*) se la sua risposta impulsiva è costituita da un numero finito di campioni.
- Un sistema SLS è ==*IIR*== (*Infinite Impulse Response*) se la sua risposta impulsiva è costituita da un numero infinito di campioni.

Come per quanto visto per i sistemi analogici, è possibile dimostrare che condizione necessaria e sufficiente per la stabilità in senso BIBO di un SLS è la assoluta sommabilità della sua risposta impulsiva, cioè
$$
\sum^\infty_{k=-\infty} |h[k]|<\infty
$$
Usando il criterio sopra esposto:
- I sistemi FIR sono sempre stabili, in quanto la sommatoria diventa somma finita di tali quantità
- I sistemi IIR, invece, non sono sempre stabili. Per esse è necessario controllare la validità o meno della condizione.

Un SLS è causale se e solo se la sua risposta impulsiva è una sequenza causale, cioè $$h[n]=0\quad \text{se }n<0$$
ovvero
$$
h[n]=h[n]u[n]
$$


> [!example]+ Esempio: Ritardatore: 
> Si considera il sistema *Ritardatore*, che ritarda la sequenza di ingresso $x[n]$ di $n_{0}$ campioni, cioè
> $$
> h[n]=\delta[n-n_{0}]
> $$
> Si ha infatti:
> $$
> y[n]=\sum^\infty_{k=-\infty} h[k]x[n-k]=\sum^\infty_{k=-\infty} \delta[k-n_{0}]x[n-k]=x[n-n_{0}]
> $$

> [!example]+ Esempio: Filtro a Finestra Mobile:
> Si considera il sistema *Filtro a Media monile*, che effettua la seguente trasformazione sulla sequenza di ingresso $x[n]$:
> $$
> y[n]= \frac{1}{N}\sum^n_{k=n-N+1}x[k]
> $$
> con $n$ dato. Si può verificare che tale sistema è lineare per via della linearità dell'operazioni di somma che lo definisce, ed è anche stazionario, infatti
> $$
> T[x[n-n_{0}]]=\frac{1}{N}\sum^{n}_{k=n-N+1-n_{0}}x[k-n_{0}]=\frac{1}{N}\sum^{n-n_{0}}_{m=n-N+1-n_{0}}x[m]=y[n-n_{0}]
> $$
> ![[Pasted image 20250527175153.png|center|400]]
> 
> Il valore $y[n^*]$ si ottiene come media aritmetica degli ultimi $N$ valori della sequenza di ingresso $x[n]$, a partire cioè dall'istante $n^*$ verso tempi discendenti. Questi campioni sono quelli contenuti all'interno della "finestra". Si osserva che il sistema è causale.
> 
> Poiché dunque il sistema è lineare e anche stazionario, è possibile calcolarne la risposta impulsiva che, per definizione, è data da
> $$
> h[n]=T[\delta[n]]= \frac{1}{N}\sum^n_{k=n-N+1}\delta[k]= \frac{1}{N}\left[ \sum^n_{k=-\infty} \delta[k]-\sum^{n-N}_{k=-\infty}\delta[k] \right]
> $$
> Osservando che 
> $$
> u[n]=\sum^n_{k=-\infty} \delta[k]
> $$
> Si ha che
> $$
> h[n]=\frac{1}{N}(u[n]-u[n-N])
> $$
> dalla quale si vede che la risposta impulsiva del filtro a media mobile è l'impulso rettangolare causale di ampiezza $\frac{1}{N}$ 
> 
> ![[Pasted image 20250527175812.png|center|400]]
> 
> La risposta è esprimibile anche nella forma
> $$
> h[n]=\frac{1}{N}\sum^{N-1}_{k=0}\delta[n-k]
> $$
> e quindi
> $$\begin{align}
> y[n]&=\sum^\infty_{k=-\infty} h[k]x[n-k]=\sum^\infty_{k=-\infty} \left( \frac{1}{N}\sum^{N-1}_{l=0}\delta[k-l] \right)x[n-k]=\frac{1}{N}\sum^{N-1}_{l=0}\sum^\infty_{k=-\infty} \delta[k-l]x[n-k]= \\
> &=\frac{1}{N}\sum^{N-1}_{l=0}x[n-l]
> \end{align}$$
> Esiste anche un'altra forma di media mobile:
> $$
> h[n]=\frac{1}{2N+1}\sum^N_{k=-N}\delta[n-k]
> $$
> In questo caso  si ottiene:
> $$
> y[n]= \frac{1}{2N+1}\sum^N_{l=-N}x[n-l]
> $$
> Cioè il sistema esegue la media aritmetica dei campioni del segnale di ingresso in una finestra di osservazione, di lunghezza $2N+1$ centrata in $n$. 
> 
> Il primo sistema è causale mentre il secondo non gode ti tale qualità.

> [!example]+ Esempio: Accumulatore:
> Si considera il sistema *Accumulatore* o *Integratore Numerico* che opera la somma di tutti i campioni arrivati al suo interno fino all'istante $n$.
> Ha una risposta impulsiva uguale alla funzione gradino unitario, cioè:
> $$h[n]=u[n]$$
> Quindi
> $$
> y[n]=\sum^\infty_{k=-\infty} x[k]h[n-k]=\sum^{\infty}_{k=-\infty}x[k]u[n-k]= \sum^n_{k=-\infty} x[k]
> $$
> essendo $u[n-k]=1$ se $n\ge k$
> 
> Usando la condizione di stabilità per la $h[k]$, si ricava che il sistema è instabile. Malgrado ciò, non è detto che l'uscita sia sempre illimitata: possono cioè esistere ingressi limitati per i quali l'uscita del sistema integratore rimane limitata (per esempio i segnali sinusoidali). Per tali ingressi, l'accumulatore può risultare utile in alcune applicazioni.

> [!example]+ Esempio: Derivatore Numerico:
> Si considera il sistema *Derivatore Numerico* o *Operatore Differenza*, che opera la differenza tra due campioni adiacenti. Ha una risposta impulsiva uguale a 
> $$
> h[n]=\delta[n]-\delta[n-1]
> $$
> oppure
> $$
> h[n]=\delta[n+1]-\delta[n]
> $$
> Quindi
> $$\begin{align}
> &y[n]=\sum^\infty_{k=-\infty}x[k]h[n-k]=x[n]-x[n-1] \\
> &y[n]=\sum^\infty_{k=-\infty}x[k]h[n-k]=x[n+1]-x[n]
> \end{align}$$
> Il primo sistema è causale, il secondo no.

Quando due SLS aventi risposte impulsive $h_{1}[n]$ e $h_{2}[n]$ sono connessi in cascata o in parallelo, le relative risposte dei sistemi equivalenti sono:
- ==**Cascata:**== ![[Pasted image 20250527181856.png|center|400]] $$h[n]=h_{1}[n]\cdot h_{2}[n]$$ Infatti, se $x[n]$ è l'ingresso che pilota il primo sistema, si ha $$\begin{align}
y[n]&=(x[n]*h_{2}[n])*h_{2}[n]=\left( \sum^\infty_{k=-\infty}x[k]h_{1}[n-k] \right)*h_{2}[n]= \\
&=\sum^\infty_{l=-\infty}\left( \sum^\infty_{k=-\infty} x[k]h_{1}[l-k] \right)h_{2}[n-l]= \sum^\infty_{k=-\infty} x[k]\sum^\infty_{l=-\infty} h_{1}[l-k]h_{2}[n-l]= \\
&= \sum^\infty_{k=-\infty}x[k]\sum^\infty_{m=-\infty} h_{1}[m]h_{2}[n-k-m]=x[n]*(h_{1}[n]*h_{2}[n])
\end{align}$$

> [!hint] Ordine Sistemi a Cascata
> Per la proprietà commutativa del prodotto di convoluzione discreta, la risposta impulsiva complessiva vale anche $h_{2}[n]\otimes h_{1}[n]$, cioè in una cascata l'ordine dei sistemi può essere variato senza alterare l'uscita

- ==**Parallelo**:== ![[Pasted image 20250527183019.png|center|400]] $$
h[n]=h_{1}[n]+h_{2}[n]
$$ Si può scrivere infatti $$\begin{align}
y[n]&=x[n]\otimes h_{1}[n]+x[n]\otimes h_{2}[n]=\sum^\infty_{k=-\infty}h_{1}[k]x[n-k]+\sum^\infty_{k=-\infty}h_{2}[k]x[n-k]= \\
&=\sum^\infty_{k=-\infty} (h_{1}[k]+h_{2}[k]x[n-k])=x[n]\otimes (h_{1}[n]+h_{2}[n])
\end{align}$$
### Risposta in Frequenza  di un SLS
La definizione di risposta in frequenza di un SLS a tempo discreto stabile non differisce dalla definizione di un SLS a tempo continuo. Si può dire quindi che:
1. La risposta in frequenza di un SLS a tempo discreto è la trasformata di Fourier della risposta impulsiva $h[n]$ del sistema: $$\overline H(f)=\sum^\infty_{n=-\infty}h[n]e^{-j 2\pi fT}$$
2. La risposta in frequenza $\overline H(f)$ è il rapporto fra le trasformate $\overline Y(f)$ e $\overline X(f)$ rispettivamente della sequenza di uscita $y[n]$ e di ingresso $x[n]$: $$\overline H(f)=\frac{\overline Y(f)}{\overline X(f)}$$
3. La risposta in frequenza $\overline H(f)$ è data dal rapporto fra la sequenza di uscita $y[n]$ e quella di in ingresso $x[n]$ quando $x[n]$ è un'oscillazione complessa alla frequenza $f$: $$\left.\overline H(f)=\frac{y[n]}{x[n]}\right|_{x=e^{j 2\pi fT}}$$
	- Data la risposta in frequenza $\overline H(f)$ si definiscono la risposta in ampiezza $$\overline A(f)=|\overline H(f)|$$che permette di stabilire le caratteristiche di selettività di un SLS e la sua risposta in fase $$\overline\theta(f)=\angle \overline H(f)$$

> [!example]+ Esempio:
> Data la risposta in frequenza $\overline H(f)$ di un SLS, si trova l'espressione del segnale in uscita $y[n]$ quando l'ingresso $x[n]$ è una sequenza periodica di periodo $N_{0}:x[n]=x[n+N_{0}]$. La sequenza data può essere scomposta in serie discreta (antitrasformata) di Fourier, cioè come somma pesata (combinazione lineare) di $N_{0}$ oscillazioni sinusoidali complesse a tempo discreto alle frequenze $f_{k}=\frac{k}{N_{0}T}$, $k=0,1,\ldots,N_{0}-1$
> $$
> x[n]=\frac{1}{N_{0}}\sum^{N_{0}-1}_{k=0}\overline X_{k}e^{j \frac{2\pi kn}{N_{0}}}
> $$
> Poiché il sistema è lineare, si può applicare il principio di sovrapposizione degli effetti, osservando che ciascuna di queste oscillazioni viene modificata dal sistema in ampiezza e fase in base al valore della risposta in frequenza corrispondente alla frequenza di oscillazione.
> Il segnale in uscita è dunque
> $$
> y[n]=\sum^{N_{0}-1}_{k=0}\overline X_{k}\cdot \overline H\left( \frac{k}{N_{0}T}e^{j \frac{2\pi kn}{N_{0}}} \right)
> $$
> cioè la trasformata di Fourier di $\overline Y_{k}$ del segnale in uscita $y[n]$ è 
> $$
> \overline Y_{k}= \overline X_{k}\cdot \overline H\left( \frac{k}{N_{0}T} \right)
> $$
> 

La condizione di non distorsione viene riformulata a partire dall'enunciato per i segnali a tempo continuo:
$$
y[n]=Kx[n-n_{0}]
$$
dove $K$ $n_{0}$ rappresentano il guadagno ed il ritardo del sistema. Nel dominio della frequenza, questa condizione si traduce nei due seguenti requisiti per la risposta in ampiezza e la risposta in fase:
$$
\overline A(f)=K \ (K>0)\qquad \overline \theta (f)=-2\pi fn_{0}T
$$
È sufficiente che queste condizioni siano verificate nell'ambito della banda del segnale per garantire l'assenza di distorsioni.

### Filtri a Tempo Discreto
Il concetto di SLS selettivo in frequenza, detto anche *Filtro*, può essere esteso al caso dei sistemi a tempo discreto con la medesima nomenclatura. Ovviamente le caratteristiche di selettività del filtro in tempo discreto con risposta in frequenza $\overline H(f)$ sono determinate dall'andamento della sua risposta in ampiezza $\overline H(f)$, in un solo periodo della funzione (per esempio nell'intervallo $\left[ -\frac{1}{2T}, \frac{1}{2T} \right)$). 
Potendo limitare l'analisi di $\overline H(f)$ ad un intervallo limitato, occorre tener conto che le basse frequenza continuano ad essere vicine alla frequenza nulla, mentre quelle alte sono prossimee al limite superiore dell'intervallo, cioè $\frac{1}{2T}$.
Le osservazioni riguardanti le classificazioni dei filtri ideali e la causalità dei sistemi analogici si sono le stesse del caso dei sistemi a tempo discreto.


| **Filtri**               |                                                   |
| ------------------------ | ------------------------------------------------- |
| **Filtro Passa-Basso**   | ![[Pasted image 20250529155015.png\|center\|300]] |
| **Filtro Passa-Alto**    | ![[Pasted image 20250529155128.png\|center\|300]] |
| **Filtro Passa-Banda**   | ![[Pasted image 20250529155213.png\|center\|300]] |
| **Filtro Elimina-Banda** | ![[Pasted image 20250529155252.png\|center\|300]] |
|                          |                                                   |

> [!example]+ Esempio:
> Calcolare la risposta impulsiva dei seguenti filtri passa-basso e passa-alto ideale a tempo discreto. La risposta in frequenza del passa-basso ideale è una funzione $\text{rect}(\cdot)$ periodicizzata con periodo frequenziale $\frac{1}{T}$:
> $$
> \overline H_{LP}(f)=\frac{1}{T}\sum^\infty_{k=\infty}T\cdot \text{rect}\left( \frac{f-\frac{k}{T}}{2B} \right)
> $$ 
>per cui
> $$
> h_{LP}[n]=2BT\text{sinc}(2Bt)|_{t=nT}=2BT\text{sinc}(2nBT)
> $$
> ![[Pasted image 20250529155708.png|center|450]] 
>  Per il filtro passa-alto si ha 
>  $$\overline H_{HP}(f)=1-\overline H_{LP}(f)$$
>  e quindi $$h_{HP}[n]=\delta[n]-h_{LP}[n]=\delta[n]-2BT\text{sinc}(2nBT)$$
>  Entrambe le risposte impulsive sono non nulle per $n<0$. 

==Si può notare che i filtri ideali non sono causali.==
Come già osservato nel caso dei sistemi continui, se l'ingresso è una sequenza sinusoidale alla frequenza $f_{0}$, l'uscita del sistema è ancora una sequenza sinusoidale alla frequenza $f_{0}$. Tale sequenza risulta modificata in ampiezza e fase relativamente al segnale d'ingresso secondo le risposte in ampiezza e fase del sistema alla frequenza $f_{0}$ considerata.


> [!example]+ Esempio:
> Si considera il seguente sistema in cui la frequenza di campionamento è $f_{c}=48 \text{ kHz}$.
> Il segnale di ingresso è $x(t)=\cos(2\pi f_{0}t)$ con $f_{0}=16\text{ kHz}$. 
> Si determina l'espressione del segnale d'uscita $y[n]$ sapendo che il sistema nonlineare (*NL*) a tempo discreto è caratterizzato dalla relazione ingresso-uscita $z[n]=x^2[n]$, e che la risposta impulsiva del successivo filtro è 
> $$
> h[n]=\frac{1}{2}\text{sinc}\left( \frac{n}{2} \right)
> $$
> ![[Pasted image 20250529161707.png|center|400]]
> 
> Si ha che $h[n]$ è la risposta impulsiva di un filtro passa-basso ideale di banmda $B= \frac{1}{4T}=12 \text{ kHz}$. Essendo $2BnT=\frac{n}{2}$, allora $2BT=\frac{1}{2}$, quindi $B=\frac{1}{4T}=\frac{f_{c}}{4}=12 \text{ kHz}$
> 
> ![[Pasted image 20250529161928.png|center|400]]
> 
> La sequenza in uscita sul campionatore è $x[n]=\cos(2\pi nf_{0}T)$ e, di conseguenza, la sequenza in uscita alla non linearità è data da
> $$
> z[n] = \cos^2(2\pi nf_{0}T)=\frac{1}{2}[1+\cos(4\pi nf_{0}T)]
> $$
> Ovvero è costituita dalla somma di una costante (componente continua ovvero a frequenza nulla) e di una oscillazione cosinusoidale a frequenza $2f_{0}=32\text{ kHz}$.
> 
> La sequenza in uscita $y[n]$ al filtro $h[n]$ è quindi
> $$
> y[n]=\frac{1}{2} \overline H(0)+\frac{1}{2}|\overline H(2f_{0})|\cos(4\pi nf_{0}T+\angle\overline H(2f_{0}))
> $$
> dove $\overline H(f)$ è la risposta in frequenza del sistema a tempo discreto.
> Si può verificare immediatamente che $\overline H(2f_{0})=0$ e $\overline H(0)=1$ per cui la sequenza $y[n]$ è $y[n]=\frac{1}{2}$
