---
sticker: emoji//0037-fe0f-20e3
order: "8"
---
## Urti tra due Punti Materiali
Si parla di urto quando due corpi vengono bruscamente a contatto, ovvero interagiscono violentemente per un intervallo ti tempo trascurabile.
Si considera inizialmente l'urto di due punti materiali, dove si possono sviluppare forze molto intense che modificano la quantità di moto di ciascun punto., Quest forze che agiscono per un tempo breve rispetto a quello di osservazioni sono chiamate **Forze Impulsive**.

![[Pasted image 20250807173945.png|center|400]]

Si osserva che le forze che si manifestano durante il processo d'urto sono forze interne al sistema, in assenza di forze esterne si verifica pertanto (durante l'urto) la conservazione della quantità di moto totale.

Si indicano con $\vec{v}_{1,in}$ e $\vec{v}_{2,in}$ le velocità nell'istante precedente all'urto dei punti materiali, di masse $m_{1}$ e $m_{2}$, con $\vec{v}_{1,fin}$ e $\vec{v}_{2,fin}$ le veolcità nell'istante successivo all'urto. La conservazione della quantità di moto $\vec{P}$ si scrive come
$$
\vec{P}_{in}= m_{1}\vec{v}_{1,in}+m_{2}\vec{v}_{2,in}= m\vec{v}_{1,fin}+m\vec{v}_{2,fin}=\vec{P}_{fin}
$$
La quantità di moto del centro di massa rimane invariata nell'urto
$$
\vec{P}=(m_{1}+m_{2})\vec{v}_{CM}= \vec{P}_{in}=\vec{P}_{fin}=\text{costante}
$$
^pp


Il moto del centro di massa non viene cioè alterato dall'urto.
Per quanto riguarda la quantità di moto di ciascun punto materiale, per effetto dell'impulso della forza di interazione si ha
$$
m_{1}\vec{v}_{1,fin}-m_{1}\vec{v}_{2,in}= \vec{J}_{2,1}=\int_{t_{1}}^{t_{2}} \vec{F}_{2,1}\ dt \qquad m_{2}\vec{v}_{2,fin}= \vec{J}_{1,2}=\int_{t_{1}}^{t_{2}}\vec{F}_{1,2}\ dt
$$
dove $\vec{J}_{2,1}$ ($\vec{J}_{1,2}$) è l'impulso dovuto alla forza impulsiva $\vec{F}_{2,1}$ ($\vec{F}_{1,2}$). Si osserva che le variazioni di quantità di moto sono uguali e opposte
$$
\vec{F}_{1,2}=-\vec{F}_{2,1}\Longrightarrow \vec{J}_{1,2}=-\vec{J}_{2,1}
$$

> [!info] Conservazione della Quantità di Moto in Presenza di Forze Esterne
> Si può conservare la quantità di moto totale anche in presenza di forze esterne se la durata $\tau$ dell'urto è sufficientemente piccola e le forze esterne non sono impulsive. Infatti, la variazione di quantità di moto totale del sistema dovuta alle forze esterne è
> $$
> \Delta \vec{P}=\int_{t_{1}}^{t_{2}} \vec{F}^{(E)}\ dt = \vec{F}_{m}^{(E)}\tau
> $$
> e se $\tau$ è molto breve allora $\Delta \vec{P}$ diventa trascurabile (se le forze esterne fossero impulsive il valore medio $\vec{F}_{m}^{(E)}$ può subire variazioni rilevanti)
> 
> Una notazione alternativa si ottiene considerando $\vec{J}_{1,2}$ o  $\vec{J}_{2,1}$
> $$
> \vec{J}
> =\int_{t_{1}}^{t_{2}} \vec{F}\ dt= \vec{F}_{m}\tau
> $$
> con $\vec{F}_{m}$ valore medio della forza impulsiva su $\tau$. Dato che $\vec{J}$ assume un valore finito e $\tau$ è molto breve, $\vec{F}_{m}$ può assumere valori molto grandi rispetto ai quali $\vec{F}_{m}^{(E)}$ è trascurabile.
> 
> ![[Pasted image 20250807175528.png|center|350]]
> 
> La forza esterna non modifica i singoli impulsi durante l'urto e quindi resta vera l'uguaglianza $\vec{J}_{1,2}= \vec{J}_{2,1}$.

