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
Le ridondanze vanno eliminate in quanto non aggiungono significato, tuttavia va presa in considerazione la stima dei costi delle operazioni se si procede con la rimozione (tabella volumi, operazioni e accessi)

da fare $\downarrow$
## 15)Che cos'è la tavola degli accessi?
## 16)Tabella dei volumi?
## 17)Calcolare la tavola accessi dato il volume dei dati?
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

22)Cos'è la normalizzazione

23)Come si esegue la normalizzazione

24) Definizione Attributo Primo:

25) Definizione di Dipendenza Completa:

26) Definizione 1FN:

27) Definizione 2FN:

28)3NF e BCNF.

29)Dimostrare che se una tabella è in 3NF è anche in 2NF (Updated)

30)Come si normalizza una tabella ?

31)Quando 2 insiemi di df sono equivalenti?

32)Cos'è la chiusura di un insieme di df?

33)Come si determina l' implicazione logica di df?

34)Cos'è la copertura minima ?

35)Cos'è una decomposizione senza perdite ? Quale è la condizione per evitare perdite nelle decomp.?

36)Condizione per cui una decomposizione conserva le dipfunz

TRANSAZIONI

37)Cos'è una transazione?

38)Cosa vuol dire che una transazione è ben formata?

39)Casi in cui una Transazione termina :

40) Motivi per cui può terminare una transazione in Oracle:

41) Dopo che ho dato il commit per chiudere una transazione sono sicuro che tutto è andato a buon fine oppure no?

42) Tipi di vincoli

43) Le proprietà "acide" delle transazioni ed in particolare quella atomica ;

44)livelli di isolamento fra le transazioni

ANOMALIE DI ISOLAMENTO

45)Cos'è il dirty-read

46)Cos è il phantom read

47)Cos è il non repeateble read

48)Differenza tra nonrepeatable read e dirty-read 
49) cursore