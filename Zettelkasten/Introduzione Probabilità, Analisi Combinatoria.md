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
\end{matrix}\ non \ funzionante$$ $\frac{3}{6}=\frac{1}{2}$
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
### Dimostrazione (per induzione)
- $n=1$
	$(x,y)=\begin{pmatrix} 1 \\ 0\end{pmatrix}x^0y^1+\begin{pmatrix}1 \\ 1\end{pmatrix}x^1y^0=x+y$
- Si suppone vera la formula per $n-1$ $$\begin{align}
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
\end{pmatrix}x^iy^{n-i}+y^n
\end{align}$$