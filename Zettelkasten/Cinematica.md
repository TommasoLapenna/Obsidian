Tags: [[Fisica I]] [[University]] 

# Cinematica di un Punto Materiale
La parte della meccanica che descrive il moto di un corpo, indipendentemente dalle cause che lo determinano viene detta *Cinematica*

- **Punto Materiale:** Oggetto che ha dimensioni più piccole rispetto allo spazio studiato.
- **Traiettoria:** Luogo dei punti che il Punto Materiale porta avanti nel tempo

![[Pasted image 20250308154041.png]]
### Sistema di Riferimento
Il moto di un punto materiale è determinato se è nota la sua posizione in funzione del tempo in un determinato *Sistema di Riferimento*. 

![[Pasted image 20250308155417.png]]
### Coordinate Polari

![[Pasted image 20250308161613.png]]

Se la traiettoria è nota, è possibile esprimere la posizione di $P$ nello spazio attraverso l'*Ascissa Curvilinea* $s(t)$ (la parte rossa), ovvero ls lunghezza dell'arco di curva da un'origine arbitria $O$. Se si riesce a dare forma della traiettoria e la funzione $s(t)$ allora si può avere una descrizione completa del moto.
### Grandezze Fondamentali
Attraverso il concetto di derivata si studiano le variazioni di posizione e velocità del punto materiale lungo la traiettoria, si ricavano così le grandezze fondamentali delle cinematica che sono *Posizione*, *Velocità* ed *Accelerazione*.
Si definisce inoltre il concetto di *Quiete*, ovvero un tipo particolare di moto dove le coordinate restano costanti e quindi velocità ed accelerazione risultano nulle.
### Vettori
Grandezze con caratteristiche direzionali, composte da:
- Modulo
- Direzione
- Verso 
- Origine

![[Pasted image 20250308163103.png]]
### Raggio Vettore
Dato un sistema di riferimento cartesiano con origine $O$ e assi $x,y,z$, la posizione del punto può essere individuata attraverso il *Raggio Vettore* $r$, che congiunge l'origine $O$ col punto $P$.

![[Pasted image 20250308164730.png]]
##### Legge Oraria
Se si conosce la dipendenza la dipendenza dal tempo, allora di conoscono le leggi orarie di $\vec{r}=(x(t),y(t),z(t))$
## Velocità
Si considerano due posizioni occupate da $P$ al tempo $t$ e al tempo $t+\Delta t$, individuate dai vettori $\vec{r}(t)$ e $\vec{r}(t+\Delta t)=\vec{r}(t)+\Delta\vec{r}$.
$$ \Delta\vec{r} = \vec{r}(t+\Delta t)- \vec{r}(t)
$$
Si chiama vettore spostamento. Si definisce la *Velocità Media* su quest'ultimo:
$$\vec{v}_{m}= \frac{\Delta\vec{r}}{\Delta t}$$

![[Pasted image 20250308182412.png]]

Se $\Delta t\to 0$, allora si passa a variazioni infinitesime, si calcola così la velocità istantanea $$\vec{v}= \frac{d\vec{r}}{dt}$$
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

![[Pasted image 20250309113243.png]]

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
### Accelerazione
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

![[Pasted image 20250309125400.png]]

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
## Classificazioni di Moto
- $\vec{a}_{T}\ne 0\quad \vec{a}_{N}\ne 0$ **Moto Curvilineo Vario**
- $\vec{a}_{T}=0\quad \vec{a}_{N}\ne 0$ **Moto Curvilineo Uniforme**
-  $\vec{a}_{T}\ne 0\quad \vec{a}_{N}= 0$ **Moto Rettilineo Vario**
-  $\vec{a}_{T}=0\quad \vec{a}_{N} 0$ **Moto Rettilineo Uniforme**