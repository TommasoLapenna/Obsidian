## 1) Introduzione
---
### 1.1) Modalità di Comunicazione
- Simplex
- Half-Duplex
- Full-Duplex
### 1.2) Topologia
- Mesh
- Stella
- Bus
- Anello

### 1.3) Tecniche di Commutazione
#### 1.3.1) Commutazione di Circuito
- Set-Up
- Utilizzo
- Abbattimento
#### 1.3.2) Commutazione di Messaggio
- Store and Foreword 
#### 1.3.3) Commutazione di Pacchetto

-  **Tecnica a Circuito** : Con fase di set-up, percorso fisico fisso
- **Tecnica a Datagramma**: Pacchetti inviati dai nodi in modo indipendente



## 2) Rete Telefonica
---
### 2.1) Telefonia Analogica
fa caha
### 2.2) Telefonia Numerica
- Teorema del Campionamento (Shannon), $f_{s}= 2B$ frequenza di Nyquist
- Quantizzazione
- $T= \frac{1}{2\cdot 4KHz} = \frac{1}{2\cdot{4}\cdot10^3}=125 \mu s$, 8 bit alla volta
### 2.3) Tecniche di Multiplexing
- **Divisione di Frequenza (FDM)**: Canali di trasmissione (frequenze e modulazione, filtri passabanda)
- **Divisione di Tempo (TDM)**: Frame, suddiviso in slot
- **Divisione di Lunghezza d'onda**: Fibra ottica
### 2.4) xDSL
- **ADSL**: asimmetrico
- **HDSL**: High-Bit-Rate Subscriber Line, doppino dedicato
- **SDLS**: simmetrico
- **VDSL**: very high bit-rate



## 3) Commutatori
---


## 4) Reti per Trasmissioni di Dati
### 4.1) Modello ISO/OSI

| Application  |
| ------------ |
| Presentation |
| Session      |
| Transport    |
| Network      |
| Data Link    |
| Physical     |
### 4.2) Modello TCP/IP

| Applicazione    |
| --------------- |
| Trasporto       |
| Internet        |
| Host to Network |

#### 4.2.1) Livello Internet
- IPv4
- IPv6
-  Dual Stack
- Tunneling
- DHCP
- NAT
- ICMPv6

#### 4.2.2) Livello di Trasporto
- UDP
- TCP
	-  Three/Four way handshake
## 4.3) Modello IEEE 802

| LLC    |
| ------ |
| MAC    |
| Fisico |
#### 4.3.1) Sottolivello Medium Access Control
- Accesso al mezzo trasmittivo considiviso da tutti i dispositivi della rete
- Indirizzi mac
### 4.4) Rete Distributed Queue Double Bus (DQDB)
- Contatore add/drop
- Contatore drop
- Buffer

### 4.5) Rete Fiber Distributed Data Interface
- Doppio Token Ring
#### 4.5.1) Livello MAC
- Token Target Rotation Time
- Token Rotation Time
- Token Holding Time
---
## 5) Accesso Multiplo
### 5.1) Tecniche di Accesso Ordinato
- CDMA
- OFDMA
#### 5.1.1) Tecniche di Polling
- **Procedura di Interrogazione:**
	- Roll-Call
	- Hub-Polling
- **Accesso al canale:**
	- Gated
	- Esaustivo
#### 5.1.2) Token Passing
- Ring
### 5.2) Tecniche di Accesso Casuale
- Riconoscimento delle collissioni
- Risoluzione delle collisioni
#### 5.2.1) Aloha
- **Puro**
- **Slotted**
#### 5.2.2) CSMA
- **CSMA 1-persistent**
- **CSMA non-persistent**
- **CSMA p-peristent**
- **CSMA con Collison-Detection**
- **CSMA con Collision-Avoidance** (per reti wireless)
---
## 6) Rete Ethernet
### 6.1) Livello MAC
- CSMA/CD 1-persistnet
- Livello di rete senza connessione (inaffidabile)
- nessun riscontro e CRC
## 6.2) Livello Fisico
- Etherent Standard
- Ethernet Veloce
- Ethernet Gigabit
- Ethernet 10-gigabit
### 6.3) Dispositivi di Connessione
- **Hub Passivi**
- **Ripetirori e Hub Attivi**
- **Bridge**
- **Switch**
- **Router**
## 7) Reti Wireless
### 7.1) IEEE 802.11
WiFi
- Basic Service Set
- Access Point
#### 7.1.1) Livello MAC
 - CSMA/CA
 - Problema del Terminale Nascosto
 - Problema del Terminale Esposto

