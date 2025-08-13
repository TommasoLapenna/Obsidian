---
sticker: emoji//0038-fe0f-20e3
order: "9"
---
## Introduzione
Un sistema termodinamico è assimilabile ad un sistema continuo, considerato che microscopicamente è costituito da un numero di elementi superiore al numero di avogrado ($N_{a}=6.022\cdot 10^{23}$). Si definisce come **Sistema Termodianamico** una porzione di universo che può essere costituita da una o più parti

![[Pasted image 20250808185500.png|center|350]]


| Definizioni         |                                                                                                         |
| ------------------- | ------------------------------------------------------------------------------------------------------- |
| **Ambiente**        | Si definisce ambiente circostante tutto ciò col quale il sistema può interagire                         |
| **Universo**        | L'insieme di sistema più ambiente si chiama universo termodinamico                                      |
| **Sistema Aperto**  | Se tra il sistema e l'ambiente avvengono scambi di energia e di materia, il sistema è detto aperto      |
| **Sistema Chiuso**  | Se tra il sistema e l'ambiente avvengono scambi di energia ma non di materia, il sistema è detto chiuso |
| **Sistema Isolato** | Se tra il sistema e l'ambiente non avvengono scambi di energia e di materia, il sistema è detto isolato |
**Variabile Termodinamiche:**
- Volume
- Pressione
- Temperatura
- Massa
- Concentrazione

Le variabili termodinamiche si dividono tra estensive, se esprimono una proprietà globale del sistema e sono additive, oppure intensive, se esprimono una proprietà locale del sistema e non sono additive.

## Equilibrio Termodinamico
Un sistema termodinamico lasciato libero di evolversi in assenza di forze esterne, tende ad uno stato di **Equilibrio Termodianamico**, nel quale i valori delle variabili termodinamiche possono essere determinati e individuano il comportamento di tutto il sistema (le variabili sono quindi anche dette **Variabili di Stato**).
L'equilibrio termodinamico è il risultato di tre diversi tipi di equilibrio, che devono essere realizzati contemporaneamente 
- **Equilibrio Meccanico:** Equilibrio delle forze e momenti
- **Equilibrio Chimico:** Non avvengono reazioni chimiche
- **Equilibrio Termico:** La temperatura è la stessa ovunque

In uno stato di equilibrio esistono in generale relazioni tra le coordinate termodinamiche, dette **Equazioni di Stato**. Da due diversi stati di equilibrio dinamico, la trasformazione tra l'uno e l'altro si chiama **Trasformazione Termodinamica del Sistema**.

Si considerano due sistemi $A$ e $B$, entrambi in equilibrio termodinamico, con le rispettive temperature $T_{A}$ e $T_{B}$. I sistemi si dicono in equilibrio termico tra loro quando hanno la stessa temperatura ($T_{A}=T_{B}$), la temperatura è pertanto l'indicatore tra l'equilibrio termico tra due sistemi

> [!gray] Principio dell'Equilibrio Termico
> Sperimentalmente, si verifica che se due sistemi $A$ e $B$ sono ciascuno in equilibrio con un terzo sistema $C$ ($T_{A}=T_{C}$, $T_{B}=T_{C}$), allora essi sono in equilibrio termico tra loro $(T_{A}=T_{B})$

Un modo di mettere in equilibrio i due sistemi è quello di metterli in contatto tramite una parte:
- Se l'equilibrio viene raggiunto, si parla di **Parete Diatermica**
- Se non si raggiunge l'equilibrio, le due temperature sono indipendenti e la parte si dice **Adiabatica**. Se un intero sistema è circondato da pareti adiabatiche allora il sistema è detto adiabatico

Due sistemi separati da una parete diatermica si dicono anche in contatto termico tra loro, e inevitabilmente verrà raggiunto l'equilibrio termico.

Quindi:
- Una trasformazione che porta all'equilibrio termico avviene con scambio di calore
- Una parete diatermica permette il passaggio di calore da un sistema all'altro
- Una parte adiabatica non permette il passaggio di calore 

![[Pasted image 20250811115117.png|center|500]]

---
## Definizione di Temperatura
Si definisce $X$ *caratteristica termica* e la temperatura come funzione di questo parametro, $\theta(X)$, detta *funzione termometrica*. Il dispositivo che fornisce il valore della caratteristica termica è il termometro.