Definendo un urto un processo in cui l'interazione tra i punti materiali abbiano un'intensità molto grande rispetto alle eventuali forze esterne presenti si ha che
- Un urto comporta uno scambio di quantità di moto tra due punti sotto forma di impulsi dovuti alle froze interne tra gli stessi
- Nell'urto la quantità di moto totale prima dell'urto è uguale alla quantità di moto totale dopo l'urto: la quantità di moto si conserva

Dato che la posizione dei punti non varia nell'urto, eventuali energie potenziali dei punti non variano nell'urto e quindi $\Delta E_{k}= \Delta E_{k}$, si può dire che in un urto non si può assumere a prescindere che l'energia cinetica si conservi.
Sempre a riguardo dell'energia cinetica torna utile il secondo teorema di Koing per i due punti: $E_{k}= \frac{1}{2}(m_{1}+m_{2})v^2_{CM}+E_{k}'$ ,  dove il primo termine non varia nell'urto. L'energia cinetica rispetto al centro di massa è
$$
E_{k}'= \frac{1}{2}m_{1}v_{1}'^2+m_{2}v_{2}'^2
$$
### Sistema del Laboratorio e Sistema del Centro di Massa
Se si pone il sistema che permette di fare urtare i due punti di riferimento inerziale, allora il sistema di rifermento si chiama **Sistema del Laboratorio**. L'urto può anche essere studiato nel sistema di riferimento del centro di massa.
Il legame tra le velocità nei due sistemi in qualsiasi istante è
$$
\vec{v}_{1}=\vec{v}_{1}'+\vec{v}_{CM}\qquad \vec{v}_{2}=\vec{v}_{2}'+\vec{v}_{CM}
$$
![[Pasted image 20250807184157.png|center|600]]

