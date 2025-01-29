Tags: [[Basi di Dati]] [[University]]
Domande: [[Domande Basi di Dati]]
# MODELLO RELAZIONALE

## 1) Cos'è l'integrità referenziale, quando può essere violata, e con quali regole si può gestire:
L'integrità referenziale garantisce che informazioni in relazione diverse sono correlate attraverso valori comuni (chiavi), che devono essere coerenti. Può essere violata da tutte e tre le operazioni di aggiornamento (inserimento, cancellazione e modifica). Si può gestire con:
- Bloccare l'esecuzione con un messaggio di errore
- Gestire azioni compensative:
	- Rifiuto dell'operazione
	- Eliminazione a cascata
	- Introduzione di valori null
## 2) Cos'è un vincolo di integrità referenziale?
Un vincolo di integrità referenziale (foreign key) è un vincolo interrelazionale, ovvero che sussiste su più relazioni. Impone che gli attributi X di una relazione R1 e un'altra relazione R2, i valori di X in R1 devono apparire come valori della chiave primaria di R2 (oppure NULL). R1 è detta tabella interna, R2 è detta tabella esterna.
## 3) Cos'è una chiave
Una chiave è il sottoinsieme di attributi di dimensione minima degli attributi di una superchiave, necessari per identificare univocamente una tupla.
Per superchiave si intende si intende l'insieme di k attributi tali che, se due tuple t1 e t2 sono distinte, allora almeno un valore di questi attriubuti sarà diverso (t1[k]!=t2[k],  la superchiave quindi appare in modo univoco).
## 4) Definizione chiave primaria?
La chiave primaria è un sottoinsieme della chiave che non ammette valori nulli.
## 5) Azioni che possono essere eseguite in risposta al fallimento di vincoli.
Vincoli: Dominio, Chiave, Chiave primaria, Integrità referenziale
L'inserimento può violare tutti i vincoli, la cancellazione può violare solo il vincolo di integrità referenziale, la modifica può violare tutti i vincoli.
Il DMBS può rispondere ad una violazione dei vincoli nei seguenti modi:
- Bloccando l'esecuzione notificando l'errore
- Eseguire le operazioni che violano il vincolo con le appropriate azioni compensative:
## 6) Come risponde un DBMS al fallimento di vincoli di integrità referenziale?
 Da decidere quando si progetta il DB:
	- Rifiuto dell'operazione 
	- Eliminazione a cascata
	- Introduzione di valori nulli
