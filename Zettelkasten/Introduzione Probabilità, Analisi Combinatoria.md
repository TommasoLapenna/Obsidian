Tags: [[Analisi 2 e Probabilità]] [[University]]

3 interpretazioni della probabilità
1) $P(E)= \frac{\#\text{ di volte che E accade}}{\#\text{ di possibili esiti}}$
2) Ripetere gli esperimenti $N\to\infty$, definire la probabilità come la frequenza che si vede al limite 
3) Grado di fiducia che si assegna ad un evento
# Analisi Combinatoria
Tecniche e principi per contare il numero di elementi di un insieme
### Esempio 
$n$ antenne identiche e allineate. 
Sistema funzionante quando sarà in grado di ricevere segnali $\iff$ se non ci sono due antenne difettose consecutive.
Sapendo che esattamente $m$ delle $n$ antenne sono difettose, qual'è la probabilità che il sistema sia funzionante?
$n=4$ $m=2$ 
$1$ antenna funzionante
$0$ antenne difettose 
$$\begin{matrix}
0 & 1 & 1& 0 \\
0 & 1 & 0 & 1 \\
1 & 0 & 1 & 0
\end{matrix} \ funzionante \quad
\begin{matrix}
0 & 0 & 1 & 0 \\
1 & 0 & 0 & 1 \\
1 & 1 & 0 & 0
\end{matrix}\ non \ funzionante$$ 
$\frac{3}{6}=\frac{1}{2}$
Domante Importanti:
- l'ordine è importante?
- Si possono ripeter gli elementi?
## Principio Fondamentale del Calcolo Combinatorio
**Idea:** Se un esperimento ha $m$ esiti possibili e un altro esperimento ha $n$ esiti possibili, i due esperimenti hanno $m\cdot n$ esiti possibili
### Definizione
Si realizzano due esperimenti. Si supponga che il primo abbia $m$ esiti e che, per ognuno di questi, il secondo esperimento abbia $n$ esiti. Allora, se sequenze distinte di esiti dei due esperimenti producono esiti distinti, i due esperimenti hanno $m\cdot n$ esiti.
### Esempio
$10$ donne/uomini
$3$ figli
Si vuole eleggere un genitore e un figlio dell'anno. Quante sono le scelte possibili?
	1° esperimento: scelta genitore $10$ 
	2° esperimento: scelta figlio 3
Allora $10\cdot 3= 30$ scelte possibili