Nel sistema di riferimento del centro di massa la quantità di moto totale è nulla, la verifica è immediata (usando la [[#^pp|relazione precedente]]):
$$
\vec{P}=m_{1}\vec{v}_{1}+m_{2}\vec{v}_{2}=m_{1}\vec{v}_{1}'+m_{2}\vec{v}_{2}'+(m_{1}+m_{2})\vec{v}_{CM}\Longrightarrow m_{1}\vec{v}_{1}'+m_{2}\vec{v}_{2}'=0
$$ 
Dunque
$$
m_{1}\vec{v}_{1,in}'+m_{2}\vec{v}_{2,in}=m_{1}\vec{v}_{1,fin}+m_{2}\vec{v}_{2,fin}=0\Longrightarrow \vec{p}_{1,in}'=-\vec{p}_{2,in}',\ \vec{p}_{1,fin}'=-\vec{p}_{2,fin}'
$$
L'energia cinetica nel sistema del centro di massa è la stessa relazione del caso generale per il centro di massa e normalmente si ha
$$
E_{k,in}'=\frac{1}{2}m_{1}v_{1,in}'^2+ \frac{1}{2}m_{2}v_{2,in}'^2 \ne E_{k,fin}'= \frac{1}{2}m_{1}v_{1,fin}'^2+\frac{1}{2}m_{2}v_{2,fin}'^2
$$
## Tipi di Urto
### Urto Elastico
Si definisce urto elastico un urto durante il quale, oltre alla quantità di moto, si conserva anche l'energia cinetica del sistema. Questo comporta che le forze esterne che si manifestano durante l'urto sono conservative. I due corpi reali che si urtano subiscono durante l'urto delle deformazioni elastiche, per poi riprendere la configurazione iniziale subito dopo l'urto.
Nello studio di un urto elastico si posso usare le equazioni 
$$
\vec{P}_{in}=\vec{P}_{fin}\qquad E_{k,in}= E_{k,fin}
$$
Ci sono inoltre due equazioni di conservazioni a due incognite, ovvero la velocità dei due punti dopo l'urto (nel caso di un urto centrale)
$$\begin{align}
&m_{1}v_{1,in}+m_{2}v_{2,in}=m_{1}v_{1,fin}+m_{2}v_{2,fin}=(m_{1}+m_{2})v_{CM} \\
& \frac{1}{2}m_{1}v_{1,in}^2+ \frac{1}{2}m_{2}v_{2,in}^2= \frac{1}{2}m_{1}v_{1,fin}^2+ \frac{1}{2}m_{2}v_{2,fin}^2
\end{align}$$
Risolvendo il sistema si trova la soluzione
$$\begin{align}
&v_{1,fin}= \frac{(m_{1}-m_{2})v_{1,in}+2m_{2}v_{2,in}}{m_{1}+m_{2}} \\
& v_{2,fin}= \frac{2m_{1}v_{1,in}+(m_{2}-m_{1})v_{2,in}}{m_{1}+m_{2}}
\end{align}$$
![[Pasted image 20250807192717.png|center|500]]

Se l'urto elastico viene considerato nel sistema di riferimento del centro di massa si trova
$$
\vec{v}_{1,fin}'= -\vec{v}_{1,in}'\qquad \vec{v}_{2,fin}'=-\vec{v}'_{2,in}
$$
### Urto Completamente Anelastico
Nell'urto completamente anelastico i due punti restano attaccati dopo l'urto formando un unico coro puntiforme di massa $m_{1}+m_{2}$.
Se $\vec{v}_{1}$ e $\vec{v}_{2}$ sono le velocità dei punti nell'istante dell'urto e $\vec{v}'$ la velocità comune dopo l'urto, si ha
$$\begin{gather}
&m_{1}\vec{v}_{1}+m_{2}\vec{v}_{2}=(m_{1}+m_{2})\vec{v}'=(m_{1}+m_{2})\vec{v}_{CM} \\
&\vec{v}_{CM}= \frac{m_{1}\vec{v}_{1}+m_{2}\vec{v}_{2}}{m_{1}+m_{2}}
\end{gather}$$
Subito dopo l'urto i punti si muovono con la velocità che aveva il centro di massa prima dell'urto ($\vec{v}_{CM}$ rimane invariata).
Le variazioni di quantità di moto dei singoli punti sono $m_{1}\vec{v}_{CM}-m_{1}\vec{v}_{1}$ e $m_{2}\vec{v}_{CM}-m_{2}\vec{v}_{2}$ che sono uguali e opposte.

Si calcola l'energia cinetica del sistema prima e dopo l'urto
$$
E_{k,in}=\frac{1}{2}m_{1}v_{1}^2 + \frac{1}{2}m_{2}v_{2}^2= E_{k,in}'+ \frac{1}{2}(m_{1}+m_{2})v^2_{CM}
$$
Applicando il teorema di Koing invece
$$
E_{k,fin}= \frac{1}{2}(m_{1}+m_{2})v^2_{CM}< E_{k,in}
$$
Infatti dopo l'urto completamente anelastico non c'è più moto rispetto al centro di massa, in questo tipo d'urto è assorbita $E_{k,in}'$.
L'energia cinetica che i due punti hanno  rispetto al centro di massa prima dell'urto è
$$
\Delta E_{k}= E_{k,fin}-E_{k,in}=-E_{k,in}'= \frac{1}{2}(m_{1}+m_{2})v_{CM}^2-\frac{1}{2}m_{1}v_{1}^2-\frac{1}{2}mv_{2}^2
$$

> [!info] Lavoro della Deformazione
> Il lavoro compiuto, a spese dell'energia cinetica iniziale, per fare avvenire la deformazione che unisce le palline non viene più recuperato, ovvero le forze interne che si sviluppano nell'urto non sono conservative.

### Urto Anelastico
L'urto anelsatico è il caso d'urto più comune, nel quale i punti ritornano separati dopo l'urto, durante il quale si conserva la quantità di moto (per l'assenza di forze impulsive esterne), ma non si conserva l'energia cinetica: una certa quantità di $E_{k}'$ viene assorbita.

![[Pasted image 20250807235905.png|center|400]]

Si considera, nel sistema di riferimento del centro di massa, il punto con quantità di moto $p_{1,in}'$ nell'istante precedente all'urto. Successivamente, per effetto dell'impulso nella fase di deformazione, la sua quantità di moto si riduce fino ad annullarsi, per poi riacquistarla fino al valore $p_{1,fin}'$ (con vero opposto e minore di modulo rispetto a $p_{1,in}'$).
Si definisce **Coefficiente di Restituzione** il rapporto
$$
e= - \frac{p_{1,fin}'}{p_{1,fin}'}= - \frac{v_{1,fin}'}{v_{1,in}'}= - \frac{p_{2,fin}'}{p_{2,fin}'}= - \frac{v_{2,fin}'}{v_{2,in}'}
$$
Essendo $P'=0$, in modulo si ha che $p_{1,in}'=p'_{2,in}$ e $p'_{1,fin}=p'_{2,fin}$ per cui il coefficiente di restituzione è lo stesso anche per la seconda particella

L'energia cinetica del sistema delle due particelle dopo l'urto è data da
$$
E_{k,fin}'= \frac{1}{2}m_{1}v_{1,fin}'^2+\frac{1}{2}m_{2}v_{2,fin}'^2= e^2\left( \frac{1}{2}m_{1}v_{1,in}'^2+\frac{1}{2}m_{2}v_{2,in}'^2 \right)\Longrightarrow E_{k,fin}'=e^2E_{k,in}'
$$
La variazione relativa di energia cinetica rispetto al centro di massa nell'urto è
$$
\delta= \frac{E_{k,fin}'-E'_{k,in}}{E_{k,in}'}=e^2-1
$$
- Nell'urto elastico $e=1$ e $\delta=0$, l'energia cinetica si conserva
- Nell'urto completamento anelastico $e=0$ e $\delta=-1$, tutta l'energia cinetica del moto relativo al centro di massa è assorbita e trasformata
- Nell'urto anelastico $0<e<1$ e $E_{k,fin}'< E_{k,fin}'$

La soluzione per le velocità finali nel sistema di riferimento inerziale, nel caso di urto centrale è
$$\begin{gather}
v_{1,fin}= \frac{(m_{1}-em_{2})v_{1,in}+m_{2}(1+e)v_{2,in}}{m_{1}+m_{2}} \\
v_{2,fin}= \frac{m_{1}(1+e)v_{1,in}+(m_{2}-em_{1})v_{2,in}}{m_{1}+m_{2}}
\end{gather}$$
---
## Urti tra Corpi Rigidi o tra Punti Materiali e Corpi Rigidi
Anche in questo caso si ha conservazione dell'energia cinetica solo se l'urto è elastico. Per quanto riguarda la quantità di moto invece essa si conserva se il corpo rigido è libero durante l'urto, mentre invece se è vincolato la reazione vincolare è di intensità comparabile alle forze interne, pertanto la quantità di moto non si conserva.
Se si sceglie un polo per il quale il momento delle forze esterne si annulla, si conserva allora il momento angolare rispetto a questo polo. 
Se agiscono invece solo forze interne, $\vec{L}$ si conserva sempre (inipendentemente dalla scelta del polo).

Quando il corpo è vincolato, il sistema di vincoli può essere riassunto in una forza risultante $\vec{F}$ e un momento risultante $\vec{M}$, l'effetto complessivo durante l'impulso dell'urto è $\vec{J}=\int \vec{F}\ dt$ e $\int \vec{M}\ dt$.

Quando due corpi si urtano, ma non restano attaccati, le quantità di moto dopo l'urto formano un certo angolo con la direzione che avevamo prima dell'urto. Infatti la forza esterna impulsiva $\vec{F}_{2,1}$ agente sul primo corpo non è parallela a $\vec{p}_{1,in}$, quindi $\vec{p}_{1,fin}$ risulta deviata.

![[Pasted image 20250808121527.png|center|300]]