### 7.2) IEEE 802.16
WiMax

### 7.3) IEEE 802.15.1
Bluethooth, WPAN (Wide Personal Area Network).
Piconet (fino ad 8 dispositivi) con master e slave.

---
## 8) Reti di Sensori
Wireless Sensor Networks
Funzioni di un sensore:
- **Sensing**
- **Comunicazione**
Nodi WSN:
- Sensori
- Sink
- Attuatori
- Processori
**Data Centric Forwarding:**
- Flooding
- Gossipping
- Direct Diffusion
- Interest e Gradient
- Data Propagation
- Reinforcement
---
## 9) Reti ISDN
Integrated Services Digital Network
Protocollo X.25
Canali:
- **B**: canale dell'utente
- **D**: segnalazioni canale B
- **H**: flussi aggregati in TDM
Accesso:
- **Base** (2B+F)
- **Primario** (30B+D o H)

Accesso alla rete ISDN da un dispositivo standard (TE1): effettuato tramite interfaccia ad un dispositivo a livello di rete NT2, tramite un punto di riferimento S.

Accesso alla rete ISDN da un dispositivo non standard: occorre un adattatore (TA) collegato al terminale TE2 tramite un punto di riferimento R.

NT2 è collgato tramite un punto di riferimento T ad un dispositivo ch eopera a livello di collegamento (NT1), quest'ultimo è collegato ad un punto di riferimento U

---
## 10) Algoritmi di Routing
Il routing può essere: 
- Diretto
- Indiretto
Gli algoritmi di routing possono essere:
- Statici
- Dinamici
- Con tabella
- Senza tabella
- Gerarchici
- Centralizzati
- Distribuiti
- Isolati
### 10.1) Algoritmi Senza Tablla
- Random
- Flooding
- Source Routing
	- Path server
	- Path discovery

### 10.2) Algoritmi con Tabella
#### 10.2.1) Distance Vector
- Bellman-Ford
- Trovare i percorsi a costo minore a partire da un nodo sorgente e selezionandoli progressivamente
- Count-to-Infinity
	- Split horizon
	- Posined resverse

Routing Information Protocol

#### 10.2.2) Link State
- Dijsktra 
- Link State Packet
Open Shortest Path First

#### 10.3) Multiprotocol Label Switching
L'MPS è un algoritmo di routing basato su etichetta, ovvero nell'header del pacchetto sono inseriti 4 campi:
- Label
- exp
- S: indica se esistono altri label nella pila delle etichette
- TTL: copia il campo TTL per ipv4 e hop limit per ipv6
Traffic engineering: opera su base di flusso (invece che ti pacchetto) e può usare più percorsi per lo stesso flusso

### 10.4) Routing Broadcast e Multicast
#### 10.4.1) Broadcast
Uno a tutti, collegamento a tutti gli host unicast
- Multidestiation routing
- Flooding
- Revese Path Forwarding (RPF)
- Spanning Tree
#### 10.4.2) Multicast
Uno a molti
- Multicast base: indirizzo comune
- Unicast multiplo
Tipologie di inoltro:
- Instradamento con albero condiviso dal gruppo
- Instradamento con albero basato sull'origine

---
## 11) Controllo della Congestione
### 11.1) Controllo Proattivo
- Traffic Shaping
- Queue Management
- Admission Control
#### 11.1.1) Leaky Bucket
- Garantisce un rate massimo
- FIFO, prelievo con cadenza fissata
- Scarto dei bacchetti non nel buffer
#### 11.1.2) Token Bucket
- Garantisce un rate medio
- Buffer per i permessi
### 11.2) Controllo Reattivo
**Sliding Window**: Se alla fine della finestra di pacchetti non si è ricevuto il riscontro del primo, allora si è in congestione e non si ricevono nuovi pacchetti
- Congestione del TCP
	- Slow Start
	- Fast Recovery
	- Congestion Avoidance
---
## 12) Sicurezza delle Reti
- RSA
- Firewall (ACL)