Vale una versione generalizzata del principio del calcolo combinatorio (più esperimenti)
### Esempio
Un comitato universitario è composto da $3$ studenti, $4$ ricercatori, $5$ professori, $2$ amministrativi. In quanti modi si può formare un sottocomitato di $4$ persone del quale vi sia un rappresentante per ogni categoria?
$4$ esperimenti $\rightsquigarrow$ scelta di un singolo rappresentante per ogni categoria
$3\cdot 4\cdot 5\cdot 2=120$ (principio fondamentale del calcolo combinatorio (versione generalizzata)
### Esempio
Quante sono le targhe con 7 caratteri sapendo che i primi 3 sono lettere e gli ultimi 4 sono numeri?
$26\cdot 26 \cdot 26 \cdot 10 \cdot 10 \cdot 10 \cdot 10=$ targhe
Cosa accade se si escludesse la ripetizione di lettere e numeri
$26\cdot 25\cdot 24\cdot 10\cdot 9 \cdot 8 \cdot 7=$ targhe
## Permutazioni
Modi di ordinare $a,b,c?\to 6$ modi. L'ordinamento degli elementi si chiama *Permutazione* $$\underset{3}{\blacksquare} \quad\underset{\cdot\quad2\quad\cdot}{\blacksquare} \quad\underset{1}{\blacksquare}=6 $$
$n$ oggetti $\rightsquigarrow n!$ permutazioni di $n$ oggetti.
### Esempio
In quanti modi si possono disporre $9$ persone in fila indiana?
$n=9$, $9!=362880$ nodi
### Esempio
Corso di probabilità frequentato da $6$ e $4$ donne. Alla fine dell'esame viene stilata una graduatoria dal voto più alto e quello più basso. Sapendo che tutti gli studenti hanno punteggi diversi, calcolare
- Le possibili classifiche
	$10!$ ad ogni classifica corrisponde una permutazione dei nomi delle persone
- Quante sono le classifiche se uomini e donne compaiono in liste separate
	$6!$ classifiche per gli uomini
	$4!$ classifiche per le donne
	$\underset{P.\ fondamentale \ del \ c.\ combinatorio}{6!4!=(720)(24)}$ classifiche
### Esempio
Dato un insieme $S$ di $n$ oggetti, si vogliono contare le configurazioni che possono assumere $k$ degli $n$ oggetti 
1) L'ordine è importante?
2) Ci sono ripetizioni?
###### Permutazioni Semplici (senza ripetizioni)
Una permutazione di $n$ oggetti è una presentazione ordinata dei suoi elementi nella quale ogni elemento viene preso una sola volta $$\underset{n}{\blacksquare}\quad \underset{n-1}{\blacksquare}\quad\ldots\quad\underset{1}{\blacksquare}\quad n!$$
### Esempio 
Anagrammi della parola ORA $3!=6$
###### Nel caso di permutazioni di $n$ oggetti alcuni dei quali sono indistinguibili 
$n_1$ sono identici tra loro
$n_2$ sono identici tra loro e distinti dai precedenti
$\vdots$
$n_r\rightsquigarrow \frac{n!}{n_1!n_2!\ldots n_r!}$
### Esempio 
Anagrammi di ORO $\frac{3!}{2!1!}=3$
### Esempio
Torneo scacchi, $10$ concorrenti: $4$ russi, $3$ statunitensi, $2$ inglesi, $1$ brasiliano. Se la classifica finale indica solo la nazionalità quanti solo gli esiti possibili?
$\frac{10!}{4!3!2!1!}=12600$
## Combinazioni
**Obiettivo:** $n$ oggetti. Determinare il numero di insiemi che si possono formare con $r$ oggetti, $r<n$
**Domanda:** Quanti insiemi si tre lettere si possono formare con le 5 lettere $A,B,C,D,E$ $$\underset{5}{\overset{1}{\blacksquare}}\quad\underset{\cdot\quad4\quad\cdot}{\overset{2}{\blacksquare}}\quad\underset{3}{\overset{3}{\blacksquare}}$$modi per scegliere l'insieme delle 3 lettere tenendo conto dell'ordine $\{A,B,C\}$, in questo modo si sta contando ogni insieme di tre lettere (quante sono le permutazioni di $\{A,B,C\}$) $\Longrightarrow \frac{5\cdot4\cdot3}{3\cdot2\cdot1}=10$
In generale:
- $n(n-1)\ldots(n-r+1)$ modi di scegliere $r$ oggetti tra gli $n$ disponibili
- $r!$ numero di volte in cui viene contato in insieme di $r$ oggetti
$$?\begin{align}
&\frac{n(n-1)\ldots(n-r+1)}{r!(n-r)!}= \frac{n!}{r!(n-r)!} \\
&\begin{pmatrix}
n \\
r
\end{pmatrix}= \frac{n!}{r!(n-r)!} \\
&\begin{pmatrix}
n \\
n
\end{pmatrix}=\begin{pmatrix}
n \\
n
\end{pmatrix}=1 \\
&\begin{pmatrix}
n \\
i
\end{pmatrix}=0 \quad \begin{matrix}
i<0 \\
i>n
\end{matrix}
\end{align}$$
DISPOSIZIONI $\rightarrow$ Se si tiene conto dell'ordine
COMBINAZIONI $\rightarrow$ Non si tiene conto dell'ordine
## Coefficiente Binomiale
$\begin{pmatrix} n \\ k \end{pmatrix}= \begin{cases}\frac{n!}{k!(n-k)!} & se \ n,k\in\mathbb{N},\ 0\le k\le n\\ 0 & se \ n,k\in\mathbb{N}, \ 0\le n<k\end{cases}$ rappresenta il numero di sottoinsiemi di $k$ elementi che si possono estrarre da un insieme di $n$ elementi (distinti, indipendentemente dall'ordine).
### Esempio 1
Si vuole formare un comitato di 3 persone scelte tra 20. Quanti sono i comitati?
$\begin{matrix}n=20 \\ k=3\end{matrix}\rightsquigarrow \frac{20!}{3!(20-3)!}=\frac{20!}{3!17!}$
### Esempio 2
1) Quanti comitati composti da 2 donne e 3 uomini si possono formare da un gruppo di 5 donne e 7 uomini?
	$\begin{pmatrix}5 \\ 2\end{pmatrix}$ possibili insiemi con 2 donne
	$\begin{pmatrix}7 \\ 3\end{pmatrix}$ possibili insiemi con 3 uomini
	$\begin{pmatrix}5 \\ 2\end{pmatrix}\cdot\begin{pmatrix}7 \\ 3\end{pmatrix}= \frac{5!}{\underset{(5-2)!}{2!3!}}\cdot \frac{7!}{\underset{(7-3)!}{3!4!}}$ 
2) $\begin{pmatrix} 5 \\ 2\end{pmatrix}$ possibili insiemi con 2 donne. se 2 uomini rifiutano di sedere insieme:
	- $\begin{pmatrix} 2 \\ 0\end{pmatrix}\cdot\begin{pmatrix}5 \\ 3\end{pmatrix}$ insiemi di 3 uomini che non contengono litiganti
	- $\begin{pmatrix} 2 \\ 1\end{pmatrix}\cdot\begin{pmatrix}5 \\ 2\end{pmatrix}$ insiemi di 3 uomini che contengono esattamente 1 litigante
	$\begin{pmatrix} 2 \\ 0\end{pmatrix}\begin{pmatrix} 5 \\ 3 \end{pmatrix}+\begin{pmatrix} 2 \\ 1\end{pmatrix}\begin{pmatrix} 5 \\ 2\end{pmatrix}=1\cdot \frac{5!}{3!2!}+2\cdot \frac{5!}{2!3!}=30$ gruppi di 3 uominio che non contengono entrambi i litiganti
	Il numero totali di comitati è $\underset{m}{30}\underset{n}{\begin{pmatrix} 5 \\ 2\end{pmatrix}}=300$
	Per il principio fondamentale della combinatoria $\begin{pmatrix} n \\ k\end{pmatrix}$ intervengono nello sviluppo del binomio di Newton
### Teorema (del Binomio)
$$(x+y)^n=\sum_{k=0}^n\begin{pmatrix} n \\ k\end{pmatrix}x^ky^{n-k}$$
Il Binomio di Newton permette di calcolare qualsiasi potenza intera di un binomio
### Dimostrazione (per induzione)
- $n=1$
	$(x,y)=\begin{pmatrix} 1 \\ 0\end{pmatrix}x^0y^1+\begin{pmatrix}1 \\ 1\end{pmatrix}x^1y^0=x+y$
- Si suppone vera la formula per $n-1$


