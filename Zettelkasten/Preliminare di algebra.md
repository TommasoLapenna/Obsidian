>**DEFINIZIONE (Anello)** 
	Struttura: $(R,\ +_R,\ \cdot_R,\ 0_R,\ 1_R)$
		$R:$ insieme
		$+_R:R\times R \overset{+_R}{\longrightarrow}R$ (somma in $R$)
		$\cdot_R:R\times R \overset{\cdot_R}{\longrightarrow}R$ (prodotto in $R$)
		$0_R\in R$
		$1_R\in R$
		- $(R, \ +_R, \ 0_R)$ è un *gruppo commutativo/alebiano*, ovvero dove valgono la proprietà associativa e simmetrica, $0_R$ è l'elemento neutro della somma e $\forall x\in R\ \exists -x \ t.c. \ x+_R-x=0$
		- $(R,\ ._R,\ 1_R)$ è un *gruppo unitario* ovvero vale la proprietà associativa e $1_R$ è l'elemento neutro del prodotto.
	Una struttura si dice **anello** se verifica le seguenti proprietà:
		1. $x+_R 0_R=x,\ \forall\in R$ ($0_R$ elemento neutro rispetto alla somma)
		2. $x+_R(y+_Rz)=(x+_Ry)+_Rz$ (proprietà associativa di $+_R$)
		3. $x+_Ry = y+_Rx$ (commutatività di $R$)
		4. $\forall x\in R,\exists y\in \ t.c. \ x+_Ry=0$ (tale elemento si dice opposto di $x$ e si indica con $-x$, esistenza dell'opposto)
	Le strutture $(R, \ +_R, \ 0_R)$ e $(R,\ ._R,\ 1_R)$ sono compatibili, cioè $(x,\ +_R y)\cdot_R z=x\cdot_R z+_R y\cdot_R z \ ; \ z\cdot_R(x+_R y)=z\cdot_R x +_R z\cdot_R \ , \ \forall x,y,z\in R$  (distributività sui due lati)
	La somma è sempre commutativa, se lo è anche il prodotto allora si dice che la struttura è un **anello commutativo**

^80205d

[[Preliminare di algebra#^80205d|(1.)]] [[Preliminare di algebra#^80205d|(2.)]]  È l'unico elemento neutro di $+_R\ (\cdot_R)$: si suppone che $0'_R\in R$ sia un altro elemento neutro di $+_R$ cioè $x+_R0'_R=x, \forall x\in R$, se $\ x=0_R \Rightarrow 0_r=0_R+_R0_R'$ , ma $0_R$ è per definizione l'elemento neutro di $+_R$. Quindi tutti gli elementi neutri sono comunque uguali a $0_R$.
[[Preliminare di algebra#^80205d|(4.)]] $\forall x\in R \ \exists!$ l'opposto di $x$: siano $y,y'\in R:x+_Ry=x+_Ry'=0_R$, allora $y=y+_R0_R=x+_Ry+_Ry'=0_R+_Ry'=y'$

>**ESEMPI DI ANELLI COMMUTATIVI**
	$(\mathbb{R}, \ +,\ \cdot, \ 0, \ 1)$
	