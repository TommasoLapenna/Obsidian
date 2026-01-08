---
sticker: emoji//0036-fe0f-20e3
order: "7"
---
- [[#Definizione di Corpo Rigido|Definizione di Corpo Rigido]]
	- [[#Definizione di Corpo Rigido#Densità|Densità]]
	- [[#Definizione di Corpo Rigido#Calcolo dell Posizione del Centro di Massa|Calcolo dell Posizione del Centro di Massa]]
	- [[#Definizione di Corpo Rigido#Centro di Massa e Forza Peso|Centro di Massa e Forza Peso]]
- [[#Moto di un Corpo Rigido|Moto di un Corpo Rigido]]
	- [[#Moto di un Corpo Rigido#Moto di Traslazione|Moto di Traslazione]]
	- [[#Moto di un Corpo Rigido#Moto di Rotazione|Moto di Rotazione]]
	- [[#Moto di un Corpo Rigido#Moto Rototraslatorio|Moto Rototraslatorio]]
- [[#Equilibrio Statico del Corpo Rigido|Equilibrio Statico del Corpo Rigido]]
- [[#Rotazioni Rigide Attorno a un Asse Fisso in un Sistema di Riferimento Inerziale|Rotazioni Rigide Attorno a un Asse Fisso in un Sistema di Riferimento Inerziale]]
	- [[#Rotazioni Rigide Attorno a un Asse Fisso in un Sistema di Riferimento Inerziale#Momento Angolare e Momento di Inerzia|Momento Angolare e Momento di Inerzia]]
	- [[#Rotazioni Rigide Attorno a un Asse Fisso in un Sistema di Riferimento Inerziale#Equazione del Moto|Equazione del Moto]]
		- [[#Equazione del Moto#Caso di $\vec{L}$ Parallelo a $\vec{\omega}$|Caso di $\vec{L}$ Parallelo a $\vec{\omega}$]]
		- [[#Equazione del Moto#Calcolo dell'Energia Cinetica e del Lavoro|Calcolo dell'Energia Cinetica e del Lavoro]]
		- [[#Equazione del Moto#Caso di $\vec{L}$ non parallelo a $\vec{\omega}$|Caso di $\vec{L}$ non parallelo a $\vec{\omega}$]]
- [[#Momento d'Inerzia|Momento d'Inerzia]]
- [[#Teorema di Huygens-Steiner|Teorema di Huygens-Steiner]]
	- [[#Teorema di Huygens-Steiner#Teorema di Huygens-Steiner e Teorema di König|Teorema di Huygens-Steiner e Teorema di König]]
- [[#Moto di Puro Rotolamento|Moto di Puro Rotolamento]]
	- [[#Moto di Puro Rotolamento#Conservazione dell'Energia, Attrito Volvente|Conservazione dell'Energia, Attrito Volvente]]
- [[#Pendolo Composto|Pendolo Composto]]
- [[#Impulso Angolare e Momento dell'Impulso|Impulso Angolare e Momento dell'Impulso]]
- [[#Leggi di Conservazione nel Moto di un Corpo Rigido|Leggi di Conservazione nel Moto di un Corpo Rigido]]
	- [[#Leggi di Conservazione nel Moto di un Corpo Rigido#Conservazione dell Quantità di Moto|Conservazione dell Quantità di Moto]]
	- [[#Leggi di Conservazione nel Moto di un Corpo Rigido#Conservazione del Momento Angolare|Conservazione del Momento Angolare]]


## Definizione di Corpo Rigido
Un corpo rigido è un insieme di punti materiali sottoposti ad un'interazione mutua tale da mantenerli in posizione fissa l'uno rispetto all'altro. Si definisce un questo tipo di sistema come *sistema di punti materiali in cui le distanze tra tutte le possibili coppie di punti non possono variare*.

![[Pasted image 20250804164408.png|center|450]]

Lo studio del moto del corpo rigido viene attraverso un sistema di riferimento inerziale, oppure viene effettuato attraverso il **Sistema di Riferimento del Centro di Massa del Corpo Rigido** (non inerziale, con gli assi $(x',y',z')$ paralleli a quelli del sistema inerziale).

![[Pasted image 20250804164859.png|center|400]]

Nel sistema del centro di massa si può studiare solo il moto rispetto al centro di massa. Si può usare infine un terzo sistema di riferimento con gli assi solidali al corpo rigido $(x^*,y^*,z^*)$ in cui ciascun punto è fermo (può essere utile per visualizzare il moto del corpo rigido rispetto agli altri due sistemi di riferimento).

Il moto del corpo rigido è determinato dalle forze esterne, caratterizzate da una risultante $\vec{F}^{(E)}$ e da un momento risultante $M^{(E)}$ (grandezze indipendenti tra loro). Considerando che il lavoro delle forze interne è nullo (i punti mantengono le distanze invariate) si può allora concludere che la variazione dell'energia cinetica è uguale al lavoro delle sole forze esterne.

> [!info] Notazione
> Le forze interne non hanno alcun ruolo nella dinamica dei corpi rigidi, quindi si tralascia la notazione ${^{(E)}}$ per le grandezze $\vec{F}^{(E)}$, $\vec{M}^{(E)}$ e $M^{(E)}$. Si riscrivono le leggi fondamentali della dinamica dei corpi rigidi come segue:
> $$
> \vec{F}=m\vec{a}_{CM}\qquad \vec{M}= \frac{d\vec{L}}{dt}\qquad W=\Delta E_{k}
> $$

### Densità
La **Densità di Massa** ($\frac{kg}{m^3}$) di un corpo rigido è definita come rapporto tra la massa infinitesima e il volume da essa occupato
$$
\rho= \frac{dm}{dV}
$$
Si riscrive questa relazione come $dm=\rho \ dV$, che indica l'eventuale variazione della distribuzione di massa all'interno del corpo. La massa totale del corpo è quindi
$$
m=\int dm=\int_{V}\rho\ dV
$$
integrale esteso a tutto il copro.
Un copro nel quale la densità è costante si dice **Omogeneo**, per esse le relazioni diventano
$$
\rho=\frac{m}{V}\qquad m=\rho V
$$
Nei corpi non omogenei si definisce invece una densità media 
$$\overline \rho= \frac{m}{V}$$
valore medio nel volume $V$ della funzione $\rho$.

In casi particolari la massa può essere distribuita su una superficie $S$ invece che su un volume, si parla quindi di **Densità Superficiale** e **Densità Lineare**:
$$
\rho_{S}= \frac{dm}{dS}\Longrightarrow m=\int \rho_{S}\ dS\qquad \rho_{l}= \frac{dm}{dl}\Longrightarrow m=\int \rho_{l}\ dl
$$
la grandezza $v= \frac{1}{p}= \frac{dV}{dm}$ si chiama **Volume Specifico** (rappresenta il volume occupato dall'unità di massa).
### Calcolo dell Posizione del Centro di Massa
Ciascun elemento del corpo rigido, di massa $dm=\rho\ dV$ è assimilabile al punto, ciascuno dei quali è individuato da un raggio vettore $\vec{r}$. Il centro di massa è dato dalla somma degli infiniti vettori $\vec{r}\ dm$ divisa per la massa totale, ovvero da integrali estesi al volume del corpo in considerazione:
$$
\vec{r}_{CM}= \frac{\int \vec{r}\ dm}{\int dm}= \frac{\int_{V} \vec{r} \rho\ dV}{\int_{V}\rho \ dV}= \frac{1}{m}\int_{V} \vec{r} \rho\ dV
$$
Se il corpo è omogeneo ($\rho=$costante):
$$
\vec{r}_{CM}= \frac{\rho}{m}\int \vec{r}\ dV= \frac{1}{V}\int \vec{r}\ dV
$$
con $\vec{r}$ e $\rho$ funzioni delle coordinate, anche $dV$ è esprimibile in termini di coordinate ($dx\ dy\ dz$).

Se un corpo omogeneo è simmetrico a un punto, un asse o un piano, il centro di massa coincide col centro di simmetria, o punto dell'asse o del piano di simmetria.

![[Pasted image 20250804175451.png|center|500]]

### Centro di Massa e Forza Peso
Si considera un corpo continuo sottoposto alla forza peso, su ciascun elemento agisce la forza $\vec{g}\ dm$ e la risultante delle forze parallele è
$$
\int \vec{g}\ dm= \vec{g} \int dm = m\vec{g}
$$
Rispetto a un polo fisso, il polo risultante è
$$
\vec{M}= \int \vec{r}\times \vec{g}\ dm= \left( \int \vec{r}\ dm \right)\times \vec{g}= m\vec{r}_{CM}\times \vec{g}
= \vec{r}_{CM}\times m\vec{g}$$
La risultante della forza peso va applicata al centro di massa.
L'energia potenziale si ottiene integrando:
$$
E_{p}= \int g z\ dm= g\int z\ dm= mgz_{CM}
$$
Se il corpo è libero e agisce solo la forza peso, la traiettoria del centro di massa è verticale rettilineo oppure parabolica delle condizioni iniziali.
## Moto di un Corpo Rigido
Ci sono due tipi di moto che un corpo rigido può effettuare: moto di traslazione e rotazione.
### Moto di Traslazione
In questo caso tutti i punti descrivono traiettorie uguali (in generale curvilinee), percorse con la stessa velocità $\vec{v}$ che coincide con $\vec{v}_{CM}$. Pertanto, noto il moto del centro di massa è noto quello di qualsiasi altro punto.

![[Pasted image 20250804184047.png|center|500]]

La dinamica è quella di un punto materiale e non c'è movimento rispetto al centro di massa $$\vec{L}'=0\qquad E_{k}'=0$$
Le grandezze significative in una traslazione sono
$$
\begin{align}
&\text{Quantita' di moto}& &\vec{P}=m\vec{v}_{CM}& \\
&\text{Energia cinetica}& &E_{k}=E_{k,CM}=\frac{1}{2}mv^2_{CM}&
\end{align}
$$
L'equazione del moto di centro di massa è
$$
\vec{F}=m\vec{a}_{CM}
$$
La conoscenza del momento angolare si ricava dalla conoscenza della quantità di moto e dalla posizione del centro di massa:
$$
\vec{L}=\vec{L}_{CM}=\vec{r}_{CM}\times m\vec{v}_{CM}=\vec{r}_{CM}\times \vec{P}
$$
$\vec{L}$ non è quindi indipendente da $\vec{P}$. Di conseguenza anche l'equazione $\vec{M}= \frac{d\vec{L}}{dt}$ non aggiunge alcuna informazione.
### Moto di Rotazione
In questo caso tutti i punti descrivono un moto circolare, le traiettorie sono archi di circonferenza che stanno su piani paralleli tra loro e hanno il centro su uno stesso asse (asse di rotazione).

![[Pasted image 20250804185228.png|center|500]]

La rigidità del corpo implica che i punti abbiano in un dato istante la stessa velocità angolare $\vec{\omega}$ parallela all'asse di rotazione, mentre le velocità $\vec{v}_{i}$ dei singoli punti sono diverse a seconda della distanza $R_{i}$ dall'asse di rotazione.
Se l'asse di rotazione è fisso nel tempo $\vec{\omega}$ può cambiare solo di modulo e verso.
L'**Equazione Dinamica di Base del Moto di Rotazione** è
$$
\vec{M}= \frac{d\vec{L}}{dt}
$$

### Moto Rototraslatorio
Il moto rigido più generale è una rototraslazione: ogni spostamento infinitesimo può essere considerato come somma si una traslazione e di una rotazione infinitesime, individuate da $\vec{v}$ e $\vec{\omega}$, variabili nel tempo.
In generale si può dire che la velocità angolare $\vec{\omega}$ è indipendente dalla descrizione data al moto, mentre la velocità $\vec{v}$ ne dipende. In una generica rototraslazione i parametri $\vec{v}$ e $\vec{\omega}$ sono indipendenti tra loro.

![[Pasted image 20250804190916.png|center|500]]

---
## Equilibrio Statico del Corpo Rigido
Per un corpo rigido inizialmente in quiete si ha l'equilibrio statico se 
$$
\vec{F}=0\qquad \vec{M}=0
$$
Per ottenere l'equilibrio statico nel centro di massa ($\vec{v}_{CM}$) infatti si deve avere $\vec{F}=0$, mentre per l'assenza di moto rotatorio ($\vec{\omega}=0$) si deve avere $\vec{M}=0$.
Se $\vec{F}=0$, $\vec{M}$ è indipendente dal polo, quindi se nullo rispetto a un polo lo è per qualsiasi altro.

Si esamina l'equilibrio dei corpi appoggiati su un piano orizzontale:

![[Pasted image 20250804192446.png|center|500]]
1. Il centro di massa 
...
---
## Rotazioni Rigide Attorno a un Asse Fisso in un Sistema di Riferimento Inerziale
Si considera la rotazione di un corpo rigido attorno a un asse fisso in un sistema di riferimento inerziale. I punti dell'asse di rotazione sono punti fissi e possono essere utilizzati come poli per il calcolo dei momenti. L'asse di rotazione può essere esterno al corpo e il centro di massa non è detto che sia un punto dell'asse stesso.
Il vettore velocità angolare $\vec{\omega}$ ha direzione fissa (quella dell'asse di rotazione), mentre il modulo è in generale variabile nel tempo. Il verso di $\vec{\omega}$ indica il verso della rotazione. Se $\vec{\omega}$ varia, il vettore accelerazione angolare $\vec{\alpha}= \frac{d\vec{\omega}}{dt}$ è diverso da zero, ed è anch'esso parallelo all'asse di rotazione.
### Momento Angolare e Momento di Inerzia
Si assume $z$ come asse di rotazione, $\vec{\omega}$ è quindi parallelo all'asse $z$. Il polo del momento è il punto $O$ sull'asse $z$. il raggio vettore $\vec{r}$ dell'elemento di massa $dm$ forma un angolo $\theta$ con l'asse $z$ e un angolo $\frac{\pi}{2}$ con la velocità $\vec{v}$ di $dm$. 

![[Pasted image 20250804195815.png|center|400]]

Il momento angolare di $dm$ rispetto al polo $O$ è dato da $d\vec{L}=\vec{r}\times dm\vec{v}$, $d\vec{L}$ è ortogonale al piano individuato dai vettori $\vec{r}$ e $\vec{v}$, e forma un angolo $\frac{\pi}{2}-\theta$ con l'asse $z$.
Il modulo $d\vec{L}$ è
$$
dL=dm\ rv= dm\ rR\omega
$$
Si calcola adesso la proiezione del momento angolare $d\vec{L}$ sull'asse di rotazione, ovvero il **Momento Assiale**:
$$
dL_{z}= dL\cos\left( \frac{\pi}{2}-\theta \right)=dL\sin \theta=dm\ r\sin \theta R\omega= dmR^2\omega
$$
Il momento angolare del corpo è $\vec{L}=\int d\vec{L}$ in generale non è parallelo all'asse di rotazione, quindi non esiste una relazione di proporzionalità tra $\vec{L}$ e $\vec{\omega}$.
La proiezione di $\vec{L}$ sull'asse $z$ è
$$
L_{z}=\int dL_{z} = \int dm\ R^2\omega = I_{z}\omega
$$
^pp

il coefficiente $I_{z}$ è chiamato **Momento di Inerzia del Corpo Rispetto all'Asse $z$**, ed è definito come ^64919a
$$
I_{z}= \int dm \ R^2 = \int dm \ (x^2+y^2)
$$

> [!hint] Momento di Inerzia
> Il momento di inerzia non dipende quindi dalle masse $dm$ e dalla loro posizione rispetto all'asse di rotazione: non è una caratteristica del corpo che si può calcolare definitivamente, ma cambia se si usa un diverso asse di rotazione.
> La relazione di $L_{z}$ esprime allora che la componente del momento angolare rispetto all'asse di rotazione è proporzionale alla velocità angolare e dipende, tramite il coefficiente $I_{z}$, solo dalla forma del corpo e dalla posizione dell'asse rispetto al corpo.

Quindi il momento angolare di un corpo rigido che ruota rispetto a un asse non è in generale parallelo all'asse di rotazione e ruota intorno ad esso insieme al corpo.

La componente parallela all'asse può variare solo in modulo, è proporzionale a $\omega$ e non dipende dalla scelta del polo. La componente ortogonale invece all'asse $\vec{L}_{\perp }$ può variare in modulo e dipende dalla scelta del polo, essa è data dalla somma vettoriale dei contributi, ciascuno dei quali in modulo
$$
L_{\perp} =\int L\cos \theta =\int dm\ rR\omega \cos \theta
$$
![[Pasted image 20250804223701.png|center|350]]

Il momento angolare risulta parallelo all'asse di rotazione e quindi a $\vec{\omega}$, allora quando l'asse di rotazione è un'asse di simmetria del corpo, o più in generale quando l'asse di rotazione coincide con un asse principale di inerzia si ha
$$
\vec{L}=I_{z}\vec{\omega}\qquad L=L_{z}\qquad L_{\perp}=0
$$

^191c27

![[Pasted image 20250804224317.png|center|350]]

In tal caso, se $\vec{L}$ è variabile (solo in modulo e verso) le variazioni $\frac{d\vec{L}}{dt}$ sono anch'esse parallele a $\vec{\omega}$ e quindi il momento delle forze esterne che provoca è parallelo a $\omega$. 
Se invece $\vec{L}$ è costante, ovvero $\vec{\omega}$ è costante, il moto si svolge senza momento esterno.
### Equazione del Moto
#### Caso di $\vec{L}$ Parallelo a $\vec{\omega}$
Nel caso più semplice in cui $\vec{L}$ è parallelo a $\vec{\omega}$ valgono le [[#^191c27|relazioni precedenti]], per cui
$$
\frac{d\vec{L}}{dt}=\frac{d}{dt}(I_{z}\vec{\omega})= I_{z} \frac{d\vec{\omega}}{dt}=I_{z}\vec{\alpha}
$$
e il momento delle forze si scrive come

> [!gray] Equazione del Moto di Rotazione
> $$
> \vec{M}=I_{z}\vec{\alpha}
> $$
> Questa relazione è detta **Equazione del Moto di Rotazione**: la conoscenza del momento delle forze esterne permette di calcolare l'accelerazione angolare, se è noto il momento d'inerzia (sia $\vec{\alpha}$ che $\vec{M}$ sono paralleli all'asse di rotazione, cioè a $\vec{\omega}$).

Si può quindi ottenere la legge oraria (note la posizione angolare e velocità angolare iniziali):
$$
\alpha=  \frac{M}{I_{z}}\Longrightarrow \omega(t)=\omega_{0}+\int_{0}^t \alpha\ dt\Longrightarrow \theta(t)=\theta_{0}+\int_{0}^t \omega\ dt
$$
- Se $M=0$ il corpo resta in quiete o ruota in modo uniforme intorno all'asse di rotazione: $$
\alpha=0\qquad \omega=\omega_{0}\qquad \theta=\theta_{0}+\omega t
$$
- Se $M$ è costante la rotazione del corpo rigido intorno all'asse avviene in modo uniformemente accelerato:
$$
\alpha=\text{costante}\qquad \omega=\omega_{0}+\alpha t\qquad \theta=\theta_{0}+\omega_{0}t+\frac{1}{2}\alpha t^2
$$
- Con $M$ generico si ha $\alpha=\alpha(t)$
#### Calcolo dell'Energia Cinetica e del Lavoro
L'**Energia Cinetica del Corpo Rigido nel Moro di Rotazione** è data da
$$
E_{k}=\int \frac{1}{2}dmv^2=\int \frac{1}{2}dm\omega^2R^2= \frac{1}{2}\omega^2 \int dmR^2= \frac{1}{2}I_{z}\omega^2
$$
Anche l'energia cinetica dipende dal momento di inerzia del corpo rispetto all'asse di rotazione.
Se il momento angolare è parallelo a $\vec{\omega}$, dalle [[#^191c27|relazioni precedenti]] si ha
$$
E_{k}= \frac{L^2}{2I_{z}}
$$
Quando un corpo rigido, in quiete o rotazione con velocità angolare $\omega_{in}$, viene portato a ruotare con velocità angolare $\omega_{fin}$ grazie all'applicazione di un momento esterno, l'energia cinetica subisce una variazione ed è stato quindi compiuto un lavoro:
$$
W=\Delta E_{k}= \frac{1}{2} I_{z}\omega_{fin}^2-\frac{1}{2}I_{z}\omega^2_{in}
$$
Si ricava adesso la relazione tra momento e lavoro (sempre nel caso di $\vec{L}$ è parallelo a $\vec{\omega}$), prendendo la forma infinitesima del lavoro si ottiene
$$
dW= dE_{k}= I_{z}\omega \ d\omega= I_{z} \frac{d\theta}{dt} \alpha\ dt= I_{z}\alpha\ d\theta=M\ d\theta
$$
Integrando dalla posizione iniziale a quella finale si ottiene
$$
W=\int_{0}^\theta M\ d\theta
$$
Per eseguire il calcolo si deve conoscere la dipendenza del momento dall'angolo.

La potenza istantanea è data da
$$\mathcal P= \frac{dW}{dt}= M \frac{d\theta}{dt}=M\omega$$
#### Caso di $\vec{L}$ non parallelo a $\vec{\omega}$
In questo caso $\vec{L}$ ruota attorno all'asse di rotazione descrivendo un **Moto di Precessione** ed in particolare un moto di precessione uniforme se la velocità angolare $\vec{\omega}$ è costante.
L'equazione del moto ha due componenti:
$$
\frac{d\vec{L}_{z}}{dt}=\vec{M}_{z}\qquad \frac{d\vec{L}_{\perp}}{dt}=\vec{M}_{\perp}
$$
Essendo $\vec{M}_{z}$ e $\vec{M}_{\perp}$ i vettori componenti del momento delle forze esterne $\vec{M}$ parallelo e perpendicolare all'asse di rotazione.
In base alla [[#^pp|relazione]] si ottiene:
$$
I_{z}\alpha= M_{z}
$$
dalla quale si ottiene la legge oraria descritta in precedenza, in particolare se $M_{z}=0$ il corpo ruota con velocità angolare costante e $L_{z}$ è costante. Invece $\vec{L}_{\perp}$ in ogni caso ruota assieme al corpo, potendo restare in modulo costante se $\omega$ è costante (ma variando sempre direzione), le variazioni di $\vec{L}_{\perp}$ sono regolate da $\vec{M}_{\perp}$.

> [!example]+ Esempio:
> Si considera un corpo rigido formato da due masse eguali $m$ collegate ad un'asta rigida che forma un angolo $\theta$ con l'asse di rotazione, esso ruota con una velocità angolare $\vec{\omega}$ attorno all'asse. Questo moto è dovuto a un momento $M_{z}$, eventualmente nullo se $\vec{\omega}$ è costante.
> Le due masse descrivono un moto circolare e per questo sono necessarie due forze centripete $F_{c}$, esercitate dall'asta di collegamento. Queste due forze costituiscono una coppia e si dimostra che il momento è proprio uguale a $\frac{d\vec{L}_{\perp}}{dt}$. Le due forze peso hanno momento nullo rispetto al polo $O$.
> Un effetto del momento delle forze centripete è quello di far cambiare direzione all'asse fi rotazione e quindi occorrono opportuni supporti per mantenere l'asta in posizione verticale.
> Se fosse $\theta= \frac{\pi}{2}$, $\vec{L}$ sarebbe parallelo a $\vec{\omega}$ e $\vec{L}_{\perp}$ sarebbe nullo e questi effetti non si verificherebbero.
>
>![[Pasted image 20250805004545.png|center|400]]

Per quanto riguarda l'energia cinetica e il lavoro, valgono le espressioni generali, cambia solo il legame tra l'energia cinetica e il momento angolare, che diventa
$$
E_{k}= \frac{L^2_{z}}{2 I_{z}}
$$
e cambia anche l'espressione del lavoro tramite il momento delle forze esterne
$$
W=\int M_{z}\ d\theta
$$
---
## Momento d'Inerzia
Il momento d'inerzia è definito come (esplicitando la dipendenza dalla densità del corpo):
$$
I=\int R^2\ dm=\int_{V}\rho R^2\ dV= \int_{V}\rho(x^2+y^2)\ dV
$$
con $R$ distanza dell'elemento di massa $dm$ dall'asse $z$ (assunto come asse di rotazione).

![[Pasted image 20250805010932.png|center|350]]

> [!hint] Dipendenza dalla Forma
> A parità di massa, un elemento infinitesimo $dm$ contribuisce al momento d'inerzia (e quindi all'inerzia rotazionale) molto più se è lontano rispetto all'asse di rotazione che se è vicino ad esso. Il contributo della massa invece è indipendente dalla posizione.
> Quindi l'inerzia rotazionale di un corpo rigido dipende anche dalla forma (ossia dalla distribuzione della masse rispetto all'asse), oltre che dalla massa totale.

![[Pasted image 20250805011557.png|center|800]]

In tutte le forme, il momento d'inerzia ha un'espressione del tipo $I=fmd^2$, con $m$ massa, $d$ dimensione significativa e $f$ fattore numerico legato alla struttura, pertanto il momento d'inerzia si può sempre riscrivere come
$$
I=mk^2\qquad k=\sqrt{ f\ d }=\sqrt{ \frac{I}{m} }
$$
con $k$ **Raggio Giratore** del corpo (rappresenta la distanza dall'asse a cui si deve porre un punto per avere lo stesso momento di inerzia $I$).
## Teorema di Huygens-Steiner
Esiste un teorema che semplifica il calcolo dei momento di inerzia quando si utilizza un'asse di rotazione diverso da un anno di simmetria

> [!gray] Teorema di Huygens-Steiner
> Il momento d'inerzia di un copro di massa $m$ rispetto a un asse che si trova a distanza $a$ dal centro di massa del corpo è dato da
> $$
> I=I_{c}+ma^2
> $$
> con $I_{c}$ è il momento di inerzia del corpo rispetto a un asse parallelo al primo passante per il centro di massa.
> 
> **Dimostrazione:**
> Si considerano due sistemi di riferimento con assi paralleli  e si calcola l'asse d'inerzia rispetto all'asse $z$
> 
> ![[Pasted image 20250806110024.png|center|350]]
> 
> $$
> x=x'\qquad y=y'+a\qquad z=z'
> $$
> Il momento d'inerzia di un generico elemento di massa $dm$ rispetto all'asse $z$ è
> $$
> dm(x^2+y^2)
> $$
> Integrando su tutti i $dm$ e utilizzando le formule di trasformazione si ottiene
> $$
> I_{z}= \int dm(x^2+y^2)=\int dm[x'^2+(y'+a)^2]=\int dm(x'^2+y'^2)+a^2\int dm+2a\int dm\ y'
> $$
> 1. Il primo termine è il momento d'inerzia del corpo rispetto all'asse $z'$
> 2. Il secondo termine è $ma^2$
> 3. Il terzo termine è nullo in quanto $\int dm \ y'=my'_{CM}$ e con $y'_{CM}$ nulla
> 

> [!example] Esempio:
> Momento d'inerzia di un disco rispetto a un asse ortogonale e passante per il bordo vale
> $$
> I= \frac{1}{2}mR^2+mR^2=\frac{3}{2}mR^2
> $$
> Momento d'inerzia di un'asta lunga $d$ rispetto a un asse passante per un estremo e ortogonale all'asta si scrive
> $$
> I=\frac{1}{12}md^2+m\left( \frac{d}{2} \right)^2= \frac{1}{3}md^2
> $$

### Teorema di Huygens-Steiner e Teorema di König
Si applica il teorema di Huygens-Steiner alla formula dell'energia cinetica di rotazione e si ottiene
$$
E_{k}= \frac{1}{2}(I_{z'}+ma^2)\omega^2= \frac{1}{2}I_{z'} \omega^2+\frac{1}{2}ma^2\omega^2
$$
$I_{z'}$ è il momento d'inerzia rispetto a un asse passante per il centro di massa e parallelo all'asse $z$, mentre $a$ è la distanza tra i due assi.
$a\omega$ rappresenta la velocità $v_{CM}$ che percorre una traiettoria circolare di raggio $a$ rispetto all'asse $z$, quindi
$$
E_{k}= \frac{1}{2}I_{z'}\omega^2+\frac{1}{2}mv^2_{CM}
$$
Quindi quando il centro di massa non è sull'asse di rotazione, l'energia cinetica è data dalla somma di $E_{k}'= \frac{1}{2}I_{z}\omega$ e di $E_{k,CM}= \frac{1}{2}mv^2$

---
## Moto di Puro Rotolamento
Si considera un corpo di forma cilindrica o sferica che si trova su un piano e si muove rispetto ad esso. Se le velocità di tutti i punti sono eguali tra loro e parallele al piano, si ha un moto di traslazione e il punto striscia sul piano. Se invece il corpo rotola, il punto di contatto $C$ ha velocità nulla rispetto al piano: allora il corpo rotola e striscia. Infine se il punto di contatto ha velocità nulla, si ha un **Moto di Puro Rotolamento**.

![[Pasted image 20250806113210.png|center|400]]

In ogni intervallo di tempo $dt$ il corpo che rotola (senza strisciare) può venire considerato come se ruotasse con velocità angolare $\vec{\omega}$ rispetto ad un asse fisso passante per il punto di contatto di $C$ e ortogonale al piano. La velocità di ogni punto del corpo è di conseguenza ortogonale alla linea che congiunge il punto $C$ ed è in modulo proporzionale alla distanza da $C$: $v_{P}=\omega|PC|$.
In un intervallo $dt$ successivo il contatto avviene in un altro  punto $C'$ (infinitamente vicino a $C$) e si ripete la rotazione attorno a un altro asse fisso passante per $C'$ e così via.

È evidente che per tenere il punto di contatto $C$ fermo nel punto $dt$ deve agire una forza di attrito statico che si esercita tra il piano e il corpo.

La velocità del punto $C$, distante $r$ dal centro di massa, si può scrivere $\vec{v}_{C}=\vec{v}_{CM}+\vec{\omega}\times \vec{r}$ (somma della velocità del centro di massa e della velocità di $C$ relativa al centro di massa).

La condizione di puro rotolamento è $\vec{v}_{C}=0$ e quindi
$$
\vec{v}_{CM}=-\vec{\omega}\times \vec{r}
$$
![[Pasted image 20250806114410.png|center|400]]

$\vec{\omega}\times \vec{r}$ risulta opposto a $\vec{v}_{CM}$. In modulo si ha
$$
v_{CM}=\omega r\Longrightarrow a_{CM}=\alpha r
$$
Nel moto di puro rotolamento esiste una precisa relazione tra velocità con cui avanza il centro di massa e la velocità angolare: queste due grandezze non sono indipendento.

Si tratta adesso il caso di un corpo di massa $m$ e raggio $r$ che rotola senza strisciare su una superficie sotto l'azione di una forza orizzontale $\vec{F}$ costante applicata all'asse. Sul corpo agiscono anche la forza peso $m\vec{g}$ e la reazione vincolare del piano $\vec{R}$ (che ha una componente normale $N$) e la forza di attrito statico $\vec{f}$. 

![[Pasted image 20250806121349.png|center|400]]

La legge del moto del centro di massa è
$$
\vec{F}+\vec{R}+m\vec{g}=m\vec{a}_{CM}
$$
che proiettata sugli assi $x$ e $y$ da rispettivamente
$$
F-f=ma_{CM}\qquad N-mg=0\Longrightarrow N=mg
$$
Il teorema del moto angolare, scelto il centro di massa $O$ come polo, si scrive
$$
\vec{M}=\vec{r}\times \vec{f}=I\vec{\alpha}\Longrightarrow rf=I\alpha= I \frac{a_{CM}}{r}
$$
Facendo sistema tra questa equazione e l'equazione del moto lungo l'asse $x$ si ricavano
$$
a_{CM}= \frac{F}{m\left( 1+ \frac{I}{mr^2} \right)}\qquad f= \frac{F}{1+ \frac{mr^2}{I}}
$$
$f$ non può assumere qualsiasi valore: essa non può superare la massima forza di attrito statico, ovvero deve essere soddisfatta la disuguaglianza
$$
f\le\mu_{s}N=\mu_{s}mg \Longrightarrow F\le \mu_{s}mg \left( 1+\frac{mr^2}{I} \right)=F_{lim}
$$
pertanto il moto può essere di puro rotolamento solo se la forza applicata non supera il valore limite, altrimenti il corpo rotola e striscia contemporaneamnte.

Invece di spingere il corpo, si può applicare all'asse un momento costante $\vec{M}$ esterno

![[Pasted image 20250806122908.png|center|400]]

Dalle equazioni
$$
\vec{R}+m\vec{g}=m\vec{a}_{CM}\qquad \vec{M}+\vec{r}\times \vec{f}=I\vec{\alpha}
$$
si ricava
$$
\begin{align}
& N=mg \qquad f=m\vec{a}_{CM}\qquad M-rf=I \frac{a_{CM}}{r}  \\
&\Longrightarrow a_{CM}= \frac{1}{m} \frac{F+ \frac{M}{r}}{1+ \frac{I}{mr^2}}\qquad f= \frac{M}{r\left( 1+\frac{I}{mr^2} \right)}
\end{align}
$$
Si deve anche verificare che
$$
f\le \mu_{s}N=\mu_{s}mg\Longrightarrow M\le \mu_{s}mgr\left( 1+ \frac{I}{mr^2} \right)= M_{\lim_{ n \to \infty } }
$$

> [!hint] Osservazione
> Mentre sotto l'azione di $\vec{F}$ la reazione tangente $\vec{f}$ si oppone al moto, a causa dell'azione di $\vec{M}$, $\vec{f}$ favorisce il moto, anzi è la forza che causa l'accelerazione del centro di massa: quando un motore fa girare una ruota, è l'attrito col suolo che la spinge avanti.

Nel caso più generale dove si ha contemporaneamente l'azione di una forza e un momento non si può stabilire a priori il verso di $f$, ma rimane comunque parallela e concorde all'asse $x$. Le equazioni del moto sono
$$
F+f=ma_{CM}\qquad M-rf= I \frac{a_{CM}}{r}\quad \Longrightarrow\quad a_{CM}= \frac{1}{m} \frac{F+\frac{M}{r}}{1+ \frac{I}{mr^2}}\qquad f= \frac{\frac{M}{r}- \frac{I}{mr^2}F}{1+\frac{I}{mr^2}}
$$

> [!info] Conclusione
> Nel rotolamento di un corpo rigido è possibile, con opportuni valori delle forze e dei momenti esterni, realizzare le condizioni per cui la reazione del piano è tale da tenere fermo il punto di contatto, così che il corpo rotola senza strisciare. Il puro rotolamento è la situazione che si cerca sempre di ottenere quando un corpo deve rotolare, ad esempio per le ruote.

### Conservazione dell'Energia, Attrito Volvente
Al moto di puro rotolamento, sotto l'azione di forze conservative (come la forza peso) è possibile applicare la legge di conservazione dell'energia meccanica: infatti la forza di attrito che normalmente è diversa da 0, agisce su un punto fermo e quindi con lavoro nullo.

Nei casi più generali e pratici, agisce sempre un attrito che si oppone al rotolamento fino a fermarlo, e questo attrito è chiamato **Attrito Volvente** (o di rotolamento). Questo attrito viene attribuito alla deformazione locale del piano o del corpo ed è schematizzato come l'azione di un momento $M_{v}=hmg$ che si oppone al moto ($h$ coefficiente di attrito volvente). Tuttavia questo valore viene trascurato.

---
## Pendolo Composto
Si chiama pendolo composto (o fisico) ogni corpo che possa oscillare, per azione del suo peso, in un piano verticale attorno ad un asse orizzontale non passante per il centro di massa.

![[Pasted image 20250806152537.png|center|350]]

Se si sposta il pendolo composto dalla posizione di equilibrio statico ($\theta=0$, centro di massa sulla retta verticale passante per $O$), l'azione della forza peso è tale da riportare il pendolo verso la posizione di equilibrio.
Il momento della forza peso, che agisce come un momento di richiamo verso $\theta=0$, è parallelo all'asse di rotazione (asse $z$) e vale $M_{z}=-mgh \sin \theta$. Se non esistono altri momenti di forze di attrito nella rotazione attorno all'asse l'equazione del moto è
$$
\frac{dL_{z}}{dt}= I_{z}\alpha= I_{z} \frac{d^2\theta}{dt^2}=-mgh\sin \theta \Longrightarrow \frac{d^2\theta}{dt^2}+\frac{mgh}{I_{z}}\sin \theta=0
$$
Se l'ampiezza delle oscillazioni è piccola ($\theta\approx \sin \theta$) e si ottiene
$$
\frac{d^2\theta}{dt^2}+ \frac{mgh}{I_{z}}\theta=0
$$
che è l'equazione del moto ed ha soluzione
$$
\theta=\theta_{0}\sin(\Omega T+\phi)
$$
La pulsazione $\Omega= \sqrt{ \frac{mgh}{I_{z}} }$ e il periodo vale
$$
T=\frac{2\pi}{\Omega}=2\pi \sqrt{ \frac{I_{z}}{mgh} }=2\pi \sqrt{ \frac{l}{g} }
$$
con $l= \frac{I_{z}}{mh}$ lunghezza ridotta del pensolo composto.

Per oscillazioni grandi il pendolo si muove ancora di moto periodico, ma non armonico.

Si osserva che, posto $h'=\frac{I_{c}}{mh}$ ovvero $I_{c}=mhh'$ si ha
$$
l= \frac{I_{z}}{mh}= \frac{I_{c}+mh^2}{mh}= \frac{I_{c}}{mh}+h=h'+h>0
$$
$l$ individua rispetto ad $O$ un punto $O'$ distante $h'$ dal centro di massa. Se si fa oscillare il pendolo rispetto ad un asse orizzontale passante per $O'$ (parallelo all'asse precedente) la distanza tra il centro di oscillazione e il centro di massa è $h'$. Si chiama $I'$ il momento d'inerzia del corpo rispetto al nuovo asse di rotazione, la nuova lunghezza ridotta è
$$
l'= \frac{I'}{mh'}= \frac{I_{c}+mh'^2}{mh'}= \frac{mhh'+mh'^2}{mh'}=h+h'=l
$$
uguale alla precedente. Di conseguenza il periodo di oscillazione è lo stesso sia che il pendolo venga fatto oscillare attorno a $O$ o $O'$. 
I due assi passanti per $O$ e $O'$ si chiamano **Assi Reciproci** e, una volta individuata la distanza $l$ tra i due assi, la misura del periodo di oscillazione permette di ricavare il valore di $g$ .

Pendolo Reversibile di Kater ...

---
## Impulso Angolare e Momento dell'Impulso
Si può dedurre che l'azione di un momento durante un intervallo di tempo causa una variazione finita del momento angolare

> [!gray] Teorema dell'Impulso Angolare
> $$
> \int_{t_{1}}^{t_{2}}\vec{M}\ dt= \vec{L}(t_{2})-\vec{L}(t_{1})=\Delta \vec{L}
> $$
> L'integrale del momento si chiama **Impulso Angolare** o **Impulso del Momento** e questa relazione si chiama *teorema dell'impulso angolare*

Se si prende un corpo rigido e per metterlo in rotazione rispetto ad un asse fisso si applica una forza intensa e molto breve (forza impulsiva). Si prende come polo il centro $O$ di sospensione del corpo
$$
\int \vec{M}\ dt = \int (\vec{r} \times \vec{F})\ dt= \vec{r}\times \int \vec{F}\ dt= \vec{r}\times \vec{J} =\Delta \vec{L}
$$
![[Pasted image 20250806162924.png|center|350]]

È possibile portare fuori dall'integrale il termine $\vec{r}$ in quanto non varia nell'integrale considerato. La grandezza $\vec{r} \times \vec{J}$ è chiamata **Momento dell'Impulso** della forza. Si inoltre osserva che nell'integrale non appaiono le forze di vincolo (momento nulle applicato al polo) e la forza peso (impulso angolare trascurabile).

> [!gray] Teorema del Momento dell'Impulso
> L'applicazione dell'impulso provoca, oltre a una variazione di quantità di moto, una variazione di momento angolare eguale al momento dell'impulso. Questo risultato è noto come *Teorema del Momento dell'Impulso*.

## Leggi di Conservazione nel Moto di un Corpo Rigido
### Conservazione dell Quantità di Moto
Se la risultante delle forze esterne è nulla, il centro di massa si muove di moto rettilineo uniforme, ma non è detto che il moto dei singoli punti sia traslatorio uniforme (come ad esempio un corpo che compie un moto di puro rotolamento oppure un punto di un disco).

![[Pasted image 20250806165101.png|center|400]]

Assumendo come polo un punto fisso in un sistema di riferimento inerziale o il centro di massa, se $\vec{M}=0$ il momento angolare $\vec{L}$ resta costante in modulo, direzione e verso. Questo però non comporta $\vec{\omega}$ costante, in quanto non è detto che il moto di rotazione avvenga attorno a un asse principale di inerzia, cioè che sia $\vec{L}=I \vec{\omega}$.

### Conservazione del Momento Angolare

> [!example]+ Esempio:
> Sono di particolare interesse i casi in cui si ha conservazione del momento angolare in un sistema formato da più corpi rigidi: si prendono per esempio due sfere uguali con massa $m$ e raggio $r$, unite da un'asta di lunghezza variabile e di momento d'inerzia trascurabile.
> 
> ![[Pasted image 20250806172520.png|center|250]]
> 
> Le due sfere sono poste inizialmente poste ad una distanza $2r_{1}\gg r$ e sono in rotazione con velocità angolare $\vec{\omega}_{1}$ attorno ad un asse verticale equidistante dalle sfere. Rispetto al centro di massa (posto sull'asse di rotazione) tutti i momenti esterni sono nulli, pertanto il momento angolare resta comunque
> $$
> L=I_{1}\omega_{1}=\text{costante}\qquad I_{1}=2\left[ \frac{2}{5} mr^2+m(r+r_{1})^2\right]\simeq 2mr^2_{1}
> $$
> Si riduce adesso la distanza tra le due sfere, avvicinandole da $2r_{1}$ a $2r_{2}$ ($r_{2}<r_{1}$), il momento d'inerzia diventa $I_{2}=2mr^2<I$. 
> 
> ![[Pasted image 20250806173401.png|center|250]]
> 
> Le forze applicate per l'avvicinamento delle sfere, essendo dirette verso l'asta, hanno momento nullo rispetto al centro di massa e quindi $L_{2}=L_{1}$:
> $$
> 2mr_{2}^2\omega_{2}=2mr_{1}^2\omega_{1}\Longrightarrow \omega_{2}= \frac{r^2_{1}}{r_{2}^2}\omega_{1}>\omega_{1}
> $$
> La variazione del momento d'inerzia porta a una variazione della velocità angolare, anche se $\vec{L}$ è costante.

Per quanto riguarda invece l'aspetto energetico di questo caso, c'è una variazione di energia cinetica, uguale al lavoro delle forze centripete.

Si può verificare l'indipendenza della legge di conservazione del momento angolare da quella dell'energia, per il calcolo del lavoro si ha
$$
W=\Delta E_{k}=E_{k,fin}-E_{k,in}= \frac{L^2}{2I_{fin}}- \frac{L^2}{2I_{in}}
$$
La legge di conservazione dell'energia meccanica del moto è valida quando non ci sono attriti (o quando questo non compie lavoro, come succede anche per la reazione vincolare) o forze di attrito che agiscono sull'asse di rotazione.

> [!example]+ Esempio:
> Si considera un asta di massa $m$ e lunghezza $l$ che può ruotare su un suo estremo.
> 
> ![[Pasted image 20250806175203.png|center|300]]
> 
> Se l'asta viene lasciata cadere, con velocità iniziale nulla, quando dalla posizione orizzontale raggiunge quella verticale ha una velocità angolare $\omega$ e il suo centro di massa ha velocità $v_{CM}$, le quali si possono calcolare utilizzando la conservazione dell'energia meccanica
> $$
> E_{in}=mgl= E_{fin}= \frac{1}{2}I\omega^2+mg \frac{l}{2}
> $$
> con $I= \frac{1}{3}ml^2$ 
> $$
> \omega= \sqrt{ \frac{3g}{l} }\qquad v_{cm}=\omega  \frac{l}{2}= \sqrt{ \frac{3gl}{l} }
> $$