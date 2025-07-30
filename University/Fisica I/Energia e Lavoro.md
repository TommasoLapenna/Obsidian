---
sticker: emoji//0034-fe0f-20e3
order: "4"
---
- [[#Lavoro|Lavoro]]
- [[#Potenza|Potenza]]
- [[#Energia Cinetica|Energia Cinetica]]
- [[#Lavori di Tipi di Forze|Lavori di Tipi di Forze]]
	- [[#Lavori di Tipi di Forze#Lavoro della Forza Peso|Lavoro della Forza Peso]]
	- [[#Lavori di Tipi di Forze#Lavoro di una Forza Costante|Lavoro di una Forza Costante]]
	- [[#Lavori di Tipi di Forze#Lavoro di una Forza Elastica|Lavoro di una Forza Elastica]]
	- [[#Lavori di Tipi di Forze#Lavoro della Forza di Attrito Radente|Lavoro della Forza di Attrito Radente]]
- [[#Forze Conservative|Forze Conservative]]
- [[#Energia Potenziale|Energia Potenziale]]
	- [[#Energia Potenziale#Energia Potenziale della Forza Peso|Energia Potenziale della Forza Peso]]
	- [[#Energia Potenziale#Energia Potenziale della Forza Elastica|Energia Potenziale della Forza Elastica]]
- [[#Conservazione dell'Energia Meccanica|Conservazione dell'Energia Meccanica]]
- [[#Momento Angolare|Momento Angolare]]
- [[#Momento della Forza|Momento della Forza]]
	- [[#Momento della Forza#Teorema del Momento Angolare|Teorema del Momento Angolare]]


## Lavoro
Si considera adesso la forza come funzione della posizione occupata (invece che il tempo), quindi si prende un punto materiale $P$ soggetto ad una forza $\vec{F}$ che provoca uno spostamento infinitesimo $d\vec{s}$. Il **Lavoro Infinitesimo** compiuto dalla forza è definito come
$$
dW=\vec{F}\cdot d\vec{s}=F ds \cos \theta=F_{T}ds
$$
con $\theta$ angolo tra $\vec{F}$ e $d\vec{s}$, $F_{T}=F\cos \theta$ proierzione della forza lungo la direzione dello spostamento.

![[Pasted image 20250728012130.png|center|400]]

3 casi possibili di angolo:
- $\theta< \frac{\pi}{2}$: il lavoro risulta positivo e viene chiamato **Lavoro Motore**
- $\theta > \frac{\pi}{2}$: il lavoro risulta negativo e viene chiamato **Lavoro Resistente**
- $\theta= \frac{\pi}{2}$: il lavoro è nullo ($\cos \frac{\pi}{2}=0$)

Per uno spostamento finito da una posizione $A$ a $B$ si sommano i contributi infinitesimi:
$$W=\int_{A}^B \vec{F}\cdot d\vec{s}= \int^B_{A} F\cos \theta\ ds= \int_{A}^B F_{T}\ ds$$

![[Pasted image 20250728012823.png|center|400]]

> [!info] Definizione Lavoro
> Il lavoro è l'integrale di linea della forza lungo la traiettoria

Quando $\vec{F}$ è una risultante di $n$ forze si ha:
$$
W=\int_{A}^B \vec{F}\cdot d\vec{s}= \int_{A}^B(\vec{F}_{1},\ldots,\vec{F}_{n})\cdot d\vec{s}= \int_{A}^B \vec{F}_{1}\cdot d\vec{s}+\ldots+\int_{A}^B\vec{F}_{n}\ d\vec{s}= W_{1}+\ldots+ W_{n}
$$
## Potenza
La potenza corrisponde al lavoro per unità di tempo. 
$$
\mathcal P= \frac{dW}{dt}
$$
dove $\mathcal P$ rappresenta la **Potenza Istantanea**.
La **Potenza Media** invece si trova con $\frac{W}{\Delta t}$, con $\Delta t$ intervallo ti tempo.
## Energia Cinetica
Utilizzando la legge di Newton si scompone ulteriormente la formula del lavoro
$$
dW=\vec{F}\cdot d\vec{s}=F_{T}ds=ma_{T}ds= m \frac{dv}{dt}ds=m \frac{ds}{dt}dv= mvdv
$$
Questa relazione indica il legame esplicito tra lavoro infinitesimo e varianza infinitesima del modulo della velocità. Per un percorso finito da $A$ a $B$ si ha quindi
$$
W=\int_{A}^B mvdv= \frac{1}{2}mv_{B}^2- \frac{1}{2}mv_{A}^2= E_{k,B}-E_{k,a}= \Delta E_{k}
$$
dove $E_{k}=\frac{1}{2}mv^2$ rappresenta l'**Energia Cinetica**.

> [!gray] Teorema dell'Energia Cinetica
> Il lavoro compiuto dalla risultante delle forze nello spostamento di un punto materiale dalla posizione $A$ alla posizione $B$ è uguale alla variazione dell'energia cinetica del punto materiale stesso. Questo teorema è una conseguenza delle seconda legge di Newton.

> [!hint] Osservazione su $\vec{p}$
> Se si riprende la definizione di quantità di moto, $\vec{p}=m\vec{v}$, si osserva che la relazoione tra energia cinetica e modulo della quantità di moto sussiste
> $$
> E_{k}= \frac{p^2}{2m}\qquad p=\sqrt{ 2mE_{k} }
> $$
> 

> [!info] Nota
> Il lavoro è la manifestazione di una forza ed è quindi conseguenza con un interazione dell'ambiente circostante, pertanto si parla di **Lavoro Scambiato**. Per quanto riguarda l'energia, essa è **Posseduta** dal sistema e viene modificata dall'ambiente esterno (un effetto misurabile è la quantità di energia).

## Lavori di Tipi di Forze
### Lavoro della Forza Peso
Il lavoro della forza peso $m\vec{g}$ si calcola come spostamento tra $A$ e $B$ sull'asse $z$ orientato verso dal suolo verso l'alto (verso opposto a $\vec{g}$)

![[Pasted image 20250728014922.png|center|350]]

$$W=\int_{A}^B \vec{F}\cdot d\vec{s}=\vec{F}\cdot \int_{A}^Bd\vec{s}=m\vec{g}\cdot \vec{r}_{AB}$$
Infatti $\vec{F}$ è costante e vale $\vec{r}_{AB}=\vec{r}_{B}-\vec{r}_{A}$.
Poiché il peso ha una sola componente diversa da zero (lungo l'asse $z$) che vale $-mg$ e la componente $\vec{r}_{AB}$ lungo l'asse $z$ è $z_{B}-z_{A}$ il prodotto finale diventa $(m\vec{g})_{z}(\vec{r}_{AB})_{z}=-mg(z_{B}-z_{A})$, quindi il lavoro della forza peso risulta
$$
W=-(mgz_{B}-mgz_{A})
$$
### Lavoro di una Forza Costante
Il lavoro di una forza costante $\vec{F}$ lungo lo stesso asse è 
$$
W=-(F_{x_{B}}-F_{x_{A}})
$$
### Lavoro di una Forza Elastica
La forza elastica $\vec{F}=-kx\hat{u}_{x}$ per uno spostamento lungo l'asse $x$ vale
$$
W=\int_{A}^B -kx\hat{u}_{x}\cdot dx\hat{u}_{x}=-k\int_{A}^Bx\ dx= -\left( \frac{1}{2}kx^2_{B}-\frac{1}{2}kx^2_{A} \right)
$$
Questo lavoro dipende solo dalla posizione iniziale e finale.
### Lavoro della Forza di Attrito Radente
La forza di attrito radente è $\vec{F}_{ad}=-\mu_{d}N\hat{u}_{v}$, com $\hat{u}_{v}$ parallelo e concorde allo spostamento $d\vec{s}$, il lavoro è quindi
$$
W=\int_{A}^B \vec{F}_{AB}\cdot d\vec{s}=\int_{A}^B-\mu_{d}N\hat{u}_{v}\cdot d\vec{s}=-\mu_{d}\int_{A}^B N\ ds
$$
Nel caso in cui $N$ sia costante si ha
$$
W=-\mu_{d}N\int_{A}^B ds= -\mu_{d}Ns_{AB}
$$
con $s_{AB}$ lunghezza tra $A$ e $B$ percorsa effettivamente. Quindi a parità di $\mu_{d}$ e $N$ si ha un lavoro diverso in base alla traiettoria

> [!info] Nota
> Il lavoro della forza di attrito radente dipende dal percorso e non è esprimibile come differenza di valori di una funzione delle coordinate nei punti $A$ e $B$, diversamente da come accade per il lavoro della forza peso e di quella elastica.
> Inoltre il valore di questo lavoro sarà sempre negativo (sempre resistente).

---
## Forze Conservative
Le forze per il cui lavoro non dipende dal percorso sono dette **Forze Conservative**. Per il calcolo del lavoro si può usare un qualsiasi percorso che colleghi $A$ e $B$ ($W=\int_{A}^B (\vec{F}\cdot d\vec{s})_{I}=\int_{A}^B (\vec{F}\cdot d\vec{s})_{II}=\int_{A}^B\vec{F}\cdot d\vec{s}$).

![[Pasted image 20250728113614.png|center|300]]

È importante avere $\int_{A}^B \vec{F}\cdot d\vec{s}=-\int_{B}^A \vec{F}\cdot d\vec{s}$, di conseguenza
$$
\oint \vec{F}\cdot d\vec{s}=0
$$
## Energia Potenziale
Se la forza è conservativa, allora il lavoro che la forza compierebbe nello spostamento tra la posizione di riferimento $O$ e la posizione generica $P$ $$W=\int_{O}^P \vec{F}\cdot d\vec{s}=0$$
può dipendere solo da $O$ e $P$ (ossia dalle sue coordinate).
La conservatività della forza consente di definire in ogni punto $P$ dello spazio una funzione dipendente unicamente dalle coordinate di $P$:
$$
E_{p}(x,y,z)=E_{p,P}=-\int_{0}^P \vec{F}\cdot d\vec{s}
$$
dove $E_{p}$ sta per **Energia Potenziale** del punto. Grazie a questa definizione è possibile calcolare il lavoro della forza per un qualsiasi spostamento da $A$ a $B$:
$$
W=\int_{A}^B \vec{F}\cdot d\vec{s}=\int_{O}^A \vec{F}\cdot d\vec{s} +\int_{O}^B \vec{F}\cdot d\vec{s} =-\int_{O}^A \vec{F}\cdot d\vec{s}+\int_{O}^B \vec{F}\cdot d\vec{s}
$$
per cui
$$
W=E_{p,A}-E_{p,B}=-\Delta E_{p}
$$

> [!info] ->
> - L'energia potenziale può essere definita solo per le forze conservative
> - Per tutte le forze conservative il lavoro si esprime sempre come l'opposto della variazione dell'energia potenziale relativa alla specifica forza
> - Non esiste una espressione generale dell'energia potenziale

### Energia Potenziale della Forza Peso
$$E_{p,P}=mgz$$
con $z$ coordinata di riferimento di $P$ rispetto al riferimento $O$
SI può verificare che la dipendenza del valore dell'energia potenziale dal punto di riferimento non influisce sul calcolo del lavoro in uno spostamento dal punto $A$ al punto $B$.

![[Pasted image 20250728121847.png|center|300]]

Se si sceglie un'origine diversa $O'$, $E_{p}'=mgz'=mg(z+z_{0})$, quindi
$$E_{p}'=E_{p}+mgz_{0}$$
Nel calcolo del lavoro però compare solo la variazione di energia potenziale e la costante $mgz_{0}$ viene eliminata:
$$
W=-\Delta E_{p}=-\Delta E'_{p}
$$

> [!hint] Osservazione
> Pur dipendendo il valore di $E_{p}$ dalla scelta dell'origine, non ne dipende il lavoro per gli spostamenti del punto materiale $P$.

### Energia Potenziale della Forza Elastica
$$
E_{p,el}= \frac{1}{2}kx^2
$$
Si osserva che l'energia potenziale è tanto più alta quanto la molla è deformata rispetto alla lunghezza di riposo. Come nel caso precedente, l'energia potenziale aumenta spostandosi nella direzione opposta alla forza.

---
## Conservazione dell'Energia Meccanica
Se agiscono solo forse conservative si ha che
$$
W=\Delta E_{k}=E_{k,B}-E_{k,A}\qquad W=-\Delta E_{p}= E_{p,A}-E_{p,B}
$$
Eguagliando le due relazioni si ottiene
$$
E_{k,A}+E_{p,A}=E_{k,B}+ E_{p,B}
$$

> [!gray] Principio di Conservazione dell'Energia Meccanica
> La somma dell'energia cinetica e dell'energia potenziale di un punto materiale che si muove sotto l'azione di forse conservative resta costante durante il moto. Questa somma si chiama **Energia Meccanica** per la quale si esprime il **Principio di Conservazione dell'Energia meccanica**, ovvero che in presenza di forse conservative l'energia meccanica di un punto materiale si conserva
> $$
> E_{m}=E_{k}+E_{p}
> $$
> 

Durante il moto, avviene una trasformazione da un tipo di energia ad un'altra (tramite il lavoro), ma il contenuto energetico totale (energia meccanica) non cambia.

Quando invece agiscono sia forze conservative che non, il lavoro complessivo è dato dalla somma delle forze conservative $W_{c}$ e quello delle forze non conservative $W_{nc}$
$$
W=W_{c}+W_{nc}=E_{k,B}-E_{k,A}
$$
Esprimendo il lavoro $W_{c}$ tramite l'energia potenziale si ottiene
$$
E_{p,A}-E_{p,B}+W_{nc}=E_{k,B}-E_{k,A}\Longrightarrow W_{nc} = (E_{k,B}-E_{p,B})-(E_{k,A}-E_{p,A})=E_{m,B}-E_{m,A}
$$

> [!info] Forze non Conservative
> In presenza di forze non conservative l'energia meccanica non resta costante e la sua variazione è uguale al lavoro delle forze non conservative.

---
## Momento Angolare
(Appendice C, momento di un vettore rispetto ad un punto)
Si definisce come **Momento Angolare** ($N m s$) rispetto al polo $O$ il momento del vettore quantità di moto 
$$
\vec{L}=\vec{r}\times \vec{p}=\vec{r}\times m\vec{v}
$$
dove $\vec{r}$ è il vettore che congiunge il polo $O$ a $P$.

![[Pasted image 20250728125718.png|center|400]]

Se si cambia il polo vale la relazione
$$
\vec{L}_{O'}=\vec{L}_{O}+\vec{O}'\vec{O}\times m\vec{v}
$$
In generale, il momento è una funzione del tempo $\vec{L}(t)$.
## Momento della Forza
Il **Momento della Forza** ($N\ m$) è definito come
$$\vec{M}=\vec{r}\times \vec{F}$$
![[IMG_0672.jpg|center|400]]

Se si cambia polo si ha 
$$
\vec{M}_{O'}=\vec{M}_{O}+\vec{O}'\vec{O}\times \vec{F}
$$
Quando sono applicate più forze con risultante $\vec{F}=\sum_{i}\vec{F}_{i}$ si ha
$$
\vec{M}=\vec{r}\times \vec{F}_{1}+\ldots+\vec{r}\times \vec{F}_{n}=\vec{r}\times(\vec{F}_{1}+\ldots+\vec{F}_{n})= \vec{r}\times \vec{F}
$$
Il momento complessivo è uguale al momento della risultante.
### Teorema del Momento Angolare
Se si calcola la variazione nel tempo del momento angolare di un punto materiale $P$ in movimento si ottiene
$$
\frac{d\vec{L}}{dt}=\frac{d\vec{r}}{dt}\times m\vec{v}+\vec{r}\times m \frac{d\vec{v}}{dt}
$$
dove $\vec{r}$ è il raggio vettore che congiunge il polo $O$ a $P$. 
Si suppone adesso che il polo $O$ sia fermo, allora $\frac{d\vec{r}}{dt}$ coincide con la velocità $P$ e il prodotto vettoriale $\frac{d\vec{r}}{dt}\times m\vec{v}$ si annulla, inoltre $m \frac{d\vec{v}}{dt}=m\vec{a}$ coincide con la forza $\vec{F}$ applicata al punto $\vec{P}$ (purché il sistema di riferimento sia inerziale) e quindi $\vec{r}\times \vec{F}$ è il momento della forza rispetto allo stesso polo $O$. Si conclude quindi

> [!gray] Teorema del Momento Angolare
> $$
> \vec{M}= \frac{d\vec{L}}{dt}
> $$
> La derivata del momento angolare è uguale al momento della forza se entrambi i momenti sono riferiti allo stesso polo fisso in un sistema di riferimento inerziale.

Il momento della forza può essere nullo sia perché la forza è nulla, sia perché $\vec{r}$ e $\vec{F}$ sono parallel: in questo caso
$$
\frac{d\vec{L}}{dt}=0\Longrightarrow \vec{L}=\text{costante}
$$

> [!info] Conservazione del Momento Angolare
> Il momento angolare di un punto materiale rimane costante nel tempo (si conserva) se il momento delle forze è nullo.


> [!gray] Teorema dell'Impulso
> Dal teorema del momento calcolare si ha che $\vec{M}dt=d\vec{L}$, integrando per un instante di tempo da $t_{0}$ a $t$ si ha
> $$
> \int_{t_{0}}^t \vec{M}\ dt=\Delta \vec{L}=\vec{L}_{fin}-\vec{L}_{in}
> $$
> Se la variazione di forza al punto per un tempo molto breve $\vec{r}$ è praticamente costante e questo integrale diventa
> $$
> \int_{t_{0}}
> ^t \vec{M}\ dt=\int_{t_{0}}^t(\vec{r}\times \vec{F})\ dt= \vec{r}\times \int_{t_{0}}^t \vec{F}\ dt= \vec{r}\times \vec{J}=\Delta \vec{L}$$
> detto **Teorema dell'Impulso**., secondo il quale la variazione di momento angolare è uguale al momento dell'impulso applicato al punto

Si osserva che anche il lavoro può essere espresso tramite il momento della forza, infatti
$$W=\int_{A}^B F_{T}\ ds=\int_{\theta_{a}}^{\theta_{b}}rF_{T}\ d\theta = \int_{\theta_{a}}^{\theta_{b}}M\ dt\eta$$
