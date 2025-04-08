Tags: [[Tags/Fondamenti di Segnali e Trasmissione|Fondamenti di Segnali e Trasmissione]] [[University]]

## Dal concetto di Segnale al Concetto di Sistema
Si passa dal come caratterizzare dal punto di vista matematico un segnale (nel dominio del tempo e nel dominio della frequenza), allo studio di come è possibile elaborare un segnale attraverso un sistema.
- Un *Sistema Monodimensionale* è un qualunque dispositivo che produce un segnale di uscita (risposta o effetto) in corrispondenza di un segnale di ingresso (sollecitazione, eccitazione o causa).
Dal punto di vista matematico, un sistema è una trasformazione che ad un segnale di ingresso $x(t)$ fa corrispondere un ben determinato e unico segnale di uscita $y(t)$
La trasformazione del segnale $x(t)$ nel segnale $y(t)$ si denota nel seguente modo:
$$
y(t)=T[x(\alpha);t]
$$
![[Pasted image 20250407120507.png|center|400]]
Questa notazione indica che il valore dell'uscita $y(t)$ all'istante $t$ dipende dall'andamento complessivo del segnale di ingresso $x(t)$, cioè tutti i suoi valori $x(\alpha)$, con $-\infty<\alpha<\infty$.
- Notazione semplificata (quando non ci sono ambiguità) $$
y(t)=T[x(t)]
$$
Un esempio di sistema è l'amplificatore ideale, per il quale la legge di trasformazione è $$y(t)=Ax(t)$$
## Proprietà dei Sistemi Monodimensionali
### Stazionarietà
Se le caratteristiche del sistema non cambiano nel tempo, la risposta all'eccitazione ritardata nel tempo $t_{0}$ ha lo stesso andamento della risposta al segnale originario $x(t)$. Questo è il caso dei circuiti elettrici, che sono costanti nel tempo

> [!gray] ->
> Se
> $$
> y(t)=T[x(t)]
> $$
> allora
> $$
> T[x(t-t_{0})]=y(t-t_{0})
> $$
### Casualità
Un sistema è causale quando il valore dell'uscita all'istante $t$ dipende soltanto dai valori assunti dall'ingresso agli istanti precedenti (o coincidenti) a $t$ stesso. Una determinazione del segnale a partire da istanti $t$ futuri violerebbe il principio di causa-effetto

> [!gray] ->
> $$y(t)=T[x(\alpha),\ \alpha\le t;\ t]$$
### Senza Memoria
Un caso particolare di sistema causale è il cosiddetto sistema istantaneo (o senza memoria), in cui l'uscita all'istante $t$ dipende solo dal valore dell'ingresso al medesimo istante

> [!gray] ->
> $$
> y(t)=T[x(\alpha),\ \alpha=t;\ t]
> $$

Un esempio di sistema istantaneo è l'amplificatore ideale $y(t)=Ax(t)$, mentre il caso opposto, ovvero l'amplificatore a finestra mobile $y(t)=\int_{t-T}^t x(\alpha)\ d\alpha$ in cui il sistema mantiene memoria del segnale tra $t-T$ e $t$
![[Pasted image 20250408114614.png]]