$$\begin{align}
(x+y)^n&=(x+y)(x+y)^{n-1}\underset{ipotesi \ aggiuntiva}{=}(x+y)\sum_{k=0}^{n-1}\begin{pmatrix}
n-1 \\ k
\end{pmatrix}x^ky^{n-k} \\
&=\underset{i=k+1}{\underline{\sum_{k=0}^{n-1}\begin{pmatrix}
n-1 \\ k
\end{pmatrix}x^{k+1}y^{n-1-k} }}+\underset{i=k}{\underline{\sum_{k=0}^{n-1}\begin{pmatrix}
n-1 \\ k
\end{pmatrix}x^{k}y^{n-k} }} \\
&=\underset{1)}{\underline{\sum_{i=1}^{n}\begin{pmatrix}
n-1 \\ i-1
\end{pmatrix}x^{i}y^{n-i} }}+\underset{2)}{\underline{\sum_{i=0}^{n-1}\begin{pmatrix}
n-1 \\ i
\end{pmatrix}x^{i}y^{n-i}}} \\
&= x^n+\sum_{i=1}^{n-1}\begin{pmatrix}
n-1 \\ i-1
\end{pmatrix}x^iy^{n-i}+\sum_{i=1}^{n-1}\begin{pmatrix}
n-1 \\ i
\end{pmatrix}x^iy^{n-i}+y^n \\
&1)\ i=n\rightarrow \begin{pmatrix}
n-1  \\
n-1
\end{pmatrix}x^ny^0=x^n  \\
&2)\ i=0\rightarrow \begin{pmatrix}
n-1  \\
0
\end{pmatrix}x^0y^n=y^n \\
&=x^n+y^n+\sum_{i=1}^{n-1}\left[\begin{pmatrix}
n-1 \\
i-1
\end{pmatrix}+\begin{pmatrix}
n-1 \\
i
\end{pmatrix}\right]x^iy^{n-1} \\
&\underset{\begin{pmatrix}
n-1  \\
i-1
\end{pmatrix}+\begin{pmatrix}
n-1 \\
i
\end{pmatrix}=\begin{pmatrix}
n \\
i
\end{pmatrix}}{=}x^n+y^n+\sum_{i=1}^{n-1}\begin{pmatrix}
n \\
i
\end{pmatrix}x^iy^{n-i}=\sum_{i=0}^n\begin{pmatrix}
n \\
i
\end{pmatrix}x^iy^{n-i}
\end{align}$$
## Coefficienti Multinomiali
**Obiettivo:** Distribuire gli oggetti in $r$ scatole distinte in modo che ciascuna di esse contenga $n_1,\ldots,n_r$ oggetti (nell'ordine) e $$\sum_{i=1}^rn_i=n$$
### Esempio
10 Poliziotti, 5 di essi devono pattugliare le strade, 2 devono restare alla stazione e 3 devono stare in riserva. In quanti modi si possono assegnare i 3 compiti?
	$\begin{pmatrix} n \\ n_1 \end{pmatrix}$ possibili scelte per gli oggetti della prima scatola
	$\begin{pmatrix} n-n_1 \\ n_2 \end{pmatrix}$ possibili scelte per gli oggetti della seconda scatola
	$\begin{pmatrix} n-n_1-n_3 \\ n_3 \end{pmatrix}$ possibili scelte per gli oggetti della terza scatola
$$\begin{align}
&\begin{pmatrix} n \\ n-1 \end{pmatrix}\cdot\begin{pmatrix}n-n_1\\ n_2  \end{pmatrix}\cdot\begin{pmatrix} n-n_1-n_2 \\ n_3 \end{pmatrix}\cdots\begin{pmatrix} n-n_1-n_2-\ldots-n_{r-1}\\ n_r \end{pmatrix} \\
&=\frac{n!}{n!\cancel{(n-n_1)!}}\cdot \frac{\cancel{(n-n_1)}!}{n_2!(n-n_1-n_2)!}\cdots\frac{\cancel{(n-n_1-\ldots-n_{r-1})!}}{n_r!\underset{n-n_1-\ldots n_{r-1}-n_r=n-\sum_{i=1}^rn_i=n-n=0}{0!}} \\
&\left( \begin{pmatrix}  n\\k\end{pmatrix}= \frac{n!}{k!(n-k)!} \right)\Longrightarrow \frac{n!}{n_1!n_2!\ldots n_r!}=\begin{pmatrix} n \\ n_1,n_2,\ldots,n_r \end{pmatrix}
\end{align}$$
possibili suddivisioni, quindi $\frac{10!}{5!3!2!}=2520$
##### Generalizzazione del Teorema del Binomio
$$(x_1+\ldots+x_n)^r=\sum_{n_1+\ldots+n_r=n}\begin{pmatrix}
n \\
n_1,n_2,\ldots,n_r
\end{pmatrix}x_1^{n_1}\ldots x_r^{x_r}$$
Per i "grandi numeri" vale la formula si Stirling $$\lim_{n\to\infty} \frac{n!}{e^{-n}n^{n+\frac{1}{2}}\sqrt{2\pi}}=1,\qquad n!\sim e^{-n}n^{n+ \frac{1}{2}}\sqrt{2\pi}\quad n\to\infty$$
# Assiomi della Probabilità
**Obiettivo:** Introdurre il concetto di probabilità di un evento

Si consideri un esperimento il cui risultato non è prevedibile con certezza. Si supponga di conoscere l'insieme dei possibili esiti
### Esempio
Lancio di 2 monte $\rightarrow \{(T,T),\ (T,C), \ (C,T),\ (C,C)\}$
### Definizione
Si definisce *Spazio Campionario* l'insieme dei possibili esiti di un esperimento. Ogni sottoinsieme $E$ dello spazio campionario $S$ si dice *Evento* (formato da possibili esiti di un esperimento)
### Operazioni Insiemistiche con gli Eventi
- $\cup_{i=1}^\infty E_i=$ evento formato da tutti gli esiti compresi in almeno un $E_i$
- $\cap_{i=1}^\infty E_i=$ evento formato da tutti glii esiti compresi in tutti gli $E_i$
- $E^c=$ tutti gli esiti di $S$ che non sono in $E$
- $E\cup F=F\cup E\quad E\cap F=F\cap E\quad\ldots$ valgono come in algebra la proprietà commutativa, associativa e distributiva
- **Leggi di De Morgan:**
	- $(\cup_{i=1}^\infty E_i)^c=\cap^\infty_{i=1} E_i^c$
	- $(\cap^\infty_{i=1}E_i)^c=\cup_{i=1}^\infty E_i^c$
### Approccio Frequentista
$S$, l'esperimento viene ripetuto sotto le stesse condizioni.
$n(E)=$ il numero di volte in cui si verifica $E$ nelle prime $n$ ripetizioni $$P(E)=\lim_{n\to\infty} \frac{n(E)}{n}$$(frequenza limite di $E$)
### Approccio Moderno
$S$, per ogni evento in $E$
- **Assioma 1:** $0\le P(E)\le 1$
- **Assioma 2:** $P(S)=1$
- **Assioma 3:** Se si ha una successione di eventi a 2 a 2 due disgiunti $E_i\cap E_j=\emptyset, \ i\ne j$ $$P(\cup_{i=1}^\infty E_i)=\sum_{i=1}^\infty P(E_i)$$
	- $P(\emptyset)=0, \quad \{E_i\}\quad E_1=S\ E_i\ne\emptyset$
		$P(S)=P(\cup_{i=1}^\infty E_i)\overset{Ax3}{=}\sum_{i=1}^\infty P(E_i)=P(S)+\sum_{i=2}^{+\infty} P(\emptyset)\Longrightarrow P(\emptyset)=0$
### Proprietà
- $P(E^c)=1-P(E)$
	$1\overset{Ax2}{=}P(S)\overset{Ax3}{=}P(E\cup E^c)$
- Se $E\subset F\Longrightarrow P(E)\le P(F)$
### Proposizione
$$P(E\cup F)=P(E)+P(F)-P(E\cap F)$$$E\cup F=E\cup(E^c\cap F)$
Per l'assioma 3:
1) $P(E\cup F)=P(E)+P(E^c\cap F)$
$F=(E\cap F)\cup (E^c\cap F)$
2) $P(E^c\cap F)=P(F)-P(E\cap F)$
2)$\Longrightarrow P(E^c\cap F)=P(F)-P(E\cap F)$
Sostituendo in 1) si ottiene $P(E\cup F)=P(E)+P(F)-P(E\cap F)$
### Esempio
$A$ ha dei libri 
	Con probabilità pari a 0,5 ad $A$ piace il primo libro
	Con probabilità pari a 0,4 ad $A$ piace il secondo libro
	Con probabilità pari a 0,3 ad $A$ piacciono entrambi