Deve esistere un sistema, in uno stato di equilibrio, definibile con precisione e riproducibile con facilità, al quale viene attribuito un valore arbitrario di temperatura (**Punto Fisso**).

> [!hint] Punto Triplo dell'Acqua
> Il punto fisso campione è il punto triplo dell'acqua, ovvero quello stato in cui il ghiaccio e vapore d'acqua saturo sono in equilibrio: si ottiene questo risultato alla temperatura di $273.16K$. Il kelvin infatti è definito come $\frac{1}{273.16}$ della temperatura del punto triplo dell'acqua.

Per descrivere numericamente la temperatura, si stabilisce che la funzione $\theta(X)$ sia $\theta(X)=a X$, con $a$ costante che viene determinate utilizzando il valore $X_{pt}$ che il termometro fornisce al punto triplo dell'acqua. Imponendo per defizione
$$
\theta(X_{pt})=a X_{pt}= 273.16
$$
Ne segue che la temperatura in Kelvin del sistema espressa dalla funzione $\theta(X)$ risulta
$$
T=273.16 \frac{X}{X_{pt}}
$$
Questa formula fornisce la **Temperatura Empirica** del termometro.

> [!info] Temperatura Empirica
> Si usa (sperimentalmente) il termine temperatura empirica in quanto si constata che termometri diversi danno sempre letture diverse quando sono in equilibrio termico con lo stesso stato del sistema, pur dando per costruzione tutti la stessa temperatura al punto triplo dell'acqua. Viene allora introdotta la *temperatura termodinamica assoluta*.


### Scale Termometriche
- **Scala Celsius:** La temperatura del punto triplo dell'acqua vale $0.01$ gradi Celsius, pertanto lo zero della scala Celsius è $273.15 K$. La conversione da Celsius a Kelvin è quindi $$t(C°)= T(K)-273.15$$
- **Scala Fahrenheit:** È definita rispetto alla scala Kelvin nel seguente modo: $$t(F°)= \frac{9}{5}T(K)-459.67$$
Il legame tra Fahrenheit e Celsius è
$$
t(F°)=\frac{9}{5}t(C°)+32\qquad t(C°)= \frac{5}{9}[t(F°)-32]
$$
![[Pasted image 20250811122958.jpg|center|400]]

## Termometro a Gas Ideale a Volume Costante ???
## Calorimetria
La quantità di calore $dQ$ che è necessario fornire ad un copro di massa $m$ per variarne la temperatura $dT$ è definita dalla
$$
dQ=mcdT
$$
con $c$ grandezza caratteristica della sostanza di cui è costituito il corpo, chiamata **Calore Specifico**
Si deduce dalla relazione precedente:

> [!gray] Calore Specifico
> $$
> c= \frac{1}{m} \frac{dQ}{dt}
> $$
> Il calore specifico rappresenta il calore che occorre scambiare con l'unità di massa di una data sostanza, alla temperatura $T$, per farne variare la temperatura di $1K$ (ovvero di $1°C$)

Il prodotto $C=mc$ rappresenta invece la **Capacità Termica** del corpo, ovvero il calore necessario per far variare di $1 K$ la temperatura del corpo.

