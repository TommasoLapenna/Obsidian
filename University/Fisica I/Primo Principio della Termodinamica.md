---
sticker: emoji//0039-fe0f-20e3
order: "10"
---
## Esperimenti di Joule
![[Pasted image 20250811172035.jpg|center|700]]

Il risultato fondamentale osservato da Joule è che il lavoro speso, a parità di massa d'acqua $W_{1}$ o $W_{2}$ o $W_{3}$ o $W_{4}$ è sempre proporzionale alla variazione di temperatura dell'acqua con la stessa costante di proporzionalità. Il sistema termodinamico massa d'acqua passa fa uno stato iniziale di equilibrio, caratterizzato dal valore $T_{in}$ della temperatura, a uno stato finale di equilibrio con temperatura $T_{fin}$ tramite 4 processi, ma il lavoro meccanico è lo stesso.
Il risultato che si osserva è il seguente: il lavoro è indipendente dal tipo di trasformazione che congiunge due stati termodinamici, purché il sistema sia adiabatico.

Sulle considerazioni sull'energia potenziale si enuncia la seguente relazione:
$$
W_{ad}=-\Delta U=U_{in}-U_{fin}
$$
con $U$ funzione che dipende solo dallo stato del sistema, cioè dalle sue coordinate termodinamiche. Se il sistema fornisce lavoro all'esterno, $W$ è assunto positivo ($U$ diminuisce), se invece l'esterno compie lavoro sul sistema $W$ è assunto negativo ($U$ aumenta).
...
Si ha che
$$Q=\Delta U$$
assumendo positivo il calore ceduto al sistema dall'esterno. Pertanto:

> [!gray] Equivalenza tra Calore e Lavoro
> $$
> Q=-W_{ad}
> $$
> Il calore $Q$ scambiato, senza lavoro esterno, per far variare la temperatura di $\Delta T$ di una massa d'acqua è uguale al lavoro $W_{ad}$ che deve essere speso, in condizioni adiabatiche, per ottenere la stessa variazione di temperatura.

## Primo Principio della Termodinamica, Energia Interna
Si considera un sistema che oltre allo scambio di lavoro meccanico con l'ambiente possa avere anche uno scambio di calore, cioè trasmissione di energia non accompagnata da fenomeni meccanici macroscopici. Sperimentalmente si trova sempre verificata una legge, nota come primo principio della termodinamica:

> [!gray] Primo Principio della Termodinamica
> Se un sistema compie una trasformazione dallo stato $A$ allo stato $B$, scambiando calore e lavoro con l'ambiente, $Q$ e $W$ dipendono dalla trasformazione che congiunge i due stati termodinamici, mentre la differenza $Q-W$ risulta indipendente dalla trasformazione.
> 
> ![[Pasted image 20250811180044.jpg|center|350]]
> 
> Si può pertanto scrivere, posto $\Delta U=U_{B}-U_{A}$
> $$
> \Delta U=Q-W
> $$

