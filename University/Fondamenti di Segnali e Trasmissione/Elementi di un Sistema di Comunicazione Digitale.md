---
Order: "9"
sticker: emoji//0039-fe0f-20e3
---
- [[#Sistema di Comunicazione|Sistema di Comunicazione]]
	- [[#Sistema di Comunicazione#Sorgente Informativa (Information Source and Input Transducer)|Sorgente Informativa (Information Source and Input Transducer)]]
	- [[#Sistema di Comunicazione#Codifica di Sorgente (Source Encoder)|Codifica di Sorgente (Source Encoder)]]
	- [[#Sistema di Comunicazione#Codifica di Canale (Channel Encoder)|Codifica di Canale (Channel Encoder)]]
		- [[#Codifica di Canale (Channel Encoder)#Codici a Blocchi|Codici a Blocchi]]
		- [[#Codici a Blocchi#Codici a Ripetizione|Codici a Ripetizione]]
		- [[#Codifica di Canale (Channel Encoder)#Codici a Controllo di Parità|Codici a Controllo di Parità]]
	- [[#Sistema di Comunicazione#Modulator Digitale (Digital Modulator)|Modulator Digitale (Digital Modulator)]]
	- [[#Sistema di Comunicazione#Canale di Comunicazione (Channel)|Canale di Comunicazione (Channel)]]
	- [[#Sistema di Comunicazione#Demodulatore (Digital Demodulator)|Demodulatore (Digital Demodulator)]]
	- [[#Sistema di Comunicazione#Decodificatore di Sorgente (Source Decoder)|Decodificatore di Sorgente (Source Decoder)]]
		- [[#Decodificatore di Sorgente (Source Decoder)#Canale con Rumore Adattivo|Canale con Rumore Adattivo]]
		- [[#Decodificatore di Sorgente (Source Decoder)#Canale a Filtro Lineare|Canale a Filtro Lineare]]
	- [[#Sistema di Comunicazione#Tecniche di Multiplazione|Tecniche di Multiplazione]]
	- [[#Sistema di Comunicazione#Multiplex a Divisione di Frequenza|Multiplex a Divisione di Frequenza]]
		- [[#Multiplex a Divisione di Frequenza#Multiplex a Divisione di Tempo|Multiplex a Divisione di Tempo]]
		- [[#Multiplex a Divisione di Frequenza#Multiplex a Divisione di Codice|Multiplex a Divisione di Codice]]

Lo scopo di un sistema di comunicazione è quello di trasmettere segnali contenenti informazioni attraverso un canale di comunicazione che separa il trasmettitore dal ricevitore. I segnali che portano informazioni sono anche chiamati *Segnali in Banda Base*. Il termine banda base viene utilizzato per designare la banda di frequenze che rappresenta il segnale originale fornito da una fonte di informazioni.

Esempi:
- Segnali audio $20\ Hz\div 15\ kHz$
- Segnali video $50 Hz\div 4,2\ MHz$

## Sistema di Comunicazione

![[Pasted image 20250531175233.png]]

### Sorgente Informativa (Information Source and Input Transducer)
L'uscita della sorgente può essere un segnale analogico, come un segnale audio o video, o un segnale digitale, come l'uscita di un computer. In un sistema di comunicazione digitale, i messaggi prodotti dalla sorgente vengono convertiti in una sequenza di cifre binarie
### Codifica di Sorgente (Source Encoder)
Idealmente, si vorrebbe rappresentare l'output digitale di origine con il minor numero possibile di cifre binarie. Quindi si cerca di rappresentare efficientemente l'output della sorgente in modo che offra una ridondanza minima o nulla.
Il processo di conversione efficiente dell'output di una sorgente analogica o digitale in una sequenza di cifre binarie è chiamata *Codifica di Sorgente* o compressione dati.

La compressione dei dati o codifica della sorgente o riduzione del bit-rate è il processo di rappresentazione di una informazione utilizzando un numero minore di bit rispetto alla rappresentazione originale
$$\text{Informazione}\ne\text{Dati}$$
È possibile utilizzare diverse quantità di dati per rappresentare le stesse informazioni. I dati potrebbero contenere informazioni che non forniscono dati, dando origine ad una ridondanza. Si tratta di un problema centrale nella compressione di segnali multimediali.

![[Pasted image 20250531180225.png|center|400]]

Si definiscono:
- Rapporto di Compressione: $C_{r}= \frac{n_{1}}{n_{2}}$
- Ridondanza Relativa della Rappresentazione con $n_{1}$ bit: $R_{D}=1- \frac{1}{C_{R}}$
Il grado in cui l'algoritmo riduce il numero di bit è chiamato la sua *Efficienza di Codifica*, inversa del rapporto di compressione:
- *Coding Efficiency:* $C_{R}^{-1}= \frac{\text{encoded bit rate}}{\text{decoded bit rate}}$
$$\begin{align}
&\text{Se }n_{1}=n_{2},\ C_{R}=1& &\text{cioè }R_{D}=0\Longrightarrow \text{No Redundancy}& \\
&\text{Se }n_{1}\gg n_{2},\ C_{R}\to \infty& &\text{cioè }R_{D}\to 1\Longrightarrow \text{High Redundancy}&
\end{align}$$

> [!example]+ Esempio:
> Un rapporto di compressione di $10$ ($10:1$) significa che il primo set di dati necessità $10$ unità di informazioni (bit) per ogni unità del secondo set di dati (compresso). La corrispondente ridondanza relativa dei dati della rappresentazione più ampia è $R=0.9$, indicando che il $90\%$ dei suoi dati è ridondante. 

Si possono identificare 3 tipi di ridondanza:
- **Ridondanza di Codifica**
- **Ridondanza Spaziale / Temporale**
- **Informazioni Irrilevanti**
![[Pasted image 20250531200040.png|center|400]]
### Codifica di Canale (Channel Encoder)
La sequenza di cifre binarie del codificatore sorgente, che si chiama sequenza informativa, viene passata al codificatore del canale
Lo scopo del *Codificatore di Canale* è quello di introdurre, in modo controllato, una certa ridondanza nella sequenza di informazioni binarie che può essere utilizzata dal ricevitore per attenuare gli effetti negativi dovuti al rumore e alle interferenze incontrati nella trasmissione del segnale attraverso il canale. Pertanto, la ridondanza aggiunta serve ad aumentare l'affidabilità dei dati ricevuti e migliora la fedeltà del segnale ricevuto, aiutando il ricevitore a decodificare la sequenza di informazioni.
Il processo di codifica di canale consiste nell'aggiungere bit di ridondanza al messaggio che vuole trasmettere. In fase di ricezione, la presenza di tali bit consente di rilevare o correggere eventuali errori introdotti nel messaggio dal rumore presente sul canale.
Si creano quindi parole di codice (code words) di opportuna lunghezza che contengono sia bit informativi che bit di ridondanza. Questo crea uno svantaggio riguardante la quantità di bit da trasmettere, in quanto quest'ultima aumenta insieme al tempo richiesto per la trasmissione.

> [!info] ->
> La codifica di canale, a parità di condizioni, non cambia la probabilità d'errore dei bit di informazione (ovvero dei bit del messaggio).

Si definiscono:
- *Capacità di Rilevazione* di un codice il numero massimo di errori che esso riesca a rilevare in una parola del codice.
- *Capacità di Correzione* di un codice il numero massimo di errori che esso riesce a correggere in una parola del codice.
#### Codici a Blocchi
Il messaggio informativo è diviso in blocchi di $k$ simboli, a cui vengono associate parole di codice formate da $n=k+q$ simboli. Si introducono quindi $q$ bit di ridondanza.

![[Pasted image 20250531201517.png|center|500]]

I *Codici a Ripetizione* e i *Codici a Controllo di Parità* sono esempi di codici a blocchi.
##### Codici a Ripetizione
Il codice a ripetizione è una semplice tecnica di correzione degli errori che si basa sulla ridondanza, consiste nel costruire parole di codice che ripetano $n$ volte il bit di informazione che si vuole trasmettere:
$$\begin{align}
&0\longrightarrow 000\ldots00 \\
&1\longrightarrow \underset{n}{\underline{{111}\ldots 1}1}
\end{align}$$
Nei codici a ripetizione si ha $k=1$ e $q=n-1$. Pertanto si hanno dei codici $(n,1)$.
Il numero di ripetizioni dipende dalle capacità di correzione degli errori richiesta. Ad esempio, nel caso a ripetizione 3, ogni bit di dati viene replicato tre volte. Quindi, un bit di dati $0$ diventa $000$ e un bit di dati $1$ diventa $111$.

| Messaggio | Parola di Codice | Singolo Errore     | Doppio Errore     | Triplo Errore |
| --------- | ---------------- | ------------------ | ----------------- | ------------- |
| $0$       | $000$            | $(001 \ 010\ 100)$ | $(011\ 110\ 101)$ | $111$         |
| $1$       | $111$            | $(011\ 101\ 110)$  | $(100\ 010\ 001)$ | $000$         |
**Rivelazione di Errori:**
- Con $n=3$, nel caso in cui si usa il codice per rilevare l'errore, si è in grado di identificare $1$ o $2$ errori (singoli o doppi).
- Al contrario, non si è in grado di rilevare errori tripli ($3$ errori trasformano una parola di codice in un'altra parola di codice).
#### Codici a Controllo di Parità
 Una codifica più sofisticata consiste nel prendere $k$ bit di informazione alla volta e mappare ogni sequenza di $k$ bit in un'unica sequenza di $n$ bit, chiamata parola di codice (con $n>k$). Il suo funzionamento si basa su una combinazione di $k$ bit di dati e $(n-k)$ *Bit di Parità*, che vengono calcolati in modo  da render rilevabili e correggibili determinati tipi di errori.
 La *Quantità di Ridondanza* introdotta codificando i dati in questo modo è misurato dal rapporto $\frac{n}{k}$. Il reciproco di questo rapporto, cioè $\frac{k}{n}$ è chiamato velocità del codice (code rate).
 Un esempio è il **Codice di Hamming** $(7,4)$, che a blocchi di $4$ bit di dati aggiunge $3$ bit di ridondanza, con i quali è possibile rilevare e correggere $1$ bit errato in ricezione.
### Modulator Digitale (Digital Modulator)
La sequenza binaria all'uscita dell'encoder del canale viene trasmessa al modulatore digitale, che funge da interfaccia per il canale di comunicazione. Poiché questi canali di comunicazione incontrati nella pratica sono in grado di trasmettere forme d'onda, lo scopo principale del modulatore digitale è mappare la sequenza di informazioni binarie in forme d'onda adatte ad essere trasmesse sul canale (signal waveforms).
I segnali che portano informazioni sono chiamati *Segnali in Banda Base*. I termine banda base viene utilizzato per designare la banda di frequenza che rappresenta il segnale originario fornito da una fonte di informazioni.
L'uso corretto del canale di comunicazione richiede uno spostamento dell'intervallo di frequenze in banda base in altri intervalli di frequenza adatti alla trasmissione e un corrispondente spostamento all'indietro nell'intervallo di frequenza originale dopo la ricezione.

> [!example]+ Esempio:
> Ad esempio, un sistema radio deve funzionare con frequenze di $30\ kHz$ e oltre, mentre il segnale in banda base solito contiene frequenze nella gamma di frequenze audio, quindi una qualunque forma di spostamento di banda deve essere utilizzato affinché il sistema funzioni in modo soddisfacente.
>
> ![[Pasted image 20250603113908.png|center|500]]

Uno spostamento della gamma di frequenze in un segnale si ottiene utilizzando la modulazione, che è definita come il processo mediante il quale alcune caratteristiche di una portante vengono variate in accordo con un'onda modulante (segnale).

![[Pasted image 20250603114424.png|center|400]]

La modulazione viene eseguita all'estremità trasmittente del sistema di comunicazione.
All'estremità ricevente del sistema, di solito si richiede il ripristino del segnale in banda base originale. Ciò si ottiene utilizzando un processo noto come demodulazione, che è l'inverso del processo di modulazione.
Nella trasmissione digitale passabanda, il flusso di dati in ingresso viene modulato su una portante (solitamente sinusoidale) con limiti di frequenza fissi imposti da un canale passabanda di interesse. Il canale di comunicazione utilizzando per la trasmissione di dati in banda passante può essere un collegamento radio a microonde, un canale satellitare o simili. In ogni caso, il processo di modulazione che rende possibile la trasmissione comporta la variazione (codificazione) dell'ampiezza, della frequenza o della fase di una portante sinusoidale in qualche modo in accordo con i dati di arrivo.

3 schemi di base di modulazione digitale:
- **Amplitude-Shift Keying (ASK)** ![[Pasted image 20250603125359.png]]
- **Frequency-Shift Keying (FSK)**![[Pasted image 20250603125451.png]]
- **Phase-Shift Keying (PSK)** ![[Pasted image 20250603125513.png]]
Si tratta di operazioni di modulazione di ampiezza, modulazione di frequenza e modulazione rispettivamente.

Si suppone che la sequenza informativa debba essere trasmessa un bit alla volta con un rate costante $R$ bit ogni $T_{b}= \frac{1}{R}$ secondi. Il modulatore digitale può semplicemente mappare il bit $0$ in una forma d'onda $s_{0}$ e il bit $1$ in una forma d'onda $s_{1}(t)$, in questo modo ogni bit viene trasmesso separatamente (*Modulazione Binaria*).
Se si definisce la funzione base ad energia unitaria la funzione
$$
\phi(t)=\sqrt{ \frac{2}{T_{b}}\cos(2\pi f_{c}t) }
$$

> [!example] Esempio:
> Ad esempio nel caso della *Binary Phase-Shift Keying*
> $$\begin{align}
> & bit\ 0\Longrightarrow s_{0}(t)=\sqrt{ \frac{2E_{b}}{T_{b}}\cos(2\pi f_{c}t) } \\
> &bit\ 1\Longrightarrow s_{1}(t)=\sqrt{ \frac{2E_{b}}{T_{b}}\cos(2\pi f_{c}t+\pi) }=-\sqrt{ \frac{2E_{b}}{T_{b}}\cos(2\pi f_{c}t) }
> \end{align}$$
> Se si definisce funzione base ad energia unitaria la funzione
> $$
> \phi(t)=\sqrt{ \frac{2}{T_{b}}\cos(2\pi f_{c}t) }
> $$
> Si ha
> $$\begin{align}
> &s_{0}(t)=\sqrt{ E_{b} }\ \phi(t) \\
> &s_{1}(t)=-\sqrt{ E_{b} }\ \phi(t)
> \end{align}$$

In alternativa, il modulatore può trasmettere $b$ bit di informazione per volta utilizzando $M=2^b$ forme d'onda distinte $s_{i}(t)=0,1,\ldots,M-1$, cioè una forma d'onda per ciascuna delle $2^b$ possibili sequenze di $b-$bit (modulazione $M-$aria, con $M>2$).
Una sequenza di $b-$bit entra nel modulatore ogni $T_{s}=\frac{b}{R}$ secondi, quindi il bit rate del canale $R$ è fisso, il tempo disponibile per trasmettere una delle $M$ forme d'onda corrispondenti a una sequenza di $b$ bit è pari a $B$ volte il periodo di tempo in un sistema che utilizza la modulazione binaria, ovvero
$$
T_{s}=b\ T_{b}
$$
### Canale di Comunicazione (Channel)
Il canale di comunicazione è il mezzo fisico utilizzato per inviare il segnale dal trasmettitore al ricevitore. Il canale di comunicazione fornisce la connessione tra il trasmettitore e il ricevitore.
Il canale fisico può essere:
- Una coppia di fili che trasportano il segnale elettrico
- Una fibra ottica che trasporta le informazioni su un fascio di luce modulato
- Un canale oceanico sottomarino in cui l'informazione viene trasmessa acusticamente
- Spazio libero in cui il segnale di rilevamento delle informazione viene irradiato mediante l'uso di un'antenna
Qualunque sia il mezzo fisico utilizzato, la caratteristica essenziale è che il segnale trasmesso viene corrotto in modo casuale da una varietà di possibili meccanismi. Per semplicità si assume spesso che il segnale attraverso qualsiasi canale viene corrotto da un rumore adattivo.
In generale, il rumore adattivo viene generato internamente da componenti come resistori e dispositivi a stato solido utilizzati per implementare il sistema di comunicazione, chiamato a volte *Rumore Termico*, oppure è il rumore prodotto dall'uomo, o il rumore atmosferico (ad esempio scariche elettriche di fulmini). Altre forme di rumore e interferenza possono sorgere esternamente al sistema, come l'interferenza di altri utenti del canale.
Quando tale rumore e interferenza occupano la stessa banda di frequenza del segnale desiderato, il loro effetto può essere minimizzato dalla corretta progettazione del segnale trasmesso e del suo demodulatore sul ricevitore. Altri tipi di degradazione che possono essere riscontrati nella trasmissione sul canale sono:
- Attenuazione del Segnale
![[Pasted image 20250603130802.png|400]]
- Distorsione Multipath 
![[Pasted image 20250603130855.png|400]]

Gli effetti del rumore possono essere ridotti al minimo aumentando la potenza nel segnale trasmesso. Tuttavia, l'attrezzatura e altri vincoli pratici limitano il livello di potenza nel segnale trasmesso. Un'altra limitazione è la larghezza di banda del canale disponibile, un vincolo di larghezza di banda è solitamente dovuto alle limitazioni fisiche del mezzo e dei componenti elettronici utilizzati per implementare il trasmettitore e il ricevitore.
Queste due limitazioni limitano la quantità di dati che possono essere trasmessi in modo affidabile su qualsiasi canale di comunicazione.
### Demodulatore (Digital Demodulator)
All'estremità ricevente di un sistema di comunicazione digitale, il demodulatore digitale elabora l'onda trasmessa corrotta dal canale e riduce le forme d'onda a una sequenza di numeri che rappresentano le stime dei simboli dei dati trasmessi (binari o $M-$ary). Per fare questo, occorre usare una regola di decisione per decidere quale segnale è stato trasmesso, a partire dal segnale ricevuto.

![[Pasted image 20250603152843.png|center|450]]

Questa sequenza di numeri viene passata al decodificatore di canale, che tenta di ricostruire la sequenza di informazioni originale dalla conscienza del codice utilizzato dal codificatore di canale e dalla ridondanza contenuta nei dati ricevuti (si utilizzano i codici a correzione di errore).
Se si usa un codice di ripetizione, la decofifica coinvolge un processo di conteggio delle ripetioni di ciascun bit e determina il valore di quel bit sulla base della maggioranza dei bit ripetuti. Ad esempio, se un bit è ripetuto tre volte e delle delle tre copie sono 0 e una è 1, il bit decodificato saà 0.

> [!info] Correzione degli errori
> Se un bit decodificato è diverso dalla maggioranza dei bit ripetuti, viene considerato un errore. In questo caso, viene apportata una correzione invertendo il valore del bit errato per farlo coincidere con la maggioranza. Ad esempio, se un bit è ripetuto tre volte von valore 0 e uno dei tre bit ripetuti viene ricevuto come 1, allora l'altro verrà corretto in 0.

I codici a correzione di errori a ripetizione sono efficaci per la correzione di errori casuali, ma richiedono una maggiore ridondanza per garantire la correzione di errori multipli o errori semantici. Inoltre, l'utilizzo di ripetizioni multiple aumenta la quantità di dati trasmessi, riducendo l'efficienza di trasmissione.

### Decodificatore di Sorgente (Source Decoder)
Nella progettazione di sistemi di comunicazione per la trasmissione di informazioni attraversi canale fisico, è conveniente costruire modelli matematici che riflettano le caratteristiche più importanti del mezzo trasmissivo. Il modello matematico per il canale viene poi utilizzato nella progettazione del codificatore di canale (sul trasmettitore) e il decodificatore di canale (del ricevitore).
#### Canale con Rumore Adattivo
L'*Additive White Channel* è il modello matematico più semplice per un canale di comunicazione. Il segnale trasmesso $s(t)$ è corrotto da un processo di rumore casuale additivo $n(t)$

![[Pasted image 20250603154439.png|center|400]]

Fisicamente, il processo di rumore adattivo può derivare da componenti elettronici e amplificatori al ricevitore o da interferenze riscontrate durante la trasmissione (come nel caso della trasmissione di un segnale radio). Se il rumore è introdotto principalmente da componenti elettronici e amplificatori nel ricevitore, può essere caratterizzato come rumore termico, definito staticamente come un processo aleatorio gaussiano. Da qui, il modello matematico risultante è solitamente chiamato *Canale di Rumore Gaussiano Adattivo*.
Poiché questo modello di canale si applica a un'ampia classe di canali fisici di comunicazione e grazie alla sua trattabilità matematica, questo è il modello di canale predominante utilizzato nell'analisi e progettazione di sistemi di comunicazione.
L'attenuazione del canale è facilmente incomparabile nel modello, il segnale ricevuto è 
$$
r(t)=\alpha s(t)+n(t)
$$
con $\alpha$ fattore di attenuazione, $n(t)$ rumore gaussiano a media nulla, bianco di densità spettrale di potenza $\frac{N_{0}}{2}$.
Questo modello permette di progettare un opportuno demodulatore e calcolare la probabilità di errore per i bit (bit error rate).

Nel caso del BINARY PASE-SHIFT KEYING, assumendo $\alpha=1$, il ricevitore che si implementa è un correlatore
$$
z=\int^{T_{b}}_{0}r(t)\phi(t)\ dt
$$
Il decisore è $$\text{bit }b=\begin{cases}
0 & se\ z>0 \\
1& se\ z<0
\end{cases}$$
Il bit error rate è $$P_{e}=\frac{1}{2}\text{erfc}\left( \sqrt{ \frac{E_{b}}{N_{0}} } \right)$$
![[Pasted image 20250603155357.png|center|400]]

#### Canale a Filtro Lineare
In alcuni canali fisici, come i canali telefonici fissi, vengono utilizzati filtri per garantire che i segnali trasmessi non superino i limiti di larghezza di banda specificati e quindi non interferiscono tra loro. Tali canali sono generalmente caratterizzati matematicamente come canali a filtro lineare con rumore adattivo

![[Pasted image 20250603155950.png|center|400]]

Se l'ingresso del canale $s(t)$, l'uscita del canale è il segnale 
$$
r(t)=s(t)\otimes h(t)+n(t)
$$
con $h(t)$ è la risposta impulsiva del filtro lineare e $\otimes$ denota la convoluzione.

I canali fisici come i canali acustici subacquei, i canali radio ionsferici e i canali radio mobili in cui si verifica una propagazione del segnale trasmesso tramite percorsi multipli variabile nel possono essere caratterizzati matematicamente come filtri lineari varianti nel tempo. Tali filtri sono caratterizzati da una risposta all'impulso di canale nel tempo $h(\tau;t)$, dove $h(\tau;t)$, è la risposta all'impulso di canale all'istante $t$ causa di un impulso applicato all'istante $t-\tau$. Pertanto $\tau$ rappresenta la variabile età (tempo trascorso).

![[Pasted image 20250603160532.png|center|400]]

Un buon modello per la propagazione del segnale multipath attraverso canali fisici, come la ionsfera (a frequenza a $30 MHz$) e canali radio cellulari mobili, è un caso speciale della precedente formula, in cui la risposta impulsiva $h(\tau,t)$ assume la forma
$$
h(\tau,t)=\sum^L_{k=1}a_{k}(t)\delta(\tau-\tau_{k})
$$
dove i valori $\{a_{k}(t)\}$ rappresentano le possibili attenuazioni, eventualmente variabili nel tempo per gli $L$ cammini di propagazione e $\{\tau_{k}\}$ sono i corrispondenti ritardi temporali. Il segnale ricevuto sarà allora
$$
r(t)=s(t)\otimes h(\tau,t)+n(t)=\sum^L_{k=1} a_{k}(t)s(\tau-\tau_{k})+n(t)
$$
### Tecniche di Multiplazione
Un canale può trasportare contemporaneamente diversi segnali. Ad esempio, sui cavi telefonici o su un sistema satellitare possono essere trasmessi centinaia o migliaia di comunicazioni allo stesso istante. L'operazione con cui diversi segnali sono trasmessi sullo stesso canale (cavo, fibra, radio, $\ldots$) senza interferenza è chiamata *Multiplexing* dei segnali e l'apparato che effettua tale operazione di multiplex.
Un multiplex riceve $N$ segnali distinti $s_{1}(t),s_{2}(t),\ldots, s_{N}(t)$ e li invia su un unico canale utilizzando opportune regole (o tecniche multiplex)

![[Pasted image 20250603161409.png|center|400]]

Il segnale in uscita $Y(t)$ è una combinazione degli $N$ segnali in ingresso e da esso è possibile recuperare i segnali di partenza attraverso un'operazione di demultiplexing.
Le tecniche di multiplexing utilizzati si dividono in 3 classi:
- *Multiplex a Divisione di Frequenze* indicati con la sigla *FDM* (Frequency Division Multiplex)
- *Multiplex a Divisione di Tempo* indicati con la sigla *TDM* (Time Division Multiplex)
- *Multiplex a Divisione di Codice* indicati con *CDM* (Code Division Multiplexing)
I multiplex a divisione di tempo sono stati introdotti per la trasmissione di segnali analogici, in particolare nella telefonia analogica. I multiplex a divisione di tempo sono utilizzati nella telefonia numerica. I multiplex a divisone di codice sono stati introdotti vome tecnica accesso multiplo nei sistemi raio cellulari come il sistema di terza generazione UTMS (Universal Mobile Telecommunication System).
La telefonia mobile attuale adotta contemporaneamente TDM, FDM e CDM.
### Multiplex a Divisione di Frequenza
Un multiplex a divisione di frequenza trasporta lo spettro dei segnali al suo ingresso su frequenze diverse. 
Si suppone che all'ingresso del multiplex siano presenti due segnali $s_{1}(t)$ e $s_{2}(t)$ ambedue con lo spettro diverso da 0 nell'intervallo $(0,B)$. Lo spettro del segnale $s_{1}(t)$ viene traslato in frequenza di $f_{1}$, mentre lo spettro del secondo segnale viene traslato di $f_{2}$ con $f_{2}\ge f_{1}+B$. Il multiplex trasmette il segnale $y(t)$ con lo spettro $Y(f)$, il canale in uscita deve avere una banda doppia rispetto al caso di trasmissione di un solo segnale.

![[Pasted image 20250603162054.png|center|400]]

Il procedimento è facilmente generalizza al caso di $N>2$

![[Pasted image 20250603162820.png|center|500]]

Il canale di comunicazione in uscita, utilizzato per trasmetter il segnale $y(t)$, deve avere una larghezza di banda $NB$. I singoli segnali sono recuperabili senza distorsioni da $y(t)$ poiché occupano zone di frequenza diverse.
#### Multiplex a Divisione di Tempo
I multiplex a divisione di tempo, i diversi segnali si differenziano sostanzialmente per l'intervallo di tempo utilizzato per la trasmissione. 
Si considera il caso di due segnali numerici, ciascuno dei quali richiede la trasmissione di $m$ bit ogni $\tau$ secondi. In questo caso il tempo viene diviso in intervalli di tempo $\tau$, questi intervalli $I$ vengono successivamente suddivisi in due sottointervalli: nel primo si trasmette il primo segnale e nel secondo il secondo segnale

![[Pasted image 20250603163734.png|center|500]]

Il procedimento può essere facilmente generalizzato al caso di $N$ segnali: l'intervallo di tempo $\tau$ è diviso tra gli $N$ segnali, a ciascuno dei quali viene assegnato un determinato sotto intervallo per la trasmissione, la situazione si ripete negli intervalli successivi. L'intervallo di tempo $\tau$ prende il nome di *Frame* ed il suo valore può variare da centinaio di $\mu \sec$ a decine di $m\sec$.

![[Pasted image 20250603164109.png|center|500]]

#### Multiplex a Divisione di Codice
La tecnica di multiplazione a divisione di codice (Code Division Multiplexing - CDM) consiste nel miscelare $N$ flussi di bit previa moltiplicazione di ciascuno di questi con una parola di codice $C_{i}$ scelta fra le $N$ parole di un codice ortogonale. Le parole del codice sono costituite da simboli binari, chiamati chip per distinguerli dai bit di informazione, di durata $N$ volte inferiore al bit di informazione.
Se si indica con $s_{i}$ (con $i=0,\ldots,N-1$) i segnali numerici degli $N$ canali, la tecniaca di multiplazione CDM consiste dunque nel moltiplicare ciascuno di essi per un codice e nel sommare i segnali così ottenuti

![[Pasted image 20250603164631.png|center|400]]

In ricezione viene effettuata la stessa operazione, che consiste nel riottenere il segnale desiderato

![[Pasted image 20250603164736.png|center|400]]