(RESTRICT, CASCADE, SET NULL)
## 7)Cosa succede se violo altri vincoli(oltre al fatto che li rifiuta e richiede l'immissione)?
vedi [[DDL]]
# SQL
## 8)Con quale costrutto si può memorizzare il risultato di una SELECT?
?
## 9)Clausola WITH CHECK OPTION
WITH CHECK OPTION garantisce che ogni tupla inserita nella vista rispetti la query di definizione della vista, ovvero inserisce un controllo nelle viste aggiornabili (da rivedere): se si cerca di aggiornare la una vista che abbia tale clausola, l'operazione verrebbe annullata qualora questa implicasse un inserimento/modifica dei dati per cui si abbia una violazione della condizione su cui tale vista è stata creata. Con CASCADED (default?) tali controlli vengono estesi anche alle viste derivate (vedi slide), conn LOCAL no
# TRIGGER
[[DDL#^cf4d0f|Trigger]]
## 10)Cos'è un trigger?
Il trigger è una regola che si attiva quando accadono specifici eventi, segue il modello ECA (event condition action). L'evento può essere di diverse tipologie: inserimento/aggiornamento/cancellazione di dati, qualcosa che deve essere fatto sistematicamente o un evento esterno. Prima dell'azione può essere specificata una condizione che deve verificarsi. L'azione è solitamente una sequenza di SQL racchiusa all'interno di un costrutto come un if else, oppure è una transazione o azione esterna. Non sono ammessi trigger ricorsivi 

TRIGGER “EACH ROW” e di “STATEMENT”:
I trigger possono essere definiti for "each row", se così definiti hanno la peculiaretà che la regola si ripete per ogni riga della tabella su cui è stato attivato. Se non definito per "each row" allora è di default "statement", la regola viene eseguita solo una colta per tabella. E' permesso l'uso di OLD e NEW (each row), altrimenti si usa trigger di istruzione (statement)

TRIGGER BEFORE o AFTER:
Varia il momento di esecuzione della regola rispetto all'evento, rispettivamente prima che il DBMS registri le modifiche e l'altro dopo.
altre cose su appunti.

CONSTRAINT TRIGGER:
?
# ER
## 11)Cardinalità dell'entità con chiave esterna:
Se si ha un'entità con chiave identificata esternamente, essa deve avere cardinalità minima è massima di una partecipazione alla relazione pari a 1, per garantire l'unicità della chiave.
## 12)Perchè si dice che una dipendenza funzionale generalizza il vincolo di chiave?
Definizione di chiave: t1, t2 tuple, x chiave, allora t1[x]=t2[x]. Definizione di dipendenza funzionale A$\to$B $\Longrightarrow$ t1[A]=t2[A] $\Longrightarrow$ t1[B]=t1[B], ma se due due tuple hanno lo stesso valore di A, ma valori diversi di B, allora A $\cancel\to$ B.
Data una relazione R(X), ogni sottoinsieme di attributi dipende funzionalmente dalla chiave K della relazione:
	A $\to$ B degenera in un vincolo di chiave se A $\cup$ B = X, A è superchiave di R(X).
Non è possibile trovare tuple distinte che abbiano lo stesso valore di K
## 13)Cos'è una ridondanza in ER?
Una ridondanza è una ripetizione di informazioni nel DB, come dati duplicati o dati ricavabili tramite altre operazioni, l'analisi delle ridondanze è il primo passo nella ristrutturazione ER.
Ci sono 4 tipi di ridondanza:
- Attributi di una stessa entità
- Attributi derivati da attributi di altre entità
- Attributi generati dal conteggio (operatori aggregati)
- Relazioni derivabili da un altro insieme di relazioni
## 14)Come si risolvono le ridondanze?
Le ridondanze vanno eliminate in quanto non aggiungono significato, tuttavia va presa in considerazione la stima dei costi delle operazioni se si procede con la rimozione (tabella volumi, operazioni e accessi
## 15)Che cos'è la tavola degli accessi?
La tavola degli accessi è una tabella che viene definita per ogni operazione eseguibile nel database: in particolare è molto importante definirla per quel 20% delle operazioni che si suppone che generi l'80% del carico computazionale. Nella tabella degli accessi vengono specificati :
- I concetti che l'operazione analizza nella sua esecuzione
- Il tipo di costrutto (E o R)
- Numero di accessi
- Tipo di accesso (lettura o scrittura)
## 16)Tabella dei volumi?
La tabella dei volumi p una tabella che fa parte della documentazione di una base di dati e informa sul volume dei dati tramite le seguenti informazioni:
- Concetto
- Tipologie
- Volume
## 17)Calcolare la tavola accessi dato il volume dei dati?
Le caratteristiche delle operazioni vengono rappresnetate nella tavola delle operazioni:
- Riporta, per ogni operaziioni, la frequenxa prevista ed il tipo di operazione (interattiva o batch). Si costruisce una tavola degli accessi basata su uno schema di navigazione
- Lo schema di navigazione la parte dello schema ER iteressata dall'operazione, estesa con delle frecce che indicano in che modo navigano i derivati
- Per ragionare su quali entità/associazioni sono interessate sall'operazione, si considera il principio di duplicazione minima di informazioni, ovvero 
## 18)GENERALIZZAZIONI:
Le generalizzazioni incrementano il grado di astrazione dello schema, introducendo entità padri e figli. Le occorrenze dei figli sono un sottoinsieme delle occorrenze del padre, le occorrenze dei figli partecipano alle stesse relazioni del padre. TOTALE, PARZIALE, ESCLUSIVA, SOVRAPPOSTA...
## 19)Una generalizzazione sovrapposta può essere trasformata in una esclusiva? Come?
Si crea una nuova entità rappresentante l'intersezione (Studente, Lavoratore $\to$ Studente-Lavoratore)
## 20)Come si traducono e vantaggi e svantaggi delle varie soluzioni:
- Eliminare le entità figlie integrandole col padre
	Vantaggiosa quando le operazioni accadono con uguale frequenza ad entrambe le entità figlie (spreco di memoria per valori nulli ma accessi più veloci)
- Eliminare il padre e mantenere i figli (SOLO TOTALE)
	Vantaggiosa quando le operazioni più frequenti si riferiscono alle occorrenze di una sola entità figlia (vantaggio nell'occupazione della memoria, no NULL e riduzione degli accessi)
- Trasformare la generalizzazione in relazioni binarie (SOLO PARZIALE)
	Vantaggiosa quando la generalizzazione non è totale e ci sono operazioni che si riferiscono specificatamente al padre e ai figli
## 21)Cos’è il vincolo di Unique ?
Indica che un particolare attributo può apparire una sola volta, utile quando si traduce un'associazione 1 a 1 con l'accorpamento e la chiave inglobata diventa unique (quando partecipazione massima è 1)
# NORMALIZZAZIONI
## 22)Cos'è la normalizzazione
La normalizzazione è un processo attraverso il quale lo schema logico viene trasformato per essere conforme alle forme normali. Così facendo di raggiungere livelli diversi di immunità rispetto alle anomalie (ridondanza dei dati, di aggiornamento, di inserimento, di cancellazione)
## 23)Come si esegue la normalizzazione
(da <R(X),F> a 3FN)
1) Copertura minima: si trova la copertura minima G per l'insieme F, si individua una chiave K e si determina la forma normale dello schema R(X)
2) Partizionamento: si dividono le df di G in gruppi con lo stesso determinante (attributi sinistri della df)
3) Fusione: se gli attributi di una df in un gruppo G1 sono tutti inclusi tra gli attributi che compaiono in un gruppo G2 la df viene spostata da G1 a G2 (può dare schemi non trasformabili in BCNF)
4) Sintesi schemi: per ogni gruppo si costruisce uno schema usando tutti e soli gli attributi che compaiono in almeno una df del gruppo. Ogni schema ha come chiave i determinanti del gruppo individuati al secondo punto
5) Decomposizione loseless: se non esiste uno schema che ha come chiave K quella individuata al primo passo. Si aggiunge allo schema un nuovo schema di relazione con i soli attributi di K
## 24) Definizione Attributo Primo:
Un attributo è primo se appare in qualche chiave della relazione R(X)
## 25) Definizione di Dipendenza Completa:
Una df A $\to$ B, si dice che B  dipende completamente da A se per ogni sottoinsieme Y $\subset$ A  la df Y $\to$ B è falsa (ovvero A $\to$ B non contiene attributi esterni)
## 26) Definizione 1FN:
La 1FN si ha se e solo se ciascun attributo è definito con valori atomici e non ci sono più di un attributo a rappresentare un concetto (no attributi aggregati o multivalore). Considerata parte integrante della definizione formale di relazione nel modello relazionale.
## 27) Definizione 2FN:
Una tabella di dice in 2FN se e solo se è in 1FN e ciascun attributo non primo è completamente dipendente dalla chiave primaria (la df non contiene attributi estranei)
## 28)3NF e BCNF.
Una tabella si dice in 3FN se e solo se è in 1FN e per ogni dipendenza funzionale non banale X $\to$ A o X è una superchiave o A è attributo primo (ovvero fa parte della chiave). 3FN $\Longrightarrow$ 2FN. (Non ci devono essere dipendenze transitive, ovvero ogni attributo dipende direttamente dalla chiave primaria e non tramite attributi non primi))
Una tabella si dice in BCNF se e solo se è in 1FN e per ogni df non banale X $\to$ A X è superchiave.