Quanto vale la probabilità che ad $A$ non piaccia nessuno dei due libri?
$E_1=${ad $A$ piace il 1° libro}
$E_2=${ad $A$ piace il 2° libro}
$P(E_1^c\cap E_2^c)=?$
	$P(\cap^2_{i=1}E_i^c)\overset{De \ Morgan}{=}P((U^2_{i=1} E_i)^c)=1-P(E_1\cup E_2)2$
	$P(E_1\cup E_2)\overset{Prop.\ precedente}{=}P(E_1)+P(E_1)-P(E_1\cap E_2)=0,5+0,4-0,3=0,6$ 
	$P(E_1^c\cap E_2^c)=1-P(E_1\cup E_2)=1-0,6=0,4$
$$P(E\cup F\cup G)= P(E)+P(F)+P(G)-P(E\cap F)- P(F\cap G)- P(E\cap G)+P(E\cap F\cap G)$$
# Spazi Campionari con Esiti Equiprobabili
$S=\{1,2\ldots,N\}$ spazio campionario finito, si suppongono esiti equiporbabili $$P(\{1\})=P(\{2\})=\ldots=P(\{N\})\Longrightarrow P(\{i\})= \frac{1}{N}=\frac{1}{\# S}=p$$
- Assioma 2 $\rightarrow P(S)=1$
- Assioma 3 $\rightarrow P(\cup E_i)=\sum P(E_i)$ disgiunti
Per l'assioma 3 vale $$P(E)= \frac{\text{numero di elementi di E}}{\text{numero di elementi di S}}$$infatti:
	Se $E\subset S$, si può calcolare $P(E)$ come segue:
		Se $E$ è composto da $k$ elementi $(s_1,\ldots,s_k)$, $k=\#E$
		$E=\{S_1\}\cup\ldots\{S_k\}$
		$P(E)=P(\{S_1\})+\ldots+P(\{S_k\})=p^k= \frac{1}{\# S}\cdot k= \frac{E}{S}$
### Esempio
Lancio di 2 dadi, calcolare la probabilità che la somma dei cue valori sulla faccia superiore sia 7 (36 esiti possibili)
$E=\{somma=7\}$
$(1,6), \ (2,5), \ (3,4), \ (4,3), \ (5,2), \ (1,6)$
$P(E)= \frac{\overset{\#E}{6}}{\underset{\# S}{36}}= \frac{1}{6}$ su 36 esiti equiprobabili
### Esempio
Estrazione casuale di 3 palline da un'urna che contiene 6 palline bianche e 5 nere. Qual'è la probabilità che una pallina sia bianca e le altre due nere?
Metodo 1
	Tenendo conto dell'ordine $E=\{1B;2N\}$, esiti equiprobabili $$11\cdot10\cdot9=990\text{ possibili esiti}$$ $$\begin{align}
6\cdot5\cdot4=120\qquad &B\quad N\quad N \\
5\cdot6\cdot4=120\qquad &N\quad B\quad N  \\
5\cdot 4\cdot 6=120 \qquad &N\quad N\quad B
\end{align}
	$$$P(E)= \frac{120+120+120}{990}= \frac{4}{11}$
Metodo 2:
	Non tendendo conto dell'ordine $$\begin{pmatrix}
11 \\
3
\end{pmatrix}=165\text{ esiti possibili}$$ $$P(E)= \frac{ \begin{pmatrix}
6 \\
1
\end{pmatrix}\begin{pmatrix}
5 \\
2
\end{pmatrix}}{\begin{pmatrix}
11 \\
3
\end{pmatrix}}= \frac{4}{11}$$
### Esempio
Commissione di 5 persone da un gruppo di 6 uomini e 9 donne. Se la selezione avviene in modo casuale, qual'è la probabilità che la commissione sia ciìomposta da 3 uomini e 2 donne?
$$\begin{pmatrix}
15 \\
5
\end{pmatrix}\text{ Possibili combinazioni di 15 persone (etratte in modo equiprobabile)}$$ 
$$P(E)= \frac{\begin{pmatrix}
6 \\
 3
\end{pmatrix}\cdot\begin{pmatrix}
9 \\
2
\end{pmatrix}}{\begin{pmatrix}
15 \\
5
\end{pmatrix}}$$
# Probabilità come Misura della Fiducia
### Definizione (Soggettività della Probabilità)
Totocalcio $1,X,2$ 13 partite.
Un evento è un possibile esito delle 13 gare. Qual'è la probabilità che una colonna sia vincente?
$N$ possibili esiti (si suppone che siano equiprobabili)
$N=3^13$
$p=3^{-13}= \frac{6}{10000000}$
### Definizione (Soggettiva)
Si considera un evento $E$, la probabilità che un soggetto attribuisce all'evento è un numero real che misura il grado si fiducia che un individuo coerente attribuisce, seconde le su informazioni e opinioni, all'avverasi di $E$.
### Osservazione
**Approccio Frequentista:** La definizione è a posteri $\lim_{n\to\infty} \frac{n(E)}{n}$
**Approccio Moderno:** $S$ finito con esiti equiporbabili
Aspetti negativi (della definizione $\frac{\text{casi favorevoli}}{casi poverset{}{}sibili}$):
- Non si può sempre dire che gli eventi sono equiprobabili
- Il numero di esiti è finito
Aspetti positivi:
- Definizione operativa
- Calcolo a priori della probabilità (tramite calcolo combinatorio)
### Esempio
Una mano a poker è detta full se consiste in tre carte di un tipo più due carte di un altro tipo. Qual'è la probabilità che si riceva un full?
Esiti equiprobabili, 52 carte $$\begin{pmatrix}
52 \\
5
\end{pmatrix}\text{Mani di poker equiprobabili (insiemi di 5 carte)}$$$E=\{full\}$, 2 dieci e 3 jack $$\begin{pmatrix}
4 \\
2
\end{pmatrix}\cdot\begin{pmatrix}
4 \\
4
\end{pmatrix}\text{ Combinazioni di 2 dieci e 3 jack}$$13 possibili scelte delle coppie e, dopo aver fissato la coppia, 12 scelte per il tris $$P(E)= \frac{13\begin{pmatrix}
4 \\
2
\end{pmatrix}12\begin{pmatrix}
4 \\
3
\end{pmatrix}}{\begin{pmatrix}
52 \\
5
\end{pmatrix}}\approx 0,0014$$
### Esempio
 In un club sportivo 36 soci giocano a tennis, 28 a squash e 18 a badminton
22 giocano sia a Tennis che Squash
12 giocano sia a Tennis che Badminton
9 giocano sia a Squash che Badminton
4 giocano a tutti e 3
Quanti membri del club giocano ad almeno uno di questi sport
T= soci che giocano a Tennis
S= soci che giocano a Squash
B= soci che giocano a Badminton
$P(C)= \frac{\text{numero dei soci in C}}{N},\quad C\text{ sottoinsieme del club}$ $$\begin{align}
P(T\cup S\cup B)&=P(T)+P(S)+P(B)-P(T\cap S)-P(T\cap B)-P(S\cap B)+P(T\cap S\cap B)
 \\
&= \frac{36}{N}+\frac{28}{N}+\frac{18}{N}-\frac{12}{N}-\frac{9}{N}-\frac{22}{N}+\frac{4}{N} \\
&= \frac{36+28+18-12-9-22+4}{N}= \frac{M}{N}=\frac{43}{N}
\end{align}$$
### Esempio
Si scelgono casualmente 5 palline, senza reinserimento, da un'urna che ne contiene 5 rosse, 6 bianche, 7 blu
Determinare la probabilità di scegliere una pallina di ogni colore
$R=${NON vengono scelte palline rosse}
$W=${NON vengono scelte palline bianche}
$B=${NON vengono scelte palline blu}
$P((R\cup W\cup B)^c=(R^c\cap W^c\cap B^c))=?$
$P((R\cup W\cup B)^c)=1-P(R\cup W\cup B)$ $$\begin{align}
P(R\cup W\cup B)&=P(R)+P(W)+P(B)-P(R\cap W)-P(R\cap B)-P(W\cap B)+P(R\cap N\cap B) \\
&= \frac{\begin{pmatrix}
13 \\
5
\end{pmatrix}}{\begin{pmatrix}
18 \\
5
\end{pmatrix}}+\frac{\begin{pmatrix}
12 \\
5
\end{pmatrix}}{\begin{pmatrix}
18 \\
5
\end{pmatrix}}+\frac{\begin{pmatrix}
11 \\
5
\end{pmatrix}}{\begin{pmatrix}
18 \\
5
\end{pmatrix}}-\frac{\begin{pmatrix}
7 \\
5
\end{pmatrix}}{\begin{pmatrix}
18 \\
5
\end{pmatrix}}-\frac{\begin{pmatrix}
6 \\
5
\end{pmatrix}}{\begin{pmatrix}
18 \\
5
\end{pmatrix}}-\frac{\begin{pmatrix}
5 \\
5
\end{pmatrix}}{\begin{pmatrix}
18 \\
5
\end{pmatrix}}+0=0,2933
\end{align}$$$P(R^c\cap W^c\cap B^c)=1-P(R\cup W\cup B)=1-0,2933$
# Probabilità Condizionata e Indipendenza
**Motivazione:** Calcolare probabilità conoscendo alcune informazioni a priori
Lancio di 2 dadi, prima esce 3. Data questa informazione, calcolare la probabiltià che la somma sia 8.
Possibili esiti: $(3,1),\ (3,2),\ (3,3),\ (3,4),\ (3,5),\ (3,6)$
$P\left( \frac{\overset{somma \ 8}{E}}{\underset{primo \ lancio \ 3}{F}} \right)=\frac{1}{6}$
### Definizione
Se $P(F)>0$, allora $P\left( \frac{E}{F} \right)= \frac{P(E\cap F)}{P(F)}$
### Osservazione
$P(\frac{E}{F})$ è definita nel modo classico come $\frac{\text{casi \ favorevoli}}{\text{casi \ possibili}}$. Se $F$ si realizza, $E$ si realizza se e solo se si realizza l'evento $E\cap F$
$P(E\cap F)$ frequenza casi favorevoli
$P(F)$ frequenza casi possibili
### Esempio
Una moneta viene lanciata 2 volte $$S=\{(T,T),\ (T,C),\ (C,T),\ (C,C)\}$$Si suppone che gli esiti siano equiprobabili. Qual'è la probabilità che venga testa in entrambi i lanci sapendo che
1) Nel primo lancio è uscita testa
	$E=\{(T,T)\}$
	$F_1=\{(T,C),\ (T,T)\}$ 
	$P(E|F_1)= \frac{P(E\cap F_1)}{P(F_1)}= \frac{P(\{T,T\})}{P(\{T,C\},\ \{T,T\})}= \frac{\frac{1}{4}}{\frac{1}{4}+\frac{1}{4}}= \frac{\frac{1}{4}}{\frac{2}{4}}=\frac{1}{2}$
2) Esce testa in almeno un lancio
	$F_2=\{(T,C), \ (C,T),\ (T,T)\}$
	$P(E|F_2)= \frac{P(E\cap F_2)}{P(F_2)}= \frac{P({T,T})}{\frac{1}{4}+\frac{1}{4}+\frac{1}{4}}= \frac{\frac{1}{4}}{\frac{3}{4}}=\frac{1}{3}$
### Esempio
A è indecisa se frequentare un corso di francese o chimica e stima che la probabilità di pendere più di 27 è pari è $\frac{1}{2}$ nel caso del corso si francese e $\frac{2}{3}$ per chimica. Se $A$ basa la sua decisione sul lancio di una moneta, qual'è la probabilità che prende più di 27 in chimica?
$C=${$A$ frequenta chimica}
$B=${$A$ prende 27, qualunque sia l'esame}
$P(C\cap B)=P(C)\cdot P(B|C)=\frac{1}{2}\cdot \frac{2}{3}=\frac{1}{3}$ (dalla definizione $P(B|C)= \frac{P(C\cap B)}{P(C)}\Rightarrow$ $P(C\cap B)=P(C)P(B|C)$) 
### Osservazione
Generalizzazione: regola del prodotto (legge delle probabilità composte)
$P(E_1\cap E_2\cap\ldots\cap E_n)>0$
$P(E_1\cap E_2\cap\ldots\cap E_n)= \begin{align}&P(E_1)P(E_2|E_1) \\ &P(E_3|E_1\cap E_2)\\ &\quad\vdots \\ &P(E_n|E_1\cap\ldots\cap E_{n-1}) \end{align}$
### Esempio
SI può utilizzare la probabilità condizionata anche in altri contesti.
52 carte suddivise in 4 mazzetti di 13 carte. Calcolare la probabilità che in ogni mazzetto ci sia un asso
Metodo 1:
	$E_i\quad i=1,2,3,4$
	$E_1=${asso di picche in uno dei mazzetti}
	$E_2=${asso di picche e cuori in due dei mazzetti}
	$E_3=${asso di picche, cuori e quadri in tre dei mazzetti}
	$E_4=${i 4 assi sono in 4 mazzetti diversi}
	$P(E_1\cap E_2\cap E_3\cap E_4)=P(E_1)P(E_2|E_1)P(E_3|E_1\cap E_2)P(E_4|E_1\cap E_2\cap E_3)$ $$\left.\begin{matrix}
P(E_1)=1 \\
P(E_2|E_1)= \frac{39}{51} \\
P(E_3| E_1\cap E_2)= \frac{26}{50} \\
P(E_4|E_1\cap E_2\cap E_3)= \frac{13}{49}
\end{matrix}\right\}\Longrightarrow P(\cap_{i=1}^4 E_i)= \frac{39\cdot 26\cdot 13}{51\cdot 50\cdot 49}$$
Metodo 2:
	$E_i=${la mano i-esima ha esattamente un asso}
	$P(E_1\cap E_2\cap E_3\cap E_4)= P(E_1)P(E_2|E_1)\ldots$
	$P(E_1)=\frac{\begin{pmatrix}4 \\ 1\end{pmatrix}\cdot\begin{pmatrix}48 \\ 12\end{pmatrix}}{\begin{pmatrix}52 \\ 13\end{pmatrix}}=\ldots$
	$P(E_2|E_1)=\frac{\begin{pmatrix}3 \\ 1\end{pmatrix}\cdot\begin{pmatrix}36 \\ 12\end{pmatrix}}{\begin{pmatrix}39 \\ 13\end{pmatrix}}=\ldots$
	$P(E_3|E_1\cap E_2)=\frac{\begin{pmatrix}2 \\ 1\end{pmatrix}\cdot\begin{pmatrix}24 \\ 12\end{pmatrix}}{\begin{pmatrix}13 \\ 13\end{pmatrix}}=1$
# Probabilità Condizionata
se $P(F)>0$ $$P(E|F)=\frac{P(E\cap F)}{P(F)}$$
Regola del prodotto: se $P(E_1\cap E_2\cap\ldots\cap E_n)>0$ $$P(E_1\cap\ldots\cap E_n)=P(E_1)P(E_2|E_1)\ldots P(E_n|E_1\cap\ldots E_{n-1})$$
### Proposizione 
$P(\cdot|F)$ è una probabilità, cioè verifica
1) $0\le P(E|F)\le 1$
2) $P(S|F)=1$
3) Se $E_i$ sono a due a due disgiunti $$P(\cup_{i=1}^\infty E_i|F)=\sum^\infty_{i=1}P(E_i|F)$$
In altre parole, $a(E)=P(E|F)$ è una funziona di probabilità sullo spazio campionario
1) $0\le P(E|F)\overset{def}{=} \frac{P(E\cap F)}{P(F)}\underset{E\cap F\subset F\Rightarrow P(F)\ge P(E\cap F)}{\le} \frac{P(F)}{P(F)}=1$
2) $P(S|F)\overset{def}{=} \frac{P(S\cap F)}{P(F)}= \frac{P(F)}{P(F)}$
3) $P(\cup_{i=1}^\infty E_i|F)\overset{def}{=} \frac{P((\cup^\infty_{i=1})\cap F)}{P(F)}=\frac{P(\cup^\infty_{i=1}(E_i\cap F))}{P(F)}\overset{per\ ipotesi}{=} \frac{\sum_{i=1}^\infty P(E_i\cap F)}{P(F)}\overset{def}{=}\sum^\infty_{i=1}P(E_i|F)$$= \frac{P(E_1\cap F)}{P(F)}+ \frac{P(E_2\cap F)}{P(F)}$
- $Q(E):=P(E|F)$
- $Q(E^c)=P(E^c|F)=1-P(E|F)=1-Q(E)$
- $Q(E_1\cup E_2)=Q(E_1)+Q(E_2)-Q(E_1\cap E_2)$
- $P(E_1\cup E_2|F)=P(E_1|F)+P(E_2|F)-P(E_1\cap E_2|F)$
## Formula di Bayes
E, F eventi con $0<P(F)<1$
$E=(E\cap F)\cup(E\cap F)^c$
$E\cap F$, $E\cap F^c$ sono disgiunti per l'assioma 3 
$$\begin{align}
P(E)&\overset{Ax3}{=}P(E\cap F)+P(E\cap F^c)\overset{def}{=}P(E|F)P(E)+P(E|F^c)P(F^c) \\
&=P(E|F)P(F)+P(E|F^c)(1-P(F))
\end{align}$$
media ponderata della probabilità di $E$ condizionata a $F$ e $F^c$, con pesi pari alla probabilità dell'evento sul quale si condiziona $F$
### Esempio
Una compagnia di assicurazioni suddivide le persone in 2 classi: propensi e non propensi ad incidenti
le  statistiche mostrano che le persone propense ad incidenti hanno probabilità $0,4$ di avere incidenti in un anno. Questa probabilità scende a $0,2$ per gli altri
1) Si suppone che il $30\%$ della popolazione sia propensa ad incidenti, calcolare la probabilità che un nuovo assicurato abbia un incidente entro un anno dalla stipula della polizza
	$A=${l'assicurato è propenso agli incidenti}
	$A_1=${l'assicurato ha un incidente entro un anno dall'acquisto}
	$P(A_1)=$? $$\begin{align}
&P(A_1)=P(A_1|A)P(A)+P(A_1|A_c)P(A^C)=0,4\cdot0,3+0,2\cdot(1-0,3)=0,26 \\
&P(A)=0,3 \\
&P(A_1|A)=0,4 \\
&P(A_1|A^c)=0,2
\end{align}$$
2) Si suppone che un nuovo assicurato abbia un incidente entro un anno dall'acquisto. Calcolare la probabilità che si tratti di una persone propensa agli incidenti $$P(A|A_1)\overset{def}{=} \frac{P(A\cap A_1)}{P(A_1)}= \frac{P(A_1|A)P(A)}{P(A_1)}= \frac{0,4\cdot0,3}{0,26}= \frac{6}{13}$$
#### Generalizzazione
$F_1,\ldots,F_n$ a due a due disgiunti e $P(F_i)>0$, $\cup_{i=1}^n F_i=S$, {$F_i$} formano una partizione di $S$
$E=\cup_{i=1}^n E\cap F_i$, $E\cap F_i$ sono a due a due disgiunti $$P(E)=\sum_{i=1}^n P(E\cap F_i)\overset{def}{=}\sum_{i=1}^nP(E|F_i)P(F_i)$$
### Legge delle Probabilità totali
$F$ e $F^c$, $P(F^c)=1-P(F)$