- Il primo principio mette in evidenza l'esistenza di un meccanismo di scambio di energia che non è esprimibile come lavoro meccanico macroscopico: si tratta del calore
- Esiste una funzione delle coordinate termodinamiche del sistema, ovvero una funzione di stato chiamata **Energia Interna** $U$, le cui variazioni dipendono dagli scambi energetici del sistema con l'ambiente che lo circonda durante una trasformazione
-  Quando durante una trasformazione si fornisce energia a un sistema, sia tramite lavoro meccanico che con uno scambio di calore, questa resta immagazzinata sotto forma di energia interna (che può poi essere successivamente riutilizzata)
- Il termine energia interna indica che non si tratta dell'energia cinetica del sistema in senso macroscopico, ma dell'energia legata alla proprietà interne al sistema che non dipendono dallo stato complessivo di moto, ma dalla temperatura, dalla pressione e dal volume che occupa (come moto molecolare o forze intermolecolari)
- La quantità $\Delta U$ può essere calcolata direttamente se è nota l'espressione esplicita, altrimenti si può utilizzare la formula $\Delta U=Q-W$
- Se si conoscono le espressioni di $\Delta U$, $Q$ e $W$ in funzione delle coordinate termodinamiche, la formula $\Delta U=Q-W$ diventa un'equazione che lega le coordinate termodinamiche durante la trasformazione, ovvero diventa l'equazione della trasformazione
- Il calore e il lavoro sono forme di scambi di energia, quindi si parla di calori e lavori scambiati tra sistema, e non lavori e calori posseduti dai sistemi
- Se un sistema termodinamico esegue una qualsiasi trasformazione che lo riporta allo stato iniziale si ha una trasformazione ciclica $$\Delta U=0\Longrightarrow Q=W$$quindi il calore scambiato è uguale al lavoro scambiato. Se nella trasformazione ciclica il sistema complessivamente assorbe calore, allora si ha $Q>0$ che fornisce lavoro $W>0$ e costituisce una macchina termica, viceversa se cede calore
- In una trasformazione termodinamica con variazioni infinitesime delle variabili di stato, si ha $$dU=dQ-dW$$ed integrando per una trasformazione finita si ha $$\Delta U=\int_{A}^B dU=U_{B}-U_{A}$$indipendente dalla trasformazione. Il calore e il lavoro scambiati nella trasformazione finita si ottengono integrando nuovamente $$Q_{AB}=\int_{A}^BdQ\qquad W_{AB}=\int_{A}^B dW$$Si conclude che la variazione infinitesima di energia interna è un differenziale esatto, mente $dQ$ e $dW$ non sono differenziali esatti

L'unità di misura di energia interna, calore e lavoro è il *joule*.
### Convenzione sui Segni di Calore e Lavoro
- Calore che entra in un sistema dall'esterno $\Longrightarrow$ *segno positivo*
- Lavoro che è compiuto da un sistema sull'esterno $\Longrightarrow$ *segno positivo*
- Calore che esce da un sistema verso l'esterno $\Longrightarrow$ *segno negativo*
- Lavoro che è compiuto dall'esterno sul sistema $\Longrightarrow$ *segno negativo*

![[Pasted image 20250811190159.png|center|400]]

---
## Leggi dei Gas, Equazione di Stato dei Gas Ideali

> [!info] Definizione Gas
> Un gas è un fluido con le seguenti caratteristiche:
> - Non ha né forma né volume propri, occupa pertanto tutto il volume a disposizione
> - È facilmente comprimibile, con conseguenti variazione di volume notevoli, densità e pressione
Le variabili termodinamiche più appropriate per descrivere lo stato termodinamico di un gas sono la pressione $p$, il volume $V$ e la temperatura $T$

### Legge Isoterma di Boyle (Temperatura Costante)
Si abbia un gas in equilibrio termodinamico a una certa pressione $p$, entro un dato volume $V$ e a temperatura $T$. Se si fanno variare la pressione e il volume, mantenendo costante la temperatura, si trova che in tutti i possibili stati di equilibrio isotermi il prodotto della pressione per il volume ha sempre lo stesso valore:

> [!gray] Legge di Boyle
> $$pV=\text{costante}$$
> A temperatura costante, la pressione è inversamente proporzionale al volume
> 
> ![[Pasted image 20250812091541.jpg|center|300]]
>

Se il gas passa da uno stato di equilibrio $p_{1}$ e volume $V_{1}$ ad un altro con pressione $p_{2}$ e volume $V_{2}$, vale sempre la legge di Boyle:
$$
p_{1}V_{1}=p_{2}V_{2}
$$
Nel piano di Clapeyron gli stati di equilibrio del gas formano un'iperbole, per ogni temperatura si ottengono delle curve chiamate *isoterme del gas ideale*.
### Legge Isobara di Volta-Gay Lussac (Pressione Costante)
Se la pressione di un gas rimane costante durante la trasformazione, si parla di *trasformazione isobara* e si verifica che in queste condizioni:

> [!gray] Legge Isobara di Volta-Gay Lussac
> $$V=V_{0}(1+\alpha t)$$
> Il volume varia linearmente con la temperatura, con $V_{0}$ volume occupato dal gas al tempo $t=0$, $\alpha$ costante che varia a seconda del gas (*coefficiente di dilatazione termica*) e la temperatura espressa in $°C$.
> 
> ![[Pasted image 20250812092818.png|center|350]]
> 

Si verifica la validità di questa legge mettendo il gas in equilibrio termico con diverse sorgenti di calori, mantenendo sempre l'equilibrio meccanico con l'ambiente, per poi misurare il volume del contenitore (con una parete mobile).
Nel piano $(p,V)$, la trasformazione è rappresentata da un segmento parallelo all'asse dei volumi.
### Legge Isocora di Volta-Gay Lussac (Volume Costante)
Se si mantiene costante il volume di un gas (condizione isocora), allora:

> [!gray] Legge Isocora di Volta-Gay Lussac
> $$
> p=p_{0}(1+\beta t)
> $$
> La pressione risulta funzione lineare della temperatura, con $p_{0}$ pressione del gas al tempo $t=0$, $\beta$ costante (indipendente dal tipo di gas) e temperatura espressa in $°C$
>
> ![[Pasted image 20250812093625.png|center|350]]

Nel piano $(p,V)$ la trasformazione isocara è rappresentata da un segmento parallelo all'asse della pressione.
Questa legge si verifica mantenendo bloccata la parte mobile del contenitore e misurando la pressione in diversi stati di equilibrio, al variare della temperatura
### Leggi di Volta-Gay Lussac nei Gas Ideali
Quando le condizioni si avvicinano a quelle dei gas ideali, ovvero bassa pressione ed alta temperatura, si osserva che le costanti $\alpha$ e $\beta$ assumono lo stesso valore per tutti i gas:
$$
\alpha=\beta= \frac{1}{273.15}°C^{-1}
$$
Le due leggi di Volta-Gay Lussac possono allora essere riscritte come
$$\begin{gather}
V=V_{0}\alpha\left( \frac{1}{\alpha}+t \right)= V_{0}\alpha T \\
p=p_{0}\alpha\left( \frac{1}{\alpha}+t \right)=p_{0}\alpha T
\end{gather}$$
con $T= \frac{1}{\alpha}+t= 273.15+t$.
### Legge di Avogrado
Si esprime adesso una legge collegata alla struttura microscopica di un gas:

> [!gray] Legge di Avogrado
> Volumi uguali di gas diversi, alla stessa temperatura e pressione, contengono lo stesso numero di molecole. Ciò vuol dire che questi due gas contengono la stessa quantità di moli.
>
>
> 

La conseguenza di questa legge è che una mole di qualsiasi gas, a una data temperatura e pressione, occupa sempre lo stesso volume. SI trova che la pressione è quella atmosferica ($p_{0}=101325\ Pa$) e la temperatura è $T_{0}=273.15\ K=0 \ °C$, tale volume vale 
$$
V_{m}=0.02241\ m^3=22.41\ l
$$
con $V_{m}$ volume molare.
### Equazione di Stato del Gas Ideale
Si cerca adesso un'equazione per i gas perfetti che metta in relazione $p$, $V$, $T$ in un dato stato termodinamico. Se si considerano $n$ moli di un gas alla pressione atmosferica $p_{0}$ e alla temperatura $T_{0}=273.15\ K$, esse occupano il volume $V_{0}=nV_{m}$. Si porta adesso questo gas da uno stato $A$ ad un altro stato $C$, ciò può essere fatto attraverso (per esempio) attraverso una trasformazione isocora $AB$ seguita da un isoterma $BC$. La pressione nello stato $B$ è quindi $p_{B}=p_{0}\alpha T$.

![[Pasted image 20250812100448.jpg|center|350]]