Integrando $dQ$, si ottiene
$$
Q=\int dQ= m\int_{T_{in}}^{T_{fin}}c(T)\ dT
$$
che rappresenta la quantità di calore $Q$ necessaria per portare un corpo di massa $m$ dalla temperatura $T_{in}$ a $T_{fin}$.
Se il calore specifico è costante (caso generale), allora si ha
$$
Q=mc(T_{fin}-T_{in})
$$
Se si hanno due corpi a contatto in un recipiente adiabatico (quindi senza scambi di calore con l'esterno), allora $Q_{TOT}= Q_{1}+Q_{1}=0$, di conseguenza $Q_{1}=-Q_{2}$: il calore ceduto dal primo corpo (più caldo) è uguale in modulo a quello assorbito dal secondo corpo (più freddo).

![[Pasted image 20250811124313.png|center|400]]

Utilizzando la relazione precedente si ha
$$
m_{1}c_{1}(T_{e}-T_{1})=-m_{2}c_{2}(T_{e}-T_{2})
$$
Da cui si può calcolare la temperatura finale d'equilibrio:
$$
T_{e}= \frac{m_{1}c_{1}T_{1}+m_{2}c_{2}T_{2}}{m_{1}c_{1}+m_{2}c_{2}}= \frac{C_{1}T_{1}+C_{2}T_{2}}{C_{1}+C_{2}}
$$
che è la media pesata delle temperature dei due corpi.

Riprendendo la definizione di calore specifico, si può fare spesso riferimento ad un certo numero $n$ di moli di una sostanza. Pertanto si definisce il calore specifico molare
$$
c= \frac{1}{n} \frac{dQ}{dt}
$$
e quindi
$$
dQ=ncdt\qquad Q=nc(T_{fin}-T_{in})\qquad Q=n\int_{T_{in}}^{T_{fin}}c(T)\ dt 
$$

> [!info] Mole
> Una mole è la quantità di materia della sostanza che contiene $N_{A}=6.022\cdot 10^{23}$ entità elementari.
> Detta $A$ la massa molare di una sostanza, il numero di moli in una massa $M$ di quella sostanza è 
> $$
> n= \frac{M}{A}= \frac{M}{N_{A}m}
> $$
> con $m$ massa di una molecola.

---
## Trasformazioni Termodinamiche
Per un gas ideale, le variazioni di stato necessarie per la descrizione di un sistema sono pressione, volume e temperatura, delle quali solo due sono indipendenti a causa dell'esistenza dell'equazione di stato. Si scelgono allora $p$ e $V$ come variabili indipendenti, quindi con una coppia di valori $p,V$ si è in grado di descrivere lo stato termodinamico del sistema.
Un'evoluzione del sistema è rappresentabile graficamente attraverso una successione di stati intermedi, su un **Piano di Clapeyron**.

![[Pasted image 20250811150055.jpg|center|250]]
### Trasformazioni Reversibili e Irreversibili
Solo gli stati di equilibrio sono univocamente definiti e quindi rappresentabili sul piano di Clapeyron, in una trasformazione qualsiasi però gli stati intermedi attraverso quali passa il sistema possono essere sia di equilibrio sia non di equilibrio.

> [!example]+ Esempio 1:
> Due corpi solidi a temperature diverse $T_{1}$ e $T_{2}$ sono contenuti in un unico contenitore adiabatico. I due corpi vengono posti in contatto termico e c'è uno scambio di calore e alla fine raggiungono uno stato di equilibrio termico (temperatura intermedia tra $T_{1}$ e $T_{2}$). Durante il processo c'è sempre una differenza di temperatura finita tra i due corpi e quindi, durante la trasformazione, non c'è mai equilibrio termico: gli stati intermedi sono di *non equilibrio* (anche se c'è equilibrio meccanico e chimico).

> [!example]+ Esempio 2:
> Un contenitore adiabatico è diviso in 2 parti: in una c'è un gas a bassa pressione e nell'altra c'è una condizione di moto. Viene aperto un collegamento nella parte divisoria tra le due parti e il gas si espande fino a riempire completamente tutto il contenitore. Si osserva che in questo caso c'è equilibrio termico, ma non meccanico: in ogni istante c'è una differenza definita di pressione tra le due parti e solo alla fine del processo la pressione è la stessa ovunque. Gli stati intermedi sono di *non equilibrio*.

> [!example]+ Esempio 3:
> Un corpo con velocità iniziale $v$ viene frenato dall'attrito con il piano su cui si muove fino a fermarsi. L'energia cinetica diminuisce e contemporaneamente si osserva un aumento di temperatura delle superfici di contatto, del corpo e del piano. Si assume che questo processo sia breve (così da essere adiabatico), successivamente i corpi riscaldati cedono calore all'ambiente e alla fine tutto ritorna alla temperatura ambiente. Nella prima fase non c'è equilibrio meccanico, nella seconda fase non c'è equilibrio termico. Tutti gli stati intermedi sono di *non equilibrio*.

> [!example]+ Esempio 4:
> Un gas è contenuto in un recipiente, immerso a sua volta in una vasca d'acqua a temperatura costante $T$. Le pareti del recipienti sono diatermiche, per cui il gas è in equilibrio termico alla temperatura $T$. Muovendo la parete del contenitore si lascia espandere il gas in modo che ci sia sempre l'equilibrio termico con l'acqua. L'espansione viene effettuata applicando alla parete mobile una forza che in ogni istante è appena inferiore a quella di pressione esercitata dal gas, in modo che sia realizzato anche l'equilibrio meccanico. In questo caso tutti gli stati intermedi si possono considerare di *equilibrio* (se l'espansione del gas avviene in modo rapido non si realizzerebbero queste condizioni).

