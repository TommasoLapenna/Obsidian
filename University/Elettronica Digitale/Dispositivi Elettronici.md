---
undefined: ""
sticker: emoji//0031-fe0f-20e3
Order: "1"
---
## Semiconduttori
I semiconduttori hanno conducibilità molto più alta degli isolanti, ma minore dei conduttori. Gli atomi sono legati da legami covalenti covalenti come per gli isolanti, con i quali condividono anche la dipendenza della conducibilità dalla temperatura.
Il semiconduttore per funzionare deve essere a cristalli secondo una matrice regolare, viene quindi prima reso monocristallino in dei cilindri per poi essere fatto a fette. Si ottengono così i *Wafer*.
### Materiali
Il semiconduttore più comune è il *Silicio* (Si) (solitamente è il migliore), un altro materiale utilizzato è il *Germanio* (Ge). 
Silicio è Germanio sono semiconduttori **non composti**, ovvero costituiti da atomi di un solo tipo. Sono invece semiconduttori **composti binari:** GaAs, GaP, GaSb, AlSb, InP, InSb, InAs.
![[Pasted image 20250414091743.jpg]]
<sup>Questi elementi si trovano tutti nella $IV$ colonna della tavola periodica (questa colonna ha quindi a che fare coi semiconduttori).</sup>

Malgrado la varietà, praticamente tutti i dispositivi elettronici sono realizzati in silicio, con le sole eccezioni dei LED e dei LASER. 

Oltre al semiconduttore servono altri materiali (impurità) per ottenere una conducibilità selettiva: partendo da un semiconduttore si inseriscono all'interno del reticolo cristallino degli atomi di un elemento drogante (con un rapporto dell'ordine di $1:100^{10}$). Ci sono due tipi di drogaggi possibili:
- **Tipo P:** Si introduce un elemento drogante con un elettrone in meno del semiconduttore (solitamente il *Boro*, B), questi sono atomi accettori, si creano delle *Lacune*.
- **Tipo N:** Si introduce un elemento drogante con un elettrone in più del semiconduttore (solitamente il *Fosforo*, P), questi atomi sono donatori, si hanno *Elettroni in Eccesso*.
Il drogaggio del silicio è necessario in quanto la sua forma intrinseca (pura) ha pochi elettroni liberi, si ha quindi poca conducibilità.
---

## Giunzione P-N
Un semiconduttore è quindi detto di tipo $n$ o $p$ se nel reticolo cristallino sono presenti impurità di tipo $n$ o $p$. Se si prende per esempio un semiconduttore di tipo p, esso può essere realizzato facendo solidificare una soluzione contenente silicio ed impurità $p$. Un lato del solito che si ottiene da questo processo è poi bombardato con un fascio di ioni di impurità di tipo $n$, che penetrano fino ad una certa profondità. Inizialmente compensano le impurità $p$, poi trasformano una zona da $p$ a $n$. Il risultato è un materiale con due zone distinte ($p$ ed $n$) senza alterazioni della struttura cristallina nell'interfaccia delle due zone. Il risultato è la **Giunzione pn**:
![[Pasted image 20250414101302.png]]
Alle due zone sono associati due valori:
- $N_{a}$: numero accettori
- $N_{d}:$ numero donatori
In condizioni di equilibrio, si crea una regione centrale dove tutte le lacune della regione p sono compensate dagli elettroni della region n. Si ottiene quindi la **Regione di Svuotamento** 
![[Pasted image 20250414102954.png|center|350]]
Più dettagliatamente:
- Gli elettroni migrano dalla zona $n$ lasciando ioni fissi positivi non compensati, mentre gli stessa elettroni nella zona $p$ si ricombinano con le lacune lasciando ioni fissi positivi non compensati. Analogamente le lacune che migrano dalla parte $p$ verso la parte $n$ lasciano ioni negativi nella parte $p$ e producono ioni positivi nella parte $n$.
Lo scopo quindi della regione di svuotamenti è impedire che altre cariche negative ti $n$ possano fluire in $p$; questa situazione si crea quando gli ioni positivi e negativi danno origine ad un campo elettrico cha verso opposto a quello della migrazione delle lacune e degli elettroni (raggiungendo così una situazione di equilibrio).
La quantità di carica presente in ciascuna delle sezioni della regione attiva deve essere uguale (in quanto il semiconduttore era neutro prima e non si allontanano cariche, va conservata la neutralità), tuttavia le aree possono essere diverse (a seconda delle percentuali di drogaggio).
![[Pasted image 20250414111736.png|center|550]]
<sup>Quindi per una disposizione non neutrale delle cariche, si creano un campo $E$ e un potenziale</sup>
## Diodo P-N
La giunzione p-n può essere utilizzata per creare un **Diodo p-n**. le due zone sono munite ciascuna di un contatto elettronico (reoforo) in modo da poter applicare una tensione. 
![[Pasted image 20250414112430.png|center|450]]
- Il reoforo a contatto con la zona $p$ è detto *Anodo* (A).
- Il reoforo a contatto con la zona $n$ è detto *Catodo* (K).

