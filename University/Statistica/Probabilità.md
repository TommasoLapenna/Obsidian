---
sticker: emoji//0032-fe0f-20e3
Order: "1"
---
- [[#Calcolo delle Probabilità|Calcolo delle Probabilità]]
	- [[#Calcolo delle Probabilità#Spazio Campionario|Spazio Campionario]]
	- [[#Calcolo delle Probabilità#Eventi Complessi|Eventi Complessi]]
	- [[#Calcolo delle Probabilità#Unione, Intersezione e Negazioni di Eventi|Unione, Intersezione e Negazioni di Eventi]]
		- [[#Unione, Intersezione e Negazioni di Eventi#Unione|Unione]]
		- [[#Unione, Intersezione e Negazioni di Eventi#Intersezione|Intersezione]]
		- [[#Unione, Intersezione e Negazioni di Eventi#Negazione|Negazione]]
		- [[#Unione, Intersezione e Negazioni di Eventi#Diagramma di Venn|Diagramma di Venn]]
	- [[#Calcolo delle Probabilità#Algebra degli Eventi|Algebra degli Eventi]]
		- [[#Algebra degli Eventi#Proprietà|Proprietà]]
		- [[#Algebra degli Eventi#Leggi di De Morgan|Leggi di De Morgan]]
- [[#Probabilità di Eventi|Probabilità di Eventi]]
	- [[#Probabilità di Eventi#Assiomi di Kolmogorov|Assiomi di Kolmogorov]]
	- [[#Probabilità di Eventi#Proprietà della Probabilità|Proprietà della Probabilità]]
- [[#Determinazione delle Probabilità|Determinazione delle Probabilità]]
	- [[#Determinazione delle Probabilità#Eventi Osservabili e Non Osservabili|Eventi Osservabili e Non Osservabili]]
- [[#Probabilità Condizionate|Probabilità Condizionate]]
	- [[#Probabilità Condizionate#Teorema delle Probabilità Condizionate|Teorema delle Probabilità Condizionate]]
	- [[#Probabilità Condizionate#Congiunte Tramite Fattorizzazione di Condizionate|Congiunte Tramite Fattorizzazione di Condizionate]]
	- [[#Probabilità Condizionate#Dipendenza, Rilevanza|Dipendenza, Rilevanza]]
	- [[#Probabilità Condizionate#Fattorizzazione con indipendenze|Fattorizzazione con indipendenze]]
	- [[#Probabilità Condizionate#Indipendenze Condizionate|Indipendenze Condizionate]]
- [[#Probabilità Totali (Extending the Conversation)|Probabilità Totali (Extending the Conversation)]]
- [[#Teorema di Bayes|Teorema di Bayes]]
	- [[#Teorema di Bayes#Teorema di Bayes in *Odds Form*|Teorema di Bayes in *Odds Form*]]
	- [[#Teorema di Bayes#Teorema di Bayes, più di un Evidenza|Teorema di Bayes, più di un Evidenza]]
	- [[#Teorema di Bayes#Formulazione delle Ipotesi|Formulazione delle Ipotesi]]
	- [[#Teorema di Bayes#Il Problema del Biliardo|Il Problema del Biliardo]]
	- [[#Teorema di Bayes#Riassunto|Riassunto]]
	- [[#Teorema di Bayes#Probabilità delle Evidenze e a Posteriori sulle Ipotesi, nel Discreto e nel Continuo|Probabilità delle Evidenze e a Posteriori sulle Ipotesi, nel Discreto e nel Continuo]]
	- [[#Teorema di Bayes#Esempi|Esempi]]
	- [[#Teorema di Bayes#Modello delle Osservazioni e Probabilità Predittiva Senza Probabilizzare i Parametri|Modello delle Osservazioni e Probabilità Predittiva Senza Probabilizzare i Parametri]]

## Calcolo delle Probabilità
Si considera un **Evento** come un possibile esito di un'esperienza aleatoria, un evento elementare è un possibile esito dell'esperienza aleatoria esprimibile solo attraverso esiti che lo comprendono.

> [!example]+ Esempio:
> - Esperimento Aleatorio: Lancio del dado
> - Evento: Realizzazione di un numero pari
> - Evento Elementare: Realizzazione di un 2
> 

### Spazio Campionario
Si chiama $\Omega$ lo **Spazio degli Eventi Elementati** o **Spazio Campionario**, insieme di tutti i possibili risultato di un esperimento aleatorio, inteso come unione logica degli eventi elementari che corrispondono all'evento certo. Se $\overline \Omega=\emptyset$ allora rappresenta la negazione dell'evento certo, detto evento impossibile

> [!info] ->
> Gli eventi elementari che compongono lo spazio campionario sono esaustivi e mutualmente esclusivi.

La cardinalità di $\Omega$ può essere:
- Finita $\longrightarrow \Omega=\{V,F\}$
- Infinita Numerabile $\longrightarrow \Omega=\{0,1,2,\ldots\}$
- Infinita non numerabile $\longrightarrow \Omega=[a,b)\quad a,b\in R$

Se l'esperimento aleatorio viene ripetuto $k$ volte nelle stesse condizioni, lo spazio campionario complessivo è dato dal prodotto cartesiano
$$
\underset{k\ volte}{\Omega \times\Omega \times\ldots\times\Omega}
$$
### Eventi Complessi
Un evento complesso è un sottoinsieme dello spazio degli eventi $\Omega$

Se si considerano per esempio:
- Esperimento Aleatorio: Lancio di un dado a 6 facce
- Eventi Elementari: Si possono definire 6 eventi elementari $\omega_{1},\omega_{2},\omega_{3},\omega_{4},\omega_{5},\omega_{6}$
- Spazio degli Eventi: $\Omega=\{\omega_{1},\omega_{2},\omega_{3},\omega_{4},\omega_{5},\omega_{6}\}$
Un evento complesso è un evento esprimibile usando eventi elementari 
- Evento Complesso: Esce un numero pari $E_{pari}=\{\omega_{2},\omega_{4},\omega_{6}\}\subset\Omega$

A partire dallo spazio dei risultati, una $\sigma$ algebra è l'insieme di tutte le possibili unioni e intersezioni degli elementi dello spazio degli eventi elementari, aggiungendo $\Omega$ e $\emptyset$
### Unione, Intersezione e Negazioni di Eventi

> [!info] Mutuale Esclusione
> Tre eventi $\{A,B,C\}$ si dicono **Mutualmente Esclusivi** se $$A\cap B=\emptyset,\quad A\cap C=\emptyset,\quad B\cap C=\emptyset,\qquad A\cap B\cap C=\emptyset$$
> 

Siano $E$ e $F$ eventi relativi a due esperienze aleatorie
#### Unione
$$G=E\cup F$$
Si verifica se almeno uno dei due eventi si realizza.
L'unione di $n$ eventi $E_{1},E_{2},\ldots, E_{n}$ si indica con $$E_{1}\cup E_{2}\cup \ldots\cup E_{n}\qquad \bigcup^n_{i=1}E_{i}$$
#### Intersezione
$$G=E\cap F$$
Si verifica se ambedue gli eventi si realizzano.
L'intersezione di $n$ eventi $E_{1},E_{2},\ldots, E_{n}$ si indica con
$$
E_{1}\cap E_{2}\cap\ldots\cap E_{n}\qquad \bigcap^n_{i=1}E_{i}
$$
#### Negazione
$$G=\overline E$$
Si verifica se e solo se non si verifica $E$. Un evento e la sua negazione sono mutualmente esclusivi, la loro intersezione è l'evento impossibile ($E\cap \overline E=\emptyset$) e la loro unione è l'evento certo ($E\cup \overline E=\Omega$)
#### Diagramma di Venn
I digrammi di Venn danno una rappresentazione grafica degli eventi e delle loro relazioni: lo spazio degli eventi è rappresentato dal rettangolo, mentre gli eventi complessi sono rappresentati dai cerchi.

![[Pasted image 20250704184157.png]]

> [!example]+ Esempio:
> Siano
> $$\begin{align}\Omega:=\{1,2,3,4,5,6,7\},\quad E:=\{1,3,5,7\},\quad F:=\{7,4,6\},\quad G:=\{1,4\}\end{align}$$
> Allora:
> - $(E\cap F)=\{7\}$
> - $(E\cup F)=\{1,3,4,5,6,7,\}$
> - $\overline G=\{2,3,5,6,7\}$
> - $(E\cap \overline G)=\{3,5,7\}$
> 

### Algebra degli Eventi
#### Proprietà 
- **Proprietà Commutative:** $$E\cup F=F\cup E\qquad E\cap F=F\cap E$$
- **Proprietà Associative:** $$(E\cup F)\cup G=E\cup (F\cup G)\qquad (E\cap F)\cap G=E\cap (F\cap G)$$
- **Proprietà Distributive:** $$(E\cup F)\cap G=(E\cap G)\cup (F\cap G)\qquad (E\cap F)\cup G=(E\cup G)\cap (F\cap G)$$
#### Leggi di De Morgan
$$
\overline{(E\cup F)}=\overline E\cap \overline F\qquad \overline{(E\cap F)}=\overline E \cup \overline F
$$
---

## Probabilità di Eventi
Gli eventi possono essere *certi/impossibili* oppure *incerti*. Nel secondo caso si attribuiscono alla proposizione (e alla sua negazione) un grado di fiducia chiamato **Probabilità**.
Un esperimento aleatorio genera un evento con una certa probabilità, che misura quindi l'incertezza degli eventi.

Ci sono due possibili interpretazioni del concetto di probabilità
- **Interpretazione Empirica:** La probabilità di un evento è considerata una proprietà dell'esperienza aleatoria stessa, che può essere determinata ripetendo più volte l'esperimento.
- **Interpretazione Soggettiva:** La probabilità di un evento esprime il livello di fiducia riposta nel verificarsi dell'evento ed è determinata dalla conoscenza delle circostanze in cui si realizza.

Il calcolo della probabilità consente di determinare la probabilità di eventi complessi e le sue regole prescindono dall'interpretazione adottata.

### Assiomi di Kolmogorov
1. Normalizzazione: $$0\le P(E)\le 1$$
2. $$P(\Omega)=1\qquad P(\emptyset)=0$$
3. Additività Finita: Valuta la probabilità dell'unione di eventi mutualmente esclusive. Se $E_{1},E_{2},\ldots,E_{n}$ sono mutualmente esclusivi $$P(E_{1}\cup E_{2}\cup\ldots\cup E_{n})=P\left(\bigcup^n_{i=1}E_{i}\right)=\sum^n_{i=1}P(E_{i})$$
### Proprietà della Probabilità 
Dagli assiomi di Kolmogorov si possono dedurre altre proprietà:
==1.== Se $E\subset \Omega$, $P(\overline {E})=1-P(E)$ $$1=P(\Omega)=P(E\cup \overline E)=P(E)+P(\overline E)$$
2. Siano $E$ ed $F$ due eventi qualsiasi ==$$P(E\cup F)=P(E)+P(F)-P(E\cap F)$$==![[Pasted image 20250705101212.png|350]]

---

## Determinazione delle Probabilità
$E=$ Osservazione della faccia superiore nel lancio di un dado a 6 facce, sia $E_{5}=$ Uscita del $5$
$\Omega=\{E_{1},E_{2},\ldots,E_{6}\}$
Si valuta la probabilità che nel prossimo lancio l'evento $E_{5}$ si realizzi disponendo delle seguenti informazioni:
1. Il dado è un dado standard (non truccato):
	- Approccio classico a priori: $$P(E_{5})=\frac{\text{casi favorevoli}}{\text{casi possibili}}= \frac{|E_{5}|}{|\Omega|}=\frac{1}{6}=0.1\overline 6$$
2. Il dado è truccato con un alta probabilità di produrre un $5$:
	- Approccio soggettivo: $P(E_{5})\simeq 0.95$, si può pensare di entrare in una scommessa sul $5$
3. Il dado è truccato, ma non si conosce il numero più probabile
	- Approccio empirico: $$P(E_{5})=\frac{1}{n}\sum^n_{i=1} \mathbb 1_{[5]}(E_{i})$$
Si definisce adesso $I$ lo stato dell'informazione sulla quale si opera, a rigore infatti non sarebbe mai corretto scrivere $P(E)$, sarebbe $P(E|I)$. Se si scrive semplicemente $P(E)$ si sottintende anche il background dell'informazione $I$, infatti nell'esempio precedente $I$ conta.
### Eventi Osservabili e Non Osservabili
- Gli eventi **Osservati** sono chiamati **Dati**
- Gli eventi **Non Osservati** o non osservabili rimangono **Incerti**
L'incertezza sulla loro realizzazione è in genere modificata dai dati disponibili, sempre che ci sia una dipendenza fra ciò che rimane osservato.

Gli eventi non osservati ma **Potenzialmente Osservabili** sono:
- Le statistiche di una variabile riferite ad una intera popolazione
- I dati mancanti in una rilevazione
- Eventi che si verificheranno in futuro
Gli eventi non osservabili che rimarranno sempre tali solo:
- Congetture sui meccanismi (teorie) che regolano l'incertezza e che si sostanziano in *modelli*
- I *parametri* che regolano i modelli probabilistici

--- 

## Probabilità Condizionate
> [!example]+ Esempio:
> Si tirano due dadi non truccati ottenendo $i$ al primo lancio e $j$ al secondo, qual'è la probabilità che la somma $i+j$ sia $8$ sapendo che l'esito del lancio del primo dado è $i=3$?
> 
> | $i,j$                                             | 1   | 2                                             | 3                                             | 4                                             | 5                                             | 6                                             |
> | ------------------------------------------------- | --- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------------------- |
> | **1**                                             | 2   | 3                                             | 4                                             | 5                                             | 6                                             | 7                                             |
> | **2**                                             | 3   | 4                                             | 5                                             | 6                                             | 7                                             | <mark style="background: #FF5582A6;">8</mark> |
> | <mark style="background: #ADCCFFA6;">**3**</mark> | 4   | 5                                             | 6                                             | 7                                             | <mark style="background: #FF5582A6;">8</mark> | 9                                             |
> | **4**                                             | 5   | 6                                             | 7                                             | <mark style="background: #FF5582A6;">8</mark> | 9                                             | 10                                            |
> | **5**                                             | 6   | 7                                             | <mark style="background: #FF5582A6;">8</mark> | 9                                             | 10                                            | 11                                            |
> | **6**                                             | 7   | <mark style="background: #FF5582A6;">8</mark> | 9                                             | 10                                            | 11                                            | 12                                            |
> 
> Sapendo che il primo esito dei dati $i$ è $3$, gli esiti possibili per il secondo (probabilità condizionata) sono solo $6$. Solo uno di essi è $8$ e la sua probabilità è $\frac{1}{6}$.
> Se si calcola invece la probabilità non condizionata come $\frac{\text{casi favoreli}}{\text{casi possibili}}$ e si ottiene $\frac{5}{36}$.
> 

### Teorema delle Probabilità Condizionate
Si vuole includere nel calcolo della probabilità $H$ l'informazione che l'evento $E$ si è realizzato 

> [!gray] Teorema delle Probabilità Condizionate
> $$P(H|E)\quad \text{Probabilita' Condizionata di }H\text{ dato }E$$
> $$P(H|E)=\frac{\overset{\text{prob. congiunta}}{P(E\cap H)}}{\underset{\text{prob. marginale}}{P(E)}},\quad P(E)>0$$
> Ovvero il rapporto fra:
> - La probabilità che ambedue $E$ e $H$ si realizzino
> - La probabilità che si realizzi $E$, qualsiasi sia $H$
>
> $P(H|E)$ è la probabilità di realizzazione di $H$ essendosi ristretto lo spazio degli eventi a $\Omega_{E}$.

### Congiunte Tramite Fattorizzazione di Condizionate
Non è sempre facile valutare $P(E,H)\equiv P(E\cap H)$. Dal teorema delle probabilità condizionare, moltiplicando entrambi i membri per $P(E)$, si deriva che 
$$
\underset{\text{congiunta}}{P(E,H)}=\underset{\text{marginale}}{P(E)}\ \underset{\text{condizionata}}{P(H|E)}
$$
Una congiunta fra due eventi si può dunque scomporre in due modi

![[Pasted image 20250705105912.png|center|500]]

La scomposizione $likelihood\times prior$ è utile perché è spesso facile valutare la probabilità di un evento osservabile al variare di ipotesi rilevanti, è inoltre più facile stabilire le probabilità iniziale di $H$ che non di $E$

> [!info] Nota
> $$P(H|E,I)\neq P(E|H,I)$$

**Generalizzazione:**
Si considerano $H$ e alcune differenti evidenze $E_{1},\ldots, E_{n}$, nel caso le evidenze siano tutte rilevanti si hanno $n!$ possibili scomposizioni (tutte valide)

> [!gray] <mark style='background:var(--mk-color-yellow)'>Chain Rule</mark>
> $$\begin{align}&P(H,E_{1},E_{2},\ldots,E_{n})= \\
> &=P(H|E_{1},\ldots,E_{n})P(E_{1},\ldots,E_{n}) \\
> &= P(H|E_{1},\ldots,E_{n})P(E_{1}|E_{2},\ldots,E_{n})\ldots P(E_{n}) \\
> &=P(H|E_{1},\ldots,E_{n})P(E_{2}|E_{1},\ldots,E_{n})\ldots P(E_{n}) \\
> &=\underset{\text{likelihood}}{P(E_{1}|E_{2},\ldots,E_{n},H})\underset{\text{likelihood}}{P(E_{2}|E_{3},\ldots,E_{n},H)} \ldots\underset{\text{prior}}{P(H)}  \end{align}$$
> 

### Dipendenza, Rilevanza
Si considerano due eventi $E$ e $H$,
- $E$ e $H$ sono dipendenti se, osservato $E$, la probabilità $H$ cambia $$P(H)\ne P(H|E)$$
![[Pasted image 20250705120216.png|center|100]]
- $E$ è indipendente da $H$ se $$P(H)=P(H|E)$$ ![[Pasted image 20250705120401.png|center|150]] In questo caso $$P(H,E)=P(H|E)P(E)=P(H)P(E)$$
### Fattorizzazione con indipendenze
1. **Indipendenza Parziale:** si hanno delle semplificazioni $$P(H,E_{1},\ldots,E_{n})=P(H|E_{3},\ldots,E_{n})P(E_{1}|E_{2},\ldots,E_{n})\ldots P(E_{n})$$
2. **Indipendenza Completa:** non si apprende niente $$\begin{align} &P(H,E_{1},E_{2},\ldots,E_{n})=P(H)P(E_{1})\ldots P(E_{n}) \\
&P(H|E_{1},E_{2},\ldots,E_{n})= \frac{P(H)P(E_{1})\ldots P(E_{n})}{P(E_{1})\ldots P(E_{n})}=P(H) \end{align}$$
3. **Indipendenza Condizionata:** $$\begin{align}
P(H,E_{1},E_{2})&=P(E_{1}|E_{2},H)P(E_{2}|H)P(H)& \quad \text{forma standard}&\\
&= P(E_{1}|H)P(E_{2}|H)P(H)&\text{se }E_{1}\coprod E_{2}|H&
\end{align}$$
Se $E_{1}$ e $E_{2}$ sono osservazioni di una medesima variabile aleatoria osservata su diversi membri di un campione allora sono dette *iid* (independent identical distributed).a


> [!gray] Dal Chat:
> ### 1️⃣ Due eventi indipendenti
> 
> - Definizione: A⊥B  ⟺  P(A∩B)=P(A)P(B)A \perp B \iff P(A \cap B) = P(A) P(B)A⊥B⟺P(A∩B)=P(A)P(B)
>     
> - Conseguenza: P(A∣B)=P(A)P(A \mid B) = P(A)P(A∣B)=P(A), P(B∣A)=P(B)P(B \mid A) = P(B)P(B∣A)=P(B)
>     
> - Fattorizzazione:
>     
> 
> P(A∩B)=P(A)P(B)P(A \cap B) = P(A) P(B)P(A∩B)=P(A)P(B)
> 
> ---
> 
> ### 2️⃣ Tre o più eventi
> 
> #### a) Indipendenza totale
> 
> - Condizione: ogni coppia e ogni insieme congiunto soddisfa l’indipendenza:
>     
> 
> $$P(A∩B)=P(A)P(B)P(A∩C)=P(A)P(C)P(B∩C)=P(B)P(C)P(A∩B∩C)=P(A)P(B)P(C)\begin{cases} P(A \cap B) = P(A) P(B) \\ P(A \cap C) = P(A) P(C) \\ P(B \cap C) = P(B) P(C) \\ P(A \cap B \cap C) = P(A) P(B) P(C) \end{cases}⎩⎨⎧​P(A∩B)=P(A)P(B)P(A∩C)=P(A)P(C)P(B∩C)=P(B)P(C)P(A∩B∩C)=P(A)P(B)P(C)$$​
> 
> - Fattorizzazione completa:
>     
> 
> P(A∩B∩C)=P(A)P(B)P(C)P(A \cap B \cap C) = P(A) P(B) P(C)P(A∩B∩C)=P(A)P(B)P(C)
> 
> #### b) Indipendenza a coppie
> 
> - Condizione: solo le coppie sono indipendenti:
>     
> 
> $$$ P(A∩B)=P(A)P(B),P(A∩C)=P(A)P(C),P(B∩C)=P(B)P(C)P(A \cap B) = P(A) P(B),\quad P(A \cap C) = P(A) P(C),\quad P(B \cap C) = P(B) P(C)P(A∩B)=P(A)P(B),P(A∩C)=P(A)P(C),P(B∩C)=P(B)P(C) $$
> 
> - **Attenzione:** non garantisce P(A∩B∩C)=P(A)P(B)P(C)P(A \cap B \cap C) = P(A) P(B) P(C)P(A∩B∩C)=P(A)P(B)P(C)
>     
> 
> ---
> 
> ### 3️⃣ Indipendenza condizionata
> 
> - Definizione: AAA e BBB sono indipendenti **dato** un evento CCC:
>     
> 
> P(A∩B∣C)=P(A∣C)P(B∣C)P(A \cap B \mid C) = P(A \mid C) P(B \mid C)P(A∩B∣C)=P(A∣C)P(B∣C)
> 
> - Fattorizzazione valida **solo all’interno del sottoinsieme CCC**.
> 

### Indipendenze Condizionate
Si considera $V=\{x_{1},\ldots,x_{n} \}$. La rappresentazione della congiunta completa può essere troppo onerosa usando la chain rule, si sfrutta allora l'indipendenza condizionata degli elementi in $V$ rispetto ad una variabile di cui si conosce l'instanziazione $H$ (per semplificare la scomposizione congiunta).

Si lancia un dado a $6$ facce, si vuole valutare la probabilità di osservare $5_{1},\overline 5_{2},\overline 5_{3},\overline 5_{4}, 5_{5}$.
Per la chain rune una possibilità è $$P(5_{1},\overline 5_{2},\overline 5_{3},\overline 5_{4}, 5_{5})=P(5_{1}|\overline 5_{2},\overline 5_{3},\overline 5_{4}, 5_{5})P(\overline 5_{2}|\overline 5_{3},\overline 5_{4}, 5_{5})P(5_{3}|\overline 5_{4}, 5_{5})P(\overline 5_{4}|5_{5})P(5_{5})$$
Assumendo che il dado sia regolare, ovvero che l'incertezza circa l'esito delle probe è nella conoscenza della probabilità di uscita di ciascuna della facce. Si assume inoltre che questa sia la stessa per tutte le facce, ovvero $$\pi_{i}=P(i)\quad i=1,\ldots,6\qquad \pi_{1}=\pi_{2}=\ldots=\pi_{6}=\pi=\frac{1}{6}$$ $$P(5,\overline 5, \overline 5, \overline 5, 5|\pi)=P(5_{1|\pi})P(\overline 5_{2}|\pi)P(\overline 5_{3}|\pi)P(\overline 5_{4}|\pi)P(5_{5}|\pi)=\left( \frac{1}{6} \right)^2\left( \frac{5}{6} \right)^3$$

---

## Probabilità Totali (Extending the Conversation)
Si considera un evento $A$ in congiunzione ad un altro evento $B$. Si considera $$A\cap B\quad e\quad A\cap \overline B$$
![[Pasted image 20250706094823.png|center|350]]
$$(A\cap B)\cup (A\cap \overline B)=A\quad (A\cap B)\cap(A\cap \overline B)=\emptyset$$
Per il [[#Assiomi di Kolmogorov|terzo assioma]], la probabilità dell'unione di eventi incompatibili è uguale alla somma delle loro probabilità
$$
P(A)=P((A\cap B)\cup (A\cap \overline B))=P(A\cap B)+P(A\cap \overline B)=\underset{\text{likelihood}\times\text{prior}}{P(A|B)P(B)}+\underset{\text{likelihood}\times\text{prior}}{P(A|\overline B)P(\overline B)}
$$
==In generale, con $E=$ evidenze e $H=$ variabili non esservabili:==
$$
P(E)=\underset{\text{likelihood}}{P(E|H)}\underset{\text{prior}}{P(H)}+P(E|\overline H)P(\overline H)
$$
Si considerano gli eventi esaustivi e mutamente esclusivi $H_{1},\ldots,H_{n}$, si considera l'evento $E$ che può essere scritto come
$$
E=E\cap\Omega=E\cap(H_{1}\cup \ldots\cup H_{n})=\bigcup^n_{i=1}(E\cap H_{i})
$$
Quindi
$$
P(E)=\sum^n_{i=1}P(E\cap H_{i})=\sum^n_{i=1}P(E|H_{i})P(H_{i})
$$
---

## Teorema di Bayes
Dal teorema delle probabilità condizionate:

> [!gray] Teorema di Bayes
> $$P(H|E)=\frac{P(E,H)}{P(E)}$$
>
Tramite la fattorizzazione della congiunta (numeratore) e l'extending conversation (denominatore) si ottiene
>$$P(H|E)= \frac{P(E|H)P(H)}{P(E|H)P(H)+P(E|\overline H)P(\overline H)}$$
>In generale:
>$$P(H_{i}|E)= \frac{P(E|H_{i})P(H_{i})}{\sum^n_{i=1}P(E|H_{i})P(H_{i})}$$

Questa formula risponde alla domanda di qual'è la probabilità della ipotesi tenendo conto delle evidenze. Per avere questa risposta si devono valutare la probabilità di ciò che è stato osservato assumendo vera ciascuna delle ipotesi considerate (likelihood), e la probabilità a priori delle ipotesi.
### Teorema di Bayes in *Odds Form*
Nel caso più semplie, quando sia $H=\{H,\overline H\}$ che $E=\{E,\overline E\}$ sono eventi elementari, il supporto che l'evidenza $E$ da alle due ipotesi è detto **Likelohhod Ratio**
$$\frac{P(H|E)}{\underset{\text{odds a posteriori}}{P(\overline H|E)}}=\frac{\frac{P(E|H)P(H)}{P(E|H)P(H)+P(E|\overline H)P(\overline H)}}{\frac{P(E|\overline H)P(\overline H)}{P(E|H)P(H)+P(E|\overline H)P(\overline H)}}=\underset{\text{likelihood ratio odds a priori}}{\frac{P(E|H)}{P(E|\overline H)} \frac{P(H)}{P(\overline H)}}$$
Ovvero
$$
O(H|E)=LR* O(H)
$$
Gli odds sono la probabilità di un evento rapportata alla probabilità dell'evento complementare
$$
O(H)=\frac{P(H)}{P(\overline H)}= \frac{P(H)}{1-P(H)}
$$
Utile derivazione:
$$P(H|E)=\frac{O(H|E)}{1+O(H|E)}$$
Con il likelihood ratio si tenta di scorporare dall'inferenza l'influenza delle probabilità a priori delle ipotesi.
### Teorema di Bayes, più di un Evidenza
$$\begin{align}
P(H|E_{1},E_{2})&=\overset{\text{teo. prob. cond.}}{\frac{P(E_{1},E_{2},H)}{P(E_{1},E_{2})}}=\overset{\text{chain rule}}{\frac{P(E_{2}|E_{1},H)}{P(E_{2}|E_{1})} \frac{P(E_{1}|H)P(H)}{P(E_{1})}}= \\
&= \overset{\text{Bayes}}{\frac{P(E_{2}|H)P(E_{1}|H)P(H)}{P(E_{2}|H)P(E_{1}|H)P(H)+P(E_{2}|\overline H)P(E_{1}|\overline H)P(\overline H)}} 
\end{align}$$
Con $E_1 \perp\!\!\!\perp E_{2}|H$
### Formulazione delle Ipotesi
La formulazione delle ipotesi riguarda la formulazione delle possibili spiegazioni di ciò che si osserva. Per esempio, le ipotesi dell'accusa e della difesa che possono riguardare l'appartenenza di tracce, oppure l'aver commesso un crimine. La formulazione delle ipotesi riguarda la formulazione delle possibili spiegazioni di ciò che si osserva.
Condizione necessaria per poter introdurre una certa ipotesi $H$ è che 
$$P(H)>0$$
Ovvero che l'ipotesi non è un evento impossibile.

### Il Problema del Biliardo
- Un boccino $W$ è lanciato su un biliardo con un meccanismo neutrale, ovvero si ritiene che si fermerà in un punto in cui la posizione (aleatoria) è regolata da una uniforme $[0,1]$. 
- $W$ si ferma in $\theta$ che non si ha modo di osservare. 
- Una palla $O$ viene lanciata $n$ volte con le stesse assunzioni e si ferma $x$ volte a sinistra di $\theta$ e $n-x$ a destra.

![[Pasted image 20250706103513.png|center|300]]

> [!hint] Domanda di Bayes: Dato $x$ cosa si può inferire su $\theta$?
> **Given** the number of times which an unknown event has happened and failed; **Required** *the chance* that the probability of its happening in a single trial *lies somewhere between any two degrees of probability that can be named*.

![[Pasted image 20250706105113.png|center|500]]
![[Pasted image 20250706105154.png|center|500]]

$$
\mathbb P(\theta_{i}|x)=\frac{l(\theta_{i};x,n)p(\theta_{i})}{\sum^{101}_{i=1}l(\theta_{i};x,n)Pr(\theta_{i})}\quad \theta=\left\{ 0, \frac{1}{100}, \frac{2}{100},\ldots,1 \right\}\quad l(\theta;x,n)=\theta^x(1-\theta^{n-x})
$$

| $\theta$                                                                          | $0$                                                | $0.05$                                              | $0.10$                                              | $0.15$                                              | $0.20$                                                | $0.25$                                             | $0.30$                                              | $\ldots$                                            |
| --------------------------------------------------------------------------------- | -------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- | ----------------------------------------------------- | -------------------------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| $\begin{align}&p(\theta) \\ &l(\theta;x=0,n=5) \\ &p(\theta\|n=5,x=0)\end{align}$ | $\begin{align} &0.09 \\ &1.00 \\ &0.26\end{align}$ | $\begin{align} &0.09 \\ & 0.77 \\& 0.20\end{align}$ | $\begin{align} &0.09 \\ &0.59 \\ &0.15 \end{align}$ | $\begin{align} &0.09 \\ &0.44 \\ &0.12 \end{align}$ | $\begin{align} &0.09 \\ & 0.33 \\ & 0.09 \end{align}$ | $\begin{align} &0.09 \\ &0.24 \\ &0.6 \end{align}$ | $\begin{align} &0.09 \\ &0.17 \\ &0.04 \end{align}$ | $\begin{align} &0.09 \\ &0.12 \\ &0.03 \end{align}$ |
| $\begin{align} &l(\theta;x=2,n=30) \\ &p(\theta\|n=35,x=2) \end{align}$           | $\begin{align} &0.00 \\ &0.00 \end{align}$         | $\begin{align}  &0.26 \\ &0.51\end{align}$          | $\begin{align} &0.23 \\ &0.34 \end{align}$          | $\begin{align} &0.10 \\ &0.12 \end{align}$          | $\begin{align} &0.03 \\ &0.03 \end{align}$            | $\begin{align}  &0.01 \\ &0.01\end{align}$         | $\begin{align} &0.00 \\ &0.00 \end{align}$          | $\begin{align} &0.00 \\ &0.00 \end{align}$          |
### Riassunto
- Si stabilisce cosa si osserva (say $X$) e su cosa si vuole acquisire informazione (say $\theta$)
- Si esprime una probabilità delle diverse modalità con cui si può presentare ciò su cui si vuole acquisire informazione $\theta$ *prima* di effettuare osservazioni $X$
- Si stabilisce una legge di probabilità diretta su come $\theta$ sia relato a $X$
- Si applica il teorema che fonde le informazioni a priori sull'oggetto dell'inferenza con le evidenza e si ottiene la *probabilità cd inversa* di $\theta$ a *posteriori*
### Probabilità delle Evidenze e a Posteriori sulle Ipotesi, nel Discreto e nel Continuo
1. $p(A)=\mathbb P(A|B)p(B)+p(A|B^c)P(C)$
2. $p(A)=\sum_{j}p(A|B_{j})p(B_{j})$
3. $f(X)=\int_{\theta}f(X|\theta)f(\theta)\ d\theta$

1. $p(B|A)= \frac{p(A|B)P(B)}{p(A|B)p(B)+p(A|B^c)p(B^c)}$
2. $p(B_{i}|A)= \frac{p(A|B_{i})p(B_{i})}{\sum_{j}p(A|B_{j})p(B_{j})}$
3. $f(\theta|X)=\frac{f(X|\theta)f(\theta)}{\int_{\theta}f(X|Y)f(\theta)\ d\theta}$
### Esempi

> [!example]+  Esempio 1: Test Diagnostico non Controverso
> Si assume di sapere chel'HIV è presente in una popolazione su $1$ persona su $1000$ $$p(HIV)=\frac{1}{1000}$$
> Un test sul mercato è dichiarato avere $95\%$ di sensitività e $98\%$ di specificità
> $$
> p(T^+|HIV)=0.95\qquad p(T^{-}|HIV^c)=0.98
> $$
> Qual'è la probabilità che il risultando $T^+$ abbia l'HIV?
> 
> L'esempio è non controverso perché basato su probabilità a priori oggettive stimate su una quantità osservabile: il numero di persone con l'HIV in un contesto a cui appartiene il soggetto. Altrettanto oggettive possono considerarsi le likelihood dopo adeguata sperimentazione.
> L'HIV però non è direttamente osservabile su un soggetto di interesse prima di un lungo periodo e per questo viene eseguito il test (possibilmente affetto da errori).
> Il risultato è un test molto affidabile che da risultato positivo ma dice che il soggetto ha l'HIV con probabilità del $4.5\%$: questo perché è stata effettua una sola osservazione.
> Comunque, dopo il test, la probabilità di HIV per quel soggetto è più che quadruplicata rispetto a quella a priori.

> [!example]+ Esempio 2: Monty Hall
> - Monty Hall mostra 3 scatole al concorrente
> - Una scatola contiene il premio e le altre 2 no
> - Dopo che il concorrente ha scelto la scatola, Monty Hall elimina una delle due scatole rimanenti che non deve contenere il premio
> - Si chiama questa azione di Monty Hall evento $MH$
> Conviene al giocatore cambiare scatola dopo che l'evento $MH$ si è realizzato
> 
> - Ipotesi di interesse: $\mathcal S=\{S_{i}:i=1,\ldots 3\}$
> - $S_{i}=$ il premio è nella scatola $i$
> - Inizialmente $pr(S_{i})=\frac{1}{3},\ \forall i$
> - inizia il gioco e, ad esempio, il concorrente sceglie la scatola $1$
> - $MH=\{2,3\}$, Monty Hall elimina la $2$, indicando che lì non c'è il premio
> - Si valuta $p(S_{3}|MH=2)$ per vedere se conviene cambiare scatola
> - $p(S_{3}|MH=2)=\frac{p(MH=2|S=S_{3})}{\sum^3_{i=1}p(MH=2|S=S_{i})p(S_{i})}$?
> - Solo valutando attentamente la likelihood $p(MH=2|S=S_{i})=\left\{ \frac{1}{2},0,1 \right\}$ si arriva al giusto risultato $\left( \frac{2}{3} \right)$
> - In questo caso la likelihood è determinata dal meccanismo che conduce $MH$ nella sua scelta
> - È evidente l'importanza della likelihood nell'inferenza Bayesiana

### Modello delle Osservazioni e Probabilità Predittiva Senza Probabilizzare i Parametri
1. Il modello di probabilità sui dati è espresso condizionatamente $\theta$, $p(X|\theta)$. Lo schema base (cd delle osservazioni ripetute) assume che tutte le osservazioni derivino dalla medesima distribuzione $p(X_{i}|\theta),\ i=1,\ldots,n$
2. La probabilità di un intero processo di osservazione $p(X_{1},\ldots,X_{n}|\theta)=\prod_{i}p(X_{i}|\theta)$ è espresso sotto condizione i.i.d., condizionatamente a $\theta$.

> [!info] Nota
> La condizione i.i.d. se assunta senza probabilizzare $\theta$ rende impossibile risolvere probabilisticamente il cd problema predittivo, infatti:
> $$
> p(x_{n+1}|x_{1},\ldots x_{n},\theta)= \frac{p(x_{n+1},x_{1},\ldots, x_{n}|\theta)}{p(x_{1},\ldots,x_{n}|\theta)}= \frac{\prod^{n+1}_{i}p(x_{i}|\theta)}{\prod^n_{i}p(x_{i}|\theta)}
> $$

1. Nell'impostazione Bayesiana $\theta$ è incerto $\theta \sim p(\theta)$,
2. L'inferenza su $\theta$ è realizzata a partire da una a priori su $\theta$, condizionatamente ai dati, ovvero nota la likelihood.
3. La probabilizzazione di $\theta$ rende possibile risolvere probabilisticamente il problema predittivo $$\begin{align}
p(x_{n+1}|x_{1},\ldots,x_{n})&=\int p(x_{n+1},\theta|x_{1},\ldots,x_{n})\ d\theta=\int p(x_{n+1}|x_{1},\ldots,x_{n},\theta)p(\theta|x_{1},\ldots,x_{n})\ d\theta= \\
&=\int p(x_{n+1}|\theta)p(\theta|x_{1},\ldots,x_{n})\ d\theta
\end{align}$$