Nell'isoterma, per la legge di Boyle si ha
$$
pV=p_{B}V_{0}=p_{0}\alpha TV_{0}=np_{0}V_{m}\alpha T
$$
Il prodotto $p_{0}V_{m}\alpha$ è una costante universale, che ha lo stesso valore per tutti i gas, quindi si ha una relazione per i gas ideali:

> [!gray] Equazione di Stato del Gas Ideale
> $$
> pV=nRT
> $$
> con $R=p_{0}V_{m}\alpha=8.314 \frac{J}{mol\ K}$
> 
> Sulla base delle tre leggi elementari e la legge di Avogrado, si definisce quindi come **Gas Ideale** un sistema le cui coordinate termodinamiche in uno stato di equilibro obbediscono all'equazione di stato precedente. Pertanto un gas ideale il prodotto della pressione per il volume è proporzionale al numero di oli e alla temperatura attraverso la costante $R$, detta **Costante dei Gas Ideali**.

In un gas ideale in equilibrio sono indipendenti solo due variabili, in quanto la terza si ricava attraverso l'equazione di stato.

È possibile scrivere l'equazione di stato in forme diverse: ad esempio se al posto del volume si utilizza la densità $\rho= \frac{M}{V}$ e al posto della massa del gas si usa $An$ (con $A$ massa molecolare)
$$
\frac{p}{\rho}= \frac{RT}{A}
$$
---
## Calori Specifici del Gas Ideale
In una trasformazione un gas può scambiare calore con l'ambiente e per il calcolo è possibile usare il primo principio. Nelle trasformazioni isoterme invece si può ricorrere al concetto di calore specifico, precisando il tipo di processo. Per una trasformazione infinitesima isocora si ha $dQ=nc_{V}dT$ mentre per quella isobara si ha $dQ=nc_{p}dT$, queste quantità sono
$$
c_{V}= \frac{1}{n}\left(  \frac{dQ}{dT} \right)_{V}\qquad c_{p}= \frac{1}{n}\left( \frac{dQ}{dT} \right)_{p}
$$
chiamate **Calore Specifico Molare a Volume Costante** e **Calore Specifico a Pressione Costante** e si misurano in $\frac{J}{mol\ K}$.
Generalmente $c_{V}$ e $c_{p}$ variano molto poco con la temperatura, per cui il valore scambiato per una variazione $\Delta T$ di temperatura si scrive
$$
Q_{V}=nc_{V}\Delta T\qquad Q_{p}=nc_{p}\Delta T
$$
Altrimenti
$$
Q_{V}=n \int_{T_{A}}^{T_{B}}c_{V}\ dT\qquad Q_{p}=n\int_{T_{A}}^{T_{B}}c_{p}\ dT
$$
Il calore scambiato dipende soltanto dalla variazione di temperatura.

Si dimostra che per un gas ideale si deve avere $c_{p}>c_{V}$, si considerano infatti due trasformazioni, una isocora e una isobara, durante la quale si abbia la stessa variazione positiva di temperatura $\Delta T$. Dal primo principio si sa che $Q=\Delta U+W$, che applicato alla trasformazione isocora $AB$ risulta
$$
Q_{V}=nc_{V}\Delta T= \Delta U
$$
in quanto $W=0$, mentre nella trasformazione isobara $AC$ invece $W=p\Delta V$ positivo, perché il valore cresce con la temperatura e quindi
$$
Q_{p}= nc_{p}\Delta T=\Delta U+p\Delta V
$$

![[Pasted image 20250812113016.jpg|center|350]]

Dato che la variazione di temperatura è la stessa nelle due trasformazioni e che l'energia interna è funzione della sola temperatura, la variazione $\Delta U$ è la stessa nei due caso, quindi $Q_{p}>Q_{V}$ da cui segue $c_{p}>c_{V}$:

> [!hint] Osservazione
> Il calore che si deve cedere a una mole di gas per fare aumentare la temperatura di $1\ K$ è maggiore a pressione costante che a volume costante, perché a pressione costante il gas compie anche lavoro.