> [!info] Convenzione Verso Corrente
> Per convenzione, si considera come verso positivo della corrente il verso dove scorrono le cariche positive. In questo caso sono gli elettroni che si muovono, quindi il verso della corrente sarà opposto (se un elettrone si sposta a sinistra la corrente positiva è a destra).
#### Polarizzazione Diretta (Forward Bias)
Con poca differenza di potenziale non succede niente. Se si riesce però ad annullare la barriera di potenziale, allora gli elettroni iniziano a spostarsi.
![[Pasted image 20250414114934.png|center|500]]
Le lacuna della zona $p$ e gli elettroni della zona $n$ neutralizzano la regione di svuotamento, annullando il potenziale accumulato. 
Essendo la polarizzazione diretta, la tensione applicata ai capi sarà positiva.

> [!gray] Formula Corrente Diodo
> $$
> I_{d}=I_{0}\left( e^{\frac{V_{d}}{nV_{t}}}-1 \right)
> $$
> con
> - $I_{0}$: Costante di saturazione inversa (nell'ordine di $10^{-10}$)
> - $V_{d}$: Differenza di potenziale ai capi del diodo
>- $n$: Tipo di diodo ?
> - $V_{t}$: Equivalente in tensione della temperatura

^79b1a1

Gli elettroni che fluiscono nella regione $p$ si chiamano *MinorityCarriers*. ^4ec113

> [!hint] Tensione di Soglia del Diodo
> Il diodo ha una tensione di soglia $V_{d}=0,7V$, una volta oltrepassata la corrente inizia a scorrere

#### Polarizzazione Inversa (Reverse Bias)
Si applica adesso una tensione ai capi inversa
![[Pasted image 20250414122449.png|center|500]]
Nella regione $p$ non ci sono lacune libere, quindi gli elettroni si posizionano negli spazi liberi direttamente precedenti. Così facendo crescono le regione della regione di svuotamento, il potenziale di barriera e il campo elettrico.
Il risultato della polarizzazione inversa è la quasi totale assenza di corrente che scorre nel diodo.
La formula della corrente è sempre la [[#^79b1a1|stessa]] della polarizzazione attiva, ma applicando una tensione ai capi $V_{d}$ negativa.
### Comportamento del Diodo
![[Pasted image 20250414120924.png]]
Partendo dalla parte positiva del grafo, si può osservare che all'aumentare della tensione applicata, non si ha un flusso di corrente finché non si arriva alla tensione di soglia ($V_{d}=0,7$V). L'incremento da quel punto in poi segue un andamento esponenziale (lineare).
Per quanto riguarda la parte che rappresenta la tensione negativa, la parte esponenziale della funzione tende a $1$, perciò il risultato sarà più o meno $I_{0}$. Se si supera però una certa soglia si raggiunge il breakdown del diodo (si brucia per la tanta corrente che scorre), dove il campo cresce a tal punto da "strappare gli elettroni dal reticolo".
Ci sono anche dei casi nei quali questa funzione non è esponenziale, come nel caso dove si raggiunge una determinata resistenza del materiale, dopo la quale si ottiene una retta. Le conseguenze sono che si passa da semiconduttore a conduttore che segue le leggi di Ohm.
Inoltre la temperatura $V_{t}$ può influenzare in modo positivo o negativo il comportamento del diodo:  più si scalda la giunzione e meglio conduce (si riduce la tensione di soglia), nel caso della polarizzazione diretta è una cosa buona, nel caso inverso no.

> [!hint] Potenza Dissipata
> $P=V\cdot I$ è la potenza termica che il diodo deve dissipare per raggiungere l'equilibrio termico. La temperatura per questo equilibrio dipende dalla forma e altri fattori fisici

> [!example]+ Esempio di Applicazione del Diodo (Condensatore):
> Si sa che se si applica tensione positiva al diodo passa corrente e si applica tensione negativa non passa corrente. Se si prende quindi un circuito con un generatore di tensione alternata collegata ad un diodo ed un condensatore, quando la tensione generata è positiva il diodo lascia passare corrente caricando il condensatore, il quale si scaricherà durante la tensione generata negativa in quanto il diodo blocca il passaggio di corrente
> ![[Pasted image 20250414171313.png]]
> Più il conduttore è grande p più l'ondulazione è piccola.
> Se però si scambia velocemente la polarizzazione del diodo allora si comporta come conduttore è può scorrere (per un breve istante) corrente inversa.

## Tipi di Diodo
### Fotodiodo
I Fotodiodi sono diodi la cui giunzione è scoperta o incapsulata in un materiale trasparente. 
In generale un fotone di lunghezza d'onda minore di $1.1 \mu m$ che incide sul silicio da origine a una coppia elettrone lacuna. Se tale generazione avviene nella regione di svuotamento, separa i due portatori, che quindi danno origine a una corrente.
![[Pasted image 20250414171951.png|450]]
Quindi se la giunzione è colpita da un fascio di protoni (che ha una certa energia), questi possono portare via dal reticolo cristallino un elettrone, creando nuove lacuna che lasciano passare corrente.
La tensione che scorre in un fotodiodo quindi non dipende solo dalla tensione applicata ai suoi capi, ma anche dal flusso luminoso che colpisce la giunzione (che fornisce energia per scavalcare la barriera)

> [!gray] Formula Corrente Fotodiodo
> $$
> I_{d}=k\cdot E_{l}
> $$
con:
>- $k$: costante del diodo (per costruzione)
>- $E_{l}$ flusso luminoso ($\frac{W}{m^2}$)

> [!example]+ Esempio:
> ![[Pasted image 20250414173655.png]]
> 

### LED
I Light Emitting Diode sono, hanno i fotodiodi, la giunzione impacchettata in un involucro trasparente. La barriera di tensione di questi diodi si trova a $1,5V$ invece che a $0,7V$.
Polarizzando direttamente un LED (e riducendo quindi di conseguenza la barriera di potenziale), lo scambio tra gli elettroni della zona $n$ e le lacuna della zona $p$ è ciò che genera i fotoni (gli elettroni perdono energia in forma luminosa.

> [!gray] Colori Led
> - $1,2V$: IR
> - $1,5V$: Rosso
> - $1,8V$: Verde
> - $2,9V$: Blu
> - $3 V$: UV
>
> Per il bianco occorre usare dei fosfori rossi, verdi e blu (al variare delle loro quantità cambia il "calore" del bianco).
> Questi colori sono determinati dal fatto che minore la soglia, maggiore la lunghezza d'onda; inoltre più corrente scorre e più fotoni si ottengono.
>

>[!hint] Formule:
>- $E$: Energia emessa
>- $h$: Costante di Plank
>- $v$: Frequenza dell'onda luminosa
>- $\lambda$: Lunghezza d'onda?
>$$
E=h\cdot v\qquad v= \frac{E}{h}\Rightarrow v \propto E\qquad \lambda v= c\qquad \lambda \propto \frac{1}{E}
>$$

### Diodo Schottky
Il diodo schottky ha una zona $p$ di metallo (solitamente alluminio) e una zona $n$ semiconduttore.
![[Pasted image 20250414180919.png|450]]
Nella zona di metallo non c'è un reticolo cristallino e non si può quindi creare una regione di svuotamento.
La tensione di soglia in questo caso è $0,3-0,4V$
Quando è freddo questo diodo si comporta bene come diodo "normale", una volta scaldato è capace di spengersi e accendersi velocemente (in quanto non ci sono cariche da rimuovere nel lato $p$) e passare rapidamente da conduzione diretta a conduzione inversa.
Viene utilizzato dove la soglia di $0,7V$ da problemi, come ad esempio nei circuiti logici o di potenza.
![[Pasted image 20250414181810.png|center|400]]
### Esempi

> [!example]+ Esercizi coi Diodi
> ![[Pasted image 20250414185644.png]]

---

## BJT: Giunzione n-p-n 
![[Pasted image 20250414191104.png|center|400]]
<sup>Il comportamento non è quello di due diodi affiancati nonostante la rappresentazione</sup>
Il *Transistor Bipolare* (Bipolar Junction Transistor) è un dispositivo a tre terminali:
- **Base**
- **Emettitore**
- **Collettore**
La zona $p$ (base) è molto stretta per fare scorrere la corrente più facilmente;
Il drogaggio del semiconduttore avviene per diffusione anziché per impiantazione ionica, questo limita le dimensione minime ottenibili del transistor.

> [!info] Definizione Tensioni
> ![[Pasted image 20250414192341.png|center|350]]

> [!info] Definizioni Correnti
> ![[Pasted image 20250414192353.png|center|350]]

### Regioni di Funzionamento
Ci sono 4 regioni di funzionamento
![[Pasted image 20250414193344.png]]

| Working Region | $V_{BE}$ | $V_{BC}$ |
| -------------- | -------- | -------- |
| Cutoff         | 0        | 0        |
| Direct Active  | 1        | 0        |
| Saturation     | 1        | 1        |
| Reverse Active | 0        | 1        |
<sup>$1$=Polarizzazione diretta</sup>
#### Cutoff
In interdizione entrambe le giunzioni sono polarizzate inversamente ed il transistor si comporta come un interruttore aperto (tutte le correnti sono nulle).
$$
V_{BE}, V_{BC}< V_{th}\qquad I_{B}=I_{C}=0
$$
#### Diretta Attiva
In regione attiva diretta la giunzione tra base ed emettitore è polarizzata direttamente e la giunzione tra base è collettore è polarizzata inversamente. Per via di queste polarizzazzioni la corrente in entrata può solo uscire dall'emettitore, oltre a subire un guadagno (legato alle caratteristiche costrittive del BJT).
$$
V_{BE}>V_{th},\ V_{BC}<0\qquad I_{B}>0,\ I_{C}=h_{FE}I_{B}
$$
con $h$ guadagno, che darà luogo ad un multiplo preciso della corrente di base
#### Saturazione
#### Attiva Inversa