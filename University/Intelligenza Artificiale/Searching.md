---
sticker: emoji//0031-fe0f-20e3
---
## Agenti ed Ambienti
Un agente è un qualsiasi elemento che può interagire con l'ambiente nel quale è immerso (attraverso dei sensori), e può anche agire su esso (attraverso degli attuatori).

![[IMG_1098.jpeg|center|500]]


Attraverso la percept sequence di un agente, si ha una lista completa di ciò che ha percepito attraverso i sensori. Di conseguenza le azioni che vengono effettivamente attuate dall'agente in un dato istante è nota e basata su ciò che è stato percepito fino a quel momento (ma niente di ciò che deve ancora percepire), in termini matematica questo comportamento è mappato da una agent function (implementato da un agent program).

È possibile espandere su delle caratteristiche di razionalità dell'agente:
- **Performance:** si valutano la sequenza di azioni effettuate sull'ambiante (in base a ciò che l'agente ha percepito) e se ne valuta le conseguenze che hanno sullo stato dell'ambiente (*consequentialism*). Si definisce quindi una performance mesure che valuta gli stati intrapresi dall'ambiente.
- **Rationality:** per agente razionale si intende un agente che, per ogni possibile percept sequence, massimizza la performance mesure.
- **Omniscience:** occorre infine distinguere razionalità da onniscenza (in quanto quest'ultima non è possibile realemente). Un agente onniscente conosce già quale sarà il risultato delle sue azioni, si distingue allora l'onniscenza dalla razionalità: la razionalità massimizza l'*expected permormance*, mentre l'altra massimizza l'*actual performance*.

Si determinano adesso le caratteristiche di un ambiente e il suo stato:
- **Fully Observable / Partially Observable:** se un agente ha accesso allo statoi dell'ambiente ad ogni momento.
- **Single-Agent / Multi-Agent:** se più agenti agiscono su uno stesso ambiente, possono collaborare o competere.
- **Deterministic / Nondeterministic (Stochastic):** se lo stato successivo dell'ambiente è completamente determinato dallo stato corrente e dalle azioni eseguite. Si usa il termine stocastico se un agente nondeterministico utilizza esplicitamente le probabilità.
- **Episodic / Sequential:** se l'ambiente è diviso in episodi, dove le azioni di quello successivo non sono determinate da quello precedente (altrimenti è sequenziale).
- **Static / Dynamic:** se l'ambiente varia mentre l'agente sta operando.
- **Discrete / Continuous:** a seconda dei tipi di variabili che descrivono lo stato dell'ambiente e il modo in cui è gestito il tempo.
- **Known / Unknown:** in base alla conoscenza che ha l'agente sull'ambiente.

Si distinguono inoltre le diverse tipologie di agenti:
- **Simple Reflex Agents:** agenti che si basano sulle percezioni presenti e non hanno uno storico di quelle passate.
- **Model-Based Reflex Agents:** agenti che mantengono uno stato interno che tiene traccia delle percezioni passate.
- **Goal-Based Agents:** agenti che si basano sul goal state per prendere decisioni riguardo lo stato in cui si trovano in quel momento.
- **Utility-Based Agents:** agenti che prendono decisioni all'interno di un ambiente in base alla scelta più ottimale (utility), utilizzando un'utility function.
- **Learning Agents**
- **Problem Solving Agents**
## Search Problems
### Problem-Solving Agents
Quando l'azione corretta non è immediatamente ovvia, un agente deve pianificare le azioni da usare (sequenza di azioni che formano un percorso fino ad un goal state). Gli agenti che si comportano in questo modo si chiamano **Problem-Solving Agents** e il processo che svolgono si chiama **Search**.

Il processo di problem-solving segue 4 fasi:
- **Goal Formulation:** viene fissato l'obiettivo.
- **Problem Formulation:** l'agente decide quali stati ed azioni sono necessari per raggiungere il goal.
- **Search:** prima di effettuare azioni nella realtà, l'agente simula le sequenze di azioni attraverso il suo modello, per trovare la **solution**
- **Execution:** vengono attuate le azioni individuate nella solution.


> [!info] Nota 
> In un ambiente fully observable, deterministic, known environment, la soluzione deve essere una sequenza finita di azioni.

### Search Problem and Solutions
Un problema può essere definito nel seguente modo:

| **Set of States**        | $S$, possibili stati dell'ambiente                                                                        |
| ------------------------ | --------------------------------------------------------------------------------------------------------- |
| **Initial States**       | stato da dove parte l'agente                                                                              |
| **Set of Goal State**    | uno o più obiettivi dell'agente                                                                           |
| **Set of Actions**       | $A(s),\ s\in S$ azioni possibili dell'agente dato uno stato $s$                                           |
| **Transaction Models**   | $\{results(a,s), \ a\in A(s)\}\subset S$                                                                  |
| **Action Cost Function** | $cost(s,a,s')$ funzione che ritorna il costo dell'azione $a$ per passare dallo stato $s$ allo stato $s'$. |
Una sequenza di azioni forma un percorso, e se questo percorso congiunge lo stato iniziale con lo stato goal allora è una soluzione. La soluzione ottimale è la soluzione il cui percorso ha il costo minore.
Lo spazio degli stati può essere rappresentato come un grafo, nel quale i vertici sono gli stati e i collegamenti tra loro sono le azioni.
### Formulating Problems
Un modello è una descrizione matematica astratta della realtà, perciò è opportuno definire un certo livello di astrazione


> [!info] Astrazione
> Un'astrazione è valida se è possibile elaborare una soluzione astratta per ottenere una soluzione nel mondo reale.

> [!example]+ Esempio: Sliding Tiles 
> ![[IMG_1100.jpeg|center|400]]
> 
> 
> | **States**                 | Posizione delle caselle                                                                        |
> | -------------------------- | ---------------------------------------------------------------------------------------------- |
> | **Initial State**          | Qualunque stato può essere uno stato iniziale                                                  |
> | **Actions**                 | La formulazione più semplice nello spostamento degli spazi vuoti in su, giù, destra e sinistra |
> | **Transaction Model** | Mappa tra stato e azione risultante                                                            |
> | **Goal Test**              | Determina se lo stato corrente è il goal                                                       |
> | **Path Cost**              | Ogni azione ha costo unitario                                                                  |
> Questo problema ha $\frac{9!}{2}=181440$ stati.

> [!example]+ Esempio: Problema delle 8 Regine
> ![[Pasted image 20260303102301.png|center]]
> 
> Il problema consiste nel piazzare 8 regine sulla scacchiera in modo che non si attacchino a vicenda.
>$$\mathcal S = \sum^8_{k=0} \begin{pmatrix}
n^2 \\ k
\end{pmatrix}$$
> - Formulazione Incrementale: a partire dalla scacchiera vuota si aggiunge una regina alla volta:
> 
> | **States**            | Ogni piazzamento sulla scacchiera della regina da 0 a 8                   |
> | --------------------- | ------------------------------------------------------------------------- |
> | **Initial State**     | Scacchiera Vuota                                                          |
> | **Actions**           | Aggiunta di una regina in una casella vuota                               |
> | **Transaction Model** | Restituisce la scacchiera con una regina in più nella casella specificata |
> | **Goal Test**         | Scacchiera con 8 regine che non si attaccano                              |
> In questa formulazione ci sono $64\cdot 63\dots \cdot 57\approx 1,8\times 10^{14}$ possibili sequenze.
> - Formulazione a Stato Completo:
> 
> | **States**            | Configurazione di $n$ regine($0\le n\le 8$), una per colonna, a partire da sinistra, in modo tale che nessuna regina attacchi l'altra |
> | --------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
> | **Actions**           | Aggiungere regina nella prima colonna libera a partire da sinistra, in modo tale che non attacchi o non sia attaccata.                |
> In questa formulazione si riduce lo spazio degli stati a solo $2057$.
> A differenza degli algoritmi per il cammino, non c'è frontiera (not systematic exploration).

> [!example]+ Esempio: Donald Knuth, Derivation of any positive integer
> $$ \left\lfloor \sqrt{ \sqrt{ \sqrt{ \sqrt{ \sqrt{ (4!)! } } } } }=5\right\rfloor$$
> 
> | **States**            | Numeri positivi reali                             |
> | --------------------- | ------------------------------------------------- |
> | **Initial States**    | 4                                                 |
> | **Actions**           | Si esegue la radice quadrata, floor, o fattoriale |
> | **Transaction Model** | Data dalla definizione matematica degli oprandi   |
> | **Goal State**        | Numero intero positivo desiderato                 |
> | **Action Cost**       | 1                                                 |
> Lo state space di questo problema è infinito.

Si ricorda che le azioni hanno un costo:
$$
cost(s_{t-1},a_{t})
$$
e il costo totale per un goal è 
$$
\sum^I_{t=1}cost(s_{t-1},a_{t})
$$
![[IMG_1104.jpeg]]
## Search Algorithms
Un algoritmo di ricerca è prende come input un search problem e restituisce una soluzione, oppure un'indicazione di fallimento. Come menzionato precedentemente, i nodi corrispondono ad uno stato nello state space e gli archi corrispondono alle azioni.
Occorre effettuare una distinzione tra lo state space e il search tree: il primo (possibilmente infinito) descrive la totalità di stati reali e gli stai che li congiungono, mentre il secondo descrive i percorsi tra gli stati fino a raggiungere il goal state (ma ogni nodo ha un solo percorso che ritorna alla root).
### Search Tree
La root corrisponde all'*Initial State*, i rami corrispondono alle *Actions* e i nodi rappresentano gli *States*.
Quando si percorre l'albero per ricercare il goal, si esegue un'espansione del nodo ad ogni passo, considerando le *ACTIONS* per quello stato, utilizzando la funzione *RESULT* per vedere dove le azioni conducono e per ognuna si genere un nuovo nodo figlio. Successivamente si sceglie quale figlio considerare (in base all'algoritmo) e si ripete il processo.

> [!info] Albero Infinito
> Si tratta di una struttura dati concettuale: infatti durante la ricerca del goal state è possibile effettuare l'operazione di espansione un numero infinito di nodi.

![[Gemini_Generated_Image_47f2qx47f2qx47f2.png|center||600]]

Negli algoritmi di ricerca, si costruisce un sottoinsieme di questo albero infinito: si utilizza una struttura dati detta **Frontiera**, ed ogni nodo generato che si trova in esso è considerato raggiunto (quindi separa i nodi già incontrati da quelli ancora da visitare).

> [!gray] Frontier Separation Propriety
> Ogni cammino dai nodi esplorati a quelli inesplorati interseca la frontiera.

Occorre prendere in considerazione anche la gestione dei loop (percorsi che portano allo stesso stato) e soprattutto dei nodi duplicati, che posso essere gestiti nei seguenti modi:
- **Hash Table:** Si usa una closed list nella quale si inseriscono i nodi visitati
- **Who Cares**
- **Only Check Loops:** Consuma meno memoria, non è esaustivo

### Search Data Structures
- **node:** 
	- STATE: stato al quale corrisponde il nodo
	- PARENT: il nodo dell'albero che l'ha generato
	- ACTION: l'azione che è stata applicata allo stato del nodo padre per generare quello corrente
	- PATH_COST: costo calcolato a partire da quello iniziale ($g(node)$)
	
- **frontier:**
	- IS-EMPTY(frontier): ritorna vero se non ci sono nodi nella frontiera
	- POP(frontier): rimuove il nodo in testa e lo ritorna
	- TOP(frontier): ritorna il nodo in testa
	- ADD(node, frontier): inserisce il nodo nella posizione appropriata nella coda

- **priority queue**: il pop viene effettuato sul nodo col costo minore (calcolato con $f$), usato nel BEST-FIRST SEARCH
- **FIFO QUEUE:** il pop viene effettuato sul primo elemento inserito nella lista.
- **LIFO QUEUE:**  il pop viene effettuato sull'ultimo elemento inserito nella lista.

Gli stati raggiunti sono invece salvati su una lookup table (come una tabella di hash), dove ad ogni chiave è associato uno stato e il valore del nodo per quello stato.

## Blind Search
### Best-First Search
Un primo approccio per decidere quale nodo espandere a partire dalla frontiera è il Best-First Search

``` python
# P problema, f evaulation funcrion, PQ priority queue
BEST-FIRST-SEARCH(P, f)
	n = Node(STATE = P.INITIAL)
	frontier = PQ(f)
	reached = Hash({P.INITIAL, n})
	while not IS-EMPTY(frontier)
		# L'elemento del POP dipende dal criterio di f
		n = frontier.POP()
		if P.is-goal(n.state)
			return n
		for c in EXPAND(P, n)
			s = c.STATE
			if s not in reached or c.PATH_COST < reached[s].PATH_COST 
				reached[s] = c
				frontier.PUSH(c)
	return None

EXPAND(P, n)
	s = n.STATE
	for a in P.ACTIONS(s)
		s_1 = P.RESULT(a, s)
		cost = n.PATH_COST + P.STEP_COST(s, a)
		yield Node(state = s_1, parent = n, action = a, path_cost = cost)
```

### Breadth-First
Quando tutte le azioni hanno lo stesso costo, allora è una buona idea usare la Breadth-First search, dove a partire e nodo e poi successivamente per ogni figlio, vengono espanti tutti i nodi. Si tratta di una ricerca *sistematica*, perciò questo algoritmo gode della proprietà di completeness (anche su spazi infiniti).
Può essere implementato con l'algoritmo del Best-First Search ponendo la funzione $f(n)$ come profondità del nodo, ma risulta più efficiente un'implementazione con una coda FIFO. Inoltre, siccome il primo goal che si trova sarà sicuramente il migliore (in quanto una volta raggiunto uno stato si è già trovato anche il percorso ottimale ad esso) si può effettuare un'early goal test, non appena il nodo viene generato (in questo caso reached è un insieme di stati invece che di percorsi).
Infine è anche cost optimal, visto che che trova la soluzione con un numero minimo di azioni.

``` python
BREADTH-FIRST-SEARCH(P)
	node = Node(P.INITIAL)
	if P.IS-GOAL(node.STATE)
		return node
	frontier = FIFO
	reached = {P.INITIAL}
	while not IS-EMPTY(frontier)
		node = POP(frontier)
		for each child in EXPAND(P, node)
			s = child.STATE
			if P.IS-GOAL(s) 
				return child
			if s is not in reached
				add s to reached
				add child to frontier
	return failure

UNIFORM-COST-SEARCH(P)
	return BEST-FIRST-SEARCH(P, PATH-COST)
```

### Dijkstra
Quando ci sono costi diversi per le azioni, risulta allora ovvio usare l'algoritmo di Best-First search, dove l'evaluation function è il costo del cammino dalla root fino al nodo corrente. L'algoritmo che si ottiene è chiamato algoritmo di Dijkstra, o nel campo dell'ai **Uniform-Cost Search**.

> [!info] Evaluation Function
> $f(n)$= PATH-COST

## Misurazione Performance del Problem-Solving
Siccome i problemi proposti utilizzano grafi teoricamente infiniti, a differenza di problemi con strutture dati esplicite (dove le misure dei costi si effettuano con $|E|$ e $|V|$), nei problemi di ai (dove lo state space è *implicito*) si utilizzano i seguenti termini:
- $d$: depth of the shallowest goal in the search tree (soluzione ottimale)
- $b$: branching factor, ovvero il numero massimo di azioni che si possono fare in un generico stato
- $m$: lunghezza del cammino più luno del grafo (maximum number of action in any path)
Ci sono anche altri criteri con il quale si valutano gli algoritmi:
- **Completeness:** Se esiste una soluzione, allora verrà trovata sicuramente dall'algoritmo.
- **Cost Optimality:** Se la soluzione che trova è quella col path (e costo) minore (se ci sono più goal=.
- **Time Complexity:** Quanto tempo impiega a trovare la soluzione.
- **Space Complexity:** Quanta memoria utilizza durante la ricerca.


|            |  **BFS**   |     **DFS**     |                                **DIJKSTRA**                                | **ITERATIVE DEEPENING** |
|:----------:|:----------:|:---------------:|:--------------------------------------------------------------------------:|:-----------------------:|
| *Complete* |    Yes     |      Yes*       |                                   Yes**                                    |           Yes           |
| *Optimal*  |   Yes***   |       No        |                                    Yes                                     |         Yes***          |
|   *Cost*   | $$O(b^d)$$ |   $$O(b^m)$$    | $$O\left( b^{1+\left\lfloor   {c^*}   /{\epsilon} \right\rfloor} \right)$$ |       $$O(b^d)$$        |
|  *Space*   | $$O(b^d)$$ | $$O(b\cdot m)$$ | $$O\left( b^{1+\left\lfloor   {c^*}   /{\epsilon} \right\rfloor} \right)$$ |     $$O(b\cdot d)$$     |

- \* $\longrightarrow$ con tabella di hash e gestione dei duplicati
- \*\* $\longrightarrow$ $STEP\_COST >\epsilon>0$, per evitare soluzioni infinite
- \*\*\* $\longrightarrow$ $STEP\_ COST= \text{ costant}$
- $c^*$ = costo ottimo

Il DFS può essere migliorato impostando una soglia massima di profondità $d$, per poi aumentarla via via fino a trovare il goal, si ottiene quindi l'algoritmo **Iterative Deepening**. Lo svantaggio principale però di questo algoritmo è che passa più volte da nodi già esplorati, aumentando lo spazio.

Un'altro algoritmo possibile, nel caso si conosca lo stato goal, è quello della **Bidirectional Search**: si fanno partire due ricerca simmetriche (in ampiezza), una dallo stato iniziale e una dal goal, e quando le due frontiere si intersecano si è trovato il path ricercato. Facendo ciò si riduce la memoria necessaria ($\frac{d}{2}$).

![[Pasted image 20260311162321.png|center|500]]

## Informed Search
Si introduce una funzione $h(n)$, funzione dello stato , che stima quanto è lontano il goal. In questo caso si parla di algoritmi che utilizzano l'**Euristica**.

**Ottimalità** di $h(n)$ (condizioni):
- *Ammissibilità*: non sovrastima mai costo per arrivare all'obiettivo.
- *Consistenza*: per ogni nodo $n$ e ogni successore $n'$ che genera tramite un'azione $a$, il costo stimato per raggiungere l'obiettivo partendo da $n$ non è mai superiore al costo di passo per arrivare da $n$ ad $n'$ sommato al costo stimato per raggiungere l'obiettivo da $n'$, ovvero se: $$h(n)\le c(n, a, n')+h(n')$$
![[IMG_1107.jpeg|center|400]]

Inoltre $$\begin{align}
Consistency &\Longrightarrow Admissibility \\
Admissibility\ &\centernot\Longrightarrow Consistency
\end{align} $$
L'euristica permette di ridurre notevolmente ill branching factor.
### Greedy Best-First
L'algoritmo Greedy Best-First è uguale al BFS, solo che espande i nodi dell'albero utilizzando il minimo $h(n)$ ($f(n)=h(n)$), valuta quindi solo sulla base dell'euristica. Questo algoritmo è efficiente, ma non è ottimale.

### A*
L'algoritmo A* è una versione migliorata dell'algoritmo Uniform Cost, utilizza l'evaluation function 
$$
f(n)=g(n)+h(n)
$$
con $g(n)$ è il miglior costo del cammino a partire dal nodo iniziale e $f(n)$ è il costo stimato del percorso più corto dal nodo $n$ fino al goal state (nell'uniform cost $h(n)=0$).


> [!gray] Teorema
> A* è ottimale per $h$ consistente
>
**Lemma:**
Un'euristica consistente è monotona (ovvero che scendendo nel grafico $f$ non è decrescente)

**Dimostrazione:**
$$\begin{align}
g(n')&= g(n)+c(n,a,n')& \\
f(n')&= g(n')+h(n')= g(n)+c(n,a,n')+h(n')& &\ge g(n)+h(n)= f(n)
\end{align}$$

![[IMG_1109.jpeg|center|400]]

Si ha che $h\ is \ consistent \Longrightarrow h\ is \ monotone$, allora:
$$\begin{align}
&f(n^*)\ge f(n') \\
&f(n')\le f(n^*)= g(n^*)+\underset{\text{è un goal}}{\cancel{h(n^*)}}<g(n)= g(n)+\underset{= 0}{\cancel{h(n)}}= f(n)
\end{align}$$
Risulterebbe che $f(n')$ è meglio di $f(n)$, quindi è un assurdo.
### Heuristic Functions
Si prende ora in esame come un'euristica impatti sulle performance di un algoritmo. Si prende per esempio il problema dell'8-puzzle. In questo caso ci sono $\frac{9!}{2}=181400$ configurazioni di stato possibile (si possono tenere tutti in memoria), ma se si passa ad un 15-puzzle se ne avrebbero $\frac{16!}{2}\simeq 10\ trillions$, quindi per effettuare ricerche su questi space state occorre una buona euristica.
- $h_{1}$ = numero di tasselli fuori posto
- $h_{2}$ = la somma delle distanze di tutti i tasselli dalla loro posizione corrente a quella della configurazione goal, e siccome i tasselli si possono muovere in orizzontale o verticale si ha la **Manhattan Distance**

Entrambe queste euristiche non sovrastimano mai il costo e sono pertanto ammissibili.

> [!gray] Teorema
> Se un'euristica $h_{2}$ è più informata di un'euristica $h_{1}$, ovvero se $h_{2}(n)\ge h_{1}(n)$, si dice allora che $h_{2}$ *domina* su $h_{1}$. 
> 
> ![[IMG_1111.jpeg|center|300]]
> 
> Si ha quindi che $E_{1} \subset E_{2}$, in quanto ogni nodo espanto da $A^*(h_{1})$  è anche espanto da $A^*(h_{2})$.

Se un problema ha più euristiche ammissibili a propria disposizione ($h_{1},h_{2},h_{3},\dots$), allora per ogni nodo si prende quella più efficace in quella situazione, ovvero
$$
h(n) = \max\{ h_{1}(n),h_{2}(n),h_{3}(n),\dots \}
$$
#### Accuratezza Funzione Euristica
Un modo per determinare l'accuratezza di un'euristica è l'**Effective Branching Factor** $b^*$. Se il numero totale di nodi generati da A* per un problema è $N$ e la profondità della soluzione è $d$, allora $b^*$ è il branching factor che un albero uniforme di profondità deve avere in modo da contenere $N+1$ nodi, perciò
$$
N+1=1+b^*+(b^*)^2+\ldots+ (b^*)^d
$$
Un $b^*$ di una funzione euristica ottimale tenderebbe ad 1, ciò significa che anche grandi problemi possono essere risolti con un costo computazionale contenuto.
### Pattern Databases
È possibile derivare euristiche ammissibili dal costo della soluzione di un sottoproblema. Questo avviene attraverso i **Database Pattern**, memorizzano i costi di ogni possibile configurazione di sottoproblema.

> [!example]+ Esempio:
> 
> ![[Pasted image 20260320173749.png|center|550]]
> 
> Si devono mettere i tasselli 1,2,3 e 4 nei tasselli liberi. Le configurazioni possibili delle soluzioni sono $9\times8\times 7 \times 6 \times  5=15,120$, che sarà il numero di pattern nel database.

Successivamente si può ottenere un'euristica ammissibile $h_{DB}$ per ogni stato completo incontrato durante una ricerca, semplicemente estraendo dal database la corrispondente configurazione del sottoproblema.
Il database è costruito eseguendo una ricerca all'indietro dallo stato obiettivo e memorizzando il costo di ogni configurazione incontrata.
(disjoint pattern database?)

### Landmarks
Un'euristica può essere generata a partire dalla precomputazione e salvataggio del costo del path ottimale per ogni serie di vertivi.
Se si aggiungono dei **Landmark** a una serie di vertici, si computa il costo del path migliore del vertice $v$ al landmark $L$ come $C^*(v,L)$. Memorizzando i costi in una tabella, si può generare una funzione euristica efficiente ma inammissibile:
$$
h_{L}(n) = \min_{L\in Landmarks} C^*(n,L)+C^*(L,goal)
$$
Se il path ottimale passa da un landmark, allora l'euristica è esatta, altrimenti non è ammissibile.
È possibile infine renderla sia efficiente, sia ammissibile se si considera
$$
h_{DH}(n)=\min_{L\in Landmarks}|C^*(n,L)-C^*(L,goal)|
$$
cioè un'*euristica differenziale*.
La scelta dei Landmark può essere effettuata in maniera randomica (scelta più rapida), oppure scegliendoli in modo che non siano troppo vicini tra loro, o in maniera greedy, scegliendo il primo Landmark random e aggiungendo gli altri in modo che siano lontani da quest'ultimo.

## Search in Complex Environments
Si passa adesso da ambienti deterministici, statici e osservabili ad altri nei quali queste ipotesi vengono alleggerite.
### Local Search and Optimization Problems
Gli algoritmi di Local Search operano partendo da uno stato iniziale a quelli vicini, non tenendo traccia del percorso effettuato e dei nodi espanti. Quindi questi algoritmi si possono applicare nei problemi con l'obiettivo di trovare il goal, ma non importano gli stati intermedi, come si arriva alla soluzione e quali azioni vengono intraprese (*no step-cost*), come ad esempio il problema delle 8 regine.
Gli algoritmi di ricerca locale non sono sistematici, e perciò potrebbero non esplorare mai lo spazio dove si trova la soluzione. In compenso hanno 2 vantaggi fondamentali:
1. Basso utilizzo di memoria
2. Possono trovare soluzioni ragionevoli in spazi infiniti (dove gli algoritmi sistematici non sono adatti)
Possono anche essere usati per risolvere problemi di ottimizzazione, attraverso una funzione obiettivo.

È possibile raffigurare la local search come state-space landscape, dove l'elevazione rappresenta il valore corrispondente della objective function.

![[Pasted image 20260320182517.png|center|500]]

- Un'algoritmo di ricerca locale *completo* trova sempre un obiettivo, se esiste. 
- Un algoritmo di ricerca locale *ottimo* trova sempre un max/min locale.
### Hill Climbing