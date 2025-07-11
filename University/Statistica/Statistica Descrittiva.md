---
sticker: emoji//0030-fe0f-20e3
---
- [[#Definizione di Statistica|Definizione di Statistica]]
- [[#Rappresentazione dei Dati|Rappresentazione dei Dati]]
- [[#Tipologie di Grafici|Tipologie di Grafici]]
	- [[#Tipologie di Grafici#Diagramma a Barre|Diagramma a Barre]]
	- [[#Tipologie di Grafici#Diagramma a Torta|Diagramma a Torta]]
	- [[#Tipologie di Grafici#Istogramma|Istogramma]]
	- [[#Tipologie di Grafici#Ogiva|Ogiva]]
	- [[#Tipologie di Grafici#Digramma Ramo-Foglia|Digramma Ramo-Foglia]]
- [[#Indici Statistici|Indici Statistici]]
	- [[#Indici Statistici#Media Aritmetica|Media Aritmetica]]
		- [[#Media Aritmetica#Proprietà della Media Aritmetica|Proprietà della Media Aritmetica]]
	- [[#Indici Statistici#Mediana|Mediana]]
	- [[#Indici Statistici#Quartili|Quartili]]
		- [[#Quartili#Box-Plot|Box-Plot]]
	- [[#Indici Statistici#Moda|Moda]]
	- [[#Indici Statistici#Campo di Variazione|Campo di Variazione]]
	- [[#Indici Statistici#Varianza|Varianza]]
		- [[#Varianza#Proprietà della Varianza|Proprietà della Varianza]]
	- [[#Indici Statistici#Deviazione Standard|Deviazione Standard]]
	- [[#Indici Statistici#Coefficiente di Variazione|Coefficiente di Variazione]]
	- [[#Indici Statistici#Differenza Interquartile|Differenza Interquartile]]
	- [[#Indici Statistici#Covarianza|Covarianza]]
		- [[#Covarianza#Indice di Correlazione|Indice di Correlazione]]

## Definizione di Statistica
La statistica è la materia che si occupa di apprendere e trarre informazioni dai dati tramite la raccolta dei dati (campionamento, disegni, ecc.), statistica descrittiva (sintesi e descrizione di quanto osservato in un campione) e statistica inferenzaile (estrazione di informazioni a partire da un campione).

| ==Concetti Base==    |                                                       |
| -------------------- | ----------------------------------------------------- |
| **Unità Statistica** | Unità osservazione o di misurazione                   |
| **Popolazione**      | Insieme completo di unità statitche                   |
| **Campione**         | Sottoinsieme della popolazione                        |
| **Variabili**        | Caratteristiche di interesse sulle unità statistiche  |
| **Dati**             | Valori assunti dalle variabili osservate sul campione |
![[Pasted image 20250702110343.png|center|400]]

L'estrazione di un campione della popolazione è determinata dal caso.
Quando si fa inferenza si deve tenere conto di ciò che è stato osservato, ma anche del fatto che al variare del campione saranno variate le osservazioni.

---

## Rappresentazione dei Dati
**Tipi di Dati:**
- Categorici
	- Nominali
	- Ordinali
- Numerici
	- Continui
	- Discreti

I Dati solo generalmente organizzato in una matrice dei dati:

![[Pasted image 20250702110850.png|center|400]]

I dati possono essere sintetizzare in tabelle e grafici che riportano le distribuzioni di **Frequenze Assolute** e **Frequenze Relative**.

Nel passaggio
$$\text{Matrice dei Dati}\longrightarrow\text{Distribuzioni di Frequenza}$$ Si perde la corrispondenza tra unità statistica e modalità della variabile

![[Pasted image 20250702111300.png|center|400]]

Nel caso in cui le variabili siano numeriche o categoriche ordinali si possono costruire distribuzioni di **Frequenze Cumulate**

![[Pasted image 20250702111449.png|center|400]]

Dal punto di vista pratico, per costruire le distribuzioni di frequenza si usa la seguente schema, con $v_{i}$ dati dei quali si osserva la frequenza:


| $v_{i}$ | Frequenza Assoluta $f_{i}$ | Frequenza Relativa $\frac{f_{i}}{n}$ | Frequenza Percentuale | Frequenza Cumulativa |
| ------- | -------------------------- | ------------------------------------ | --------------------- | -------------------- |
| ...     | ...                        | ...                                  | ...                   | ...                  |


Le variabili numeriche (==quantitative==) possono avere molte modalità diverse (continue e discrete), in questi casi è utile raggruppare le modalità in classi e calcolare la frequenza delle classi:
- Si possono decidere che le classi abbiano tutte la stessa **ampiezza**, in questo caso, l'ampiezza delle classi è determinata come  $$\frac{\text{Valore Massimo}- \text{Valore Minimo}}{\text{Numero di Classi}}$$Maggiore è l'ampiezza delle classi maggiore è la perdita di informazioni nel passaggio dalla matrice dei dati alla distribuzione di frequenza.

> [!example]+ Esempio:
> Un produttore di isolante seleziona a caso 20 giorni invernali e registra la temperatura massima giornaliera:
> $$\begin{align} 24,35,17,21,24,37,26,46,59,30,32,13,10,38,41,43,44,27,53,27 \end{align}$$
> Si ordinano i dati grezzi in ordine crescente:
> $$10,13,17,21,24,24,26,27,27,30,32,35,37,38,41,43,44,46,53,59$$
> Si sceglie il numero di classi, per esempio 5, allora l'ampiezza della classi è:
> $$\frac{59-10}{5}\simeq 10$$
> ![[Pasted image 20250702112316.png|center|400]]
> 

--- 

## Tipologie di Grafici
### Diagramma a Barre
L'ascissa indica la modalità della variabile, se la variabile è qualitativa non ci sono vincoli sul posizionamento delle barre sull'ascisse; le ordinate indicano le frequenze assolute o relative

![[Pasted image 20250702112645.png|center|400]]

Utilizzo: Variabili di tipo qualitativo o quantitativo discreto.
### Diagramma a Torta
Ogni settore circolare corrisponde ad una modalità della variabile, l'angolo interno è proporzionale alla frequenza ($360°\times\text{ Frequenza Relativa della Modalita'}$).

![[Pasted image 20250702113012.png|center|200]]

Utilizzo: Variabili di tipo quantitativo.
### Istogramma
L'ascissa riporta gli estremi delle classi, la base del rettangolo è proporzionale all'ampiezza della classe e l'altezza del rettangolo è proporzionale alla densità di frequenza della classe, calcolata come $\frac{\text{Frequenza}}{\text{Ampiezza}}$

![[Pasted image 20250702113235.png|center|300]]

Utilizzo: Variabili di tipo quantitativo continue.
### Ogiva
L'ascissa riporta gli estremi delle classi, mentre l'ordinata riporta il valore della frequenza cumulata

![[Pasted image 20250702113415.png|center|300]]

Utilizzo: Variabili di tipo quantitativo continue.
### Digramma Ramo-Foglia
I rami rappresentano la cifra più grande del dato (per esempio le decine), mentre le foglie rappresentano la cifra più piccola

![[Pasted image 20250702120126.png|center|350]]

Utilizzo: Variabili di tipo Quantitativo.

---

## Indici Statistici
- Indici di **Tendenza Centrale** (o di posizione)
	- Media
	- Mediana
	- Quartili
	- Moda
- Indici di **Variabilità**
	- Campo di Variazione
	- Differenza Interquartile
	- Varianza
	- Deviazione Standard
	- Coefficiente di Variazione

### Media Aritmetica
La media aritmetica è la misura della tendenza centrale più comune. Essa può essere  calcolata per variabili per variabili quantitative.
- Si suppone di osservare un insieme di $n$ dati $x_{1},x_{2},\ldots,x_{n}$. La media campionaria è la media aritmetica di questi dati e si calcola come $$\overline{x}= \frac{x_{1}+x_{2}+\ldots+x_{n}}{n}=\frac{1}{n}\sum^n_{i=1}x_{i}$$
La media di popolazione $\mu$ è calcolata usando tutte le $N$ unità statistiche che costituiscono la popolazione di riferimento.

La media **Campionaria** può essere calcolata a partire dalla distribuzione di frequenza assoluta o relativa. Si suppone che le modalità che la variabile assume nel campione siano $v_{1},v_{2},\ldots,v_{k}$ con numerosità $f_{1},f_{2},\ldots,f_{k}$. Allora:
- Usando le frequenza assolute:$$\overline x=\frac{1}{n}\sum^k_{i=1}f_{i}v_{i}$$
- Usando le frequenze relative: $$\overline x=\sum^k_{i=1} \frac{f_{i}}{n}v_{i}$$

> [!info] Robustezza Media
> La media non è un indice robusto: risente di valori eccezionalmente grandi o piccoli.

> [!example]+ Esempio:
> Si considera un campione di 8 complessi petrolchimici. In ciascuno di essi è stat rilevata la concentrazione di particelle in sospensione (microgrammi per metro cubo)
> 
> | Id  | Concentrazione |
> | --- | -------------- |
> | 1   | 3              |
> | 2   | 1              |
> | 3   | 2              |
> | 4   | 3              |
> | 5   | 4              |
> | 6   | 2              |
> | 7   | 1              |
> | 8   | 3              |
> 
> | Concentrazione ($v_{i}$) | Frequenza Assoluta $f_{i}$ | Frequenza Relativa $\frac{f_{i}}{n}$ |
> | ------------------------ | -------------------------- | ------------------------------------ |
> | 1                        | 2                          | 1/4                                  |
> | 2                        | 2                          | 1/4                                  |
> | 3                        | 3                          | 3/8                                  |
> | 4                        | 1                          | 1/8                                  |
> $$\begin{align} 
> \overline x=& \frac{3+1+2+3+4+2+1++3}{8}=\frac{19}{8}=2.375 \\
> \overline x=& \frac{(1\times 2)+(2\times2)+(3\times 3)+(4\times 1)}{8}= \frac{19}{8}=2.375 \\
> \overline x=& 1\times \frac{1}{4}+2\times \frac{1}{4}+3\times \frac{3}{8}+1 \times \frac{1}{8}=2.375 
> \end{align}$$

#### Proprietà della Media Aritmetica
- La media aritmetica è compresa tra il valore minimo e il valore massimo: $$x_{min}\le \overline x\le x_{max}$$
- La media aritmetica è il baricentro della distribuzione: $$\sum^k_{i=1}f_{i}v_{i}=\overline x\sum^k_{i=1}f_{i}$$
- La somma degli scarti della media aritmetica è $0$ $$\sum^k_{i=1}f_{i}(v_{i}-\overline x)=\sum^k_{i=1}f_{i}v_{i}-\sum^k_{i=1}f_{i}\overline x=0$$
- La media minimizza $$\begin{align}f(a)&=\underset{\text{somma delgi scarti al quadrato}}{\sum^k_{i=1}f_{i}(v_{i}-a)^2}: \\
&\frac{\delta f(a)}{\delta a}=-2\sum^k_{i=1}f_{i}(v_{i}-a) \\
& \frac{\delta f(a)}{\delta a}=0\Longrightarrow\sum^k_{i=1}f_{i}v_{i}=\sum^k_{i=1}f_{i}a\Longrightarrow a=\overline x \\
& \frac{\delta^2f(a)}{\delta a^2}=2\sum^k_{i=1}f_{i}>0 \end{align}$$
- Proprietà Associativa $$\begin{align}
&\underset{n_{1}\text{ elementi media }\overline x_{1}}{x_{1},x_{2},\ldots,}\underset{n_{2}\text{ elementi media }\overline x_{2}}{\ldots,\ldots},\ldots, \underset{n_{h} \text{ elementi media }\overline x_{h}}{\ldots,x_{n}} \\
&\overline x= \frac{\overline xn_{1}+\ldots+\overline x_{h}n_{h}}{n_{1}+\ldots+n_{h}}
\end{align}$$
- Proprietà Ricorsiva $$\underset{\text{media }\overline x_{n}}{x_{1},x_{2},\ldots, x_{n}},\ x_{n+1};\quad \overline x= \frac{\overline xn+x_{n+1}}{n+1}$$
### Mediana
In una lista ordinata di dati, la mediana è il valore centrale. Il modo di individuare questo valore dipende dal numero di unità campionarie $n$:
- $n$ Dispari: la mediana occupa la posizione $\frac{n+1}{2}$
- $n$ Pari: la mediana è la media tra i due valori nelle posizioni $\frac{n}{2}$ e $\frac{n}{2}+1$

> [!info] Robustezza Mediana
> La mediana è un indice robusto a differenza della media, ma dati molti diversi possono avere la stessa mediana
> $$\begin{align}
> &29 \ 31 \ 35\ 39 \ 39\ 40\ 43 \ 44\ 44 \ \underline{52} \\
> &29\ 31\ 35\ 39\ 39 \ 40\ 43\ 44\ 44\ \underline{92}
> \end{align}$$
> Le media sono rispettivamente $39.6$ e $43.6$, le mediane sono invece entrambe $39.5$
> 

### Quartili
I quartili sono i valori che dividono in 4 parti la distribuzione dei dati
- $Q_{1}$: La prima modalità la cui frequenza relativa cumulata è almeno $0.25$
- $Q_{2}$: La prima modalità la cui frequenza relativa cumulata è almeno $0.5$
- $Q_{3}$: La prima modalità la cui frequenza relativa cumulata è almeno $0.75$

> [!hint] $Q_{2}$
> La **mediana** è anche detta secondo quartile $Q_{2}$.

Dal punto di vista pratico, per trovare i quartili:
1. Si ordinano le osservazioni
2. Si calcola il $Q_{2}$ come la mediana
3. Guardando i dati divisi in due dalla mediana, si calcola nuovamente la mediana in queste due meta $Q_{1}$ e $Q_{2}$
#### Box-Plot
Il box-plot è un diagramma che rappresenta la distribuzione dei dati e presuppone la conoscenza dei quartili. Questo tipo di diagramma risulta utile per evidenziare la presenza di valori eccezzionali, chiamati *outliers*.

![[Pasted image 20250704155545.png|center|500]]

$$\begin{align}&a=max\{x_{min};\ Q_{1}-1.5(Q_{3}-Q_{1})\} \\
&b=min\{x_{max};\ Q_{3}+1.5(Q_{3}-Q_{1})\}\end{align}$$
### Moda
La moda è il valore che occorre più frequentemente nel campione; non è influenzata da valori estremi, può essere usata sia per dati numerici che categorici e ce ne possono essere un numero qualsiasi.

![[Pasted image 20250704160028.png|center|500]]

### Campo di Variazione
Il campo di variazione è la più semplice misura di variabilità, si calcola come $$x_{max}-x_{min}$$
Dipende dall'unità di misura della variabile considerata e ignora il modo in cui i dati sono distribuiti. È molto sensibile ai valori estremi.
### Varianza
La varianza è la media dei quadrati degli scarti degli scarti fra ciascuna osservazione e la loro media.
- **Varianza della Popolazione:** $$\sigma^2=\frac{1}{N}\sum^N_{i=1}(x_{i}-\mu)^2$$
- **Varianza Campionaria:** $$s^2=\frac{1}{n-1}\sum^n_{i=1}(x_{i}-\overline x)^2$$

con $\mu$ media della popolazione e $\overline x$ media campionaria.
#### Proprietà della Varianza
- La varianza è sempre positiva
- La varianze è uguale a 0 quando tutti i dati sono uguali
- L'unità di misura della varianza è pari al quadrato dell'unità di misura della variabile considerata
- La varianza può essere calcolata usando il **Momento Primo** (media) e il **Momento Secondo**, ovvero: $$\begin{align}\sigma^2&=\frac{1}{N}\sum^N_{i=1}(x_{i}-\mu)^2=\frac{1}{N}\sum^N_{i=1}x^2_{i}-\frac{2}{N}\sum^N_{i=1}+x_{i}\mu+\frac{1}{N}\sum^N_{i=1}\mu^2= \\
&=\mu_{2}-2\mu^2+\mu^2=\mu_{2}-\mu^2\end{align}$$
> [!info] Momento
> Il momento $h-$esimo è la media dei valori elevati alla $h-$esima potenza:
> - Momento Primo $(h=1)\longrightarrow \ \mu=\frac{1}{N}\sum^N_{i=1}x_{i}$
> - Momento Secondo $(h=2)\longrightarrow \ \mu_{2}=\frac{1}{N}\sum^N_{i=1}x^2_{i}$
> 

### Deviazione Standard
La deviazione standard è un modo per esprimere la variabilità ==nella stessa unità di misura dei dati==, ovvero
$$
\sigma=\sqrt{ \sigma^2 }=\sqrt{ \frac{1}{N}\sum^N_{i}(x_{i}-\mu)^2 }
$$
### Coefficiente di Variazione
==Il coefficiente di variazione è un modo per esprimere la variabilità in modo indipendente dall'unità di misura,== ovvero
$$CV=\frac{\sigma}{|\mu|}$$
### Differenza Interquartile
La differenza interquartile è una misura di variabilità robusta, definita come $$DQ=Q_{3}-Q_{1}$$
Indica dove si trovano nel box-plot il 50% dei valori.
### Covarianza
Su ciascuna unità statistica può essere rilevata più di una variabile, nel caso quest'ultime siano due si parla di **Dari Bivariati**. Per sintetizzare questo tipo di problema si possono usare:
- Distribuzioni di di frequenza doppia
![[Pasted image 20250704162911.png|400]]
- Diagrammi a Dispersione 
![[Pasted image 20250704163001.png|300]]

La **Covarianza** indica (con riferimento al grafo di dispersione) se a valori grandi della prima variabile corrispondo valori grandi o piccoli  della seconda. Dato un campione bivariato $(x_{i},y_{i})$ per $i=1,\ldots, n$, la covarianza *campionaria* è definita come
$$
Cov(x,y)= \frac{\sum^n_{i=1}(x_{i}-\overline x)(y_{i}-\overline y)}{n-1}
$$

> [!hint] Casi di Covarianza
> Covarianza $>0$ (Dipendenza lineare positiva)
> ![[Pasted image 20250704163653.png|center|350]]
> Covarianza < 0 (Dipendenza lineare negativa)
> ![[Pasted image 20250704163734.png|center|350]]
> Covarianza $=0$ (Dipendenza lineare assente)
> ![[Pasted image 20250704163838.png|center|350]]

#### Indice di Correlazione
Dato un campione bivariato $(x_{i},y_{i})$ per $i=1,\ldots,n$, la **Correlazione Campionaria** è definita come segue:
$$
r=\frac{\sum^n_{i=1}(x_{i}-\overline x)(y_{i}-\overline y)}{(n-1)} \frac{1}{s_{x}s_{y}}=\frac{Cov(x,y)}{s_{x}s_{y}}
$$
- $-1\le r\le 1$
	- $r=1$ in caso di perfetta relazione lineare positiva
	- $r=-1$ in caso di perfetta relazione lineare negativa

![[Pasted image 20250704164540.png|center|400]]