Si può trarre la conclusione che per effettuare una trasformazione che passi attraverso stati di equilibrio si deve procedere con variazioni molto piccole delle coordinate termodinamiche, in modo che queste siano in pratica definite in ogni istante. Per ottenere questo risultato in pratica si effettua una **Trasformazione Quasi-Statica**, scostando di molto poco uno stato di equilibrio per permettere che la trasformazione avvenga per poi far ristabilire l'equilibrio.
Oltre all'esame delle condizioni di equilibrio o non equilibrio si deve verificare l'eventuale presenza di forze dissipative (come attriti, scambi di lavoro ecc.)

Una trasformazione attraverso stati di non equilibrio può realizzarsi come conseguenza di un processo di espansione o compressione rapida per cui non sussiste né equilibrio meccanico né termico.


| Classificazione delle Trasformazioni |                                                                                                                                                                                       |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Trasformazione Reversibili**       | Una trasformazione è detta reversibile se essa avviene attraverso stati di equilibrio e in assenza di qualsiasi forza dissipativa                                                     |
| **Trasformazioni Irreversibili**     | Una trasformazione è detta irreversibile qualora non si svolga secondo le modalità precedenti, ossia passi attraverso stati di equilibrio o avvenga in presenza di forze dissipative. |

Le trasformazioni reversibili sono un caso limite (di difficile realizzazione), nelle quali si può invertire il verso della trasformazione ripercorrendo gli stessi passi all'indietro. Questa cosa non è possibile nelle trasformazioni irreversibili, visto che negli stati di equilibrio non è possibile assegnare un valore alle coordinate termodinamiche.
Solo le trasformazioni reversibili sono rappresentabili come una successione di punti.

![[Pasted image 20250811154102.jpg|center|300]]

## Lavoro Termodinamico
SI considerano due stati di equilibrio $A$ e $B$ di un sistema descritto dalle coordinate termodinamiche $p$, $V$, $t$ e suscettibile al cambio del proprio volume. Noti i valori della pressione e del volume, dall'equazione di stato si ricavano i valori della temperatura, e le trasformazioni effettuate dal sistema possono essere rappresentate nel piano di Clapeyron.

![[Pasted image 20250811162139.png|center|400]]

Quando il sistema si espande, o viene compresso avviene uno scambio di lavoro che in termini infinitesimi si può scrivere in generale $dW=pdV$. Per un fluido in compresione in una trasformazioni finita dallo stato $A$ allo stato $B$ si avrebbe
$$
W=\int_{A}^Bp(V)\ dV
$$
Questa espressione esplicita del lavoro è utile soltanto quando si conosce la funzione $p(V)$, circostanza verificata sostanzialmente in due situazioni:
- È nota la pressione esterna $p$ e quindi l'integrale è direttamente calcolabile in particolare per processi che avvengono a pressione atmosferica $p=p_{amb}$ è costante e $$W=p_{amb}(V_{B}-V_{A})$$
- La trasformazione è reversibile e pertanto si può calcolare l'integrale, dato che la pressione è determinata in ogni stato intermedio, $p=p_{sist}=p_{amb}$

In tutti gli altri casi dove $p(V)$ non è applicabile la formula.

> [!gray] Lavoro
> - Se la trasformazione è **Isocora** ($V=$ costante, $\Delta V=0$), il lavoro è sempre nullo
> - Se il sistema si espande il volume $V_{B}$ è maggiore del volume iniziale $V_{A}$ e il sistema compire un lavoro sull'ambiente (che secondo la convezione adottata è positivo)
> - Se il sistema viene compresso ($V_{B}<V_{A}$) il sistema subisce un lavoro negativo compiuto dall'ambiente
> 
> ![[Pasted image 20250811163856.png|center|700]]

> [!info] Calcolo del Lavoro
> Il lavoro compiuto dal sistema termodinamico è uguale all'area compresa tra la curva e l'asse dei volumi.
Il lavoro compiuto dal sistema termodinamico in una trasformazione ciclica reversibile è dato dall'area racchiusa dal ciclo stesso, il lavoro è positivo ($W>0$) se il ciclo è compiuto in senso orario, negativo ($W<0$) se in senso antiorario.
>
>![[Pasted image 20250811165131.jpg|center|400]]

