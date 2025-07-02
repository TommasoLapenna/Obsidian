---
sticker: emoji//0030-fe0f-20e3
---
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

Le variabili numeriche (quantitative) possono avere molte modalità diverse (continue e discrete), in questi casi è utile raggruppare le modalità in classi e calcolare la frequenza delle classi:
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
- Si suppone di osservare un insieme di $n$ dati $x_{1},x_{2},\ldots,x_{n}$. La media campionaria è la media aritmetica di questi dati e si calcola come $$\overline{x}= \frac{x_{1}+x_{2}+\ldots+x_{n}}{n}=\frac{1}{n}\sum^n_{i=1}x_{i}$$La media di popolazione $\mu$ è calcolata usando tutte le $N$ unità statistiche che costituiscono la popolazione di riferimento.

La media **Campionaria** piò essere calcolata a partire dalla distribuzione di frequenza assoluta o relativa. Si suppone che le modalità che la variabile assume nel campione siano $v_{1},v_{2},\ldots,v_{k}$ con numerosità $f_{1},f_{2},\ldots,f_{k}$. Allora:
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