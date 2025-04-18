---
undefined: ""
Order: "5"
sticker: emoji//0035-fe0f-20e3
---
## Processi Aleatori
Un processo aleatorio logico $x(t)$ è un segnale il cui valore, ad ogni istante $t$, è una **variabile aleatoria**, le quali sono quindi ordinate dalla variabile del tempo $t$.
Il concetto di processo aleatorio quindi si base sul quello di variabile aleatoria e di esperimento aleatorio.
## Richiami di Probabilità
### Esperimento Aleatorio
- *Spazio Campine* $\Omega=\{\omega_{1},\omega_{2},\ldots\}$: Tutti i possibili risultati dell'esperimento.
- *Classe degli eventi* $A=\{w_{1},\omega_{2},\ldots\}$: Insieme di tutti i possibili sottoinsiemi (eventi) di $\Omega$ (include anche $\emptyset$).
- *Probabilità* $P{\{\cdot\}}, \ P\{\omega_{i}\}$: Probabilità di occorrenza dell'eventi.
### Distribuzioni di Probabilità di Variabili Aleatorie
Uba variabile aleatoria viene descritta in modo probabilistico tramite le seguenti funzioni:
- *Funzione Distribuzione di Probabilità (PDF)* di una v.a. $X$: $$P_{X}(x)=Prob\{X\le x\}$$ e ha le seguenti proprietà:
	- $0\le P_{X}(x)\le 1$
	- $\lim_{ x \to -\infty } P_{X}(x)=0$
	- $\lim_{ x \to +\infty }P_{X}(x)=1$
	- $Prob\{A<X\le B\}= P_{X}(B)-P_{X}(A)$ (dim ...)
