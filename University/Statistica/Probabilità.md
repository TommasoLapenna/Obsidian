---
sticker: emoji//0031-fe0f-20e3
---
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
1. Se $E\subset \Omega$, $P(\overline {E})=1-P(E)$ $$1=P(\Omega)=P(E\cup \overline E)=P(E)+P(\overline E)$$
2. Siano $E$ ed $F$ due eventi qualsiasi $$P(E\cup F)=P(E)+P(F)-P(E\cap F)$$![[Pasted image 20250705101212.png|350]]

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
> $P(E|H)$ è la probabilità di realizzazione di $H$ essendosi ristretto lo spazio degli eventi a $\Omega_{E}$.

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

> [!gray] Chain Rule
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
Se $E_{1}$ e $E_{2}$ sono osservazioni di una medesima variabile aleatoria osservata su diversi membri di un campione allora sono dette *iid* (independent identical distributed).
### Indipendenze Condizionate
Si considera $V=\{x_{1},\ldots,x_{n} \}$. La rappresentazione della congiunta completa può essere troppo onerosa usando la chain rule, si sfrutta allora l'indipendenza condizionata degli elementi in $V$ rispetto ad una variabile di cui si conosce l'instanziazione $H$ (per semplificare la scomposizione congiunta).

Si lancia un dado a $6$ facce, si vuole valutare la probabilità di osservare $5_{1},\overline 5_{2},\overline 5_{3},\overline 5_{4}, 5_{5}$.
Per la chain rune una possibilità è $$P(5_{1},\overline 5_{2},\overline 5_{3},\overline 5_{4}, 5_{5})=P(5_{1}|\overline 5_{2},\overline 5_{3},\overline 5_{4}, 5_{5})P(\overline 5_{2}|\overline 5_{3},\overline 5_{4}, 5_{5})P(5_{3}|\overline 5_{4}, 5_{5})P(\overline 5_{4}|5_{5})P(5_{5})$$
Assumendo che il dado sia regolare, ovvero che l'incertezza circa l'esito delle probe è nella conoscenza della probabilità di uscita di ciascuna della facce. Si assume inoltre che questa sia la stessa per tutte le facce, ovvero $$\pi_{i}=P(i)\quad i=1,\ldots,6\qquad \pi_{1}=\pi_{2}=\ldots=\pi_{6}=\pi=\frac{1}{6}$$ $$P(5,\overline 5, \overline 5, \overline 5, 5|\pi)=P(5_{1|\pi})P(\overline 5_{2}|\pi)P(\overline 5_{3}|\pi)P(\overline 5_{4}|\pi)P(5_{5}|\pi)=\left( \frac{1}{6} \right)^2\left( \frac{5}{6} \right)^3$$
## Probabilità Totali