## Energia Interna del Gas Ideale
La dipendenza dell'energia interna di un gas ideale dalle coordinate termodinamiche è ricavata usando il risultato dell'esperienza sull'espansione libera eseguita da Joule:

![[Pasted image 20250812114049.jpg|center|1000]]

Dal primo principio applicato all'interno del sistema segue che $\Delta U= \Delta U_{gas}+\Delta U_{cal}= Q-W=0$, in quanto il sistema non scambia né il calore né il lavoro con l'ambiente. Ne segue che nell'espansione libera l'energia di un gas ideale non varia, si può allora raggiungere la conclusione che nel processo la temperatura del gas non cambia, mentre variano pressione, volume ed energia: l'energia interna deve essere funzione soltanto della temperatura.
Questo risultato è vero rigorosamente solo per un gas ideale.

Per determinare l'espressione esplicita della funzione $U(T)$ si considerano due generici stati di equilibrio $A$ e $B$: $\Delta U=U_{B}-U_{A}$ deve essere la stessa qualsiasi trasformazione si scelga, essendo $U$ una funzione di stato.
Se si sceglie una trasformazione $AC$ isocora e una $CB$ isoterma si ha
$$
\Delta U=U_{B}-U_{A}= U_{B}-U_{C}+U_{C}-U_{A}=U_{C}-U_{A}
$$
in quanto $U_{B}=U_{C}$ essendo gli stati $B$ e $C$ alla stessa temperatura e $U$ funzione solo della temperatura

![[Pasted image 20250812115222.jpg|center|350]]

Si applica il primo principio alla trasformazione isocora dato che $W=0$, $\Delta U=Q$ dove $Q$ è il calore scambiato in condizione isocore. Pertanto
$$\begin{gather}
\Delta U=U_{B}-U_{A}=nc_{V}(T_{B}-T_{A})=nc_{V}\Delta T \\
\Delta U=U_{B}-U_{A}=n \int_{T_{A}}^{T_{B}}c_{V}\ dt 
\end{gather}$$
Per trasformazioni initesime:
$$
dU=nc_{V}dT
$$
da cui si ricava
$$
c_{V}= \frac{1}{n} \frac{dU}{dT}
$$
Poiché l'energia interna è funzione soltanto della temperatura, anche il calore specifico a volume costante di un gas ideale dipende solo dalla temperatura, potendo essere, in particolare, costante.

Si può scrivere adesso in maniera esplicita il primo principio per quel che riguarda le trasformazioni di gas ideali, considerando $c_{V}$ costante:
$$
dQ=nc_{V}dT+dW\Longrightarrow Q=nc_{V}\Delta T+W
$$
^pppp

