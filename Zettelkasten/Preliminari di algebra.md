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

[[Preliminari di algebra#^80205d|(1.)]] [[Preliminari di algebra#^80205d|(2.)]]  È l'unico elemento neutro di $+_R\ (\cdot_R)$: si suppone che $0'_R\in R$ sia un altro elemento neutro di $+_R$ cioè $x+_R0'_R=x, \forall x\in R$, se $\ x=0_R \Rightarrow 0_r=0_R+_R0_R'$ , ma $0_R$ è per definizione l'elemento neutro di $+_R$. Quindi tutti gli elementi neutri sono comunque uguali a $0_R$.
[[Preliminari di algebra#^80205d|(4.)]] $\forall x\in R \ \exists!$ l'opposto di $x$: siano $y,y'\in R:x+_Ry=x+_Ry'=0_R$, allora $y=y+_R0_R=x+_Ry+_Ry'=0_R+_Ry'=y'$

>**ESEMPI DI ANELLI COMMUTATIVI**
	$(\mathbb{R}, \ +,\ \cdot, \ 0, \ 1)$    $(\mathbb{C}, \ +, \ \cdot,\ 1)$    $(\frac{\mathbb{Z}}{2}, \ +, \ \cdot, \ 0, \ 1)$ $(M_{n,n}(\mathbb{R} \ o \ \mathbb{C}), \ +, \begin{bmatrix} 0 & \cdots & 0 \\ \vdots  & \ddots & \vdots \\0 & \cdots & 0 \end{bmatrix}, \begin{bmatrix} 1 & \cdots & 1 \\ \vdots  & \ddots & \vdots \\1 & \cdots & 1 \end{bmatrix})$ (anello non commutativo se $n>1$)

>**ANELLI DI POLINOMI**
	$R[x]:=\{a_0+a_1x_1+\ldots+a_nx^n|a_0,a_1,\ldots,a_n\in R,n\ge1 \ qualsiasi \}$
	$+_{R[x]}:=a_0+_Rb_0+(a_1+_Rb_1)x+\ldots+(a_n+_Rb_n)x^n, \ i\in\{0,\ldots,n\}, \ a_i,b_i\in R$ 
	$\cdot_{R[x]}:=c_0+\ldots+c_kx^k,c_k = \sum_{i=j=k}a_i\cdot_Rb_j, \ i,j\in\{0,\ldots,n\},\  a_i,b_i\in R$
	$0_{R[x]}:=0 \ (=a_0+a_1x+\ldots+a_nx^n,a_i=0\in R)$
	$1_{R[x]}:=1\in R \ (a_0=1,a_i=0\ \forall i>0)$

$(\mathbb{R}[x]), \ +_\mathbb{R}[x],  \ \cdot_\mathbb{R}[x], \ 0_\mathbb{R}[x], \  1_\mathbb{R}[x])$ $(\mathbb{C}[x]), \ +_\mathbb{C}[x],  \ \cdot_\mathbb{C}[x], \ 0_\mathbb{C}[x], \  1_\mathbb{C}[x])$ $(\mathbb{Z}[x]), \ +_\mathbb{Z}[x],  \ \cdot_\mathbb{Z}[x], \ 0_\mathbb{Z}[x], \  1_\mathbb{Z}[x])$  sono anelli commutativi.
$R[x,y]=\{\sum\limits^n_{i=0}\sum\limits^m_{j=0}a_{ij}x^iy^j|a_{ij}\in R,\ n,m\ge 0\}$ ha $+_{R[x,y]}, \ \cdot_{R[x,y]}, \ 0_{R[x,y]},\ 1_{R[x,y]}$ con cui diventa anello commutativo.

$S$ insieme, $F_m(S,R):=\{f:S\rightarrow R| f\ applicazione \ tra \ insiemi\}$ 
$+_{F_m(S,R)}:=F_m(S,R)\times F_m(S,R)\rightarrow F_m(S,R)$
	$f,g\in F_m(S,R),\ f+_{F_m(S,R)}g \rightarrow F_m(S,R), \ s\in S \mapsto f(s)+_R g(s)$
$\cdot_{F_m(S,R)}:=F_m(S,R)\times F_m(S,R)\rightarrow F_m(S,R)$ 
	$f,g\in F_m(S,R),\ f\cdot_{F_m(S,R)}g \rightarrow F_m(S,R), \ s\in S \mapsto f(s)\cdot_R g(s)$
$0_{F_m(S,R)}:=S\rightarrow R, \ s\in S \mapsto 0_r$
$1_{F_m(S,R)}:=S\rightarrow R, \ s\in S \mapsto 1_r$

>**DEFINIZIONE (Morfismo tra anelli commutativi)**
	Siano $(R,\ +_R,\ \cdot_R,\ 0_R,\ 1_R)$ e $(S,\ +_S,\ \cdot_S,\ 0_S,\ 1_S)$ anelli commutativi, un morfismo tra anelli $R\rightarrow S$ è un'applicazione di insieme $R\overset{f}{\rightarrow}S$ (fra insiemi soggiacenti) tale che:
		1. $f(1_R) = 1_S$
		2. $f(r+_R r') = f(r)+_Sf(r'),\ \forall r,r'\in R$
		3. $f(0_R) = 0_S$
		4. $f(r\cdot r')=f(r)\cdot_S f(r')$

>**ESEMPIO (Morfismi tra anelli)**
	$\mathbb{Z}\overset{i}\hookrightarrow\mathbb{Q}$
	$\mathbb{R}\rightarrow \mathbb{R}[x],\ \alpha\in \mathbb{R} \mapsto\alpha$
	$\mathbb{R}[x]\rightarrow \mathbb{R}, \ a_0+a_1x+\ldots+a_nx^n=f(x)\in \mathbb{R}[x]\mapsto a_0=f(a_0)\in \mathbb{R}$	
		${(\sum\limits^n_{j=0}a_jx^j\ldots\sum\limits^n_{j=0})}_{deg\ 0}$ 
	$\mathbb{Z}\hookrightarrow\mathbb{Q}\hookrightarrow \mathbb{R} \hookrightarrow \mathbb{C}$  (tre morfismi)

Più in generale, se $R$ è un anello commutativo qualsiasi, $R\rightarrow R[x] \rightarrow R \ (a\in R\mapsto a,\ \sum^n_{i=0}a_ix^i\mapsto a_0)$ sono entrambi morfismi di anelli.

>**OSSERVAZIONE**
	Se $(R,\ +_R,\ \cdot_R,\ 0_R,\ 1_R)$ è una anello commutativo allora anche $R[x]=\{a_0+a_1x+\ldots+a_nx^n|n\ge1,a_i\in R \ \forall i\}$(anello di polinomi con coefficentienti in $R$).

>**DEFINIZIONE (Ideale)**
	Sia $R$ una anello commutativo, un sottoinsieme $I\subseteq R$ si dice ideale (in $R$) se:
	(i) $I\neq \emptyset$
	(ii) $I$ è chiuso rispetto alla somma, cioè $r,r'\in I \Rightarrow r \cdot_R r' \in I$
	(iii) $I$ è assorbente, cioè $r\in I,\ r'\in R \Rightarrow r \cdot_R r' \in I$

^d46f00

>**OSSERVAZIONE**
	1.  Se $R$ è un qualsiasi anello commutativo, allora $I=R$ e$I=\{0_R\}$ sono ideali in $R$ ($x\cdot_R 0_R = 0_R\in I$).
	2. Sia $I\underset{ideale}\subseteq R$ tale che $1_R\in I$, allora $I=R$ ($\forall x \in R, x\cdot_R 1_R=x\in I$). Se $1_R\notin I$, allora $I$ è un ideale proprio.
	3. Se $R$ è un anello commutativo, $r_0\in R$, si definisce $(r_0):=\{r\cdot_Rr_0|r\in R\}\subseteq R$
		$r_0\in(r_0)$ [[Preliminari di algebra#^d46f00|(i)]], $(r_0)$ è chiuso rispetto alla somma [[Preliminari di algebra#^d46f00|(ii)]], sia $r\cdot_R r_0(\in(r_0))$ e $r'\in R$ , $r'\cdot_R(r\cdot_R r_0)\overset{associativa}=\underset{(\in R)}{(r'\cdot_Rr)}\cdot_Rr_0\in R$ [[Preliminari di algebra#^d46f00|(iii)]]
	4. Sia $I\underset{ideale}\subseteq R$, allora $r\in I\Rightarrow -r\in I$ (opposto rispetto a $+_R$). Infatti: $(-1_R)\cdot_Rr=-r\in I$ per assorbenza.
	5. Sia $I\underset{ideale}\subseteq R\Rightarrow 0_R\in I$ (da [[Preliminari di algebra#^90c038|(4.)]] e [[Preliminari di algebra#^d46f00|(i)]])

>**PROPOSIZIONE**
	Sia $\phi:R\rightarrow S$ un morfismo di anelli commutativi. Allora $Ker(\phi)\underset{ideale}\subseteq R$

***Notazione:** Se $f:A\rightarrow B$ è un applicazione di insiemi: $\underset{sottoinsiemi}{B_0\subseteq B \ A_0\subseteq A}\ , \ f^{-1}(B_0):=\{a\in A|f(a)\in B\}\subseteq A,f(A_0):=\{f(a_0)|a_0\in A_0\}$

>**DIMOSTRAZIONE**
	$Ker(\phi)\neq 0 \ (0_R \in Ker(\phi):\phi(0_R)=0_S)$. $r,r'\in Ker(\phi)\Rightarrow \phi(r+_Rr')=\phi(r)+_S\phi(r')=0_S+_S+0_S\Rightarrow r+_Rr'\in Ker(\phi)$ .
	$Ker(\psi)\subseteq R$ è assorbente rispetto a $\cdot_R$ , $r\in Ker(\phi),r'\in R\Rightarrow r\cdot_R r'\in Ker(\phi)$, ma $\phi(r\cdot_Rr')\overset{\phi\text{ è un morfismo di anelli}}=\phi(r)\cdot_S\phi(r')=0_S \Rightarrow Ker(\phi)$ è assorbente

>**RICHIAMI SU RELAZIONI DI EQUIVALENZA**
	Sia $A$ un insieme, una relazione di equivalenza $\mathcal{R}$ su $A$ è un sottoinsieme su $A\times A$ ($a\sim a'$ se $(a,a')\in \mathcal{R}$) tale che:
		1. $a\sim_\mathcal{R}$ a (proprietà riflessiva)
		2. $a\sim_{\mathcal{R}}a'\Rightarrow a'\sim_{\mathcal{R}}a$ (proprietà simmetrica)
		3. $a\sim_{\mathcal{R}}a',a'\sim_{\mathcal{R}}a''\Rightarrow a\sim_{\mathcal{R}}a''$ (proprietà transitiva $\left.\begin{matrix}{(a,a')\in\mathcal{R}} \\{(a',a'')\in\mathcal{R}}\end{matrix}\right\}\Rightarrow(a,a'')\in\mathcal{R}$)

Sia $A$ insieme, $\mathcal{R}$ relazione di equivalenza su $A$. Si costruisce l'**insieme quoziente**  $\,^{A}\!/\!_{\sim\mathcal{R}}$ o$\,^{A}\!/\!_{\sim\mathcal{R}}$.
Si vogliono identificare tutti gli elementi in $A$ che sono in $\mathcal{R}$-relazione tra loro.
Si definisce per $a\in A: [a]_{\sim\mathcal{R}}:=\{a'\in A|a\sim_{\mathcal{R}}a'\}\subseteq A$ (**classe di $\mathcal{R}$-eq. di $a$**).

>**ESEMPIO**
	$[a_0]_{\sim\mathcal{R}}$ e $[a_1]_{\sim\mathcal{R}}$ , $a_0,a_1\in A$ sono insiemi di $a$ disgiunti o coincidenti.
	Sia $a\in[a_0]_{\sim\mathcal{R}}\cap[a_1]_{\sim\mathcal{R}}$ allora $\left.\begin{matrix} a_0\sim_{\mathcal{R}} a \\ a\sim_{\mathcal{R}} a_1 \end{matrix}\right\}\Rightarrow a_0\sim_{\mathcal{R}}a_1\Rightarrow[a_0]_{\sim\mathcal{R}}=[a_1]_{\sim\mathcal{R}}$ 
	$\{[a]|a\in A\}\Rightarrow$ è una partizione di $A$.

>**DEFINIZIONE**
	L'insieme i cui elementi sono tutte le classi di $\mathcal{R}$-equivalenza $[a]_{\sim\mathcal{R}}$, $a\in A$ si dice **insieme quoziente di $A$ secondo $\mathcal{R}$** e si indica con $\,^{A}\!/\!_{\sim\mathcal{R}}$ oppure $\,^{A}\!/\!_{\mathcal{R}}$ (cioè $\,^{A}\!/\!_{\sim\mathcal{R}}$ ha come elementi i sottoinsiemi di $A:[a]_{\sim\mathcal{R}}(a\in A):=\{a'\in A \ t.c. \ a'\sim a\}(\subseteq A)$, classe di $\mathcal{R}$-equivalenza per $A$).
	L'applicazione $A\overset{\pi}\rightarrow\,^{A}\!/\!_{\mathcal{R}}:a\mapsto[a]_{\mathcal{R}}$ si dice **applicazione (o mappa) quoziente**

>**DIMOSTRAZIONE**
	$[a]_\sim = [a']_\sim \iff a\sim a'$.
		Siano $a,\overline{a}\in A$ per ipotesi. Si sa che $[a]_\sim = [a']_\sim$, quindi $\{s'\in S \ t.c. \ s'\sim s\} = \{s''\in S \ t.c. \ s''\sim\overline{s}\}$. Si sa però che il primo insieme è contenuto in $S$ perché in relazione con $s$, ma si può dire lo stesso anche per il secondo insieme , quindi $s\sim[\overline{s}]_\sim$ cioè $s\sim\overline{s}$. Per la proprietà transitiva $s\sim s'\Rightarrow[s]_\sim=[s']_\sim$
	$[s]_\sim[s']_\sim = \emptyset$ se $s\nsim s'$
		Sia $s\nsim s'$. Se $\exists t \in S \ t.c. \ t \in[s]_\sim\cap[s']_\sim$. Allora $t\sim s$ e $t\sim s'$ per definizione di classe di equivalenza. Da questo deriva il fatto che $s\sim s'$, ma questo è un assurdo per le ipotesi, quindi $\nexists t\in[s]_\sim\cap[s']_\sim\Rightarrow [s]_\sim\cap[s']_\sim = \emptyset$	
	$\underset{s\in S}\cup = S$
	
Sia $I\underset{ideale}\subseteq R$ anello commutativo. Si definsisce $\sim_I$ relazione su $R$ (cioè $\mathcal{R}\subseteq R\times R$): $r,r'\in R, \ r\sim_I r'$ se (**DEF**) $r-_R r'\in I$. Facile verificare che: $I\underset{ideale}\subseteq R\Rightarrow\sim_I$ è una relazione di equivalenza su $R$, quindi si può considerare l'insieme quoziente $\,^{R}\!/\!_{\sim_I}$ (o $\,^{R}\!/\!_{I}:=\{[r]_{\sim_I} \ t.c.r\in R\}$ dove$[r]_{\sim_I}=\{r'\in  \ t.c. r'-r\in I\}$ e $[r]_{\sim_I}\subseteq R$).
Su tale insieme si definiscono le operazioni ch lo  rendono un anello commutativo:
	$+_{\,^{R}\!/\!_{\sim_I}}:\,^{R}\!/\!_{\sim_I}\times\,^{R}\!/\!_{\sim_I}\rightarrow\,^{R}\!/\!_{\sim_I } \ , \ ([r]_{\sim_I},[r]_{\sim_I})\mapsto[r+_R r']_{\sim_I}$
		Si deve verificare che se $[r_1]=[r]$ e $[r_1'] = [r']$ (dove $r_1$ è un altro rappresentante di $[r]$ e $[r_1']$ è un altro rappresentate di $[r']$). Allora $[r+_Rr']\overset{tesi}=[r_1+_Rr_1']$.
		Siccome $[r_1]=[r]\Rightarrow(r_1-r)\in I$, analogamente$[r_1+_Rr_1']\Rightarrow(r_1'-_Rr')\in I$ (stesse classi di equivalenza).
		Si calcola $(r+_Rr')-(r_1+_Rr_1')=\underset{\in I}{(r-_Rr_1)}+\underset{\in I}{(r'-_Rr_1')}\in I$. Poiché $I$ è chiuso rispetto alla  somma, $+_{\,^{R}\!/\!_{\sim_I}}$ è ben definito.
	$\cdot_{\,^{R}\!/\!_{\sim_I}}:\,^{R}\!/\!_{\sim_I}\times\,^{R}\!/\!_{\sim_I}\rightarrow\,^{R}\!/\!_{\sim_I} \ , \ ([r]_{\sim_I},[r]_{\sim_I})\mapsto[r\cdot_R r']_{\sim_I}$ 
		Si deve dimostrare che $r_1\cdot_Rr_1'-r\cdot_Rr'\in R$. $r'-r=x, \ r_1'-r'=y$, si ottiene $r_1=r+x,\ r_1'=r'+y$. Sostituendo si ottiene $r_1\cdot_Rr_1'=(r+x)(r'+y)-rr'=rr'+ry+xr'-rr'\in I$, per la proprietà assorbente degli ideali $r$ e $r'\in I$, quindi $\cdot_{\,^{R}\!/\!_{\sim_I}}$ è ben definito.
Dunque $(+_{\,^{R}\!/\!_{\sim_I}}, \ \cdot_{\,^{R}\!/\!_{\sim_I}}, \ [0_R]_{\sim_I}, \ [1_R]_{\sim_I})$ è un anello commutativo.

>**OSSERVAZIONE**
	$R\overset{\pi}{\rightarrow}\,^{R}\!/\!_I \ , \ r\mapsto[r]_{\sim_I}$, $\pi$ è un morfismo di anelli

>**ESEMPIO**
	Si considera $R=\mathbb{Z}, \ n\in \mathbb{Z}$ e l'ideale generato da $n:I=(n)=\{k\cdot n| k\in\mathbb{Z}\},n\in\mathbb{Z}_{>0}$. Si vuole descrivere $\,^{\mathbb{Z}}\!/\!_{(n)}$. Si afferma che $\exists$ una biezione $\,^{\mathbb{Z}}\!/\!_{(n)}\overset{\sim}{\underset{\phi}{\rightarrow}}\{0,1,\ldots,n-1\}$.
	Sia $[K]_{mod \ n}\in \,^{\mathbb{Z}}\!/\!_{(n)}$ con $k\ge 0$ senza perdita di generallità.
		- Se $n=0, \,^{\mathbb{Z}}\!/\!_{(n=0)}\simeq\mathbb{Z}$ biezione
		- Se $0\le k\le n$ si definisce $\phi([k]_{mod \ n})=k\in\{0,1,\ldots,n-1\}$ 
		- Se $k\ge n$ si usa l'algoritmo euclideo di divisione con resto: $k=q\cdot n+r, \ 0\le r\le n$ e si definisce $\phi([k])=r\in\{0,1,\ldots,n-1\}$ 
	Questo definisce $\phi:\,^{\mathbb{Z}}\!/\!_{(n)}\rightarrow\{0,1,\ldots,n-1\}$ con inversa $\{0,1,\ldots,n-1\}\overset{\phi^{-1}}\rightarrow\,^{\mathbb{Z}}\!/\!_{(n)} \ (l\mapsto [l]_{mod \ n}) \ , \ n\underset{ideale}\subseteq\mathbb{Z}\rightarrow\,^{\mathbb{Z}}\!/\!_{(n)}$ anello quoziente.
	$\,^{\mathbb{Z}}\!/\!_{(n)}=\{[0]_{\sim_I}, \ [1]_{\sim_I}, \ldots, [n-1]_{\sim_I}\}=\{0,1,\ldots,n-1\}$

Sia $I\underset{ideale}\subseteq R$, si vuole poter descrivere $Ideali(\,^{R}\!/\!_{I})$ in termini di $Ideali(R)$.

>**PROPOSIZIONE** 
	Sia $R$ un anello commutativo, $I\underset{ideale}\subseteq R$. Allora esiste una biezione: $Ideali(\,^{R}\!/\!_{I})\overset{\sim}{\underset{\phi}{\rightarrow}}\{Ideali \ J\underset{ideale}\subseteq R|J\supseteq I\}$ tale che $\left\{\begin{matrix} \phi(0_{\,^{R}\!/\!_{I}})=I \\ \phi({\,^{R}\!/\!_{I}})=R\end{matrix}\right.$