$F_1\ldots F_n$ a due a due disgiunti$\quad\cup F_i=S\quad P(F_i)>0$  $$P(F_j|E)\overset{def}{=} \frac{P(E\cap F_J)}{P(E)}\overset{Legge\ della\ prob.\ totale}{=} \frac{P(E|F_j)P(F_j)}{\sum_{i=1}^nP(E|F_j)P(F_i)}$$Formula di Bayes
### Esempio (Falsi Positivi nei Test Medici)
Test per una certa malattia
Da prove sperimentali il test da un risultato positivo corretto (cioè in effettiva presenza della malattia) nel 99% dei casi. Da un risultato negativo corretto (in assenza della malattia) nel 93% dei casi.
Si suppone di sapere che la malattia ha un'incidenza della 0,2% nella popolazione (si può interpretare come la proprietà che il paziente abbia la malattia)
-  Calcolare la probabilità che il paziente sia sano anche se il test ha dato un risultato positivo (falso positivo) $$\begin{align}
&A=\{\text{Paziente ha la malattia}\} \\
&B=\{\text{Il test è positivo}\} \\
&P(A)=0,002 \\
&P(B|A)=0,99 \\
&P(B^c|A^c)=0,93 \\
&P(A^c|B)=1-P(A|B)=?
\end{align}$$$A$ e $A^c$ formano una partizione $$\begin{align}
&P(A|B)= \frac{P(B|A)P(A)}{P(B)}\overset{Legge\ della\ prob.\ totale}{=} \frac{P(B|A)P(A)}{P(B|A)P(A)+P(B|A^c)\cdot P(A^c)} \\
&P(B|A^c)=1-P(B^c|A^c)=1-0,93=0,07 \\
&P(A|B)= \frac{0,99\cdot 0,002}{0,99\cdot0,002+0,07\cdot0,998}\approx0,028 \\
&P(A^c|B)=1-P(A|B)\approx 1-0,028
\end{align}$$
### Osservazione
$\left.\begin{matrix} \text{Affidabilità del test è alta} \\ \text{La malattia è rara} \end{matrix}\right\}\Longrightarrow\text{Falso positivo è "probabile"}$
Il risultato non dice che il test è inutile
$$\begin{align}
&P(A)=0,2\%\overset{14 \ volte\ maggiore}{\longrightarrow}P(A|B)=2,8\% \\
&P(A)\rightsquigarrow P(A|B) \\
&P(A|B)= \frac{0,99\cdot0,028}{0,99\cdot0,028+0,07\cdot\underset{(1-0,028)}{0,972}}\approx0,029
\end{align}$$
### Esempio
Una scatola con 3 tipi di lampadine diverse. La probabilità che la lampadina di tipo 1 duri di più di 1000 ore è pari a 0,7, vale 0,4 per il tipo 2 e 0,3 per il tipo 3. Si suppone che il 20% delle lampadine sia di tipo 1, il tipo 30% di tipo 2 e il 50% di tipo 3
1) Probabilità che una lampadina scelta a caso duri più di 1000 ore $$\begin{align}
P(A)&=\sum^3_{i=1}P(A|F_i)P(F_i)=P(A|F_i)P(F_i)+P(A|F_2)P(F_2)+P(A|F_3)P(F_3) \\
&=0,7\cdot0,2+0,4\cdot0,3+0,3\cdot0,5=0,41
\end{align}$$
2) Sapendo che la lampadina scelta duri più di 1000 ore, calcolare la probabilità che sia di tipo $j=1,2,3$ $$\begin{align}
&P(F_j|A)= \frac{P(A|F_j)P(F_j)}{P(A)}\ \forall j \\
&P(F_1|A)= \frac{P(A|F_1)P(F_1)}{P(A)}= \frac{0,7\cdot0,2}{0,41}\approx 0,341 \\
&P(F_2|A)= \frac{0,4\cdot0,3}{0,41} \\
&P(F_3|A)= \frac{0,3\cdot0,5}{0,41}
\end{align}$$
## Eventi Indipendenti
### Definizione
Due eventi $E$, $F$ si dicono *Indipendenti* se $$P(E\cap F)=P(E)P(F)$$si dicono *Dipendenti* altrimenti
### Esempio
52 carte
$E=${La carta è un asso}
$F=${La carta è di picche}
$P(E\cap F)= \frac{1}{52}\quad P(E)=\frac{4}{52} \ P(F)=\frac{13}{52}$
$\frac{1}{52}=P(E\cap F)=P(E)P(F)= \frac{4}{52}\cdot \frac{13}{52}$
### Proposizione
$E$ e $F$ indipendenti, allora $E$ e $F^c$ sono indipendenti
**Significato:** Se $E$ è indipendente da $F$, la probabilità che $E$ si realizzi non è modificata dalla realizzazione o meno di $F$.
### Dimostrazione
$E$,$F$ sono indipendenti $P(E\cap F^c)\overset{?}{=}P(E)P(F^c)$ $$\begin{align}
&E=(E\cap F)\cup(E\cap F^c)\ disgiunti \\
&P(E)=P(E\cap F)+P(E\cap F^c)\overset{E,F\ indip.}{=}P(E)P(F)+P(E\cap F^c) \\
&\Longrightarrow P(E\cap F^c)=P(E)-P(E)P(F)=P(E)(1-P(F))=P(E)P(F^c)
\end{align}$$
### Osservazione
$E_1,\ldots,E_n$ si dicono indipendenti se ogni sottoinsieme $E_{i1},\ldots,E_{ir}$ di essi vale $$P(E_{i1}\cap E_{i2}\cap\ldots\cap E_{ir})=P(E_{i1})\ldots P(E_{ir})$$
### Esempio
3 eventi $E,F,G$ $$\begin{cases}
P(E\cap F\cap G)=P(E)P(F)P(G) \\
P(E\cap F)=P(E)P(F) \\
P(E\cap G)=P(E)P(G) \\
P(F\cap G)=P(F)P(G)
\end{cases}$$
