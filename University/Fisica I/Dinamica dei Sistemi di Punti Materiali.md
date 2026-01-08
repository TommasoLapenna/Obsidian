---
sticker: emoji//0035-fe0f-20e3
Order: "6"
order: "6"
---
- [[#Sistemi di Punti|Sistemi di Punti]]
- [[#Centro di Massa di un Sistema di Punti|Centro di Massa di un Sistema di Punti]]
- [[#Conservazione della Quantità di Moto|Conservazione della Quantità di Moto]]
- [[#Teorema del Momento Angolare|Teorema del Momento Angolare]]
- [[#Conservazione del Momento Angolare|Conservazione del Momento Angolare]]
- [[#Sistema di Riferimento del Centro di Massa|Sistema di Riferimento del Centro di Massa]]
- [[#Teorema di König|Teorema di König]]
	- [[#Teorema di König#Teorema di König per il Momento Angolare|Teorema di König per il Momento Angolare]]
	- [[#Teorema di König#Teorema di König per l'Energia Cinetica|Teorema di König per l'Energia Cinetica]]
- [[#Teorema dell'Energia Cinetica|Teorema dell'Energia Cinetica]]
- [[#Proprietà dei Sistema di Forze Applicate a Punti Diversi|Proprietà dei Sistema di Forze Applicate a Punti Diversi]]
	- [[#Proprietà dei Sistema di Forze Applicate a Punti Diversi#Sistema di Forze Parallele|Sistema di Forze Parallele]]


## Sistemi di Punti
Si considera un sistema di $n$ punti materiali, interagenti tra loro e col restante universo. La forza $\vec{F}_{i}$ agente sull'$i-$esimo punto si può pensare come la risultante delle:
- **Forze Esterne** agenti sul punto $\vec{F}_{i}^{(E)}$
- **Forze Interne** esercitate dagli altri $n-1$ punti al sistema $\vec{F}_{i}^{(I)}$
$$
\vec{F}_{i}=\vec{F}_{i}^{(E)}+\vec{F}_{i}^{(I)}
$$

Si deve ovviamente prendere in considerazione la terza legge di Newton, infatti se il punto $i$ esercita sul punto $j$ una forza $\vec{F}_{ij}$, allora si avrà anche una forza $\vec{F}_{ji}$ esercitata dal punto $j$ su $i$ (stessa direzione e modulo, ma verso opposto).

![[Pasted image 20250728164522.png|center|400]]

In generale, la risultante $\vec{F}_{c}^{(I)}$ delle forza agenti sull'$i-$esimo punto è diversa da zero, ma la risultante di tutte le forze interne del sistema è nulla (per via del principio di azione e reazione)
$$
\vec{F}^{(I)}=\sum_{i}\vec{F}_{i}^{(I)}=\sum_{i,j}\vec{F}_{i,j}=0\qquad i=1,\ldots,n\quad j=1,\ldots,n\quad i\ne j
$$

![[Pasted image 20250728165116.png|center|300]]

Il principio di azione e reazione si applica anche con le forze esterne e sull'universo circostante, ma quest'ultimo non è di initeresse.

Si considerano un punto $P_{i}$ di massa $m_{i}$ sottoposto ad una forza $\vec{F}_{i}$, si hanno quindi le grandezze misurate in un sistema di riferimento inerziale

| Posizione            | $$\vec{r}_{i}$$                                    |
| -------------------- | -------------------------------------------------- |
| **Accelerazione**    | $\vec{a}_{i}=\frac{\vec{F}_{i}}{m_{i}}$            |
| **Momento Angolare** | $$\vec{L}_{i}=\vec{r}_{i}\times m_{i}\vec{v}_{i}$$ |
| **Velocità**         | $$\vec{v}_{i}$$                                    |
| **Quantità di Moto** | $$\vec{p}_{i}=m_{i}\vec{v}_{i}$$                   |
| **Energia Cinetica** | $$E_{k,i}= \frac{1}{2}mv_{i}^2$$                   |
Per il sistema complessivo di punti si possono inoltre definire le grandezze

| Quantità di Moto Totale     | $$\vec{P}=\sum_{i}\vec{P}_{i}=\sum_{i}m\vec{v}_{i}$$                         |
| --------------------------- | ---------------------------------------------------------------------------- |
| **Momento Angolare Totale** | $$\vec{L}=\sum_{i}\vec{L}_{i}=\sum_{i}(\vec{r}_{i}\times m_{i}\vec{v}_{i})$$ |
| **Energia Cinetica Totale** | $$E_{k}=\sum_{i}E_{k,i}=\sum_{i} \frac{1}{2}m_{i}v_{i}^2$$                   |
## Centro di Massa di un Sistema di Punti
Si definisce **Centro di Massa di un Sistema di Punti Materiali** il punto geometrico la cui posizione è individuata, nel sistema di riferimento, dal raggio vettore
$$
\vec{r}_{CM}= \frac{\sum_{i}m_{i}\vec{r}_{i}}{\sum_{i}m_{i}}= \frac{m_{1}\vec{r}_{1}+\ldots+m_{n}\vec{r}_{n}}{m_{1}+\ldots+m_{n}}
$$

![[Pasted image 20250728171219.png|center|300]]

Le componenti cartesiane di $\vec{r}_{CM}$ sono 
$$x_{CM}= \frac{\sum_{i}m_{i}x_{i}}{\sum_{i}m_{i}}\qquad y_{CM}= \frac{\sum_{i}m_{i}y_{i}}{\sum_{i}m_{i}}\qquad z_{CM}= \frac{\sum_{i}m_{i}z_{i}}{\sum_{i}m_{i}}$$
La posizione non dipende dal sistema di riferimento, ma cambiano le coordinate a seconda del sistema di riferimento

Se si considerano $n$ punti e i centri di due sistemi di riferimento $O$ e $O'$, le posizioni die punti $P_{i}$ sono individuate rispettivamente dai raggi vettori $\vec{r}_{i}$ e $\vec{r}_{i}'$ con
$$
\vec{r}_{i}=\vec{r}_{i}'+\vec{O}\vec{O}'\quad \text{ovvero}\quad \vec{r}_{i}'=\vec{r}_{i}+\vec{O}'\vec{O}
$$
La posizione dl centro di massa rispetto ad $O'$ è
$$
\vec{r}'_{CM}= \frac{\sum_{i}m_{i}\vec{r}_{i}'}{\sum_{i}m_{i}}= \frac{\sum_{i}m_{i}(\vec{r}_{i}+\vec{O}'\vec{O})}{\sum_{i}m_{i}}=\frac{\sum_{i}m_{i}\vec{r}_{i}}{\sum_{i}m_{i}}+\vec{O}'\vec{O}=\vec{r}_{CM}+\vec{O}'\vec{O}
$$

Se gli $n$ punti sono in movimento, si può calcolare la velocità del centro di massa:
$$
\vec{v}_{CM}= \frac{d \vec{r}_{CM}}{dt}= \frac{\sum_{i}m_{i} \frac{d\vec{r}}{dt}}{\sum_{i}m_{i}}= \frac{\sum_{i}m_{i}\vec{v}_{i}}{\sum_{i}m_{i}}= \frac{\vec{P}}{m}
$$

> [!info] Definizione
> Massa totale del sistema:
> $$
> m=\sum_{i}m_{i}
> $$

> [!hint] Osservazione
> La quantità di moto di un sistema di punti materiali è eguale alla quantità di moto $m\vec{v}_{CM}$ che avrebbe il centro di massa se considerato come un punto materiale che abbia la posizione $\vec{r}_{CM}$ e la velocità $\vec{v}_{CM}$ e massa pari alla massa totale $m$.

Analogamente si può calcolare l'accelerazione del centro di massa derivando l'espressione precedente:
$$
\vec{a}_{CM}= \frac{d\vec{v}_{CM}}{dt}= \frac{\sum_{i}m_{i} \frac{d\vec{v}_{i}}{dt}}{\sum_{i}m_{i}}= \frac{\sum_{i}m_{i}\vec{a}_{i}}{\sum_{i}m_{i}}= \frac{\sum_{i}m_{i}\vec{a}_{i}}{m}
$$
Se il sistema di riferimento è inerziale allora vale $\vec{F}_{i}=m_{i}\vec{a}_{i}=\vec{F}_{i}^{(E)}+\vec{F}_{i}^{(E)}$, sostituendo quindi questa espressione nella relazione dell'accelerazione si ottiene si ottiene
$$
m\vec{a}_{CM} = \sum_{i}m_{i}\vec{a}_{i}=\sum_{i}(\vec{F}_{i}^{(E)}+\vec{F}_{i}^{(I)})= \vec{F}^{(E)}
$$
Dato che la risultante delle forze interne è nulla (come visto precedentemente), si può esprimere il seguente teorema

> [!gray] Teorema del Moto del Centro di Massa
> $$
> \vec{F}
> ^{(E)}=m\vec{a}_{CM}$$
> Il centro di massa si muove come un punto materiale in cui sia concentrata tutta la massa del sistema e a cui sia applicata la risultante delle forze esterne.

Utilizzando i risultati precedenti si ottiene anche la **Prima Equazione Cardinale della Dinamica dei Sistemi**:
$$
\vec{F}^{(E)}=m\vec{a}_{CM}= m \frac{d\vec{v}_{CM}}{dt}= \frac{d}{dt}(m\vec{v}_{CM})= \frac{d\vec{P}}{dt}
$$

> [!hint] Risultante delle Forze Esterne
> Si osserva quindi che la risultante delle forze esterne è uguale alla derivata rispetto al tempo della quantità di moto totale del sistema, il moto del centro di massa è quindi determinato solo dalle forze esterne.

> [!info] Proprietà del Centro di Massa
> - La sua velocità è uguale alla quantità di moto totale divisa per la massa totale, ovvero la sua quantità di moto $m\vec{v}_{CM}$ è eguale alla quantità di moto totale $\vec{P}$
> - La sua accelerazione è determinata dalla risultante delle sole forze esterne
> 
Facendo riferimento a $\vec{P}$ e $\vec{F}^{(E)}$, si può dire che il moto del centro di massa rappresenta quello globale, si può pensare come una media del sistema (in effetti $\vec{r}_{CM}$, $\vec{v}_{CM}$ e $\vec{a}_{CM}$ sono medie pesate sulle masse dei raggi vettori).

## Conservazione della Quantità di Moto
Se un sistema di punti è isolato, cioè non è soggetto a forze esterne (risultante $\vec{F}^{(E)}=0$) si ha
$$
\vec{a}_{CM}=0\qquad \vec{v}_{CM}=\text{costante}\qquad \vec{P}=\text{costante}
$$

> [!gray] Principio di Conservazione della Quantità di Moto
> Quando la risultante delle forze esterne è nulla, la quantità di moto totale del sistema rimane costante nel tempo e il centro di massa si muove di moto rettilineo uniforme o resta in quiete.

Si considerano adesso due punti isolati, che posso interagire solo tra di loro:
$$
\vec{P}=\vec{p}_{1}+\vec{p}_{2}
=m\vec{v}_{1}+m\vec{v}_{2}=\text{costante}$$
Derivando rispetto al tempo si ottiene
$$
\frac{d}{dt}(m_{1}\vec{v}_{1}+m_{2}\vec{v}_{2})=m_{1}\vec{a}_{1}+m_{2}\vec{a}_{2}=0\Longrightarrow \vec{F}_{1}+\vec{F}_{2}=0,\ \vec{F}_{1}=-\vec{F}_{2}
$$
Il principio di conservazione della quantità di moto per un sistema isolato di due punti ha come conseguenza che le forze che si esercitano tra i due punti sono eguali in modulo e di verso opposto, ma questo non corrisponde al principio di azione e reazione in quanto $\vec{F}_{1}=-\vec{F}_{2}$ non implica che le due forze abbiano la stessa retta di azione. In generale, c'è equivalenza tra la conservazione della quantità di moto e principio di azione e razione nei sistemi più complessi.

Il principio di conservazione della quantità di moto permette di definire dinamicamente la massa, indipendentemente dalla forza peso

> [!example]+ Esempio della Molla:
> Se si considerano due punti materiali agli estremi di una molla compressa, dato che il centro di massa è in quiete, la quantità di moto del sistema dei due punti è nulla ($\vec{P}=0$). Se si lascia espandere la molla, i due punti si muovono in versi opposti, ma siccome le forze che agiscono in questo caso sono solo interne, la quantità di moto rimane sempre la stessa ($\vec{P}=0$ di nuovo).
> 
> 
> ![[Pasted image 20250729161504.png|center|400]]
> 
> Se si prende la formula della quantità di moto del sistema, si può ottenere la seguente relazione utile nei calcoli:
> $$
> m_{1}\vec{v}_{1}+m_{2}\vec{v}_{2}\Longrightarrow \text{(in modulo) }m_{2}= m_{1} \frac{v_{1}}{v2}
> $$

## Teorema del Momento Angolare
Si considera il momento angolare di un sistema di punti materiali rispetto ad un polo $O$, detto $\vec{r}_{i}=\vec{O}\vec{P}_{i}$ si ha
$$
\vec{L}=\sum_{i}(\vec{r}_{i}\times m_{i}\vec{v}_{i})
$$

![[Pasted image 20250729164258.png|center|400]]

La derivata di $\vec{L}$ rispetto al tempo è
$$
\frac{d\vec{L}}{dt}= \sum_{i}\left( \frac{d\vec{r}_{i}}{dt} \times m_{i}\vec{v}_{i}\right)+\sum_{i}\left( \vec{r}_{i}\times m_{i} \frac{d\vec{v}_{i}}{dt} \right)
$$
Per [[Cinematica#Velocità ed Accelerazione di un Punto rispetto ad un Altro|1.]] e [[Cinematica#^pp|2.]] si ha che $\frac{d\vec{r}_{i}}{dt}$, in quanto posizione di $P_{i}$ rispetto ad $O$ (i quali possono seesere entrambi in movimento), può essere riscritto come $\frac{d\vec{r}_{i}}{dt}=\vec{v}_{i}-\vec{v}_{o}$, ed essendo il sistema di riferimento inerziale:
$$
m_{i} \frac{d\vec{v}_{i}}{dt}=m_{i\vec{a}_{i}}= \vec{F}_{i}= \vec{F}_{i}^{(E)}+\vec{F}_{i}^{(I)}
$$
ne segue
$$
\begin{align} 

\frac{d\vec{L}}{dt}&= \sum_{i}[(\vec{v}_{i}-\vec{v}_{O})\times m_{i}\vec{v}_{i}]+\sum_{i}[\vec{r}_{i}\times(\vec{F}_{i}^{(E)}+\vec{F}_{i}^{(I)})]= \sum_{i}(\vec{v}_{i}\times m_{i}\vec{v}_{i})-\sum_{i}(\vec{v}_{O}\times m_{i}\vec{v}_{i})+\sum_{i}(\vec{r}_{i}\times \vec{F}_{i}^{(E)})+\sum_{i}(\vec{r}\times \vec{F}_{i}^{(I)}) \\
&=-\vec{v}_{O}\times m\vec{v}_{CM}+\vec{M}^{(E)}+\vec{M}^{(I)}
\end{align}
$$
Infatti $\sum_{i}\vec{v}_{i}\times m_{i}\vec{v}_{i}$ è nulla (ogni addendo è un prodotto vettoriale di vettori paralleli), $\vec{v}_{O}$ è stato spostato fuori dalla sommatoria perché indipendente dall'indice $i$, infine si è usata la formula della velocità del centro di massa si ottiene $\vec{v}_{CM}= \frac{\vec{P}}{m}$.

- Il vettore$$\vec{M}^{(E)}=\sum_{i}(\vec{r}_{i}\times \vec{F}_{i}^{(E)})$$rappresenta il momento totale delle forze esterne rispetto al polo $O$ 

- Il vettore $$\vec{M}^{(I)}=\sum_{i}(\vec{r}_{i}\times \vec{F}^{(I)})$$ rappresenta il momento totale delle forze interne rispetto al polo $O$

![[Pasted image 20250729172447.png|center|350]]

Si dimostra che $\vec{M}^{(I)}=0$: la simma dei momenti delle due forze interne $\vec{F}_{i,j}$ e $\vec{F}_{j,i}$ rispetto al polo $O$ è
$$
\vec{M}_{i,j}^{(I)}= \vec{r}_{j}\times \vec{F}_{i,j}+\vec{r}_{i}\times \vec{F}_{j,i}= (\vec{r}_{j}-\vec{r}_{i})\times \vec{F}_{i,j}= \vec{r}_{i,j}\times \vec{F}_{i,j}
$$
Il vettore $\vec{r}_{i,j}= \vec{P}_{i}\vec{P}_{j}$ è parallelo a $\vec{F}_{i,j}$ e quindi $\vec{M}_{i,j}^{(I)}=0$. $\vec{M}^{(I)}$ è costituito dalla somma di tutti i termini $\vec{M}_{i,j}^{(I)}$ e risulta perciò nullo.
In conclusione:
$$
\frac{d\vec{L}}{dt}=\vec{M}^{(E)}-\vec{v}_{O}\times M\vec{v}_{CM}
$$
e se il termine $-\vec{v}_{O}\times m\vec{v}_{CM}$ risulta nullo si ha

> [!gray] Teorema del Momento Angolare
> $$
> \vec{M}^{(E)}= \frac{d\vec{L}}{dt}
> $$
> Questo caso si verifica se:
> - Il polo $O$ è fisso nel sistema di riferimento inerziale: $\vec{v}_{O}=0$
> - Il centro di massa è in quiete nel sistema di riferimento inerziale: $\vec{v}_{CM}=0$
> - Il polo di $O$ coincide con il centro di massa: $\vec{v}_{O}=\vec{v}_{CM}$ e $\vec{v}_{O}\times \vec{v}_{CM}=0$
> - $\vec{v}_{O}$ è parallelo a $\vec{v}_{CM}$
> 
> La relazione appena espressa è detta **Seconda Equazione Cardinale della Dinamica dei Sistema**, costituisce il **Teorema del Momento Angolare**: se il polo $O$ è fisso nel sistema di riferimento inerziale, o coincide con il centro di massa (anche se quest'ultimo non è fisso), l'evoluzione nel tempo del momento angolare del sistema di punti è determinata dal momento delle forze esterne rispetto a $O$. Le forze interne non influenzano $\vec{L}$.
> 

## Conservazione del Momento Angolare
In una situazione dove vale il teorema del momento angolare (cioè se $\vec{v}_{O}\times m\vec{v}_{CM}=0$), se il momento delle forze esterne è nullo risulta 
$$
\frac{d\vec{L}}{dt}=0\quad \text{ovvero}\quad \vec{L}=\text{costante}
$$
Questa relazione costituisce il **Principio di Conservazione del Momento Angolare**, ovvero se è nullo il momento angolare delle forze esterne che agiscono sul sistema il momento angolare si conserva.
La condizione $\vec{M}^{(E)}$ si può verificare quando:
- Non agiscono forze esterne, quindi quando il sistema è isolato: allora $\vec{L}$ si conserva rispetto a qualsiasi polo per il quale $\vec{v}_{O}=m\times \vec{v}_{CM}=0$. In questa situazione in cui anche $\vec{F}^{(E)}=0$, si ha pure la conservazione della quantità di moto ($\vec{P}=\text{costante}$)
- Il momento delle forze esterne è nullo rispetto ad un determinato polo, ma non rispetto ad un qualsiasi polo, pure in presenza di forze esterne. Pertanto si ha conservazione del momento angolare solo se calcolato rispetto a quel polo

La conservazione del momento angolare è una proprietà molto generale, si dimostra che discende dalla caratteristica dello spazio di essere isotropo, cioè che non predilige una certa direzione.

## Sistema di Riferimento del Centro di Massa
Il sistema di riferimento del centro di massa ha le seguenti caratteristiche:
- L'origine è nel centro di massa
- Gli assi mantengono sempre la stessa direzione rispetto agli assi di riferimento inerziale (possono essere assunti paralleli a questi)
- Si tratta in generale di un sistema di riferimento non inerziale, infatti il moto del sistema del centro di massa è traslatorio ma non necessariamente rettilineo e uniforme, ciò avviene solo se $\vec{F}^{(E)}$ e $\vec{a}_{CM}=0$

![[Pasted image 20250730123016.png|center|400]]

Per il punto $P_{i}$ si ha
$$
\vec{r}_{i}=\vec{r}_{i}'+\vec{r}_{CM}
$$
Dal teorema delle velocità relative si ha poi con $\vec{\omega}=0$ (moto di trascinamento traslatorio)
$$
\vec{v}_{i}=\vec{v}_{i}'+\vec{v}_{CM}
$$
Infine assumendo il centro di massa come riferimento, la posizione, velocità e accelerazione del centro di massa rispetto a se stesso sono nulle
$$
\vec{r}_{CM}'=0\qquad \vec{v}_{CM}'=0\qquad \vec{a}'_{CM}=0
$$
Riprendendo le formule del raggio vettore, velocità ed accelerazione del centro di massa (valide per qualunque sistema) segue che
$$
\sum_{i}m_{i}\vec{r}_{i}'=0\qquad \sum_{i}m_{i}\vec{v}_{i}'=0\qquad \sum_{i} m_{i}a\vec{v}_{i}'=0
$$

> [!hint] Quantità di Moto Totale rispetto al CM
> La quantità di moto totale del sistema $\vec{P}'= \sum_{i}m_{i}\vec{v}_{i}'$ risulta nulla se misurata nel sistema di riferimento del centro di massa (anche se i singoli termini $m_{i}\vec{v}_{i}'$ sono generalmente diversi da 0)

È importante evidenziare il fatto che il sistema del centro di massa non è in generale inerziale: pertanto sui singoli punti agisce anche la forza di trascinamento $-m_{i}\vec{a}_{t}=-m_{i}\vec{a}_{CM}$, in quanto l'accelerazione di trascinamento è pari a quella dell'origine (cioè del centro di massa).
Per ogni punto si ha quindi
$$
\vec{F}_{i}^{(E)}+\vec{F}_{i}^{(I)}-m_{i}\vec{a}_{CM}=m_{i}\vec{a}_{i}'
$$
Per quanto riguarda invece il momento risultante, esso è nullo non solo quello delle forze interne, ma anche quello di eventuali forze apparenti, infatti:
$$\begin{align}
\vec{M}'^{(E)}&=\sum_{i}[\vec{r}_{i}'\times(\vec{F}_{i}^{(E)}-m_{i}\vec{a}_{CM})]=\sum_{i}(\vec{r}_{i}'\times \vec{F}_{i}^{(E)})-\sum_{i}(\vec{r}_{i}'\times m_{i}\vec{a}_{CM})=\sum_{i}(\vec{r}_{i}'\times \vec{F}_{i}^{(E)})-\left(  \sum_{i}m_{i}\vec{r}' \right)\times \vec{a}_{CM} \\
&=\sum_{i}(\vec{r}_{i}'\times \vec{F}_{i}^{(E)})
\end{align}$$
di conseguenza, dato $\vec{L}'=\sum_{i}(\vec{r}_{i}'\times m_{i}\vec{v}_{i}')$, momento angolare rispetto al centro di massa nel sistema del centro di massa, vale la relazione
$$
\vec{M}'^{(E)}= \frac{d\vec{L}'}{dt}
$$

> [!info] Teorema del Momento Angolare per Sistema di Riferimento del CM
> Il teorema del momento angolare sussiste anche per grandezze calcolate nel sistema di riferimento non inerziale del centro di massa, purché come polo si assuma il centro di massa.

## Teorema di König
I teoremi di König si basano sulla nozione di sistema di riferimento del centro di massa, forniscono sia per il momento angolare e sia per l'energia cinetica di un sistema di punti materiali una relazione tra valore misurato di un sistema inerziale e quello misurato nel sistema del centro di massa.
### Teorema di König per il Momento Angolare
Si assume come polo l'origine del sistema inerziale, il momento angolare è dato da
$$
\vec{L}=\sum_{i}(\vec{r}_{i}\times m_{i}\vec{v}_{i})
$$
Si riscrive adesso questa relazione utilizzando le relazioni precedenti $\vec{r}_{i}=\vec{r}_{i}'+\vec{r}_{CM}$ e $\vec{v}_{i}=\vec{v}_{i}'+\vec{v}_{CM}$
$$
\vec{L}=\sum_{i}[(\vec{r}_{i}'+\vec{r}_{CM})\times m_{i}(\vec{v}_{i}'+\vec{v}_{CM})]= \sum_{i}(\vec{r}_{i}'\times m_{i}\vec{v}_{i}')+\sum_{i}(\vec{r}_{i}'\times m_{i}\vec{v}_{CM})+\sum_{i}(\vec{r}_{CM}\times m_{i}\vec{v}_{i}')+\sum_{i}(\vec{r}_{CM}\times m_{i}\vec{v}_{CM})
$$
Ci sono quindi 4 sommatorie:
1. $\sum_{i}\vec{r}_{i}'\times m_{i}\vec{v}_{i}'=\vec{L}'$ rappresenta il momento angolare rispetto al momento di massa
2. $\left( \sum_{i}m_{i}\vec{r}_{i} \right)\times \vec{v}_{CM}=$ nulla
3. $\vec{r}_{CM}\times\left( \sum_{i}m_{i}\vec{v}_{i}' \right)=$ nulla
4. $\vec{r}_{CM}\times m\vec{v}_{CM}= \vec{r}_{CM}\times \vec{P}$ rappresenta il momento angolare rispetto all'origine del sistema inerziale di un punto materiale che ha una massa totale a quella del sistema, coincide col centro di massa e ha la stessa velocità di quest'ultimo. Questo elemento viene infatti chiamato momento angolare del centro di massa

Si può quindi enunciare il seguente teorema

> [!gray] Primo Teorema di König
> $$\vec{L}=\vec{L}'+\vec{r}_{CM}\times m\vec{v}_{CM}=\vec{L}'+\vec{L}_{CM}$$
>![[Pasted image 20260108155551.png|center]]
> Il momento angolare del sistema angolare si può scrivere, nel sistema di riferimento inerziale, come somma del momento angolare dovuto al moto del centro di riferimento di massa $\vec{L}_{CM}$ e di quello rispetto al centro di massa
> 


### Teorema di König per l'Energia Cinetica
L'energia cinetica per un sistema inerziale è $E_{k}=\sum_{i}\frac{1}{2} m_{i}v_{i}^2$, utilizzando la relazione $\vec{v}_{i}=\vec{v}_{i}'+\vec{v}_{CM}$ si ottiene
$$
E_{k}= \sum_{i} \frac{1}{2} m_{i}(\vec{v}_{i}'+\vec{v}_{CM})^2= \sum_{i} \frac{1}{2}m_{i}v_{i}'^2+\sum_{i} \frac{1}{2}m_{i}v_{CM}^2+\sum_{i}m_{i}\vec{v}_{i}'\cdot \vec{v}_{CM}
$$
Ci sono quindi 3 sommatorie:
1. $\sum_{i} \frac{1}{2}m_{i}\vec{v}_{i}'^2$ rappresenta l'energia cinetica nel sistema di riferimento nel centro di massa (ossia l'energia cinerica rispetto al centro di massa $E_{k}'$)
2. $\sum_{i} \frac{1}{2}m_{i}v_{CM}^2$ rappresenta l'energia cinetica di un punto materiale che possiede tutta la massa del sistema e si muove con la velocità del centro di massa (detta energia cinetica del centro di massa)
3. $\sum_{i}m_{i}\vec{v}_{i}'\cdot \vec{v}_{CM}=$ nulla (è uguale a $\sum_{i}m_{i}\vec{v}_{i}'\cdot \vec{v}_{CM}$)

Si può quindi enunciare il seguente teorema

> [!gray] Secondo Teorema di König
> $$E_{k}=E_{k}'+\frac{1}{2}mv^2_{CM}= E_{k}'+E_{k,CM}$$
> L'energia cinetica del sistema di punti si può scrivere, nel sistema di riferimento inerziale, come la somma dell'energia cinetica dovuta al moto del centro di massa $E_{k,CM}$ e di quella del sistema rispetto al centro di massa.

## Teorema dell'Energia Cinetica
Si calcola il lavoro associato al moto di un sistema di punti materiali:
$$
dW_{i}=\vec{F}_{i}\cdot d\vec{r}_{i}= \vec{F}_{i}^{(E)}\cdot d\vec{r}_{i}+\vec{F}_{i}^{(I)}\cdot d\vec{r}_{i}= dW_{i}^{(E)}+dW_{i}^{(I)}
$$
Sommando tutti i punti e integrando le traiettorie $C_{i}$ percorse si ottiene il lavoro totale come somma del lavoro delle forze interne ed esterne
$$
W=W^{(E)}+W^{(I)}
$$
Questa volta il contributo delle forze interne non scompare, infatti $dW^{(I)}$ è formato da coppie di termini del tipo 
$$
\vec{F}_{i,j}\cdot d\vec{r}_{j}+\vec{F}_{j,i}\cdot d\vec{r}_{i}= \vec{F}_{i,j}\cdot (d\vec{r}_{j}-d\vec{r}_{i})=\vec{F}_{i,j}\cdot d(\vec{r}_{j}-d\vec{r}_{i})= \vec{F}_{i,j}\cdot d\vec{r}_{i,j}
$$
in generale non nulle e con somma diversa da zero. La struttura di $dW^{(I)}$ implica che al lavoro delle forze interne è legato un cambiamento dell distanze mutue tra i vari punti.

Riprendendo l'espressione $dW_{i}=\vec{F}_{i}\cdot d\vec{r}_{i}$, che è uguale a $m_{i}v_{i}dv_{i}$, sommando e integrando su tutti i punti si ottiene
$$
W=\sum_{i} \frac{1}{2} m_{i}v_{i,B}^2-\sum_{i} \frac{1}{2} m_{i}v_{i,A}^2= E_{k,B}-E_{k,A}
$$
con $v_{i,\ldots}$ i moduli delle velocità del punto $i-$esimo nelle posizioni $A$ e $B$ del percorso, $E_{k,\ldots}$ l'energia cinetica associata a queste velocità.

![[Pasted image 20250730203722.png|center|500]]

Unendo i risultati, si ottiene

> [!gray] Teorema dell'Energia Cinetica
> $$
> W^{(E)}+W^{(I)}=E_{k,B}-E_{k,A}=\Delta E_{k}
> $$
> Il lavoro complessivo fatto dalle forze esterne ed interne che agiscono su un sistema di punti materiali è uguale alla variazione dell'energia cinetica dello stesso sistema tra la configurazione (posizione) finale e quella iniziale.

Se le forze interne, il lavoro è esprimibile come l'opposto della variazione dell'energia potenziale legata a queste forze:
$$
W^{(I)}=-\Delta E_{p}^{(I)}\qquad W^{(E)}=-\Delta E_{p}^{(E)}
$$

> [!gray] Teorema di Conservazione dell'Energia Meccanica del Sistema
> Quando sia le forze interne ed esterne sono conservative, si può allora esprimere il **Teorema di Conservazione dell'Energia Meccanica del Sistema**:
> $$\begin{align}
> &W=\Delta E_{k}=-\Delta E_{p}=-(E_{p,B}-E_{p,A})
>  \\ &E_{m,A}= (E_{k}+E_{p})_{A}=E_{m,B}=(E_{k}+E_{p})_{B}=\text{costante}
> \end{align}$$
> 

Se invece non tutte le forze agenti sono conservative si ha
$$
W_{nc}=(E_{k}+E_{p})_{B}-(E_{k}+E_{p})_{A}=E_{m,B}-E_{m,A}
$$
In questa formula il lavoro delle forze conservative è espresso da $E_{p,A}-E_{p,B}$ e quello delle forze non conservative da $W_{nc}$
## Proprietà dei Sistema di Forze Applicate a Punti Diversi
Si indica con $\vec{F}=\sum_{i}\vec{F}_{i}$ la risultante delle forze e con 
$$
\vec{M}_{O}=\sum_{i}(\vec{O}\vec{P}_{i}\times \vec{F}_{i})= \sum_{i} (\vec{r}_{i}\times \vec{F}_{i})
$$
il **Momento Risultante delle Forze Rispetto al Polo $O$**.
Se si cambia polo, si ha allora $\vec{M}_{O'}=\sum_{i}(\vec{r}_{i}'\times \vec{F}_{i})$ con $\vec{r}_{i}'=\vec{r}_{i}-\vec{O}\vec{O}'= \vec{r}_{i}+\vec{O}'\vec{O}$ per cui
$$
\vec{M}_{O'}=\sum_{i}[(\vec{r}_{i}+\vec{O}'\vec{O})\times \vec{F}_{i}]=\sum_{i}(\vec{r}_{i}\times \vec{F}_{i})+\vec{O}'\vec{O}\times \sum_{i}\vec{F}_{i}=\vec{M}_{O}+\vec{O}'\vec{O}\times \vec{F}
$$
Il moto dipende dal polo, a meno che non sia $\vec{F}=0$.

![[Pasted image 20250730210516.png|center|350]]

> [!example]+ Applicazione: Coppia di Forze
> Si chiama coppia di forze un sistema formato da due forze eguali e opposte, avendo una differente retta d'azione, e la distanza tra le due rette d'azione è chiamata *braccio*. La risultante delle due forze è pertanto il momento $\vec{M}$, ortogonale al piano individuato dalle due rette, con verso individuato dal prodotto vettoriale.
> 
> ![[Pasted image 20250730211911.png|center|300]]
> 
> Le forze interne di un sistema di punti materiali costituiscono un insieme di coppie a braccio nullo, pertanto il momento risultante è nullo rispetto a qualsiasi polo.

In generale, dato un qualsiasi sistema di forze, i vettori $\vec{F}$ e $\vec{M}_{O}$ non sono ortogonali e quindi non possibile trovare due punti $O$ e $P$ tali che $\vec{M}_{O}=\vec{O}\vec{P}\times \vec{F}$. Ciò vuol dire che $\vec{M}_{O}$ non è indipendente da $\vec{F}$ e conferma che le equazioni cardinali della dinamica dei sistemi sono indipendenti.

> [!info] Risultato Generale
> Dato un sistema di forze applicate in punti diversi e fissato un polo per i momenti, noti $\vec{F}$ e $\vec{M}_{O}$, questo sistema può essere sempre ridotto a una forza $\vec{F}$ con retta d'azione passante per il polo (con momento rispetto al polo nullo) e ad una coppia di forze di momento $\vec{M}_{O}$ (che ha risultante nulla e momento indipendente dal polo).

### Sistema di Forze Parallele
Questo sistema  formato da forze aventi la stessa direzione, individuata dal versore $\hat{u}$. Pertanto $\vec{F}_{i}=F_{i}\hat{u}$ e la risultante $\vec{F}=\sum_{i}\vec{F}_{i}\left( \sum_{i}F_{i} \right)\hat{u}$ risulta parallela a $\hat{u}$.
Il momento della risultante è dato da 
$$
\vec{M}= \sum_{i}(\vec{r}_{i}\times F_{i}\hat{u})= \left( \sum_{i}F_{i}\vec{r}_{i} \right)\times \hat{u}
$$
ed è ortogonale a $\hat{u}$ (quindi ad $\vec{F}$). Deve essere quindi possibile trovare un punto $C$ dove applicare $\vec{F}$, tale che
$$
\vec{M}=\vec{O}\vec{C}\times \vec{F}=\vec{r}_{C}\times \vec{F}
$$
Eguagliando queste due espressioni scritte per $\vec{M}$
$$\left( \sum_{i}F_{i}\vec{r}_{i} \right)\times \hat{u}=\vec{r}_{C}\times\left( \sum_{i}F_{i} \right)\hat{u}= \left( \sum_{i}F_{i} \right)\vec{r}_{C}\times \hat{u}\Longrightarrow \vec{r}_{C}=\vec{O}\vec{C}= \frac{\sum_{i}F_{i}\vec{r}_{i}}{\sum_{i}F_{i}}= \frac{F_{1}\vec{r}_{1}+\ldots+F_{n}\vec{r}_{n}}{F_{1}+\ldots+F_{n}}$$
Il punto $C$ è chiamato **Centro delle Forze Parallele**. Questi tipi di sistemi sono riducibili ad una sola forza (la risultante $\vec{F}$) applicata al punto $C$. Il risultato non dipende da $O$, ma solo dalla posizione relativa dei punti.

Un sistema comune di forze parallele è quello delle forze peso applicate ad un insieme di punti. Le singole forze sono pari a $m_{i}\vec{g}$, la risultante è $\vec{F}=m\vec{g}$ e il centro, detto **Baricentro** (o centro di gravità) è individuato dal vettore
$$
\vec{r}_{C}= \frac{\sum_{i}m_{i}g\vec{r}_{i}}{\sum_{i}m_{i}g}= \frac{\sum_{i}m_{i}\vec{r}_{i}}{\sum_{i}m_{i}}= \vec{r}_{CM}
$$

![[Pasted image 20250730214922.png|center|400]]

Il momento risultante della forza peso è $\vec{M}=\vec{r}_{C}\times m\vec{g}=\vec{r}_{CM}\times m\vec{g}$.