Se la trasformazione è reversibile diventano
$$
dQ=nc_{V}dT+pdV\Longrightarrow Q=nc_{V}\Delta T+\int_{V_{A}}^{V_{B}}p\ dV
$$
### Relazione di Mayer
In un gas ideale il calore specifico a pressione costante è maggiore di quello a volume costante, si pone adesso questa affermazione in modo quantitativo.
In una trasformazione isobara infinitesima, $dQ=nc_{V}dT$  e $dW=pdV$ per cui, dalla [[#^pppp|relazione precedente]], si ha che
$$
nc_{p}dT= nc_{V}dT+pdV
$$
Differenziando l'equazione di stato di stato dei gas ideali $pV=nRT$ si ha
$$
pdV+Vdp=nRdT
$$
In una trasformazione isobara $dp=0$ e quindi $pdV=nRdT$. Pertanto
$$
nc_{p}dT=nc_{V}dT+nRdT
$$
e in conclusione si ottiene la **Relazione di Mayer**
$$
c_{p}
-c_{V}=R$$

Di conseguenza in un gas ideale anche $c_{p}$ è funzione soltanto della temperatura potendo in particolare essere costante.

Il rapporto tra i calori specifici
$$
\gamma= \frac{c_{p}}{c_{V}}
$$
risulta (in un gas ideale) sempre maggiore di 1 ed è funzione soltanto della temperatura o, in particolare, costante. Sperimentalmente si trovano per i calori specifici dei gas ideali questi risultati:

![[Pasted image 20250812160252.jpg|center|1000]]

Nei primi due casi si usano le relazioni
$$
\begin{align}
& \Delta U=nc_{V}\Delta T& &\text{per qualsiasi trasformazioni}& \\
&Q=nc_{V}\Delta& &\text{se }V=\text{costante}\quad Q=nc_{p}\Delta T\quad\text{se }p=\text{costante}& 
\end{align}
$$
^apap

Per un gas ideale si hanno le seguenti proprietà
$$
\begin{align}
&\text{Equazione di stato}& &pV=nRT\quad \text{in uno stato di equilibrio}& \\
&\text{Relazione di Mayer}& &c_{p}-c_{V}=R&
\end{align}
$$
---
## Studio di Alcune Trasformazioni del Gas Ideale
### Trasformazioni Adiabatiche
Il gas è racchiuso in un contenitore con pareti adiabatiche e quindi può scambiare solo lavoro. Dal primo principio e dalla [[#^apap|relazione precedente]] si ha una trasformazione tra due qualsiasi stati di equilibrio $A$ iniziale e $B$ finale
$$
W_{AB}=-\Delta U=-nc_{V}(T_{B}-T_{A})= \frac{1}{\gamma-1}(p_{A}V_{A}-p_{B}V_{B})
$$
Se si ha un'espansione adiabatica il lavoro $W_{AB}$ è positivo e quindi $\Delta U$ è negativo e $T_{B}$ è minore di $T_{A}$ e il gas si raffredda; se invece si ha una compressione adiabatica, $W_{AB}<0$, $\Delta U>0$, $T_{B}>T_{A}$ il gas si riscalda.
Non è possibile ricavare altre relazioni tra le coordinate termodinamiche di due stati collegati da una trasformazione adiabatica generica salvo alcune limitazioni.

Se invece la trasformazione è adiabatica reversibile, l'espressione infinitesima del primo principio diviene
$$
dQ=dU+dW=nc_{V}dT+pdV=0
$$
in quanto si può esprimere il lavoro in funzione delle coordinate termodinamiche (perché la trasformazione è reversibile). Si può utilizzare l'equazione di stato di un qualsiasi stato intermedio per esprimere la pressione come $p=\frac{nRT}{V}$ e si ottiene
$$
nc_{V}dT+ \frac{nRT}{V}dV=0
$$
Si separano le variabili e si utilizza la relazione di Mayer
$$
\frac{c_{p}-c_{V}}{c_{V}} \frac{dV}{V}=- \frac{dT}{T}\Longrightarrow (\gamma-1) \frac{dV}{V}=- \frac{dT}{T}
$$
Questa equazione differenziale rappresenta la condizione a cui obbediscono le coordinate degli stati in un gas ideale collegati da una trasformazione adiabatica reversibile. Integrando dallo stato $A$ allo stato $B$
$$
(\gamma-1) \ln \frac{V_{B}}{V_{A}}=\ln \frac{T_{A}}{T_{B}}\Longrightarrow \ln\left( \frac{V_{B}}{V_{A}} \right)^{\gamma-1}=\ln \frac{T_{A}}{T_{B}}
$$
L'uguaglianza tra i logaritmi comporta l'uguaglianza tra gli argomenti, per cui
$$
T_{A}V_{A}^{\gamma-1}= T_{B}V_{B}^{\gamma-1}
$$
da la relazione tra le coordinate termodinamiche del gas durante una trasformazione adiabatica reversibile.
Tramite l'equazione di stato si può trasformare la relazione tra $T$ e $V$ in una tra $p$  e $V$ o tra $p$ e $T$, ottenendo 3 equazioni equivalenti:
$$
TV^{\gamma-1}=\text{costante}\qquad pV^{\gamma}=\text{costante}\qquad Tp^{\frac{1-\gamma}{\gamma}}=\text{costante}
$$