> [!example]+ Esempio:
> - Amplificatore ideale $y(t)=A\cdot x(t)$ è un sistema causale, stazionario (si verifica l'uguaglianza $T[x(t-t_{0})]=y(t-t_{0})$) e senza memoria.
> - Amplificatore con guadagno variabile nel tempo $y(t)=(A+Bt)x(t)$ è un sistema causale e senza memoria, ma non stazionario poiché $$
> T[x(t-t_{0})]= (A+Bt)x(t-t_{0})\ne y(t-t_{0})=(A+B(t-t_{0}))x(t-t_{0})
> $$

### Stabilità
Un sistema è stabile se,  sollecitato da un segnale arbitrario ma di ampiezza limitata, produce a sua volta in uscita un segnale di ampiezza limitata
$$
|x(t)|\le M\Longrightarrow |y(t)|\le K
$$
con $M$ e $K$ finiti.
Questa definizione si indica con l'acronimo BIBO (Bounded Input Bounded Output).
### Invertibilità
A volte è necessario ricostruire il segnale di eccitazione in ingresso a un sistema nota la risposta al segnale stesso. Questo è possibile solo nei sistemi invertibili, ovvero per i quali esiste un sistema inverso $T^{-1}$ tale che

> [!gray] -> 
> $$
> T^{-1}=x(t)
> $$
> Per qualunque ingressi $x(t)$
### Linearità
Un sistema è lineare se ad esso è applicabile il principio di sovrapposizione degi effetti

> [!gray] ->
> Se
> $$
> x(t)= \alpha \cdot x_{1}(t)+\beta \cdot x_{2}(t)
> $$
> Allora
> $$
> y(t)=T[x(t)]=\alpha \cdot y_{1}(t)+\beta \cdot y_{2}(t)
> $$

> [!example]+ Esempio: Raddrizzatore a Doppia Semionda:
> Si considera il raddrizzatore a doppia semionda, la cui relazione costruttiva è $T[x(t)]=|x(t)|$. Si pone al suo ingresso il segnale $x(t)=x_{1}(t)+x_{2}(t)$. Si ottiene
> $$
> T[x(t)]=|x_{1}(t)+x_{2}(t)|\ne y_{1}(t)+y_{2}(t)=|x_{1}(t)|+|x_{2}(t)|
> $$
> Il sistema non è quindi lineare.

> [!example]+ Esempio: Amplificatore a Guadagno Variabile:
> Si riconsidera $y(t)=(A+Bt)x(t)$. Si pone al suo ingresso il segnale $x(t)=\alpha x_{1}(t)+\beta x_{2}(t)$. Si ottiene
> $$
> T[x(t)]=(A+Bt)[\alpha x_{1}(t)+\beta x_{2}(t)]=(A+Bt)\alpha x_{1}(t)+(A+Bt)\beta x_{2}(t)=y(t)=\alpha y_{1}(t)+\beta y_{2}(t)
> $$
## Caratterizzazione e Analisi dei Sistema Lineari e Stazionari
Si restringe lo studio ai *Sistemi Lineari Tempo Invarianti* (LTI) o *Sistemi Lineari Stazionari* (SLS), in quanto sono più sono più semplici da analizzare e sintetizzare.
Si introducono delle grandezze che permettono la loro caratterizzazione nel tempo e in frequenza.
### Risposta Impulsiva
Per un SLS, è possibile misurare la *Risposta Impulsiva*, ovvero l'uscita del sistema in corrispondenza di un ingresso di tipo impulsivo ($x(t)=\delta(t)$)
$$
h(t)=T[\delta(t)]
$$
La conoscenza di quest'ultimo è importante per determinare la risposta del sistema ad un segnale di ingresso di andamento arbitrario, infatti

> [!gray] ->
> $$
> y(t)=\int_{-\infty}^\infty x(\alpha)h(t-\alpha)\ d\alpha = x(t)\otimes h(t)
> $$
> **Dimostrazione:**
> Per le proprietà della delta di Dirac (ovvero $\delta$ è elemento neutro della convoluzione) risulta
> $$
> x(t)=x(t)\otimes \delta(t)=\int_{-\infty}^\infty x(\alpha)\delta(t-\alpha)\ d\alpha
> $$
> Risulta quindi
> $$
> T[x(t)]=T[x(t)\otimes \delta(t)]= T\left[ \int_{-\infty}^\infty x(\alpha)\delta(t-\alpha)\ d\alpha \right]
> $$
> Essendo $T[\cdot]$ e $\int$ entrambi operatori lineari, è possibile invertirne l'ordine di calcolo, segue che
> $$
> y(t)=T[x(t)]=\int_{-\infty}^\infty T[x(\alpha)\delta(t-\alpha)]\ d\alpha
> $$
> Si osserva che $T[\cdot]$ opera solo su funzioni del tempo $t$, essendo però $x(\alpha)$ costante rispetto ad esso si ottiene
> $$
> 
> y(t)=\int_{-\infty}^\infty x(\alpha)\cdot T[\delta(t-\alpha)]\ d\alpha$$
> Da cui, per la stazionarietà del sistema ($T[\delta(t-\alpha)]=h(t-\alpha)$)
> $$
> y(t)= \int_{-\infty}^\infty x(\alpha)h(t-\alpha)\ d\alpha= x(t)\otimes h(t)
> $$
> Quest'ultima stabilisce la relazione fondamentale del sistema lineare stazionario: il segnale di uscita può essere calcolato attraverso la convoluzione del segnale di ingresso con la risposta impulsiva.

La conoscenza della risposta impulsiva permette anche di verificare le proprietà possedute dal sistema e quindi caratterizza completamente il suo comportamento.
- Un SLS è causale se e solo se la sua risposta impulsiva è un segnale causale, cioè $$
h(t)=h(t)\cdot u(t)
$$
- Condizione necessaria e sufficiente affinché un SLS sia stabile è che la sua risposta impulsiva sia assolutamente integrabile $$
\int_{-\infty}^\infty |h(t)| \ dt <\infty 
$$
## Risposta in Frequenza
La risposta impulsiva può essere ricavata applicando in ingresso al sistema stesso un segnale che approssimi la funzione $\delta(t)$ e misurando l'uscita corrispondente. Si tratta di un'approssimazione perché la $\delta$ di Dirac è un'entità matematica astratta, per essere una buona approssimazione della sollecitazione impulsiva può essere un impulso rettangolare sufficientemente breve e di ampiezza sufficientemente elevata.
In molti casi non è possibile o non conviene applicare al sistema una sollecitazione impulsiva, si cambia dunque tipo di eccitazione e si fornisce al sistema un segnale in ingresso di tipo sinusoidale.
Se si fornisce ad un SLS un segnale di ingresso sinusoidale (o per semplicità di calcolo una oscillazione complessa alla frequenza $f$)
$$
x(t)=e^{j 2\pi ft}
$$
l'uscita corrispondente è espressa da
$$
y(t)= x(t)\otimes h(t)=\int_{-\infty}^\infty h(\alpha)x(t-\alpha)\ d\alpha = \int_{-\infty}^\infty h(\alpha)e^{j 2\pi f(t-\alpha)}\ d\alpha= e^{j 2\pi ft}\int_{-\infty}^\infty h(\alpha)e^{-j 2\pi f\alpha}\ d\alpha
$$
e quindi
$$
y(t)=H(f)e^{j 2\pi ft}
$$
Dove si definisce 
$$
H(f)=\int_{-\infty}^\infty h(\alpha)e^{-j 2\pi ft\alpha}
$$
Se il sistema è stabile, la risposta ad un'oscillazione di frequenza $f$ assegnata è a sua volta un'oscillazione alla stessa frequenza $f$, ma modificata in ampiezza e fase rispetto all'ingresso di un fattore a valori complessi, che si chiamano *Risposta in Frequenza* del sistema
$$
y(t)=H(f)\cdot x(t)\qquad H(f)= \left.\frac{y(t)}{x(t)}\right|_{x(t)=e^{j 2\pi ft}}
$$
^pp

Si ottiene così una descrizione del comportamento del sistema al variare della sinusoide in ingresso.
Al variare della frequenza $f$, la variazione di ampiezza e lo sfasamento introdotto dal sistema su un segnale sinusoidale cambiano, così che la risposta in frequenza deve intendersi come funzione della frequenza $f$ esprimibile per esempio in modulo e fase.
La risposta in frequenza è anche ricavabile come trasformata di Fourier della risposta impulsiva
$$
H(f)=\int_{-\infty}^\infty h(\alpha)e^{-j 2\pi f\alpha}\ d\alpha \iff H(f)= TCF[h(t)]
$$
^poopp

Le due definizioni precedenti sono equivalenti
- La [[#^pp|1)]] suggerisce un metodo per misurare la risposta in frequenza attraverso segnali sinusoidali a frequenza variabile.
- La [[#^poopp|2)]] richiede la conoscenza della risposta impulsiva e quindi ha come prerequisito la caratterizzazione temporale del sistema.
Se infine si indicano con $X(f)$ e $Y(f)$ le trasformate dei segnali $x(t)$ e $y(t)$, si ottiene
$$
y(t)=x(t)\otimes h(t)\iff Y(f)=X(f)\cdot H(f)\qquad H(f)=\frac{Y(f)}{X(f)}
$$
Questa relazione permette di calcolare la risposta in frequenza del SLS attraverso la conoscenza delle trasformate dell'ingresso $x(t)$ e l'uscita $y(t)$, bypassando nuovamente la misura della risposta impulsiva (definizione sensata sole per i valori di $f$ per cui $X(f)\ne 0$).

> [!hint] Calcolo della risposta in frequenza
> Le tre definizini:
> - $H(f)= \left. H(f)=\frac{y(t)}{x(t)}\right|_{x(t)=e^{j 2\pi ft}}$
> - $H(f)= TCF[h(t)]$
> - $H(f)=\frac{Y(f)}{X(f)}$
> possono essere utilizzate indifferentemente nella risoluzione dei problemi a seconda della convenienza

Si sa che la trasformata di Fourier di un segnale reale gode della proprietà di simmetria Hermitiana, perciò se la risposta impulsiva di un sistema è reale, si può scrivere
$$
H(f)=H^*(-f)\Longrightarrow \begin{cases}
A(f)=A(-f) \\
\theta(f)= -\theta(-f)
\end{cases}
$$
Dove $A(f)$ è la *Risposta in Ampiezza* e $\theta(f)$ è la *Risposta in Fase*.
Si può scrivere anche
$$
|H(f)|=|H(-f)|\qquad \angle H(f)=-\angle H(-f)
$$
Per comprendere il perché di questa nomenclatura (analoga a quella degli spettri dei segnali), si pone in ingresso al sistema il segnale $x(t)=a\cos (2\pi f_{0}t+\phi_{0})$ e si calcola il segnale corrispondente in uscita $y(t)$. Si osserva che
$$
x(t)= \left( \frac{a}{2} e^{j\phi_{0}} \right)e^{j 2\pi f_{0}t}+ \left( \frac{a}{2} e^{-j \phi_{0}} \right)e^{-j 2\pi f_{0}t}
$$
ovvero somma di due sinusoidi alle frequenza $f_{0}$ e $-f_{0}$
Utilizzando la definizione di risposta in frequenza $y(t)= \left.H(f)\cdot x(t)\right|_{x(t)=e^{j 2\pi ft}}$ e la linearità del sistema si ottiene
$$\begin{align}
y(t)&=H(f_{0}) \frac{a}{2}e^{j \phi_{0}}e^{j 2\pi f_{0}t}+H(-f_{0}) \frac{a}{2}e^{-j\phi_{0}}e^{-j 2\pi f_{0}t}=  \\
&=|H(f_{0})|^{j\angle H(f_{0})}\cdot \frac{a}{2} e^{j\phi_{0}}\cdot e^{j 2\pi f_{0}t}+\overset{\text{Per la simmetria Hermitiana: }=\frac{|H(f_{0})|e^{-j\angle H(f_{0})}a}{2}e^{-j\phi_{0}}e^{-j 2\pi f_{0}t}}{|H(f_{0})|e^{j\angle H(-f_{0})}\cdot \frac{a}{2}e^{-j\phi_{0}}e^{-j 2\pi f_{0}t}}= \\
&= |H(f_{0})|\cdot \frac{a}{2}e^{j(2\pi f_{0}t+\phi_{0}\angle H(f_{0})}+|H(f_{0})|\cdot \frac{a}{2}e^{-j (2\pi f_{0}t)+\phi_{0}+\angle H(f_{0})}= \\
&= a\cdot |H(f_{0})|\cdot \cos(2\pi f_{0}t+\phi_{0}+\angle|H(f_{0})|)
\end{align}$$
In altri termini
$$\begin{align}
y(t)&= H(f_{0}) \frac{a}{2}e^{j\phi_{0}}e^{j 2\pi f_{0}t}+H(-f_{0}) \frac{a}{2} e^{-j\phi_{0}}e^{-j 2\pi f_{0}t}=  \\
&=A(f_{0})e^{j\theta(f_{0})} \frac{a}{2} e^{j\phi_{0}}e^{j 2\pi f_{0}t}+A(-f_{0})e^{j\theta}(-f_{0}) \frac{a}{2} e^{-j 2\pi f_{0}t}= \\
&=A(f_{0}) \frac{a}{2}[e^{j\theta(f_{0})+\phi_{0}}e^{j 2\pi f_{0}t}+e^{-j(\theta(f_{0})+\phi_{0})}e^{-j 2\pi f_{0}t}]=aA(f_{0})\cos(2\pi f_{0}t+\phi_{0}+\theta(f_{0}))
\end{align}$$
Come già ricavato nel caso dell'oscillazione complessa, l'uscita del sistema risulta ancora sinusoidale, ma modificata in ampiezza e fase relativamente al segnale di ingresso, rispettivamente seguendo le risposte in ampiezza e fase del sistema alla frequenza $f_{0}$ di oscillazione.
$$
x(t)=a\cdot (2\pi f_{0}t+\phi_{0})\Longrightarrow y(t)=a\cdot |H(f_{0})|\cdot \cos(2\pi f_{0}t+\phi_{0}+\angle H(f_{0}))
$$
Quindi basta Prendere $H(f)$
![[Pasted image 20250408172150.png|center|250]]
$$x(t)=a\cdot \cos(2\pi f_{0}t+\phi_{0})\Longrightarrow y(t)=a\cdot |H(f_{0})|\cdot \cos(2\pi f_{0}t+\phi_{0}+\angle H(f_{0}))$$

> [!example]+ Esempio:
> un SLS è caratterizzato dalla seguente equazione differenziale: $y(t)+2 \frac{dy(t)}{dt}+ \frac{d^2y(t)}{dt^2}=x(t)$
> 1. Ricavare la risposta in frequenza di ampiezza e di fase del sistema
> 2. Ricavare l'uscita quando l'ingresso è $x(t)=\cos\left( \pi t+ \frac{\pi}{3} \right)$
> 
> **Soluzione:**
> 1. Applicando la trasformata di Fourier $$
> \begin{align} 
> &\begin{aligned} &Y(f)+2(j 2\pi f)Y(f)+(j 2\pi f)^2 Y(f)=X(f) \\
> &Y(f)(1+j 4\pi f-4\pi^2f^2)=X(f) \\  \\
> \end{aligned}\\
> &H(f)= \frac{Y(f)}{X(f)}=\frac{1}{1-4\pi^2f^2+j4\pi f}= \frac{1-4\pi^2f^2-j_{4}\pi f}{(1-4\pi^2f^2+j 4\pi f)(1-4\pi^2f^2)(1-4\pi^2f^2-j 4\pi f)} \\ 
> &=\frac{1-4\pi^2f^2-j4\pi f}{(1-4\pi^2f^2)^2+16\pi^2f^2}= \frac{1-4\pi^2f^2-j 4\pi f}{(1+4\pi^2f^2)^2}
> \end{align}$$Quindi si ottiene $$
> |H(f)|= \frac{1}{1+4\pi^2f^2}\qquad \angle H(f)=\arctan \frac{-4\pi f}{(1-4\pi^2f^2)}=-\arctan \frac{4\pi f}{(1-4\pi^2f^2)}
> $$
> 2.  Il segnale $x(t)=\cos\left( \pi t+ \frac{\pi}{3} \right)$ è la sinusoide alla frequenza $f_{0}= \frac{1}{2}$ $$\begin{align}
> &|H(f_{0})|= \frac{1}{1+4\pi^2f_{0}^2}= \frac{1}{1+\pi}=0.092 \\
> &\angle H(f_{0})=-\arctan \frac{4\pi f_{0}}{(1-4\pi^2f_{0}^2)}=-\arctan \frac{2\pi}{(1-\pi^2)}=0.616 \ rad \\
> &y(t)=|H(f_{0})|\cos\left( \pi t+ \frac{\pi}{3}+ \angle H(f_{0}) \right) \\
> &y(t)=0.092\cos\left( \pi t + \frac{\pi}{3}+0.616 \right)
> \end{align}$$

## Sistemi in Cascata e in Parallelo
### Sistemi in Cascata
Si considerano ora due sistemi SLS stabili in cascata (o in serie)
![[Pasted image 20250408174519.png]]
$$
y(t)=\int_{-\infty}^\infty z(\alpha)h_{2}(t-\alpha)\ d\alpha = z(t)\otimes h_{2}(t) \qquad z(t)=\int_{-\infty}^\infty x(\beta)h_{1}(t-\beta)\ d\beta = x(t)\otimes h_{1}(t)
$$
Mettendo insieme le relazioni si ottiene
$$
y(t)=x(t)\otimes h_{1}(t)\otimes h_{2}(t)
$$
Questo risultato dimostra che la cascata può essere rappresentata come un unico sistema equivalente con risposta impulsiva
$$
h(t)=h_{1}(t)\otimes h_{2}(t)
$$
e risposta in frequenza 
$$
H(f)=H_{1}(f)H_{2}(f)
$$
Quest'ultimo risultato si può ottenere calcolando la trasformata di Fourier di entrambi i membri delle due relazioni
$$
Y(f)=Z(f)\cdot H_{2}(f)\qquad Z(f)= X(f)H_{1}(f)
$$
da cui
$$
Y(f)= X(f)\cdot H_{1}(f)\cdot H_{2}(f)
$$
e quindi $H(f)=H_{1}(f)\cdot H_{2}(f)$.
- Vale l'ipotesi che i due sistemi a cascata non si influenzino a vicenda
- Se l'ipotesi non è verificata occorre interporre tra i due un circuito disaccoppiatore (o buffer) che impedisce reciproche influenze.
### Sistemi in Parallelo
Un'altro tipo di interconnessione è quello in parallelo, in cui i sistemi vengono alimentati dallo steso ingressi e le uscite vengono sommate
![[Pasted image 20250408175632.png]]
La risposta impulsiva e in frequenza sono in questo caso pari a 
$$
h(t)=h_{1}(t)+h_{2}(t)\qquad H(f)=H_{1}(f)+H_{2}(f)
$$
## Filtri
### Generalità sui Filtri e Filtri Ideali
Un caso tipico che si presenta nell'elaborazione dei segnali è quello in cui il segnale osservato $x(t)$ è costituito dalla sovrapposizione, cioè la somma di due segnali
$$
x(t)=x_{1}(t)+x_{2}(t)
$$
dei quali il primo è un segnale utile, mentre il secondo rappresenta un disturbo ineliminabile alla fonte.
### Filtro Passa Basso Ideale
Considerando i segnali in ambito frequenziale, lo spettro del segnale utile e quello del disturbo insistono su intervalli frequenziali disgiunti.
![[Pasted image 20250408183405.png|center|400]]
Si intuisce allora che è possibile seperare il segnale utile dal disturbo utilizzando un SLS con risposta in frequenza opportuna, ovvero un SLS con caratteristiche di selettività rispetto alle varie componenti frequenziali che compongono il segnale
$$
X(f)=X_{1}(f)+X_{2}(f)
$$
Se si vuole reiettare il disturbo $x_{2}(t)$ occorre usare un sistema chiamato *Filtro Passa Basso Ideale* che ha risposta in frequenza
$$
H_{LP}(f)=\text{rect}\left( \frac{f}{2B} \right)
$$
![[Pasted image 20250408184029.png|center|400]]
- Le componenti frequenziali all'interno di una certa banda vicino a $f=0$ (basse frequenze) rimangono inalterate. Questa zona è chiamata *Banda Passante*, si ha $H(f)=1$
- Viceversa, all'esterno della banda passante (*Banda Oscura*), le componenti frequenziali vengono completamente cancellate perchè $H(f)=0$
- La frequenza $B$ rappresenta il *Limite di Banda*
Se si utilizza questo filtro
![[Pasted image 20250408184353.png|center|350]]
si ottiene
![[Pasted image 20250408184431.png|center|400]]
- Nella pratica si tende ad identificare il limite di banda $B$ con l'ampiezza della banda passante (o tout-court), considerando solo il semiasse positivo delle frequenze
La risposta impulsiva del filtro passo-basso (low-pass) ideale si ricava antitrasformando l'espressione della risposta in frequenza
$$
h_{LP}(t)=2B\text{sinc}(2Bt)
$$
![[Pasted image 20250408184741.png|center|450]]
Si nota che $h_{LP}(t)$ è diversa da $0$ anche per valori di $t<0$ per cui il filtro passa basso ideale è un sistema non causale.
### Filtro Passa Alto Ideale
Se si vuole ottenere un risultato opposto, ovvero isolare il disturbo $x_{2}(t)$ e cancellare $1(t)$, occorre usare un sistema chiamato *Filtro Passa Alto Ideale* che ha una risposta in frequenza
$$
H_{HP}(f)=1-H_{LP}(f)=1-\text{rect}\left( \frac{f}{2B} \right)
$$
![[Pasted image 20250408185307.png|center|400]]
La risposta impulsiva (anche questo sistema non è causale)
$$
h_{HP}(t)=\delta(t)-2B\text{sinc}(2Bt)
$$
- La banda passante sta al di là di banda $B$, on cui le componenti frequenziali del segnale di ingresso non vengono alterate.
### Filtro Passa Banda Ideale
Si suppone di avere un segnale somma di 3 componenti
$$
x(t)=x_{1}(t)+x_{2}(t)+x_{3}(t)
$$
![[Pasted image 20250408190816.png|center|400]]
Per isolare il segnale $x_{2}(t)$ occorre usare un *Filtro Passa Banda Ideale* (band-pass) che ha risposta in frequenza
$$
H_{BP}(f)=\text{rect}\left( \frac{f-f_{0}}{B} \right)+\text{rect}\left( \frac{f+f_{0}}{B} \right)
$$
e risposta impulsiva (non causale)
$$
h_{BP}=2B\text{sinc}(Bt)\cos(2\pi f_{0}t)
$$
![[Pasted image 20250408192301.png|center|450]]
con $f_{0}$ frequenza centrale e $B$ banda passante.
È necessario disporre il sistema con risposta in frequenza non nulla solo nella banda occupata dal segnale $x_{2}(t)$.
![[Pasted image 20250408192549.png]]
I parametri utilizzati sono:
- $f_{L}$ limite inferiore di banda
- $f_{H}$ limite superiore di banda
- $f_{0}=\frac{f_{L}+f_{H}}{2}$ frequenza centrale
- $B=f_{H}-f_{L}$ ampiezza della banda passante
### Filtro Elimina Banda Ideale
Per eliminare il segnale $x_{2}(t)$ nel caso $x(t)=x_{1}(t)+x_{2}(t)+x_{3}(t)$ occorre utilizzare un *Filtro Elimina Banda Ideale* che risposta in frequenza 
$$
H_{BR}(f)=1-H_{BP}(f)
$$
e risposta impulsiva (sistema non causale) 
$$
h_{BR}=\delta(t)-2B\text{sinc}(Bt)\cos(2\pi f_{0}t)
$$
con i parametri:
- $f_{0}$ frequenza centrale
- $B$ banda oscura
![[Pasted image 20250408193152.png]]
I parametri utilizzati sono:
- $f_{L}$ limite inferiore della banda oscura
- $f_{H}$ limite superiore della banda oscura
- $f_{0}=\frac{f_{L}+f_{H}}{2}$ frequenza centrale
- $B=f_{H}-f_{L}$ ampiezza banda oscura
### Distorsioni Introdotte dai Filtri
Un filtro viene utilizzato (come analizzato precedentemente) per separare un segnale da altri segnali di disturbo. Durante questa operazione, bisogne porre attenzione a non alterare o distorcere il segnale utile. Occorre perciò stabilire sotto quali condizioni il segnale di uscita $y(t)$ di un sistema SLS rappresenta una replica fedele del segnale in ingresso $x(t)$.
Un sistema SLS non introduce distorsioni quando, dato l'ingresso $x(t)$, l'uscita $y(t)$ del sistema è 
$$
y(t)=Kx(t-t_{0})
$$
con $K$ costante reale e $t_{0}$ una traslazione temporale (ritardo).
- L'uscita è una replica del segnale in ingresso, al più modificato in ampiezza e ritardato nel tempo mantiene l'informazione che sta nella forma del segnale inalterata
![[Pasted image 20250408222521.png|center|500]]
La risposta impulsiva del SLS sarà allora 
$$
h(t)=K\delta(t-t_{0})
$$
essendo $h(t)$ l'uscita quando in ingresso si ha $\delta(t)$
Passando alla trasformata di Fourier si ottiene
$$
Y(f)=K\cdot X(f)e^{-j 2\pi ft_{0}}
$$
Da cui si trova l'espressione per la risposta in frequenza del sistema
$$
H(f)= \frac{Y(f)}{X(f)}=Ke^{-j 2\pi ft_{0}}
$$
e le corrispondenti risposte in ampiezza e fase 
$$
A(f)=|K|\text{ costante}\qquad \theta(f)=-2 \pi ft_{0} \text{ proporzionale a }f$$
Quindi, affinché un sistema non introduca distorsioni, deve possedere una risposta in ampiezza costante e una risposta in fase proporzionale alla frequenza, ovvero le componenti sinusoidali in cui il segnale arbitrario viene scomposto devono essere amplificate o attenuate tutte nella medesima misura e ritardate della stessa quantità.
Tuttavia ogni sistema reale ha dei limiti di banda intrinseci e non può garantire una risposta in frequenza con queste caratteristiche per tutti i valori della frequenza. La condizione di non distorsione in questo caso sembra irrealizzabile, in quanto il sistema non avrebbe riposta in ampiezza costante.
In realtà le condizioni basta che siano verificate all'interno di una banda limitata contenente il segnale utile $x(t)$ (non hanno cioè rilevanza l'andamento delle risposte del sistema per frequenza alle quali non esistono componenti nello spettro del segnale stesso).
![[Pasted image 20250408224036.png]]
Se non si riescono a garantire le condizioni di non distorsione neanche nella sola banda del segnale, questo subisce distorsioni.
In particolare:
- Se la risposta in ampiezza non è costante nella banda del segnale, si avranno distorsioni in ampiezza.
- Se la risposta in fase non è lineare nella banda del segnale, si hanno distorsioni di fase.
![[Pasted image 20250408224307.png]]
Esempio:
Si considerano i quattro segnali
1. $x_{1}(t)2\sin(\pi Bt)$
2. $x_{2}(t)=\cos(\pi Bt)+\sin(3\pi Bt)$
3. $x_{3}(t)=4\cos(2\pi Bt)+\sin(4\pi Bt)$
4. $x_{4}(t)=\text{sinc}^2(Bt)$
Si cerca di stabilire se questi segnali vengono o non vengono distorti nel passaggio attraverso il SLS la cui risposta è
![[Pasted image 20250408224713.png]]
ricordando che
$$x(t)=\cos(\pi f_{0}t)\Longrightarrow y(t)=A(f_{0})\cos(\pi f_{0}t+\theta(f_{0}))$$
![[Pasted image 20250408230752.png]]
![[Pasted image 20250408231012.png]]
![[Pasted image 20250408231045.png]]
![[Pasted image 20250408231405.png]]
## Densità Spettrale di Energia e Potenza
### Teorema di Parseval e Densità Spettrale di Energia
I criteri di banda 