## 29)Dimostrare che se una tabella è in 3NF è anche in 2NF
Dimostrazione per assurdo: sia R(Z) in 3FN. Si supponga che non sia in 2FN, quindi $\exists$Y $\to$ B t.c. B è attributo non primo e Y è parte della chiave. Questo risultato però contrasta con l'ipotesi che R(Z) sia in 3FN perché a sinistra non si ha una superchiave e a destra non si ha un attributo primo. Questo vuol dire che se una df è in 3FN, allora è anche in 2FN.
## 30)Come si normalizza una tabella ?
## 31)Quando 2 insiemi di df sono equivalenti?
Due insiemi di df sono equivalenti se e solo se hanno la stessa chiusura, ovvero (cond. necessaria e sufficiente) le df del primo sono logicamente implicate dal secondo e viceversa: $G^+\subseteq F^+$ e $F^+\supseteq G^+$
## 32)Cos'è la chiusura di un insieme di df?
Dato <R(x),F>, F$^+$ è l'insieme di tutte le df implicate logicamente da quelle di F
## 33)Come si determina l' implicazione logica di df?
L'implicazione si determina utilizzando gli assiomi di Armstrong nelle df:
- Transitività: se A $\to$ B e A $\to$ C allora A $\to$ C
- Riflessività: se B $\subset$ A e B $\to$ C allora A $\to$ C (X $\supseteq$ Y, X $\to$ Y)
- Estensione: se A $\to$ B allora AC $\to$ BC
## 34)Cos'è la copertura minima ?
Dato <R(X), F>, si dice che un insieme di df G costruisce una copertura minima di F se valgono le seguenti proprietà:
- F$^+$=G$^+$
- Ogni df in G è semplice
- Nessuna df non contiene attributi estreni
- Nessuna df è ridondante
Insieme minimale
## 35)Cos'è una decomposizione senza perdite ? Quale è la condizione per evitare perdite nelle decomp.?
Sia data una relazione <R(X),F>, si definisce la sua decomposizione R1(A) è R2(B), dove A e B sono sottoinsiemi di X, tali che A $\cup$ B = X. Una decomposizione si dice senza perdita se è possibile con un (loseless) join tra R(A) e R(B) ottenere (X). Ne consegue che deve esistere un insieme C = A $\cap$ B che è la superchiave di almeno una delle due relazioni (C $\to$ A o C $\to$ B) (cond. necessaria e suff) DA RIVEDERE
## 36)Condizione per cui una decomposizione conserva le df
Una decomposizione conserva le df quando non vanno perse ovvero, data df, tutti gli attributi che ne partecipano sono la medesima relazione in seguito alla decomposizione. Matematicamente si traduce in FX+...?
# TRANSAZIONI
## 37)Cos'è una transazione?
Una transazione è l'unità logica di eleaborazione su database che include una o più operazioni di accesso . Una transazione può essere parte di un programma oppure standalone. Il DBMS è responsabile del fatto che:
- Tutte le operazioni della transazione siano completate con successo
- nessuna delle operazioni abbia effetto sul DB?
- Non deve consentire che solo una parte delle operazioni di transazione abbia effetto del DB
## 38)Cosa vuol dire che una transazione è ben formata?
Una transazione è ben formata se:
- Inizia con un begin transaction
- Ternina con edn transactionLa sua esecuzione comporta il raggiungimento di un commit o un rollback work e dopo il commit/rollback non si eseguono altri accessi al DB
>Esempio:
>	*begin transaction;
>		update CONTO set saldo = saldo-1200;
>		where filiale = '005' and numero =15;
>		update CONTO set saldo = saldo+1200;
>		where filiale = '005' and numero=105;
>		commit work;
>	end transaction;* 
## 39)Casi in cui una Transazione termina :
- Rotture di vincoli immediati (vengono verificati nello stato partially committed e sono gestiti dal DBMS effettuando il rollback)
- Rotture di vincoli differiti (vengono verificati nello stato committed)
- Computer failure
- Transaction or system error
- Local error or expectation condition detected by the transaction
- concurrency control enforcement
- Disk failure
- Physical problem and catastrophes 
## 40) Dopo che ho dato il commit per chiudere una transazione sono sicuro che tutto è andato a buon fine oppure no?
No, ci sono alcuni vincoli (detti differiti) che pososno essere definiti in modo che la loro verifica avvenga solo

3) Tipi di vincoli

4) Le proprietà "acide" delle transazioni ed in particolare quella atomica ;

44)livelli di isolamento fra le transazioni

ANOMALIE DI ISOLAMENTO

45)Cos'è il dirty-read

46)Cos è il phantom read

47)Cos è il non repeateble read

48)Differenza tra nonrepeatable read e dirty-read 
49) cursore