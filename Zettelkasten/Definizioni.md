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
	- $d(\underline{x},\underline{y}) \le d(\underline{x},\underline{z})+d(\underline{z},\underline{y}),\forall\underline{x},\underline{y},\underline{z}\in A^q_n$ (disuguaglianza triangolare)

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
	1. Si dice che $C$ **segnala $\le$ S errori** (in mdd) se $\forall\underline{x}\in C$, se si modifica $\underline{x}$ in almeno 1 digit e al più $S$ digits, allora il vettore che si ottiene in $A^q_n$ non appartiene al codice, cioè $\overline{B_s} (\underline{x})\cap C = \{\underline{x}\},\forall\underline{x}\in C$
	2. Si dice che **corregge $\le$ S errori** (a mdd) se : { $\underline{\omega}\in A^n_q\Rightarrow\exists!\underline{x}\in C:\underline{\omega}\in \overline{B_s}(\underline{x})$ , $d(\underline{\omega},C)\iff d(\underline{\omega},\underline{x})$ }

^ddd543

>**OSSERVAZIONE**
	Si noti che se $d(\underline{\omega},C)\le S$, si sa che se $\exists\underline{x'}\in C$ t.c. $\underline{\omega}\in\overline{B_s}(\underline{x'})$. C corregge errori se tale $\underline{x'}$ è unico.
	//immagine palle

>**PROPOSIZIONE**
	Sia $C\subseteq A^q_n$:
	1. $C$ segnala $\le$ $S$ errori $\iff$ $d(C)\ge$ $S+1$ 
	2. $C$ corregge $\le$ $S$ errori $\iff$ $d(C)\ge$ $2S+1$  

>**DIMOSTRAZIONE**
	1. Da [[Definizioni#^ddd543|(1.)]], è ovvio che se $C$ segnala $\le S$ errori, allora $d(\underline{x},\underline{x'})>S,\forall\underline{x},\underline{x'}\in C\Rightarrow d(C) = S+1$ $(>S)$. Viceversa: ovvio.
	2. $C$ corregge $\le S$ errori $\Rightarrow d(C)>2S$ $(\ge2S+1)$, viceversa $d(C)\ge 2S+1$ e sia per assurdo $\underline{\omega}\in A^q_n,\ \underline{\omega}\in\overline{B_s}(\underline{x})\cap\overline{B_s}(\underline{x'})\in C\longrightarrow$ ASSURDO: la distanza tra le palle non sarebbe $2S$.

>**DIMOSTRAZIONE (Estesa)**
	1. $\Leftarrow)$ Sia $d(C)\ge S+1.\ \exists\underline{x},\underline{x'}\in C \ t.c \ \underline{x'}\in\overline{B_s}(\underline{x})\Rightarrow d(\underline{x},\underline{x'})\le S\rightarrow$ contraddizione dell'ipotesi, dunque c segnala $S+1$ errori.
	1. $\Rightarrow)$ Sia $\overline{B_s}(\underline{x})\cap C=\{\underline{x}\},\ \forall\underline{x}\in C$, ovvero $C$ segnala$\le S$ errori. Allora $d(\underline{x},\underline{x'})>S, \ \forall\underline{x},\underline{x'}\in C\Rightarrow d(C)=S$.
	2. $\Rightarrow)$ Se corregge $\le S$ error, allora si dimostra che $\overline{B_s}(\underline{x})\cap\overline{B_s}(\underline{x'}) = \emptyset, \ \forall\underline{x},\underline{x'}\in C, \ \underline{x}\neq\underline{x'}$. Per assurdo, se $\exists\underline{\omega}\in\overline{B_s}(\underline{x})\cap\overline{B_s}(\underline{x'})\Rightarrow d(\underline{\omega}, C)\le S\Rightarrow\underline{x} = \underline{x'}$ , impossibile visto che si è supposto $\underline{x}\neq\underline{x'}$.
	2. $\Leftarrow$) Sia $d(C)\ge 2S+1, \ \underline{\omega}\in A^n_q \ t.c. \ d(\underline{\omega}, C)\le S$ e si suppone che $\exists\underline{x}\neq\underline{x'},\underline{x'}\in C \ t.c. \ \underline{\omega}\in\overline{B_s}(\underline{x})\cap\overline{B_s}(\underline{x'})$. Allora$d(\underline{x},\underline{x'})\le d(\underline{x},\underline{\omega})+d(\underline{\omega},\underline{x'})\le 2S$ perché è stato supposto che $d(C)\ge 2S+1$.

>**DEFINIZIONE (Potere correttivo di un codice)**
	Sia $C\subseteq A^q_n, \ e(C):=\left\lfloor  \frac{d(C+1)}{2}  \right\rfloor$ è il massimo numero di errori che $C$ può correggere (a mdd). A parte i bounds, questo si può dire per codici arbitrari $C\in A^q_n$.

Per definire un codice di solito si dice che C è un $(n, M,d)_q-$codice, dove $n$ è la lunghezza delle parole del codice in $C$, $M$ è la taglia del codice $(M=\#(C))$, $d$ è $d(C)$ e $q$ è la taglia dell'alfabeto.	