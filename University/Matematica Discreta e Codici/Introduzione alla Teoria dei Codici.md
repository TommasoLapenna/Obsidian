---
sticker: emoji//0031-fe0f-20e3
---
## Introduzione alla Teoria dei Codici

![[Pasted image 20260116160539.png|center|800]]



Si prende per esempio il seguente messaggio sorgente
 $$ \begin{align}
\text{SUD}     &\longrightarrow  00\\
 \text{NORD}  &\longrightarrow  10\\
 \text{EST}      &\longrightarrow  01\\
 \text{OVEST} &\longrightarrow  11
\end{align} $$
A causa del rumore se si invia SUD = 00, si potrebbe avere (per esempio) in output 10 a causa del rumore. Essendo questa codifica biettiva, non ci si accorge dell' errore, perciò non è possibile correggerlo.
Una possibile soluzione è aggiungere dei bit di ridondanza, passando da uno spazio $\mathbb{F}^2_{2}$  ad uno $\mathbb{F}^2_{n}$  , $n >2$ . Quindi dopo la "vecchia modfica primaria", si aggiunge una codifica di canale, con due obiettivi:

1. ==Accorgersi dell'errore $\longrightarrow$ ERROR DETECTION==
2. ==Correggere l'errore $\longrightarrow$ ERROR CORRECTION==

> [!example]+ Esempio (Controllo Parity Check):
>$$
\begin{matrix}
\mathbb{F}^2_{2}&  &      \mathbb{F}^3_{2} \\
 00 & \longrightarrow &000 \\
 10 &\longrightarrow &101    \\
 01 &\longrightarrow & 011 \\
 11 &\longrightarrow & 110
\end{matrix}
>$$
 >In questo caso si è aggiunto un $3° bit = \text{somma dei bit precedenti}$, e la codifica di canale è 
>$$
 \mathbb{F}^2_{2}\underset{(\text{mappa iniettiva)}}\hookrightarrow \mathbb{F}^3_{2} \qquad Im(\text{codifica di canale}) = C
>$$

> [!info] MDD
> In generale, $\exists!$ decodifica che valga per tutti i codici per tutti i canali: 
> - **MDD (Minimum Distance Decoding):** 
> 	Riceve in input del canale $\underline{\omega}\in\mathbb{F}^3_2$ e cerca la parola (elemento del codice) o le parole nel codice $C\subset\mathbb{F}^3_2$ che hanno distanza minima da $\underline{\omega}$.
> 	

> [!gray] DEFINIZIONE (Distanza di Hamming)
> Siano $\underline{x},\underline{y}\in\mathbb{F}^n_2$ .  La distanza di Hamming è:
> $$d(\underline{x},\underline{y})=\#\{i\in\{1,\ldots,n\}|x_i\neq y_i\}$$ 
>  Esempio:
>  $$
>  d(100,011)=3\quad d(100,010)=2 
> $$

Con $\underline{\omega}\in\mathbb{F}^2_2,\forall x\in C$ e si sceglie di decodificare $\underline{\omega}$ ad $\underline{x}\in C$ che realizza il minimo (per minimi multipli si richiede la ritrasmissione del mesaggio), mdd ha successo se tale minimo è unico.

**Nell'esempio:**
![[Pasted image 20260116171708.png|center|600]]

- Se $\underline{\omega}=101\Rightarrow$ decodifica univocamente a $101\in C$
 - Se $\underline{\omega}=001,100,111\notin C\Rightarrow$ sicuramente c'è stato un errore di trasmissione (1. si) 	
 - Se mdd: $\underline{\omega}=001\rightarrow000\in C,011\in C,101\in C\Rightarrow$ non si sa decodificare in modo univoco
 - Stessa cosa per $\underline{\omega}=100,111$

Per avere successo con 2. ERROR CORRECTION, si può scegliere $C\subset\mathbb{F}^5_2$ , si aumenta $C$ (rispetto al codice $C\subset\mathbb{F}^3_2$) per aumentare la distanza tra le parole.

> [!example]+ Esempio
> $00\longrightarrow00000$ |
> $01\longrightarrow01111$ |
> $10\longrightarrow10110$ |
> $11\longrightarrow11001$ | $:=C\subset\mathbb{F}^5_2$
> 
> 1. Si accorge di al più di 2 errori ($\leq2$ errori)
> 2. Corregge al più un errore ($\leq1$ errori)

**OSSERVAZIONE (Sull'esempio)**
- $d(C):=\min\limits_{\underline{x},\underline{y}\in C,\underline{x}\neq\underline{y}}\{d(\underline{x},\underline{y})\}=3$
- $d(C)=3$:
	- $2=3-1$ 
	- $1=\frac{{3-1}}{2}$ (fatto generale)	

In conclusione nel caso $\mathbb{F}^3_2$ non si ha un'unicità di decodifica (solo rilevazione dell'errore ma senza correzione).  Si vorrebbe quindi aumentare $n$ di $\mathbb{F}^n_q$ con $C\subset\mathbb{F}^n_2$ (criterio per aumentare $d(C)$), ma aumentare $n$ comporta diminuire la velocità di trasmissione e l'efficenta di decodifica.
Quindi si hanno due desideri contrastanti:
- Aumentare il potere correttivo di C
- Aumentare la velocità di trasmissione e decodifica di mdd
$\Rightarrow$ si ha bisogno di ottimizzazione $\rightarrow$ TEORIA DEI CODICI