- *Funzione Densità di Probabilità (pdf)* di una v.a. $X$: $$
p_{X}= \frac{dP_{X}(x)}{dx}$$ cioè $$
p_{X} = \lim_{ \Delta x \to 0 } \frac{P_{X}(x+\Delta x)-P_{X}(x)}{\Delta x}= \lim_{ \Delta x \to 0} \frac{Prob\{x<X\le X+\Delta x\}}{\Delta x}  
$$ (dim ...)
Queste funzioni si possono stimare nei seguenti modi:
- $P_{X}(x)\approx \frac{\#\{X\le x\}}{N}$
- $p_{X}(x)\approx \frac{\#\{x<X\le x+\Delta x\}}{N\cdot \Delta x}$

>[!example]+ Esempi di distribuzioni
>![[Pasted image 20250417153328.png|center|450]]
>![[Pasted image 20250417153358.png|center|450]]
>![[Pasted image 20250417153424.png|center|450]]
### Valore Atteso e Indici di una v.a.
Le funzioni PDF e pdf descrivono in modo completo il comportamento di una v.a.
Si può però ottenere una descrizione più semplificata attraverso gli *Indici*, ricavati attraverso l'operatore di *Media Statistica*:
$$
m_{X}=E[X]=\int_{\infty}^\infty x \cdotp_{X}(x)\ dx
$$
con le seguenti proprietà:
- Data $Y=g(X)$ $$
E[Y]=E[g(X)]=\int_{-\infty}^\infty g(X)p_{X}(x)\ dx \qquad E[Y]=\int_{-\infty}^\infty y\cdot p_{Y}(y)\ dy
$$
- Linearità: $$
E[\alpha g(X)+\beta h(X)]=\alpha E[g(x)]+\beta E[h(x)]
$$
Altri indici importanti di una v.a:
- *Potenza* (media di $X^2$) $$
P_{X}=E[X^2]=\int_{-\infty}^\infty x^2 p_{X}(x)\ dx
$$
- *Varianza* (media di $(X-m_{X})^2$), misura la dispersione dei risultati rispetto alla media (dim ...) $$
\sigma^2_{X}=E[(X-m_{X})^2]=\int _{-\infty}^\infty (x-m_{X})^2 p_{X}(x)\ dx
$$

> [!example]+ Esempio: Indici di distribuzioni comuni: 
> ![[Pasted image 20250417154651.png|center|425]]

### Sistemi di Variabili Aleatorie
Studio del comportamento di due v.a. correlate.
- *Funzione Distribuzione di Probabilità Congiunta* di due v.a. $X_{0}$,$X_{1}$: $$P_{{X_{0},X_{1}}}(x,y)= Prob\{X_{0}\le x,\ X_{1}<y\}$$ e ha le seguenti proprietà:
	- $0\le P_{X_{0},X_{1}}(x,y)\le 1$
	- $\forall x,y$ si ha:
		- $P_{X_{0},X_{1}}(-\infty, Y)= Prob\{X_{0}\le-\infty,X_{1}\le y\}=0$
		- $P_{X_{0},X_{1}}(x,-\infty)=Prob\{X_{0}\le x, X_{1}\le -\infty\}=0$
		- $P_{X_{0},X_{1}}(-\infty,-\infty)=0$
		- $P_{X_{0},X_{1}}(+\infty,+\infty)=1$
	- PDF marginali: $\forall x,y$ si ha:
		- $P_{X_{0}}(x)=P_{X_{0},X_{1}}(x,+\infty)=Prob\{X_{0}\le x, X_{1}\le+\infty\}$
		- $P_{X_{1}}(y)=P_{X_{1}}(+\infty,y)=Prob\{X_{0}\le +\infty, X_{1}<y \}$

- *Funzione Densità di Probabilità Congiunta* di due v.a. $X_{0}$,$X_{1}$ $$p_{X_{0},X_{1}}(x,y)=\frac{\partial^2 =P_{X_{0},X_{1}}(x,y)}{\partial x \partial y}=\lim_{\begin{aligned} &\Delta x\to_{0} \\ & \Delta y\to 0 \end{aligned} } \frac{Prob\{(x<X_{0}\le x+\Delta x)\}\ AND\  (y<X_{1}\le y+\Delta y)}{\Delta x \Delta y}$$ da cui risulta $$P_{X_{0},X_{1}}(x,y)=\int_{-\infty}^x \int_{-\infty}^y p_{X_{0},X_{1}}(\alpha,\beta)\ d\alpha d\beta$$con le seguenti proprietà:
	- $p_{X_{0},X_{1}}(x,y)\ge 0$
	- $\int_{-\infty}^\infty \int_{-\infty}^\infty p_{X_{0}X_{1}}(x,y)\ dxdy=1$
	- $X_{0}$ e $X_{1}$ sono statisticamente indipendenti se $$p_{X_{0}X_{1}}(x,y)=p_{X_{0}}(x)\cdot p_{X_{1}}(y)$$
Per descrivere il comportamento congiunto di due v.a. si possono definire degli indici:
- *Valore Atteso*: $E[Z]=E[g(X_{0},X_{1})]=\int_{-\infty}^\infty\int_{-\infty}^\infty g(x,y)p_{X_{0}X_{1}}(x,y)\ dxdy$
- *Correlazione*: $r_{X_{0},X_{1}}=E[X_{0}X_{1}]=\int_{-\infty}^\infty \int_{-\infty}^\infty xy\cdot p_{X_{0},X_{1}}(x.y)\ dxdy$
- *Covarianza*: $c_{X_{0}X_{1}}=E[(X_{0}-m_{X_{0}})(X_{1}-m_{X_{1}})]=\int_{-\infty}^\infty\int_{-\infty}^\infty (x-m_{X_{0}})(y-m_{X_{1}})p_{X_{0},X_{1}}(x,y)\ dx dy$
Si dimostra facilmente che $c_{X_{0}X_{1}}=r_{X_{0}X_{1}}-m_{X_{0}X_{1}}$
- Due v.a. sono incorrelate se $$E[X_{0}X_{1}]=E[X_{0}]E[X_{1}]$$da cui si ricava $c_{X_{0}X_{1}}$

---

## Processi Aleatori
 Un processo aleatorio può essere visto come il risultato di un esperimento aleatorio in cui lo spazio campione è formato da funzioni del tempo. Ad ogni realizzazione dell'esperimento viene osservata una funzione diversa non predicibile a priori.
 Un processo aleatorio a tempo continuo può anche essere visto come un segnale i cui campioni $X(t)$, ad un certo istante $t$, sono v.a. e la variabile temporale $t$ permette quindi di ordinare le v.a. osservate ad ogni istante.
 ![[Pasted image 20250417163707.png|center|500]]
 Per descrivere $X(t)$ è possibile usare le definizioni di PDF e pdf, aggiungendo però l'instante $t$ di riferimento
 - *Funzione Distribuzione di Probabilità (PDF)*:$$P_{X}(x;t)=Prob\{X(t)\le x\}$$ Si può anche definire con ==$p_{X(t)}(X)$==
 - *Funzione Densità di Probabilità (pdf):* $$p_{X}(x;t)= \frac{dP_{X}(x;t)}{dx}$$ Si può anche definire con ==$p_{X(t)}(X)$==
 
 Per i campioni di un processo aleatorio si possono definire degli indici statistici, detti *Statistiche del Primo Ordine*
 - *Media*: $m_{X(t)}=E[X(t)]=\int_{-\infty}^\infty xp_{X(T)}(x)\ dx$
 - *Potenza*: $P_{X(t)}=E[X^2(t)]=\int_{-\infty}^\infty x^2p_{X(t)}(x)\ dx$
 - *Varianza*: $\sigma^2_{X(t)}=E[(X(t)-m_{X(t)})^2]=\int_{-\infty}^\infty (x-m_{X(t)})^2p_{X(t)}(x)\ dx$
 
 Inoltre, si può dimostrare che vale
 $$
 \sigma^2_{X(t)}=P_{X(t)}-m^2_{X(t)}
 $$
In generale, questi indici dipendo da $t$.

Considerando congiuntamente una coppia di campioni del processo aleatorio $X(t_{1})$ e $X(t_{2})$, è possibile definire delle funzioni statistiche del secondo ordine:
- ==*Funzione di Autocorrelazione*==: $$R_{XX}(t_{1},t_{2})=\int_{-\infty}^\infty\int_{-\infty}^\infty x\ y \ p_{X(t_{1}),X(t_{2})}(X,Y)\ dxdy$$
- ==*Funzione di Autocovarianza*==: $$\begin{align}C_{XX}&=E[(X(t_{1})-m_{X(t_{1})})(X(t_{2})-m_{X(t_{2})})] \\ &=\int_{-\infty}^\infty\int_{-\infty}^\infty(x-m_{X(t_{1})})(y-m_{X(t_{2})})p_{X(t_{1}),X(t_{2})}(x,y)\ dxdy \end{align}$$
### Processi Stazionari
> [!gray] Processo Stazionario
>  Un processo aleatorio si dice *Stazionario* nella media, potenza o varianza) se la quantità $m_{X(t)}$, $P_{X(t)}$ o $\sigma^2_{X(t)}$ è costante, cioè quindi non dipende dalla variabile temporale $t$.
Un processo aleatorio si dice *Stazionario*  nella funzione di autocorrelazione se la funzione $R_{XX}(t_{1},t_{2})$ dipende solo da $t_{1}-t_{2}$ (distanza o lag tra i campioni), e non $t_{1}$, $t_{2}$ singolarmente.
Si può dimostrare che $$C_{XX}(t_{1},t_{2})=R_{XX}(t_{1},t_{2})-m_{X(t_{1})}m_{X(t_{2})}$$

> [!gray] Processo Aleatorio in Senso Stretto
>  Un processo aleatorio è detto *Stazionario in Senso Stretto* se le pdf dei campioni e le pdf congiunte non sono alterate da una traslazione solidale nel tempo applicata agli indici temporali dei campioni, quindi deve risultare $$p_{X(t)}(X)=p_{X(t+\Delta t)}(X)$$
>(Richiede dunque che le funzioni pdf del processo siano invarianti rispetto a una traslazione rigida degli istanti temporali)
>  Per ogni scelta di $\Delta t$, le pdf dei campioni $X(t)$ sono quindi uguali per ogni $t$. Di conseguenza le statistiche del primo ordine (media, potenza, varianza), derivate della pdf, sono costanti nel tempo.
>  Deve risultare inoltre anche $$p_{X(t_{1}),X(t_{2})}(x,y)=p_{X(t_{1}+\Delta t),X(t_{2}+\Delta t)}(x,y)$$
>  Si può quindi dedurre che la funzione di autocorrelazione del processo è una funzione solo della distanza $t_{1}-t_{2}$, e di conseguenza le statistiche del secondo ordine (autocorrelazione, autocovarianza) devono dipendere solo da $t_{1}-t_{2}$.
>  La proprietà di indipendenza della pdf da una traslazione nel tempo degli indici temporali deve essere verificata anche per ordini superiori (per esempio nel caso di tre campioni del processo si ha $p_{X(t_{1}),X(t_{2}),X(t_{3})}(X,Y,Z)=p_{X(t_{1}+\Delta t)}p_{X(t_{2}+\Delta t)}p_{X(t_{3}+\Delta t)}$).

La proprietà di stazionarietà in senso stretto si basa sulle funzioni di densità congiunte per qualsiasi ordine ed è complessa da verificare. Però molte proprietà dei processi aleatori si basano su ipotesi molto meno forti.
Solitamente nelle applicazioni si considera una definizione di stazionarietà molto meno restrittiva e più semplice da verificare.

> [!gray] Processo Stazionario in Senso Lato
> Un processo è detto *Stazionario in Senso Lato* (WSS, Wide Sense Stationary) se soddisfa le seguenti condizioni: $$\begin{align}
> &\text{Media: }E[X(t)]=m_{X}=\text{costante} \\
> &\text{Autocorrelazione: } R_{XX}(t,t+\tau)=R_{XX}(\tau) \text{ funzione solo di }\tau
> \end{align}$$
> Questa definizione di stazionarietà richiede solo due statistiche semplificate (una del primo ordine e una del secondo) e non richiede proprietà di invarianza della pdf.
> 

> [!example]+ Esempio: Processo Amronico
> Sia $X(t)=A\cos(2\pi f_{0}t+\phi)$, con $\phi \sim \mathcal U(-\pi,\pi)$, cioè v.a. uniformemente distribuita in $[-\pi,\pi]$, con $p(\phi)= \frac{1}{2\pi}I_{{[-\pi,\pi]}}(\phi)$, dove $I_{\mathcal A}(x)$ è la funzione indicatrice (su slide) dell'intervallo $\mathcal A$
> - Media di un processo armonico: $$\begin{align}
>  E[X(t)]&=E[A\cos(2\pi f_{0}t+\phi)]=\int_{-\infty}^\infty A\cos(2\pi f_{0}t+\phi)p(\phi)\ d\phi \\
> &=\int_{-\pi}^\pi A\cos(2\pi f_{0}t+\phi) \frac{1}{2\pi}\ d\phi=0
> \end{align}$$
> - Autocorrelazione di un processop armonico: $$\begin{align}
> R_{XX}(t,t+\tau)&=E[X(t)X(t+\tau)]=E[A\cos(2\pi t_{0}t+\phi)A\cos( 2\pi f_{0}(t+\tau)+\phi)]= \\
> &=\int_{-\pi}^\pi A^2 \frac{1}{2}[\cos (2\pi f_{0}(2t+\tau)+2\phi)+\cos(2\pi f_{0}\tau)] \frac{1}{2\pi}\ d\phi= \\
> &= \frac{A^2}{2}\cos(2\pi f_{0}\tau)=R_{XX}(\tau)
> \end{align}$$
> La potenza del processo armonico è $R_{XX}(0)= \frac{A^2}{2}$.
> Poiché la media è costante e la funzione di autocorrelazione $R_{XX}(t,t+\tau)$ dipende solo da $\tau$ (e non da $t$), il processo armonico è stazionario in senso lato.

### Processo Ergodico
Nelle applicazione, spesso è possibile osservare solo un'unica realizzazione di un processo aleatorio. Il calcolo delle medie di insieme basato sulla conoscenza della densità di probabilità non è quindi praticabile.
Un *Processo Ergodico* è caratterizzato dalla possibilità di  poter calcolare alcuni indici tramite medie temporali. 
Da una realizzazione $X(t)$ è possibile calolcare le seg
... Slide 5