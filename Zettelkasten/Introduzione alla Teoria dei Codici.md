Tags: [[Matematica Discreta e Codici]]  [[University]]

///immagine 

> **ESEMPIO**
> 	Messaggio sorgente
> 		SUD     $\longrightarrow$  00
> 		NORD  $\longrightarrow$  10
> 		EST      $\longrightarrow$  01
> 		OVEST $\longrightarrow$  11

A causa del rumore se si invia SUD = 00, si potrebbe avere (per esempio) in output 10 a causa del rumore. Essendo questa codifica biettiva, non ci si accorge dell' errore, perciò non è possibile correggerlo.
Una possibile soluzione è aggiungere dei bit di ridondanza, passando da uno spazio $\mathbb{F}^2_{2}$  ad uno $\mathbb{F}^2_{n}$  , $n >2$ , quindi dopo la "vecchia modfica primaria", si aggiunge una codifica di canale.
	1. Accorgersi dell'errore $\longrightarrow$ ERROR DETECTION
	2. Correggere l'errore $\longrightarrow$ ERROR CORRECTION

> **ESEMPIO (Controllo Parity Check**)
	 $\mathbb{F}^2_{2}$         $\mathbb{F}^3_{2}$
	00 $\longrightarrow$ 000 
	10 $\longrightarrow$ 101    
	01 $\longrightarrow$ 011
	 11 $\longrightarrow$ 110
	 3° bit = somma dei bit precedenti, codifica di canale $\mathbb{F}^2_{2}\hookrightarrow \mathbb{F}^3_{2}$ (mappa iniettiva), $Im(codifica di canale) = C$

In generale, $\exists!$ decodifica che valga per tutti i codici per tutti i canali.

**MDD (Minimum Distance Decoding):** 
	Riceve in input del canale $\underline{\omega}\in\mathbb{F}^3_2$ e cerca la parola (elemento del codice) o le parole nel codice $C\subset\mathbb{F}^3_2$ che hanno distanza minima da $\underline{\omega}$.
	
> **DEFINIZIONE (Distanza di Hamming)** 
	Siano $\underline{x},\underline{y}\in\mathbb{F}^n_2$ .  $d(\underline{x},\underline{y})=\#\{i\in\{1,\ldots,n\}|x_i\neq y_i\}$ 

> **ESEMPIO**
	$d(100,011)=3$
	$d(100,010)=2$ 

Con $\underline{\omega}\in\mathbb{F}^2_2,\forall x\in C$ e si sceglie di decodificare $\underline{\omega}$ ad $\underline{x}\in C$ che realizza il minimo (per minimi multipli si richiede la ritrasmissione del mesaggio), mdd ha successo se tale minimo è unico.

> **Nell'esempio:**
>                            *possibili output:*
> 						   $101$| = 0 errori	
> 	*Messaggio in input*: $101 \rightsquigarrow$ $001$|
> 						   $100$| = *errori a 1 bit*
> 						   $111$| 
> 						   $\ldots$ | = *errori a 2, 3 bit*
>
> 	- Se $\underline{\omega}=101\Rightarrow$ decodifica univocamente a $101\in C$
> 	- Se $\underline{\omega}=001,100,111\notin C\Rightarrow$ sicuramente c'è stato un errore di trasmissione (1. si)
> 	- Se mdd: $\underline{\omega}=001\rightarrow000\in C,011\in C,101\in C\Rightarrow$ non si sa decodificare in      modo univoco
> 	-Stessa cosa peer $\underline{\omega}=100,111$

Per avere successo con 2. ERROR CORRECTION, si può scegliere $C\subset\mathbb{F}^5_2$ , si aumenta $C$ (rispetto al codice $C\subset\mathbb{F}^3_2$) per aumentare la distanza tra le parole.

>**ESEMPIO**
	$00\longrightarrow00000$ |
	$01\longrightarrow01111$ |
	$10\longrightarrow10110$ |
	$11\longrightarrow11001$ | $:=C\subset\mathbb{F}^5_2$
>
	1. Si accorge di al più di 2 errori ($\leq2$ errori)
	2. Corregge al più un errore ($\leq1$ errori)

>**OSSERVAZIONE**
	$d(C):=\min\limits_{\underline{x},\underline{y}\in C,\underline{x}\neq\underline{y}}\{d(\underline{x},\underline{y})\}=3$
	$d(C)=3$ e:  $2=3-1$ , $1=\frac{{3-1}}{2}$ (fatto generale)	

In conclusione nel caso $\mathbb{F}^3_2$ non si ha un'unicità di decodifica (solo rilevazione dell'errore ma senza correzione).  Si vorrebbe quindi aumentare $n$ di $\mathbb{F}^n_q$ con $C\subset\mathbb{F}^n_2$ (criterio per aumentare $d(C)$), ma aumentare $n$ comporta diminuire la velocità di trasmissione e l'efficenta di decodifica.
Quindi si hanno due desideri contrastanti:
	- Aumentare il potere correttivo di C
	- Aumentare la velocità di trasmissione e decodifica di mdd
$\Rightarrow$ si ha bisogno di ottimizzazione $\rightarrow$ TEORIA DEI CODICI