---
order: "3"
sticker: emoji//0033-fe0f-20e3
---
Tags: [[Fisica I]] [[Old Vault/Indexes/University]]

- [[#Dinamica del Punto Materiale|Dinamica del Punto Materiale]]
	- [[#Dinamica del Punto Materiale#Principio di Inerzia|Principio di Inerzia]]
	- [[#Dinamica del Punto Materiale#Leggi di Newton|Leggi di Newton]]
		- [[#Leggi di Newton#1° Legge di Newton|1° Legge di Newton]]
		- [[#Leggi di Newton#2° Legge di Newton|2° Legge di Newton]]
		- [[#Leggi di Newton#3° Legge di Newton|3° Legge di Newton]]
	- [[#Dinamica del Punto Materiale#Quantità di Moto, Impulso|Quantità di Moto, Impulso]]
		- [[#Quantità di Moto, Impulso#Teorema dell'Impulso|Teorema dell'Impulso]]
	- [[#Dinamica del Punto Materiale#Risultante delle Forze|Risultante delle Forze]]
		- [[#Risultante delle Forze#Equilibrio Statico|Equilibrio Statico]]
	- [[#Dinamica del Punto Materiale#Tipi di Moto|Tipi di Moto]]
		- [[#Tipi di Moto#Moto Curvilineo|Moto Curvilineo]]
	- [[#Dinamica del Punto Materiale#Forza Peso|Forza Peso]]
	- [[#Dinamica del Punto Materiale#Reazione Vincolare|Reazione Vincolare]]
		- [[#Reazione Vincolare#Sensazione di Peso|Sensazione di Peso]]
	- [[#Dinamica del Punto Materiale#Forza di Attrito Radente|Forza di Attrito Radente]]
		- [[#Forza di Attrito Radente#Forza di Attrito Statica|Forza di Attrito Statica]]
		- [[#Forza di Attrito Radente#Forza di Attrito Dinamica|Forza di Attrito Dinamica]]
	- [[#Dinamica del Punto Materiale#Piano Inclinato|Piano Inclinato]]
	- [[#Dinamica del Punto Materiale#Forza di Attrito Viscoso|Forza di Attrito Viscoso]]
	- [[#Dinamica del Punto Materiale#Tensione dei Fili|Tensione dei Fili]]
	- [[#Dinamica del Punto Materiale#Forza Elastica|Forza Elastica]]
	- [[#Dinamica del Punto Materiale#Pendolo Semplice|Pendolo Semplice]]


# Dinamica del Punto Materiale
La parte della *Dinamica* si occupa di studiare le cause fisiche che mettono in moto un punto (e anche lo stato di equilibrio). Viene usato il concetto di *Forza*, ovvero la grandezza che esprime e misura l'interazione tra sistemi di misura
## Principio di Inerzia
Secondo il *Principio di Inerzia*, un corpo non soggetto a forze non subisce cambiamenti di velocità. Da sottolineare che l'assenza di forze non implica la quiete, ma che la velocità non varia.
Quindi in caso di moto, esso sarà rettilineo uniforme e un'accelerazione indica la presenza di una forza. Un esempio è il moto circolare uniforme: la velocità, nonostante sia di modulo costante, cambia continuamente direzione per effetto dell'accelerazione centripeta, quindi c'è una forza in azione.
## Leggi di Newton
### 1° Legge di Newton
La prima legge di Newton è quella del principio di inerzia:  *La variazione di velocità, in modulo e/o direzione è dovuta all'azione di una forza*.
### 2° Legge di Newton
La seconda legge di Newton esprime il legame tra forza e stato del moto
$$\vec{F}=m\vec{a}=m \frac{d\vec{v}}{dt}=m \frac{d^2r}{dt}$$

> [!hint] Unità di Misura
> L'unità di misura della forza è il *Newton*, definito come
> $$N=kg \frac{m}{s^2}$$

L'interazione del punto con l'ambiente circostante espressa come forza $\vec{F}$ determina l'accelerazione del punto (ovvero la variazione della velocità nel tempo), proporzionale alla *Massa Inerziale* $m$
Con il termine *Massa Inerziale* si intende il fatto che la massa di un punto ne esprime l'inerzia, cioè la resistenza a variare il proprio stato di moto (è inversamente proporzionale all'accelerazione).
La seconda legge esprime la *Legge Fondamentale della Dinamica del Punto*, da essa vengono ricavate tutte le proprietà relative al moto del punto.
Questa legge è sperimentale, cioè la prova delle sua validità è effettuata a posteriori delle deduzioni fatte in partenza, oltre all'analisi del moto di un punto soggetto ad una forza. Si tratta di una legge vettoriale, si può scrivere come:
$$\begin{align}
&F_{x}=ma_{x}=m \frac{dv_{x}}{dt}=m \frac{d^2x}{dt^2} \\
&F_{y}=ma_{y}=m \frac{dv_{y}}{dt}=m \frac{d^2y}{dt^2} \\
&F_{z}=ma_{z}=m \frac{dv_{z}}{dt}=m \frac{d^2z}{dt^2}
\end{align}$$

> [!info] Validità
> La legge vale solo nei *Sistemi di Riferimento Inerziali* (altrimenti nella formula appaiono altri termini) ad una velocità inferiore a quella della luce ($c=3\cdot 10^8\ ms^{-1}$) 

### 3° Legge di Newton
La terza legge di Newton esprime il principio di *Azione e Reazione*
- *Se un corpo $A$ esercita una forza $F_{A,B}$ su un corpo $B$, il corpo $B$ reagisce con una forza $F_{B,A}$ sul corpo $A$*
- *Le forza hanno stessa direzione e modulo, ma verso opposto cioè $F_{A,B}=-F_{B,A}$, queste due forze hanno la stessa retta di azione*

![[Pasted image 20250313185821.png|center|500]]

---
## Quantità di Moto, Impulso
Si definisce **Quantità di Moto** di un pm il vettore
$$\vec{p}=m\vec{v}$$
Se la massa è costante si può scrivere allora 
$$\vec{F}=\frac{d\vec{p}}{dt}$$
L'azione di una forza determina la variazione nel tempo della quantità di moto, ovvero di qualcuna o di tutte queste quantità: massa, direzione, verso e modulo.
La formula appena espressa non è altro che una forma più generale della 2° legge di Newton e, nel caso la massa sia costante (come nel caso del punto materiale in tempo stretto), allora le formule di $\vec{F}$ coincidono.
### Teorema dell'Impulso
Si osserva che che l'azione di una forza durante un tempo infinitesimo $dt$ provoca una variazione infinitesima della quantità di moto in un punto:
$$\vec{J}=\int^t_{t_{0}} \vec{F}\ dt= \int^\vec{p}_{\vec{p}_{0}}d\vec{p}=\vec{p}-\vec{p}_{0}=\Delta \vec{p}$$
Con $\vec{J}$ chiamato *Impulso della Forza*, si esprime il seguente teorema

> [!gray] Teorema dell'Impulso
> - L'impulso di una forza applicata a un punto materiale provoca la variazione della quantità di moto
> - Se la massa $m$ è costante, allora $$\vec{J}=m(\vec{v}-\vec{v}_{0})=m\Delta \vec{v}$$

Il teorema dell'impulso è utilizzabile per calcolare effettivamente $\Delta \vec{p}$ solo se si conosce la funzione $\vec{F}(t)$. Se invece misurando $\Delta \vec{p}$ si applica il teorema della media integrale $\int_{t_{0}}^t\vec{F}\ dt$ pari a $\vec{F}_{m}(t-t_{0})$, si può calcolare il valore medio $F_{m}$ della forza agente nell'intervallo di tempo $t-t_{0}$
$$
\vec{F}_{m}= \frac{\Delta \vec{p}}{t-t_{0}}
$$

> [!info] Principio di Conservazione della Quantità di Moto
> Quando $\vec{F}$ è nulla, allora $\Delta \vec{p}=0$ e pertanto $\vec{p}$ è costante. Vale allora il principio della conservazione della quantità di moto, secondo la quale in assenza di forza applicate la quantità di moto di un punto materiale rimane costante (ovvero si conserva)

---
## Risultante delle Forze
![[IMG_0666.jpg|center|400]]
La risultante vettoriale delle forze applicate al punto è 
$$
\vec{F}=\vec{F}_{1}+\vec{F}_{2}+\ldots+\vec{F}_{n}=\sum_{i}\vec{F}_{i}
$$
Mentre per quanto riguarda l'accelerazione risulta
$$
\vec{a}= \frac{\vec{F}}{m}=\sum_{i} \frac{\vec{F}_{i}}{m}=\sum_{i} \vec{F}_{i}
$$
Queste forze agiscono in modo indipendente l'una dall'altra, dando un contributo $\vec{a}_{i}= \frac{\vec{F}_{i}}{m}$ all'accelerazione del punto.
### Equilibrio Statico
Se $\vec{F}=0$ e il punto ha inizialmente velocità nulla, esso rimane in quiete. Sono quindi realizzate le condizioni di **Equilibrio Statico** del punto. Devono quindi risultare nulle le componenti della risultante (con riferimento agli assi cartesiani):
$$
\vec{F}=\sum_{i}F_{i}=0\Longrightarrow\begin{cases}
F_{x}=\sum_{i}F_{i,x}=0 \\
F_{y}=\sum_{i}F_{i,y}=0 \\
F_{z}=\sum_{i}F_{i,z}=0
\end{cases}
$$
---
## Tipi di Moto

| Tipo di Moto                  | Forza e Velocità                                                                                                    |                                                                                       |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Moto Vario                    | $\vec{F}\ne\text{costante}$                                                                                         |                                                                                       |
| Moto Uniformemente Accelerato | $\vec{F}=\text{costante}$                                                                                           | Questa situazione si può ottenere anche se agiscono forze, purché la risultante sia 0 |
| Moto Rettilineo Uniforme      | $\vec{F}=0$, $\vec{v}=\text{costante}$                                                                              |                                                                                       |
| Moto Curvilineo               | $$\vec{F}=\vec{F}_{T}+\vec{F}_{N}=m\vec{a}_{T}+m\vec{a}_{N}= m\frac{dv}{dt}\hat{u}_{T}+m \frac{v^2}{R}\hat{u}_{N}$$ |                                                                                       |
### Moto Curvilineo
La risultate delle forze agenti sul punto materiale deve avere una componente ortogonale alla traiettoria $\vec{F}_{n}$ per provocare una variazione di direzione, mentre la componente tangente $\vec{F}_{T}$ determina invece la variazione del modulo della velocità.

> [!info] Forza Centripeda
> La componente $\vec{F}_{n}= m\vec{a}_{N}=m \frac{\vec{v}^2}{r}$ è chiamata ==**Forza Centripeta**==  ed è sempre diversa da 0 in un moto curvilineo

Se questa quantità è costante in modulo, il moto che compie il punto materiale è circolare uniforme: si tratta di un caso di ==**Equilibrio Dinamico**==, ossia l'azione di forze provoca un moto uniforme e non accelerato. 

> [!info] Equilibrio DInamico
> L'equilibrio dinamico si riferisce a quei casi particolari in cui in presenza di forze il moto del punto avviene con velocità costante in modulo, ma variabile in direzione se $\vec{F}_{N}\ne0$. In generale, se il punto compie un moto rettilineo ciò è possibile solo se la risultante delle forze è nulla, mentre se il moto del punto è curvilineo deve essere nulla solo la componente $\vec{F}_{T}$ e pertanto l'unica accelerazione del punto è $\vec{a}_{N}$

---
## Forza Peso

> [!info] Accelerazione di Gravità
> $$
> g=9.8\ \frac{m}{s^2}
> $$

Se agisce solo la forza peso, essa risulta proporzionale alla massa
$$
\vec{P}=m\vec{g}
$$
Si tratta di una forza costante in modulo, direzione e verso e, in assenza di altre forze, il moto ha una componente uniformemente accelerata nella direzione parallela a $\vec{g}$.
Se intervengono altre forze in generale si ha che $\vec{a}\ne \vec{g}$
## Reazione Vincolare
Se un corpo sulla quale agisce una risultante di forze diversa da 0 rimare fermo, ci deve necessariamente essere un'azione dell'ambiente circostante uguale e contraria alla risultante delle forze agenti, detta **Reazione Vincolare**.

> [!example]+ Esempio:
> 
> ![[Pasted image 20250726004943.png|center|400]]
> 
> Nel caso di un corpo posato su un tavolo, se si applicano ulteriori forze normali $\vec{N}$, il tavolo dovrà necessariamente esercitare una forza vincolare $\vec{R}$ tale che $\vec{R}+\vec{N}=0$. La stessa cosa succede se si ha un corpo appeso ad un filo, il quale sarà in equilibrio statico se $\vec{P}+\vec{N}=0$

### Sensazione di Peso
Si considera il corpo posato su una piattaforma che può muoversi verticalmente con accelerazione $\vec{a}$
$$\vec{N}+\vec{P}=m\vec{a}\Longrightarrow \vec{N}=m\vec{g}=m\vec{a}\Longrightarrow N=m(\vec{a}-\vec{g})$$
![[Pasted image 20250726005915.png|center|400]]
Si ha che
$$\vec{a}=0\Longrightarrow N=P=mg\qquad \vec{a}\ne 0\Longrightarrow N=m(a-g)$$
Si distinguono allora 4 casi (come asse di riferimento si prende $z$, perciò $\vec{g}=-g\hat{u}_{z}$):
1. $\vec{a}$ discorde a $\vec{g}$, la piattaforma accelera verso l'alto, con $$\vec{N}=m[a\hat{u}_{z}-(-g\hat{u}_{z})]=m(g+a)\hat{u}_{z}\Longrightarrow N>mg$$
2. $\vec{a}$ concorde a $\vec{g}$, la piattaforma accelera verso il basso, con $a<g$ $$\vec{N}=m[-a\hat{u}_{z}-(-g\hat{u}_{z})]\Longrightarrow N<mg$$
3. $\vec{a}$ concorde a $\vec{g}$ con $\vec{a}=\vec{g}$ $$\vec{N}=0$$
4. $\vec{a}$ concorde a $\vec{g}$, con $a>g$ $$\text{Distacco della piattaforma}$$
---
## Forza di Attrito Radente
Sperimentalmente, si osserva che il corpo non entra in movimento per effetto di $\vec{F}$ fino a che il suo modulo non supera il valore di $\mu_{s}N_{s}$, con $\mu_{s}$ chiamato **Coefficiente di Attrito Statico**. (Questo si verifica su una superficie *scarba*, altrimenti la superficie è *liscia*)
![[Pasted image 20250726150741.png|center|400]]
Si ha dunque:
- *Condizione di Quiete*: $$F\le \mu_{s}N_{s}$$In queste condizioni è realizzato l'equilibrio statico $\vec{R}+\vec{F}+\vec{P}=0$, con $\vec{R}$ reazione vincolare e $\vec{P}$ forza peso.
$\vec{R}$ ha come componente verticale $N=mg$ e orizzontale $F_{as}=F$.
- *Condizione di Moto*: $$F> \mu_{s}N_{s}$$
### Forza di Attrito Statica
Il vincolo è in grado di sviluppare una forza, detta di **Attrito Radente Statico**, eguale e contraria a $\vec{F}$. Ciò avviene fino a che $F$ non supera il valore di $\mu_{s}N$

> [!hint] Valore di $F_{as}$
> La forza di attrito radente statico non ha pertanto un valore prefissato, ma varia col valore della forza $\vec{F}$ applicata, da $0$ fino a $\mu_{s}N$

### Forza di Attrito Dinamica
Quando $F$ supera $\mu_{s}N$ e quindi entra in moto, si osserva che si ha una forza ad opporre il movimento, chiamata **Forza di Attrito Radente Dinamico** $F_{ad}=\mu_{d}N$, dove $\mu_{d}$ è detto **Coefficiente di Attrito Dinamico**

> [!hint] Vale Sempre
> $$\mu_{d}<\mu_{s}$$

L'equazione del moto è pertanto
$$
F-\mu_{d}N=mA
$$
La forza di attrito radente dinamico non dipende dalla velocità del corpo ed ha verso contrario alla direzione del moto e quindi al versore della velocità 
$$\vec{F}_{ad}=-\mu_{d}N\hat{u}_{v}$$
---
## Piano Inclinato

![[Pasted image 20250726160900.png|center|900]]
 
 Se agisce solo la forza $\vec{P}$, in assenza di attrito tra corpo e piano inclinato, si ha secondo la legge di Newton $\vec{P}+\vec{R}=m\vec{a}$, con $\vec{R}$ reazione vincolare del piano d'appoggio che ha un'unica componente normale al piano stesso (vincolo liscio).
 Scomponendo le componenti lungo le direzioni ortogonali e parallela al piano inclinato si ottiene: 
 $$
-mg\cos \theta+N=0 \qquad mg\sin \theta=ma
$$
Si ricava inoltre che la reazione vincolare è $N=mg\cos \theta$ e l'accelerazione è $a=g\sin \theta<g$: il corpo si muove quindi con *moto uniformemente accelerato* (con accelerazione inferiore a quella di gravità). Il caso limite è quello di $\theta= \frac{\pi}{2}$, con $a=g$ siccome $\sin \frac{\pi}{2}=1$.

Se esiste un attrito radente, il moto non può avvenire se la componente lungo il piano inclinato non supera la massima forza di attrito statico:
$$
mg \sin \theta\le F_{as,max}=\mu_{s}N=\mu_{s}mg \cos \theta
$$
Pertanto la condizione per l'equilibrio statico su un piano inclinato scabro è 
$$\tan \theta\le\mu_{s}$$
Le scomposizioni precedenti diventano
$$
-mg \cos \theta+N=0\qquad mg \sin \theta-\mu_{d}N=ma
$$
Combinando le due equazioni si ottiene che il corpo scende lungo il piano inclinato con accelerazione:
$$a=(\sin \theta-\mu_{d}\cos \theta)g$$
---
## Forza di Attrito Viscoso
La forza di attrito viscoso è una forza che si oppone al moto, in un liquido o gas, ed è proporzionale alla velocità del corpo soggetto a tale forza:
$$\vec{F}=-b\vec{v}$$
Con $b$ costante positiva $(kg\ s^{-1})$.
Si ricava che l'accelerazione è 
$$\vec{a}=- \frac{\vec{b}v}{m}$$
L'accelerazione provocata dalla forza di attrito viscoso è sempre contraria alla velocità (la quale diminuisce).

![[Pasted image 20250726165513.png|center|400]]

Proiettando sull'asse del moto, la condizione si traduce nell'equazione differenzale
$$\frac{dv}{dt}=-\frac{bv}{m}$$
Che, integrando col metodo di separazione delle variabili, diventa
$$
\frac{dv}{v}=-\frac{b}{m}dt\Longrightarrow \int_{v_{0}}^v \frac{dv}{v}=-\frac{b}{m} \int^t_{0} dt\Longrightarrow \ln\left( \frac{v}{v_{0}} \right)=-\frac{b}{m}t
$$
con $v_{0}$ velocità iniziale all'istante $t=0$ ($v_{0}\ne 0$).
Passando agli esponenziali si ottiene
$$
v(t)=v_{0}e^{-\frac{bt}{m}}=v_{0}e^{-\frac{t}{\tau}}
$$
con $\tau=\frac{m}{b}$ costante di tempo ($s$). La velocità decresce esponenzialmente fino a poi fermarsi.
Al diminuire di $\tau$ aumenta la decrescita della velocità, mentre all'aumentare di $\tau$ decresce la decrescita di velocità.

> [!info] Equilibrio Statico per Attrito Viscoso
> In presenza di attrito viscoso, **non** si può verificare una condizione di equilibrio statico, in quanto se $\vec{v}=0$, la forza si annulla


Si considera adesso un punto materiale di massa $m$ lasciato cadere in un fluido con le sole forze $\vec{P}=m\vec{g}$ e $\vec{F}=-b\vec{v}$ e condizioni iniziali $z=0$, $v=0$ per $t=0$.
Applicando la 2° legge di Newton si ha
$$
\vec{P}+\vec{F}=m\vec{g}-b\vec{v}=m\vec{a}=m \frac{d\vec{v}}{dt}
$$
Proiettando l'equazione sull'asse $z$ si ottiene
$$
\frac{dv}{dt}=g- \frac{bv}{m}\Longrightarrow \frac{dv}{dt}=g- \frac{v}{\tau}
$$
Che integrando con il metodo della separazione delle variabili diventa
$$
\frac{dv}{g- \frac{v}{\tau}}=dt \Longrightarrow \int^v_{0} \frac{dv}{g- \frac{v}{\tau}}=\int^t_{0} dt\Longrightarrow \ln \left( \frac{g- \frac{v}{\tau}}{g} \right)= - \frac{t}{\tau}
$$
Passando agli esponenziali e risolvendo per la velocità:
$$
v(t)=g\tau \left( 1- e^{- \frac{t}{\tau}} \right)
$$
![[Pasted image 20250726171436.png|center|200]]

> [!hint] Equilibrio Dinamico
> Si osserva che sotto l'azione della sola forza peso il moto sarebbe uniformemente accelerato, ma con l'opposizione della forza di attrito viscoso che si oppone alla velocità, il moto al limite diventa uniforme (risultato asintotico). Quando la velocità assume il valore limite $g\tau$, la forza di attrito viscoso vale in modulo $bv=bg\tau=mg$ r la risultante delle forze si annulla: si realizza così un equilibrio dinamico tra peso e forza viscosa.

---
## Tensione dei Fili
La forza, con direzione lungo il filo teso, che il filo esercita su un qualsiasi punto materiale viene chiamata **Tensione** del filo.

![[Pasted image 20250726172643.png|center|600]]

Si esamina un infinitesimo $ds$ di un filo teso in quiete (supposto inestensibile e di massa trascurabile), le due forze agenti agli estremi di $ds$ devono avere moduli uguali e versi opposti per garantire l'equilibrio statico. In particolare, ad un estremo del filo si ha $\vec{T}=-\vec{F}$ e per un filo $AB$ si ha $F_{A}=F_{B}=T$ ($\vec{F}_{A}, \vec{F}_{B}=-\vec{F}_{A}$).

---
## Forza Elastica
Si definisce forza elastica (unidimensionale) una forza di direzione costante con verso rivolto verso $O$ (chiamato centro) e modulo proporzionale alla distanza da $O$.
$$
\vec{F}=-kx\hat{u}_{x}
$$
con $k$ **Costante Elastica** (positiva), $\hat{u}_{x}$ versore dell'asse $x$.
Il moto di un punto sottoposto a una forza elastica è rettilineo, l'accelerazione vale
$$
a= \frac{F}{m}=-\frac{k}{m}x=-\omega^2x
$$
e quindi, il sistema costituisce un *oscillatore armonico semplice*, il moto è *armonico semplice* con pulsazione $\omega$ e periodo $T$ determinati dal rapporto tra la costante elastica e la massa del punto materiale a cui è applicata la forza elastica:
$$
\omega= \sqrt{ \frac{k}{m} }\qquad T= \frac{2\pi}{\omega}= 2\pi \sqrt{ \frac{m}{k} }
$$

![[Pasted image 20250726180908.png|center|400]]

**Molla Estesa:**
Assumendo una lunghezza $l>l_{0}$, essa sviluppa una forza $\vec{F}$ che tende a riportarla alla condizione di riposo
$$\vec{F}=-k(l-l_{0})\hat{u}_{x}=-kx\hat{u}_{x}$$
con $x>0$ che rappresenta la deformazione.

**Molla Compressa:**
Se la molla viene compressa alla lunghezza $l<l_{0}$, la forza ha la stessa espressione con $x<0$ e quindi direzione opposta. In ogni caso si può scrivere $\vec{F}=-kx\hat{u}_{x}$.

> [!hint] Mantenimento Lunghezza
> Il modulo di $\vec{F}=-kx\hat{u}_{x}$, chiamata **Forza di Richiamo**, è proporzionale alla deformazione fino a che non si supera il limite di eleasticità della molla. Se si vuole mantenere la molla deformata con una lunghezza determinata $l$ si deve applicare alla molla una forza eguale e opposta alla forza esercitata dalla molla.
>![[Pasted image 20250726182744.png|center|500]]
>Se si vuole deformare una molla di una quantità $x$, si devono applicare ai due estremi due forze eguali e contrarie di modulo $kx$.

### Moto Armonico e Forza Elastica
Si suppone adesso che la molla si bloccata ad u estremo, deformata di $x_{0}$, all'altro estremo è fissata una massa $m$ poggiata su un piano orizzontale liscio. Se all'istante $t=0$ il punto viene lasciato libero con velocità nulla ($x=x_{0}, v=0$ per $t=0$) esso si muovo di moto armonico per la forza elastica. 
La soluzione dell'equazione di moto è
$$
m \frac{d^2x}{dt^2}=-xk\Longrightarrow \frac{d^2x}{dt^2}+\frac{k}{m}x=0
$$
con $x=A\sin(\omega t+\phi)$ con $\omega=\sqrt{ \frac{k}{m} }$. 

> [!info] Oscillatore armonico
> Un punto materiale di massa $m$ soggetto ad una forza elastica $F=-kx$, quando viene spostato dalla sua posizione di equilibrio delle oscillazioni armoniche regolate dall'equazione differenziale dell'oscillatore armonico
> $$
> \frac{d^2x(t)}{dt^2}+\omega^2x(t)=0
> $$
>  La quale soluzione è la relazione
>  $$
>  x=A\sin(\omega t+\phi)
>  $$
>  con $A$ ampiezza dell'oscillazione e $\phi$ fase che determina la condizione iniziale $x(0)$.

I valori delle costanti $A$ e $\phi$ si calcolano dalle condizioni iniziali:
$$
x_{0}=A\sin \phi\qquad 0=\omega A\cos \phi
$$
dato che $v=\omega A\cos(\omega t+\phi)$.
Per $\phi$ compreso tra $0$ e $2\pi$ sono possibili due soluzioni: $A=x_{0},\ \phi=\frac{\pi}{2}$ e $A=-x_{0},\ \phi= \frac{3}{2}\pi$; in ogni caso si hanno per la legge oraria e per la velocità le espressioni
$$
x=x_{0}\cos \omega t\qquad v=-\omega x_{0}\sin \omega t
$$

Se le condizioni iniziali sono diverse si ottiene sempre un moto armonico con la medesima $\omega$, però il valore dell'ampiezza è in generale diverso da $x_{0}$. Per $x=x_{0}, \ v=v_{0}$ per $t=0$ si ottiene
$$
A= \sqrt{ x_{0}^2+ \frac{v_{0}^2}{\omega^2} }\qquad \tan \phi=\omega  \frac{x_{0}}{v_{0}}
$$

Il chat dice (da ricontrollare) per la fase iniziale del moto armonico
- **Guarda dove si trova la particella all’inizio**
    
    - Se è **al centro** → la fase iniziale è 0 o π.
        
    - Se è **a un’estremità** (massimo o minimo) → la fase iniziale è π/2 o -π/2.
        
- **Guarda la direzione della velocità all’inizio**
    
    - Se la particella parte verso **destra (positivo)** → scegli la fase che rende la velocità positiva.
        
    - Se parte verso **sinistra (negativo)** → scegli la fase che rende la velocità negativa.
        
- **Combina i due punti**
    
    - Centro + velocità positiva → fase iniziale = 0.
        
    - Centro + velocità negativa → fase iniziale = π.
        
    - Estremo positivo + velocità negativa → fase iniziale = π/2.
        
    - Estremo negativo + velocità positiva → fase iniziale = -π/2.

---
## Pendolo Semplice
Il pendolo semplice è costituito da un punto materiale appeso tramite un filo ideale. La posizione di equilibrio statico è quella verticale, mentre la forza esercitata dal filo vale in modulo $T_{F}=mg$

![[Pasted image 20250726184907.png|center|350]]

Se il punto si sposta dalla verticale, allora inizia ad oscillare lungo un arco di circonferenza di lunghezza $L$ (pari alla lunghezza del filo) in un piano verticale.
Le forze agenti sul punto $P$ sono il peso $m\vec{g}$ e la tensione $\vec{T}_{F}$, per cui il moto è regolato da
$$
m\vec{g}+\vec{T}_{F}=m\vec{a}
$$
Si considera le componenti lungo la traiettoria circolare:
$$
R_{T}=-mg\sin \theta=ma_{T}\qquad R_{N}=T_{F}-mg \cos \theta=ma_{N}
$$
La forza $R_{T}$ è una forza di richiamo, che tende a riportare il punto sulla verticale.

Le componenti dell'accelerazione sono:
$$
a_{T}=L\alpha=L \frac{d^2\theta}{dt^2}\qquad a_{N}=\frac{v^2}{L}
$$
Sostituendo le due accelerazioni alle equazioni precedenti si ottiene
$$
\frac{d^2\theta}{dt^2}=-\frac{g}{L}\sin \theta\qquad m \frac{v^2}{L}=T_{F}-mg\cos \theta
$$
Per ==piccole oscillazioni== ($\sin \theta \approx \theta$), l'equazione differenziale diventa
$$
\frac{d^2\theta}{dt^2}+ \frac{g}{L}\theta=0
$$
e coincide con quella del moto armonico semplice, posto $\omega^2=\frac{g}{L}$. In questo caso la legge oraria del moto è
$$
\theta=\theta_{0}\sin(\omega t+\phi)
$$
l'ampiezza $\theta_{0}$ dell'oscillazione e la fase iniziale $\phi$ dipendono dalle condizioni iniziali del moto.

Il periodo del moto $T$ è dato da
$$
T=\frac{2\pi}{\omega}=2\pi  \sqrt{ \frac{L}{g} }
$$
ed è indipendente dall'ampiezza.

La legge oraria dello spostamento lungo l'arco di circonferenza è dato da 
$$
s=L\theta=L\theta_{0}\sin(\omega t+\phi)
$$
mentre la velocità angolare e la velocità lineare hanno le espressioni
$$
\omega= \frac{d\theta}{dt}=\omega \theta_{0}\cos(\omega t+\phi)\qquad v=\frac{ds}{dt}=L \frac{d\theta}{dt}=L\omega \theta_{0}\cos(\omega t+\phi)
$$
La velocità massima è quando il punto passa per la verticale $\theta=0$ e nulla agli estremi delle oscillazioni $\theta=\theta_{0}$ dove il verso del moto di inverte.

Quando l'ampiezza delle oscillazioni non è piccola, il moto è ancora periodico ma non armonico e il periodo $T'$ dipende dall'ampiezza.

La tensione del filo che sostiene il punto è 
$$
T_{F}=m\left[ g\cos \theta(t)+ \frac{v^2(t)}{L} \right]
$$
La tensione massima è nella posizione verticale, dove $\theta(t)$ e $v(t)$ assumono valori massimi, ed è minima nei punti di inversione.