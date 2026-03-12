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