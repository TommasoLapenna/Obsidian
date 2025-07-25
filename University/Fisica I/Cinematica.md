---
order: "2"
sticker: emoji//0032-fe0f-20e3
---
Tags: [[Fisica I]] [[Old Vault/Indexes/University]] 

- [[#Cinematica di un Punto Materiale|Cinematica di un Punto Materiale]]
	- [[#Cinematica di un Punto Materiale#Sistema di Riferimento|Sistema di Riferimento]]
		- [[#Sistema di Riferimento#Coordinate Polari|Coordinate Polari]]
	- [[#Cinematica di un Punto Materiale#Grandezze Fondamentali|Grandezze Fondamentali]]
	- [[#Cinematica di un Punto Materiale#Vettori|Vettori]]
		- [[#Vettori#Raggio Vettore|Raggio Vettore]]
	- [[#Cinematica di un Punto Materiale#Velocità|Velocità]]
		- [[#Velocità#Componenti Cartesiane della Velocità|Componenti Cartesiane della Velocità]]
		- [[#Velocità#Componenti Polari della Velocità|Componenti Polari della Velocità]]
	- [[#Cinematica di un Punto Materiale#Accelerazione|Accelerazione]]
		- [[#Accelerazione#Componenti Cartesiane|Componenti Cartesiane]]
		- [[#Accelerazione#Componenti Polari|Componenti Polari]]
- [[#Classificazioni di Moto|Classificazioni di Moto]]
	- [[#Classificazioni di Moto#Moto Rettilineo|Moto Rettilineo]]
		- [[#Moto Rettilineo#Moto Rettilineo Uniforme|Moto Rettilineo Uniforme]]
		- [[#Moto Rettilineo#Moto Uniformemente Accellerato|Moto Uniformemente Accellerato]]
	- [[#Classificazioni di Moto#Moto Verticale|Moto Verticale]]
	- [[#Classificazioni di Moto#Moto Armonico Semplice|Moto Armonico Semplice]]
	- [[#Classificazioni di Moto#Moto Circolare|Moto Circolare]]
		- [[#Moto Circolare#Moto Circolare Uniforme|Moto Circolare Uniforme]]
		- [[#Moto Circolare#Moto Circolare Non Uniforme|Moto Circolare Non Uniforme]]
		- [[#Moto Circolare#Moto Circolare Uniformemente Accelerato|Moto Circolare Uniformemente Accelerato]]
		- [[#Moto Circolare#Moto Circolare e Moto armonico|Moto Circolare e Moto armonico]]
			- [[#Moto Circolare e Moto armonico#Notazione Vettoriale del Moto Circolare|Notazione Vettoriale del Moto Circolare]]
	- [[#Classificazioni di Moto#Moto Parabolico|Moto Parabolico]]
	- [[#Classificazioni di Moto#Velocità ed Accelerazione in Funzione della Posizione|Velocità ed Accelerazione in Funzione della Posizione]]

# Cinematica di un Punto Materiale
La parte della meccanica che descrive il moto di un corpo, indipendentemente dalle cause che lo determinano viene detta *Cinematica*

- **Punto Materiale:** Oggetto che ha dimensioni più piccole rispetto allo spazio studiato.
- **Traiettoria:** Luogo dei punti che il Punto Materiale porta avanti nel tempo

![[Pasted image 20250308154041.png|center|500]]

## Sistema di Riferimento
Il moto di un punto materiale è determinato se è nota la sua posizione in funzione del tempo in un determinato *Sistema di Riferimento*. 

![[Pasted image 20250308155417.png|center|450]]
### Coordinate Polari

![[Pasted image 20250308161613.png|center|500]]

Se la traiettoria è nota, è possibile esprimere la posizione di $P$ nello spazio attraverso ==l'*Ascissa Curvilinea* $s(t)$== (la parte rossa), ovvero la lunghezza dell'arco di curva da un'origine arbitria $O$. Se si riesce a dare forma della traiettoria e la funzione $s(t)$ allora si può avere una descrizione completa del moto.
## Grandezze Fondamentali
Attraverso il concetto di derivata si studiano le variazioni di posizione e velocità del punto materiale lungo la traiettoria, si ricavano così le grandezze fondamentali delle cinematica che sono *Posizione*, *Velocità* ed *Accelerazione*.
Si definisce inoltre il concetto di *Quiete*, ovvero un tipo particolare di moto dove le coordinate restano costanti e quindi velocità ed accelerazione risultano nulle.
## Vettori
Grandezze con caratteristiche direzionali, composte da:
- Modulo
- Direzione
- Verso 
- Origine

![[Pasted image 20250308163103.png|center|800]]
### Raggio Vettore
Dato un sistema di riferimento cartesiano con origine $O$ e assi $x,y,z$, la posizione del punto può essere individuata attraverso il *Raggio Vettore* $r$, che congiunge l'origine $O$ col punto $P$.

![[Pasted image 20250308164730.png|center|800]]

> [!info] Legge Oraria
> Se si conosce la dipendenza la dipendenza dal tempo, allora di conoscono le leggi orarie di $\vec{r}=(x(t),y(t),z(t))$

---
## Velocità
Si considerano due posizioni occupate da $P$ al tempo $t$ e al tempo $t+\Delta t$, individuate dai vettori $\vec{r}(t)$ e $\vec{r}(t+\Delta t)=\vec{r}(t)+\Delta\vec{r}$.
$$ \Delta\vec{r} = \vec{r}(t+\Delta t)- \vec{r}(t)
$$
Si chiama vettore spostamento. Si definisce la *Velocità Media* su quest'ultimo:
$$\vec{v}_{m}= \frac{\Delta\vec{r}}{\Delta t}$$

![[Pasted image 20250308182412.png|center|750]]

Se $\Delta t\to 0$, allora si passa a variazioni infinitesime, si calcola così la ==velocità istantanea==
$$\vec{v}= \frac{d\vec{r}}{dt}$$
L'incremento $d \vec{r}$ infinitesimo risulta in direzione tangente alla traiettoria nel punto $P$. Essendo quindi il vettore velocità sempre tangente si può scrivere come 
$$ \vec{v}=v \hat{u}_{T}=\frac{ds}{dt} \hat{u}_{T}$$
con $\hat{u}_{T}$ versore tangente.
Se si considera la dipendenza dal tempo della velocità istantanea, si considera $d \vec{r}=\vec{v}(t)dt$ e si fa l'operazione inversa si ottiene:
$$
\int_{r_{0}}^r d \vec{r}=\int_{t_{0}}^t \vec{v}(t)dt \Longrightarrow \vec{r}(t)= \vec{r}(t_{0})+\int_{t_{0}}^t \vec{v}(t)dt
$$
Infine, dalla definizione di velocità media come $\vec{v}_{m}=\frac{\vec{r}-\vec{r_{0}}}{t-t_{0}}$ si ottiene:
$$\vec{v}_{m}= \frac{1}{t-t_{0}}\int_{t_{0}}^t \vec{v}(t)dt
$$
### Componenti Cartesiane della Velocità
Siccome $\vec{r}=x \hat{u}_{x}+y \hat{u}_{y}+z \hat{u}_{z}$, allora
$$ \vec{v}= \frac{d\vec{r}}{dt}= \frac{dx}{dt}\hat{u}_{x}+ \frac{dy}{dt}\hat{u}_{y}+\frac{dz}{dt}\hat{u}_{z}
$$
Il modulo del vettore darà quindi 
$$|\vec{v}|=\sqrt{v_{x}^2+ v_{y}^2+v_{z}^2}$$
### Componenti Polari della Velocità
Per le coordinate polari il sistema di riferimento usato è composto da $r(t)$ (il raggio vettore) e $\theta(t)$ (l'angolo che $r$ forma con l'asse $x$). Le relazioni tra coordinate cartesiane e polari sono 
$$
x=r \cos \theta \quad y= r \sin \theta \quad \iff r =\sqrt{ x^2+y^2 } \quad \tan \theta = \frac{y}{x}
$$

![[Pasted image 20250309113243.png|center|600]]

Si introducono i versori $\hat{u}_{r}$ e $\hat{u_{\theta}}$, rispettivamente della direzione di $\vec{r}$ e il versore ortogonale, questi versori ruotano durante il moto. Applicando la formula di derivazione di un versore si ottiene:
$$
\vec{v}= \frac{d \vec{r}}{dt}= \frac{dr}{dt}\hat{u}_{r}+r \frac{d \hat{u}_{r}}{dt}=\frac{dr}{dt}\hat{u}_{r}+ r \frac{d\theta}{dt}\hat{u}_{\theta}
$$
Quindi la velocità è sempre tangente alla traiettoria, si può poi scomporre in due elementi:
- *Velocità Radiale:* $\vec{v}_{r}$, diretta lungo $\vec{r}$ di modulo $\frac{dr}{dt}$
- *Velocità Trasversa:* $\vec{v_{\theta}}$, ortogonale ad $\vec{r}$ di modulo $r \frac{d\theta}{dt}$
Il modulo della velocità è
$$
|\vec{v}|= \sqrt{ \left( \frac{dr}{dt} \right)^2+r^2 \left( \frac{d\theta}{dt} \right)^2 }
$$
---
## Accelerazione
L'accelerazione media è definita in modo analogo alla velocità media, espressa come variazione della velocità nel tempo 
$$
\vec{a}_{m}= \frac{\Delta \vec{v}}{\Delta t}
$$
Passando poi al limite $\Delta t\to 0$ si ottiene l'accelerazione istantanea
$$
\vec{a}= \frac{d \vec{v}}{dt}= \frac{d^2 \vec{r}}{dt^2}
$$
L'accelerazione indica la rapidità di variazione della velocità nel tempo, pertanto se $\vec{a}=0$, la velocità è costante.
Analogamente alla velocità, considerando l'accelerazione in funzione del tempo $d \vec{v}=\vec{a}(t)dt$ ed eseguendo il calcolo inverso si ottiene:
$$
\vec{v}(t)=\vec{v}(t_{0})+\int_{t_{0}}^t \vec{a}(t)dt
$$
### Componenti Cartesiane
Dalle uguaglianze precedenti risulta
$$
\vec{a}= \frac{\vec{d}v}{dt}= \frac{dv_{x}}{dt}\hat{u}_{x}+ \frac{du_{y}}{dt}\hat{u}_{y}+ \frac{dv_{z}}{dt}\hat{u}_{z}=\frac{d^2x}{dt^2}+\frac{d^2y}{dt^2}+\frac{d^2z}{dt^2}=a_{x}\hat{u}_{x}+a_{y}\hat{u}_{y}+a_{z}\hat{u}_{z}
$$
e le leggi orarie sono espresse da 
$$
((\ddot{x}(t)),\ddot{y}(t),\ddot{z}(t))
$$
### Componenti Polari
L'accelerazione deve esprimere le variazioni di velocità come modulo e e direzione, quindi avrà due componenti legati ad essi. 

![[Pasted image 20250309125400.png|center|800]]

Applicando la formula di derivazione di un versore si ottiene:
$$
\vec{a} = \frac{d}{dt}(v \hat{u}_{T})=\frac{dv}{dt} \hat{u}_T+ v \frac{d \hat{u}_{T}}{dt} = \frac{dv}{dt} \hat{u}_{T}v \frac{d\phi}{dt}\hat{u}_{N}
$$
dove il primo componente indica il cambiamento del modulo di velocità, mentre il secondo indica il cambio di direzione della velocità, si ha inoltre che $\frac{dv}{dt}\hat{u}_{T}\parallel \vec{v}$.
Per esprimere in maniera più significativa la componente normale, si considera il fatto che le rette normali alla traiettoria in punti vicini si incontrano in un punto $C$, detto *Centro di Curvatura* (nei tratti rettilinei va all'infinito. L'arco di traiettoria $ds =R d\phi$ (variazione infinitesima della coordinata curvilinea) con $R= \overline{CP}$ *Raggio di curvatura*. Pertanto 
$$
\frac{d\phi}{dt}=\frac{1}{R} \frac{ds}{dt}=\frac{d\phi}{ds} \frac{ds}{dt}=\frac{1}{R}v
$$
sostituendo alla formula precedente:
$$
\vec{a}= \frac{dv}{dt}\hat{u}_{T} + \frac{v^2}{R}\hat{u}_{N}=\vec{a}_{T}+\vec{a}_{N}
$$
con modulo
$$
|\vec{a}|=a=\sqrt{ a^2_{T}+a^2_{N} }= \sqrt{ \left( \frac{dv}{dt} \right)^2+\frac{v^4}{R^2} }
$$
L'accelerazione è composta quindi da due elementi:
- *Accelerazione Tangenziale*, $\vec{a}_{T}$
- *Accelerazione Normale* o *Centripeta*, $\vec{a}_{N}$
---
# Classificazioni di Moto

| Tipo di Moto             | Accelerazione Tangenziale | Accelerazione Normale |
| ------------------------ | ------------------------- | --------------------- |
| Moto Curvilineo Vario    | $\vec{a}_{T}\ne 0$        | $\vec{a}_{N}\ne 0$    |
| Moto Curvilineo Uniforme | $\vec{a}_{T}= 0$          | $\vec{a}_{N}\ne 0$    |
| Moto Rettilineo Vario    | $\vec{a}_{T}\ne 0$        | $\vec{a}_{N}= 0$      |
| Moto Rettilineo Uniforme | $\vec{a}_{T}= 0$          | $\vec{a}_{N}= 0$      |

## Moto Rettilineo
![[Pasted image 20250310184050.png|center|600]]

Il moto è descrivibile da una sola coordinata $x(t)$, quindi i vettori $\vec{r}$, $\vec{v}$ e $\vec{a}$ hanno una sola componente.
Dato uno spostamento in un intervallo di tempo si può ricavare la *Velocità Media*
$$
v_{m}= \frac{\Delta x}{\Delta t} = \frac{x_{2}-x_{1}}{t_{2}-t_{1}}
$$
Calcolando il rapporto incrementale $\frac{\Delta x}{\Delta t}$ per il limite di $\Delta t \to 0$ si ottiene la *Velocità Istantanea* 
$$
v = \frac{dx}{dt}
$$
Si può calcolare la legge orario $x(t)$ a partire da $dx = dv(t)dt$
$$
\Delta x = \int_{x_{0}}^x dx = \int_{t_{0}}^t v(t)dt \Longrightarrow x(t)= x_{0}+ \int_{t_{0}}^t v(t)dt
$$
^dd

Usando la relazione tra velocità media e istantanea si ottiene anche che 
$$
v_{m}= \frac{1}{t-t_{0}}\int_{t_{0}}^tv(t)dt
$$
Per quanto riguarda l'*Accelerazione Media* si procede in modo analogo alla velocità
$$
a_{m} = \frac{\Delta v}{\Delta t} = \frac{v_{2}-v_{1}}{t_{2}-t_{1}}
$$
Uguale per l'*Accelerazione Istantanea*
$$
a = \frac{dv}{dt}= \frac{d^2x}{dt}
$$
Sfruttando il legame tra accelerazione e variazione di velocità $dv = a(t)dt$ si ottiene
$$
\Delta v=\int_{t_{0}}^tdv= \int_{t_{0}}^ta(t)dt \Longrightarrow v(t) = v_{0}+\int_{t_{0}}^t a(t)dt
$$

^0a73da

### Moto Rettilineo Uniforme
Nel moto rettilineo uniforme $v=\text{costante}$. si ha
$$
x(t)=x_{0}+v\int_{t_{0}}^tdt=x_{0}+v(t-t_{0})
$$

^a732e6

Legge oraria del moto rettilineo uniforme.
### Moto Uniformemente Accellerato
Se l'accelerazione è costante durante il moto, la dipendenza della velocità dal tempo è lineare e da [[#^0a73da|(*)]] si ottiene
$$
v(t)= v_{0}+a(t-t_{0})
$$
utilizzando l'espressione appena trovata e [[#^dd|(**)]] si calcola $x(t)$
$$
x(t)=x_{0}+\int_{t_{0}}^t[v_{0}+a(t-t_{0})]dt = x_{0}+\int_{t_{0}}^t v_{0}dt+\int_{t_{0}}^ta(t-t_{0})dt
$$
In conclusione
$$
x(t) = x_{0}+v_{0}(t-t_{0})+ \frac{1}{2}a(t-t_{0})^2
$$
nel moto uniformemente accelerato la velocità è una funzione del tempo mentre lo spazio percorso è una funzione quadratica del tempo
## Moto Verticale
(Attrito dell'aria trascurato)
*Costante di Accelerazione Gravitazionale*
$$
g= 9,8 ms^{-2}
$$
Il moto di un corpo lasciato cadere è costante

![[Pasted image 20250311181845.png|center|450]]

Si considera $a=-g$ per riscrivere le espressioni della velocità e posizione:
$$
v(t)=v_{0}-gt \quad x(t)=x_{0}+v_{0}t- \frac{1}{2} gt^2
$$
Il tempo in caduta $t_{c}$ e velocità al suolo $v_{c}$ sono
$$
t_{c}= \sqrt{ \frac{2h}{g} }\quad v_{c}=\sqrt{ 2gh }
$$
- Caduta libera da un'altezza $h$ e $v_{0}=0$
$$
	v(t)=-gt \quad x(t)=h- \frac{1}{2} gt^2
	$$
- Punto lanciato verso il basso
$$
\begin{align}
&v(t)=-v_{1}-gt &x(t)=h-v_{1}t- \frac{1}{2}gt^2 \\ &t_{c}=- \frac{v_{1}}{g}+ \sqrt{ \frac{v_{1}^2}{g^2}+ \frac{2h}{g} }\quad &v_{c}= \sqrt{ v_{1}^2 +2gh }
\end{align}
$$ ^1bedc0
- Punto lanciato verso l'alto partendo dal suolo ($x_{0}=0$, $v_{0}=v_{2}>0$, $t_{0}0$) $$
v=v_{2}-gt \quad x=v_{2}t- \frac{1}{2}gt^2
$$la velocità scende progressivamente, fino a fermarsi all'istante $t_{M}=\frac{v_{2}}{g}$ e posizione $x_{M}=x(t_{M})= \frac{v_{2}^2}{2g}$. Una volta raggiunto $x_{M}$, il copro cade partendo da una velocità nulla e la caduta avrà lo stesso tempo $t_{c}=\sqrt{ \frac{2x_{M}}{g} }=t_{M}$ (la durata complessiva del moto sarà quindi $2t_{M}= \frac{2v_{2}}{g}$)
## Moto Armonico Semplice
Un punto segue un *Moto Armonico Semplice* quando la sua legge oraria è
$$
x(t)=A\sin(\omega t+\phi)
$$
^pp

con: 
- $A$: Ampiezza del moto (costante)
- $\phi$: Fase del moto (costante)
- $\omega$: Pulsazione

Dunque il moto armonico semplice è un tipo moto rettilineo vario. Inoltre risulta essere periodico di periodo $T$ (per via del seno). 
Per definizione di periodo si prendono due istanti di tempo $t'$ e $t$ tali che $t' = t+T$, quindi $x(t)=x(t')$. Essendo poi $T=2\pi$ (periodo del seno), si ha che $\omega t'+\phi=\omega t+\phi+2\pi$. Ne segue che $\omega(t'-t)=2\pi$ ($T=t'-t$)
$$ T= \frac{2\pi}{\omega}\quad \omega = \frac{2\pi}{T}$$
Si definisce *Frequenza* $v$ del moto il numero di oscillazioni in un secondo
$$
v = \frac{1}{T} = \frac{\omega}{2\pi}
$$
il periodo e la frequenza sono indipendenti dall'ampiezza del moto
- Velocità
$$
v(t)= \frac{dx}{dt}= \omega A\cos(\omega t+\phi)
$$
- Accelerazione
$$
a(t)= \frac{dv}{dt}=\frac{d^2x}{dt^2}=-\omega ^2A\sin(\omega t+\phi)=-\omega^2x(t)
$$
 ^8f41d9

![[Pasted image 20250311201814.png|center|400]]

La posizione, velocità e accelerazione sono sfasate l'una con l'altra di $\frac{\pi}{2}$. Inoltre la velocità raggiunge il massimo nel centro di oscillazione e si annulla agli estremi di, mentre l'accelerazione si comporta in modo opposto.
Le tre funzioni $x(t)$, $v(t)$ e $a(t)$ hanno la stessa forma e periodo, cambiano solo il valore dell'ampiezza che rispettivamente risulta $A$, $\omega A$ e $\omega^2 A$.
- Le costanti $A$ e $\phi$ individuano le condizioni iniziali $x_0$ e $v_{0}$ viceversa: 
$$
\begin{align}
&x(0) =x_{0}=A\sin \phi &v(0)=v_{0}=\omega A\cos \phi \\
&tg\phi =  \frac{\omega x_{0}}{v_{0}}\quad &A^2=x_{0}^2+ \frac{v_{0}^2}{\omega^2}
\end{align}
$$
Dalla legge oraria [[#^pp|(*)]]  si osserva che l'accelerazione è proporzionale allo spostamento, ma con segno negativo $a=-\omega^2x$. quindi:
- *Condizione Necessaria e Sufficiente per il Moto Armonico*
$$
\frac{d^2x(t)}{dt^2}+\omega ^2x(t)=0
$$

> [!hint] Dimostrazione Moto Armonico
> Per dimostrare che un moto è armonico basta quindi dimostrare che $-a$ è proporzionale a $x(t)$. Le uniche funzioni che riescono a soddisfare la condizione precedente sono $\sin$ e $\cos$; una sistema che obbedisce all'equazione del moto armonico si chiama *Oscillatore Armonico Semplice*.

## Moto Circolare
Un moto di dice *Circolare* se la sua traiettoria segue una circonferenza, la velocità cambia continuamente direzione e l'accelerazione centripeta è sempre diversa da 0.

![[Pasted image 20250312105844.png|center|500]]

- $\vec{a}= \vec{a}_{T}+\vec{a}_{N}$
- $\vec{a}_{N}\ne 0$
- $\vec{a}_{T}=0$
- $\phi= \frac{s(t)}{R}$

Il moto circolare può essere descritto facendo riferimento all'ascissa curvilinea $s(t)$ oppure utilizzando l'angolo $\theta(t)$, sotteso dall'arco $s(t)$ (quindi $\theta(t)=\frac{s(t)}{R}$).
Usare come variabile l'angolo $\theta(t)$ significa porsi in un sistema di coordinate polari con centro in $O$ in cui il moto avviene con $R=r(t)$, le Coordinate Polari sono:
- $x(t)=R\cos \phi(t)$
- $y(t)=R\sin \phi(t)$

Si definisco la *Velocità Angolare Media*
$$
\omega_{m}= \frac{\theta_{2}(t+\Delta t)-\theta_{1}(t)}{\Delta t}= \frac{\Delta \theta(t)}{\Delta t}
$$
e la *Velocità Angolare Istantanea* e considerando la relazione $s(t)=R\theta(t)$
$$
\omega= \frac{d\theta}{dt}= \frac{1}{R} \frac{ds}{dt}= \frac{v}{R}
$$
Si ottiene che la velocità angolare è proporzionale alla velocità con cui viene percorsa la circonferenza
$$
v=\omega R
$$
la relazione precedente si ottiene nel seguente modo:
$$\vec{v}= \frac{d\vec{r}}{dt}= \frac{dr}{dt}\hat{u}_{N}+ \frac{d \hat{u}_{r}}{dt}= \frac{dr}{dt}\hat{u}_{N}+ r \frac{d\theta}{dt}\hat{u}_{\theta}= \vec{v}_{r}+\vec{v}_{\theta}= R \frac{d\theta}{dt}= R\omega$$
### Moto Circolare Uniforme
In questo caso di moto uniforme, $v$ e $\omega$ sono costanti e le leggi orarie si ottengono integrando la velocità angolare istantanea
$$\begin{align}
&\theta(t)=\theta_{0}+\omega t\quad \theta=\theta_{0}\text{ per }t=0 \\
&s(t)=s_{0}+vt\quad s=s_{0} \text{ per } y=0
\end{align}$$
In questo caso l'accelerazione è costante e ortogonale alla traiettoria
$$
a=a_{N}= \frac{v^2}{R}=\omega^2R
$$
Questo moto è periodico, con
$$
T=\frac{2\pi R}{v}= \frac{2\pi}{\omega}
$$
### Moto Circolare Non Uniforme
Nel caso non uniforme, si ha anche il contributo dell'accelerazione tangenziale $a_{T}= \frac{dv}{dt}$. Siccome varia, in questo caso si può considerare l'*Accelerazione Angolare Media*
$$
\alpha_{m}= \frac{\Delta \omega}{\Delta t}
$$
Passando successivamente al limite per $\Delta\to 0$ di $\alpha_m$ si ottiene l'*Accelerazione Angolare Media*
$$
\alpha= \frac{d\omega}{dt}= \frac{d^2\theta}{dt^2}=\frac{1}{R} \frac{dv}{dt}= \frac{a_{T}}{R}
$$
Se si conosce $\alpha(t)$ si può integrare per ottenere 
$$
\omega (t)= \omega_{0}+\int_{t_{0}}^t\alpha(t)dt\quad \theta(t)=\theta_{0}+\int_{t_{0}}^t\omega(t)dt
$$
### Moto Circolare Uniformemente Accelerato
In questo caso particolare di moto circolare non uniforme si ha che $\alpha=\text{costante}$ e $a_{T}= \text{costante}$ e si avrà quindi
$$
\omega =\omega_{0}+\alpha t\quad \theta=\theta_{0}+\omega _{0}t+ \frac{1}{2}
\alpha t$$
Per quanto riguarda le due componenti dell'accelerazione
$$
a_{T}=\text{costante} = R\alpha\quad a_{N}= \omega^2R=(\omega_{0}+\alpha t)^2
$$
### Moto Circolare e Moto armonico
i moti dei un moto circolare uniforme proiettati sugli assi cartesiani sono
$$
x=R\cos \theta=R\cos(\omega t+\theta_{0})\quad y=R\sin \theta=R\sin(\omega t+\theta_{0})
$$
Il moto circolare può essere quindi scomposto in due moti armonici di eguale ampiezza, sfasati di $\frac{\pi}{2}$ e con lo stesso periodo del moto originale. Numericamente la velocità angolare coincide con la pulsazione (ma hanno significato fisico diverso)

... necessità approfondimento?
#### Notazione Vettoriale del Moto Circolare
Il vettore della velocità angolare $\vec{\omega}$ ha modulo $\omega= \frac{d\theta}{dt}$ ha direzione perperdicolare al piano e direzione tale che dall'estremo del vettore il moto appaia antiorario.
Quindi per definizione risulta
$$
\vec{v}= \vec{\omega}\times \vec{r}
$$
Questo è vero se si applica $\vec{\omega}$ applicata con $O$ centro della circonferenza, com $r=R$

![[Pasted image 20250313154913.png|center|450]]

Nel caso si applichi $\vec{\omega}$ in un altro punto $O'$ sempre sull'*Asse di Rotazione* (retta ortogonale al piano passante per il centro della circonferenza), la definizione precedente rimane comunque valida e il modulo vale ancora $v=\omega r\sin \phi=\omega R$
Tramite $\vec{\omega}$ e $\vec{\alpha}$ (ottenuta derivando nel tempo $\vec{\omega}$) si può esprimere l'accelerazione del moto circolare:
$$
\vec{a}=\frac{d\vec{v}}{dt}=\frac{d}{dt}(\vec{\omega}\times \vec{r})= \frac{d\omega}{dt}\times \vec{r}+\vec{\omega}\times \frac{d\vec{r}}{dt}=\vec{\alpha}\times \vec{r}+\vec{\omega}\times \vec{v}
$$
in cui:
- $\vec{\alpha}\times \vec{r}=\vec{a}_{T}$ con modulo $\alpha R$
- $\vec{\omega}\times \vec{v}=\vec{a}_{N}$ con modulo $\omega^2R$
Infine, se il moto è circolare uniforme allora $\vec{\omega}$ è un vettore costante anche in modulo, $\vec{\alpha}$ è nula e $\vec{a}=\vec{a}_{N}=\vec{\omega}\times \vec{\omega}\times r$
## Moto Parabolico

Si studia un punto $P$ lanciato dall'origine $O$ con una velocità iniziale $\vec{v}_{0}$, nello specificola traiettoria, altezza massima raggiunta r punto $G$ di atterraggio (gittata $OG$).

![[Pasted image 20250313172142.png|center|700]]

Il moto è caratterizzato da un'accelerazione costante $\vec{a}=-\vec{g}=-g\hat{u}_{y}$ con condizioni iniziali $\vec{r}=0$ e $\vec{v}=\vec{v}_{0}$ (al tempo $t=0$)
$$
\vec{v}(t)= \vec{v}_{0}+\int_{0}^t \vec{a}(t)dt=\vec{v}_{0}-g\hat{u}_{y}
$$
Si osserva che la velocità sta sempre nel piano individuato dai vettori costanti $\vec{v}_{0}$ e $\vec{g}$ (è il piano $x,y$).
Poiché $\vec{v}_{0}=v_{0}\cos \theta \hat{u}_{x}+v_{0}\sin \theta \hat{u}_{y}$
$$
\vec{v}(t)=v_{0}\cos \theta \hat{u}_{x}+(v_{0}\sin \theta-gt)\hat{u}_{y}
$$
La velocità dei moti proiettati sugli assi sono $v_{x}=v_{0}\cos \theta$ (costante) e $v_{y}=v_{0}\sin \theta-gt$ (accelerato), quindi le leggi orarie di questi moti sono
$$
x=v_{0}t\cos \theta\quad y=v_{0}t\sin \theta -\frac{1}{2}gt^2
$$
La traiettoria si calcola eliminando il tempo da $x(t)$ e $y(t)$, ottenendo così $t=\frac{x}{v_{0}}\cos \theta$ e 
$$
y(x)=x\tan\theta- \frac{g}{2v_{0}^2\cos^2\theta}x^2
$$
ed è un'equazione di una parabola.
La direzione del moto può essere calcolata come l'angolo $\phi$ che il vettore velocità forma con l'asse orizzontale
$$
\tan \phi= \frac{v_{x}}{v_{y}}=\tan \theta- \frac{g}{v_{0}\cos \theta}t=\tan \theta- \frac{g}{v_{0}^2\cos^2\theta}x
$$
La *Gittata* $OG$ so calcola imponendo $y(x)=0$, una soluzione sarà ovviamente $0$, mentre l'altra sarà
$$
X_{G}= \frac{2v_{0}^2\cos^2\theta \tan \theta}{g}= \frac{2v_{0}^2\cos \theta \sin \theta}{g}= \frac{v_{0}^2\sin 2 \theta}{g}=2x_{M}
$$
con $x_{M}=\frac{v_{0}^2\cos \theta \sin\theta}{g}$ coordinata del punto di mezzo del segmento $OG$, che coincide con il punto di altezza massima raggiunta nella parabola, pertanto
$$
y(x_{m})=y_{m}= \frac{v_{0^2}\sin^2\theta}{2g}
$$
Il *Tempo di Volo* $t_{G}$ si calcola come il tempo impiegato per percorrere $OG$ con velocità costante $v_{x}=v_{0}\cos \theta$
$$
t_{G}=2 \frac{x_{m}}{v_{0}}\cos \theta= \frac{2v_{0}\sin\theta}{g} = 2t_{m}
$$
$t_{G}$ coincide infatti col tempo necessario per salire all'altezza $y_{m}$ e ritornare al suolo.
Si nota infine che la velocità nel punto $G$ è la stessa in modulo, ma è orientata simmetricamente rispetto all'asse $x$
$$
v_{x}(t_{G})=v_{0}\cos \theta,\quad v_{y}(t_{G})=-v_{0}\sin \theta,\quad \tan \phi=-\tan \theta
$$

> [!hint] Gittata Maggiore
>  L'angolo che da la gittata maggiore è $45°$, infatti $\frac{dx_{G}}{dt}=0$ cioè $2v_{0}^2(-\sin^2\theta+\cos^2\theta)=0$ da $\theta=45°$ e $x_{G}= \frac{v_{0}^2}{g}$

---
## Velocità ed Accelerazione in Funzione della Posizione
Si osserva che se a un certo istante $t$ un punto occupa una determinata posizione $x$ con una velocità $v$, si può allora pensare di comporre una funzione $v(t)=v[x(t)]$ e si deriva nel tempo:
$$
a = \frac{dv}{dt}= \frac{d}{dt} v[x(t)]= \frac{dv}{dx} \frac{dx}{dt} \Longrightarrow a = v \frac{dv}{dx}, \ ax=vdv
$$
Integrando si ottiene
$$
\int_{x_{0}}^x a(x)dx = \int_{v_{0}}^v vdv\Longrightarrow \int_{x_{0}}^x a(x)dx = \frac{1}{2}v^2-\frac{1}{2}v^2_{0}
$$
con $v_{0}$ velocità nel punto $x_{0}$. Si applica questo risultato trovato ai casi studiati in precedenza:
- **Moto Uniformemente Accelerato:** l'accelerazione è una funzione costante $$ v^2(x)=v_{0}^2+2a(x-x_{0})$$
- **Caduta di un Corpo:** si considera $a=-g=-9.8 ms^{-2}$
	- Caduta da $h$ con $v_{0}=0$: $$ v(x)=\sqrt{ 2g(h-x) }$$
	- Caduta da $h$ con $v_{0}\ne 0$: $$ v(x)=\sqrt{ v_{1}^2 +2g(h-x)}$$
	- Lancio verso l'alto: $$v(x)\pm \sqrt{ v_{2}^2-2gx }$$
- **Moto Armonico:** considerando [[#^8f41d9|(*)]] si osserva che $a$ varia linearmente con la distanza dal centro di oscillazione (con segno opposto), quindi$$\begin{align}
 &\int _{x_{0}}^x a(x)dx=-\omega \int_{x_{0}}^x xdx=\frac{1}{2}\omega^2(x_{0}^2-x^2)=\frac{1}{2}v^2-\frac{1}{2}v_{0}^2  \\
&\Longrightarrow v^2(x)=v_{0}^2+\omega^2(x_{0}^2-x^2)
\end{align}$$con riferimento al centro ($x_{0}=0$ e $v_{0}=\omega A$) $$v^2(x)=\omega^2(A^2-x^2)$$
- **Moto Circolare:** nota la funzione $\alpha(\theta)$ si calcola l'incremento della velocità angolare in corrispondenza all'incremento $\theta-\theta_{0}$ $$\alpha= \frac{d\omega}{dt}=\frac{d\omega}{d\theta} \frac{d\theta}{dt}=\omega\frac{d\omega}{d\theta}\Longrightarrow \alpha d\theta=\omega d\omega\Longrightarrow \int_{\theta_{0}}^\theta \alpha(\theta)d\theta= \frac{1}{2}\omega^2-\frac{1}{2}\omega^2$$
