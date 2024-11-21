Tags: [[Matematica Discreta e Codici]] [[University]]

>  **DEFINIZIONE (Alfabeto)** 
	$A_q$ insieme finito di $q$ elementi
	{L'insieme di parole di lunghezza $n$ sull'alfabeto assegnato} $=$ $A^n_q:=A_q\times\ldots\times A_q$ (n volte)
	$\underline{x}\in A^n_q ,\underline{x}=(x_1,\ldots,x_n),x_i\in A_q$ 
	codice di lunghezza n sull'alfabeto assegnato $:=C\subseteq A^n_q$ (elementi di C$\rightarrow$ parole del codice)

Quindi un codice $C$ ha 2 parametri: $q$ (lunghezza delle parole del codice), $n$ (numero di lettere dell'alfabeto).

> **DEFINIZIONE (Distanza di Hamming su $A_q$**
	la distanza di Hamming su $A_q$ è $\underset{\underline{x},\underline{y}\in A^n_q}{d(\underline{x},\underline{y})}:=\#\{i\in\{1,\ldots,n\}|x_i\neq y_i\}$

>**PROPRIETÀ DI d**
- $0\le d(\underline{x},\underline{y})\le n,\forall\underline{x},\underline{y}\in A^n_q$
- $d(\underline{x},\underline{y}) =d(\underline{y},\underline{x})$ (simmetria)
- $d(\underline{x},\underline{y})=0 \iff \underline{x}=\underline{y}$ (non degenerazione della distanza)
- $d(\underline{x},\underline{y}) \le d(\underline{x},\underline{z})+d(\underline{z},\underline{y}),\forall\underline{x},\underline{y},\underline{z}\in A^q_n$

>**DEFINIZIONE (Distanza minima del codice)** 
	$d(C):=\underset{\underline{x},\underline{y}\in C,\underline{x}\neq\underline{y}}{min}\{d(\underline{x},\underline{y})\}$

>**DEFINIZIONE (Distanza di $\underline{\omega}$ DA $C$)**
	Se $\underline{\omega}\in A^n_q,d(C,\underline{\omega}):=\underset{\underline{x}\in C}{min}\{d(\underline{\omega},\underline{x})\}$

È possibile definire 2 tipologie di palle di raggio r, una aperta ed una chiusa:
	***Palla aperta di raggio r e centro in $\underline{\omega}$:*** $B_r(\underline{\omega})=\{y\in A^q_n |d(\underline{y},\underline{\omega})<r\}$ $(\le r-1)$
	***Palla chiusa di raggio r e centro in $\underline{\omega}$:*** $\overline{B_r}(\underline{\omega})=\{y\in A^q_n |d(\underline{y},\underline{\omega})\le r\}$ $(< r-1)$
Tuttavia, visto che una palla aperta è una palla chiusa con una altro raggio nei naturali, si considera $\overline{B_r}(\underline{\omega})=B_{r+1}(\underline{\omega}),\forall\underline{\omega}\in A^n_q,\forall r>0$ (si useranno quindi solo palle chiuse)

>**DEFINIZIONE**
	Sia $S\in\mathbb{N}_{\ge1}$ e $C \subseteq A^n_q$ un codice.
	(i) Si dice che $C$ **segnala $\le$ S errori** (in mdd) se $\forall\underline{x}\in C$, se si modifica $\underline{x}$ in almeno 1 digit e al più $S$ digits, allora il vettore che si ottiene in $A^q_n$ non appartiene al codice, cioè $\overline{B_s} (\underline{x})\cap C = \{\underline{x}\},\forall\underline{x}\in C$
	(ii)