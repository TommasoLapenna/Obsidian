---
sticker: emoji//0032-fe0f-20e3
Order: "2"
---
Tags: [[Old Vault/Tags/Fondamenti di Segnali e Trasmissione|Fondamenti di Segnali e Trasmissione]] [[Old Vault/Indexes/University]]
## Analisi Armonica dei Segnali Periodici
Un segnale è periodico se $x(t)=x(t+T_{0})$, con potenza media $P_{x}=\frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}|x(t)|^2\ dt$, valore medio $x_{m}= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}} x(t) \ dt$ e frequenza di ripetizione $f_{0}=\frac{1}{T_{0}}$ (velocità di variazione del segnale).

> [!example]+ Esempio: Coseno
> ![[Pasted image 20250324190650.png]]
> Il segnale coseno ($x(t))=\cos(2\pi tf_{0}+\theta)$) è conosciuto completamente se è nota la sua frequenza ($f_{0}$) e la fase iniziale ($\theta$). 
Esiste una rappresentazione che permette di analizzare un segnale reale periodico con la stessa semplicità

Attraverso l'*Analisi di Fourier*, secondo le opportune ipotesi, è possibile esprimere un segnale reale periodico come somma di oscillazioni sinusoidali (conm la relativa ampiezza, frequenza e fase)
$$
x(t)=a_{0}+a_{1}\cos(2\pi f_{1}t+\theta_{1})+a_{2}\cos(2\pi f_{2}+\theta_{2})+\ldots
$$
### Sviluppo in Serie di Fourier (Forma Polare)
$$
x(t)=A_{0}+2\sum^\infty_{k=1}A_{k}\cos(2\pi kf_{0}t+\theta_{k})
$$
![[Pasted image 20250324192624.png|center|450]]
è rappresentato come la somma di una costante $A_{0}$ e di una serie il cui il $k-$esimo termine (detto $k-$esima oscillazione armonica, o armonica) ha:
- Ampiezza $2A_{k}$
- Frequenza $kf_{0}$ (frequenza armonica) 
- Fase iniziale $\theta_{k}$

I termini coseno costituiscono la base dello spazio vettoriale dei segnali periodici di periodo $T_{0}$
![[Pasted image 20250324192654.png]]
Attraverso le formule di Eulero, la serie di Fourier può essere riscritta nel seguente modo:
$$
\begin{align}
x(t)&=A_{0}+2\sum_{k=1}^\infty A_{k}\cos(2\pi kf_{0}t+\theta_{k})=A_{0} +2\sum_{k=1}^\infty A_{k} \frac{e^{j_{2}\pi kf_{0}t+\theta_{k}}+e{-j_{2}\pi kf_{0}t+\theta_{k}}}{2} \\
&=A_{0}+\sum_{k=1}^\infty A_{k}e^{j\theta_{k}}e^{j_{2}\pi kf_{0}t}+\sum_{k=1}^\infty A_{k}A_{k}e^{-j\theta_{k}}e^{-j_{2}\pi kf_{0}t} \\
&= A_{0}+\sum_{k=1}^\infty A_{k}e^{j\theta_{k}}e^j_{2}\pi f_{0}t+\sum_{k=-\infty}^{-1}A_{-k}e^{-j\theta_{{-k}}}e^{j_{2}\pi kf_{0}t}
\end{align}
$$
Si definiscono le quantità:
$$X_{0}=A_{0}, \quad X_{k}=A_{k}e^{j\theta}\text{ con } k=-1,-2,\ldots$$
Si ottiene :
$$
x(t)=X_{0}+\sum_{k=1}^\infty X_{k}e^{j_{2}\pi f_{0}t}+\sum_{k=-1}^{-\infty} X_{k}e^{j_{2}\pi f_{0}t}
$$
### Sviluppo in Serie di Fourier (Forma Complessa)
Si determina un espressione per il calcolo del coefficiente $X_{n}$:

> [!gray] ->
> $$\begin{align} \\
> x(t)&=\sum^\infty_{k=-\infty}X_{k}e^{j_{2}\pi f_{0}t}\rightarrow \begin{aligned}
> &\text{Si moltiplicano entramni i membri per } \\
>  &e^{j_{2}\pi nf_{0}t}\text{ e si  integra nel periodo }T_{0} 
> \end{aligned}\rightarrow \int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi nf_{0}t}\ dt= \\
> &=\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}\sum_{k=-\infty}^\infty X_{k}e^{j_{2}\pi kf_{0}t}e^{-j_{2}\pi nf_{0}}\ dt\rightarrow  
>   
> \begin{aligned}
> &\text{Si ipotizza che la serie converga uniformemente}
> \end{aligned} \\
> &\rightarrow \int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi nf_{0}t}\ dt= \sum_{k=-\infty}^\infty\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}e^{j_{2}\pi(k-n)f_{0}t}\ dt\rightarrow \end{align}
> $$
> Si calcola lì'integrale del secondo membro
> $$
> \begin{align}
> &\rightarrow \int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}e^{j_{2}\pi(k-n)f_{0}t}\ dt=\left[ \frac{e^{j_{2}\pi(k-n)f_{0}t}}{j_{2}\pi(k-nf_{0})} \right]^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}} \overset{ \text{Essendo }f_{0}T_{0}=1}{=} \frac{e^{j_{2}\pi(k-n)}-e^{-j(k-n)}}{j_{2}\pi(k-n)f_{0}}= \\
> &= \frac{\sin[\pi(k-n)]}{\pi(k-n)f_{0}}
> \end{align}$$
> Il valore dell'integrale è pertanto nullo se $k\ne n$ (essendo $\sin[\pi(k-n)]=0$). Invece se $k=n$ il risultato finale perde significato, ma se si sotituisce nell'espressione iniziale si ricava il risultato $T_{0}$. Ponendo $k=n$ nell'espressione di partenza si ricava che l'integrale cercato vale in questo caso $T_{0}$. Riassmuendo
>$$ \int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}e^{j 2\pi (k-n)f_{0}t}\ dt = \begin{cases} T_{0} & k=n \\ 0 & k\ne 0
>\end{cases}
>$$
> $$
> \Longrightarrow \int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)e^{j_{2}\pi nf_{0}t}\ dt=\sum_{k=-\infty}^\infty\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}e^{j_{2}\pi(k-n)f_{0}t}\ dt= X_{n}T_{0}
> $$
> dalla quale si ottiene infine <span style="background:rgba(240, 200, 0, 0.2)">l'espressione del generico coefficiente di Fourier $X_{k}$:</span>
> $$
> X_{n}= \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}} x(t)e^{-j_{2}\pi nf_{0}t}\ dt\qquad X_{0}= \frac{1}{T_{0}}\int_{\frac{-T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)\ dt\text{ (corrisponde al valore medio)}
> $$
>
### Sviluppo in Serie di Fourier (Forma Rettangolare)

$$
\begin{align}
x(t)&=A_{0}+2\sum^\infty_{k=1} A_{k}\cos(2\pi kf_{0}t+\theta_{k}) \\
&=A_{0}+2\sum^\infty_{k=1}A_{k}[\cos(2\pi kf_{0}t)\cos \theta_{k}-\sin(2\pi kf_{0}t)\sin \theta_{k}]
\end{align}
$$
Si definiscono $a_{0}=A_{0}$, $a_{k}=A_{k}\cos \theta_{k}$, $b_{k}=A_{k}\sin \theta_{k}$ per $k=1,2,\ldots$, si ricava
$$
x(t)=a_{0}+2\sum^\infty_{k=1}[a_{k}\cos(2\pi f_{0}t)-b_{k}\sin(2\pi f_{0}t)],\quad \small{x_{k}=a_{k}+jb_{k}=A_{k}
\cos \theta_{k}+jA_{k}\sin \theta_{k}=A_{k}e^{j\theta_{k}}}$$
## Convergenza della Serie di Fourier
Per i segnali di comune applicazione pratica, l'ipotesi di convergenza è verificata. Spesso però si fa ricorso a funzioni per schematizzare fenomeni fisici che però non rappresentano esattamente i segnali in esami, ma forniscono una maggiore semplicità. Per queste funzioni è necessario disporre di criteri che garantiscono la correttezza dello sviluppo.

>[!example]+ Esempio: 
>![[Pasted image 20250325154019.png]]
Il primo segnale dente di sega presenta una discontinuità di prima specie all'istante $T_{0}$ (non eliminabile), $x(T_{0}^+)\ne x(T_{0}^-)$. Nella  realtà, un fenomeno fisico non si manifesterà mai con tale andamento, tuttavia ci possono comunque essere segnali con discontinuità (come nel secondo caso).
Occorre verificare se questi tipi di segnali si possono rappresentare attraverso lo sviluppo di Fourier

### Criterio di Dirichlet
Un insieme di condizioni sufficienti che garantiscono la possibilità di sviluppare un segnale in serie di Fourier è il cosiddetto *Criterio di Dirichlet*, che può essere enunciato nel seguente modo:

>[!gray] Criterio di Dirichlet
> 1. Se $x(t)$ è assolutamente integrabile sul periodo $T_{0}$ (se è verificata la condizione $\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}|x(t)|\ dt<\infty$)
> 2. Se $x(t)$ è continua o presenta in un periodo un numero finito di discontinuità di 1° specie
> 3. Se $x(t)$ è derivabile rispetto al tempo nel periodo, escluso al più un numero finito di punti nei quali esistono finite la derivata destra e sinistra
> 	- Se il segnale presenta un numero finito di massimi e minimi nel periodo


Allora la serie Fourier converge al valore assunto dalla funzione nei punti in cui questa è continua, e alla semisomma dei limiti destro e sinistro nei punti in cui si presentano le discontinuità di prima specie.
La terza ipotesi del criterio può essere sostituita (in modo equivalente) con la sua alternativa.

>[!example]+ Esempio:
> Si può quindi affermare che la prima funzione dente di sega può essere sviluppata in serie di Fourier. Nel punto di discontinuità il valore a cui la serie converge è $x_{0}(T_{0})=\frac{[x(T_{0}^+)+x(T_{0}^-)]}{2}=\frac{A}{2}$

## Spettri di Ampiezza e di Fase
Si ha che ogni segnale $x(t)$ che soddisfa il Criterio di Dirichlet può essere rappresentato con lo sviluppio in serie di Fourier

![[Pasted image 20250325161350.png]]

 L' equazione di sintesi prevede l'uso di infinite armoniche per ricostruire il segnale. D'altronde, la condizione necessaria alla convergenza della serie è che l'ampiezza $|X_{k}|$ delle armoniche tenda a $0$ quando $k\to \infty$. Questo comporta che le armoniche importanti sono in un numero limitato (si può quindi utilizzare una sommatoria più semplice).
 L'equazione di analisi e di sintesi permettono di stabilire una corrispondenza tra il segnale $x(t)$ e la sequenza $X_{k}$ (costituita dai coefficienti della serie di Fourier):
 $$ x(t)\iff X_{k}\qquad \text{DOMINIO DEL TEMPO}\iff \text{DOMINIO DELLE FREQUENZA}$$
 La notazione indica che la conoscenza dell'andamento del segnale $x(t)$ nel tempo è equivalente alla conoscenza dei coefficienti Fourier $X_{k}$ (il passaggio tra un dominio e l'altro è immediato, attraverso la sintesi e l'analisi).
 La quantità $X_{k}$ è in generale complessa, per rappresentarla conviene rappresentare separatamente il modulo e la base
 
![[Pasted image 20250325161814.png]]

Gli spettri di ampiezza e fase del segnale sono a righe, perciò sono discreti, in quanto sono definiti in corrispondenza delle frequenze armoniche. Gli spettri di ampiezza dei segnali periodici si misurano con gli analizzatori di spettro.
Calcoli esempi sotto nella slide 2

>[!example]+ Esempio: 
>$x(t)=a\cos(2\pi f_{0}t)$
>![[Pasted image 20250325162523.png|center|500]]
>$$
>x(t)=\sum^\infty_{k=1}A_{k}\cos(2\pi kf_{0}t)\Longrightarrow \begin{aligned}
>&A_{1}=\frac{a}{2},\ \theta_{1}=0,\quad A_{k},\ \theta_{k}=0\ \forall k\ne 1 \text{ ovvero:}
>\\ & X_{1}=\frac{a}{2},\ X_{-1}= \frac{a}{2},\quad X_{k}=0\ \forall k\ne\pm 1
>\end{aligned}
>$$

>[!example]+ Esempio:
>$x(t)=a\sin(2\pi f_{0}t)=a\cos\left( 2\pi f_{0}t- \frac{\pi}{2} \right)$
>![[Pasted image 20250325162712.png| center | 500]]
>$$\begin{align}
>&A_{1}= \frac{a}{2},\ \theta_{1}=\frac{\pi}{2}, \quad A_{k}, \ \theta_{k}=0 \ \forall k\ne  \\
>&\text{ovvero: } X_{1}=\frac{a}{2}e^{-j \frac{\pi}{2}},\ X_{-1}= \frac{a}{2}e^{j \frac{\pi}{2}},\ X_{k}=0 \ \forall k\ne\pm 1
>\end{align}
>$$

## Proprietà dello Spettro di un Segnale Reale Periodico
### Simmetria
Calcolare il complesso coniugato corrisponde al cambiare il segno della fase, quindi
$$
\begin{align}
X_{k}&= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi kf_{0}t}\ dt\longrightarrow X_{k}^*=\left( \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi kf_{0}t} \right)^* \\
&=\frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)^*e^{j_{2}\pi kf_{0}t}\ dt = \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi (-k)f_{0}t}\ dt = X_{-k}
\end{align}
$$
I coefficienti $X_{k}$ godono quindi si simmetria coniugata (o hermitiana), ovvero:

> [!gray] ->
> $$
> X_{-k}= X^*_{k}=\begin{cases}
> |X_{k}|=|X_{-k}| \\
> \angle X_{k}=-\angle X_{-k}
> \end{cases}
> $$

Infatti se due numeri complessi $A=a_{R}+ja_{I}$ e $B=b_{R}+jb_{I}$ sono tali che
$$
\begin{align}
A&=a_{R}+ja_{I}=B^*=b_{R}-jb_{I} \\
&\Longrightarrow \begin{aligned}
&a_{R}=b_{R} \\ & a_{I}=-b_{I}
\end{aligned}\Longrightarrow 
\begin{aligned}
&|A|=\sqrt{ a_{R}^2+a_{I}^2 }=\sqrt{ b_{R}^2+(-b_{I})^2 }=\sqrt{ b_{R}^2+b_{I}^2 }=|B|
\\ & \angle A = \tan^{-1}\left( -\frac{b_{I}}{b_{R}} \right)=\tan^{-1}\left( \frac{b_{I}}{b_{R}} \right)=-\angle B
\end{aligned}
\end{align}
$$
Quindi, per un segnale reale lo spettro di ampiezza è simmetrico rispetto a $k$, lo spettro di fase è invece antisimmetrico rispetto a $k$.
### Linearità
Se $x(t)$ e $y(t)$ sono entrambi segnali periodici con lo stesso periodo $T_{0}$ e aventi coefficienti di Fourier $X_{k}$ e $Y_{k}$
$$
z(t)= a\cdot x(t)+b\cdot y(t)\Longrightarrow Z_{k}=a\cdot X_{k}+b\cdot Y_{k}
$$
Significa che una combinazione lineare di segnali con lo stesso periodo $T_{0}$ è costituito da una somma di oscillazioni aventi la stessa frequenza di $x(t)$ e $y(t)$, ovvero la somma non introduce nuove armoniche.

>[!gray] Dimostrazione:
>La proprietà di linearità dei coefficienti di Fourier deriva dalla medesima proprietà dell'integrale: $$ \begin{align}
&Z_{k}=\frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}z(t)e^{-j_{2}\pi kf_{0}t}\ dt=\frac{1}{T_{0}} \int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}[ax(t)+by(t)]e^{-j_{2}\pi kf_{0}t}\ dt= \\
 &\overset{\text{Linearità Integrale}}{=} \frac{a}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi kf_{0}t}\ dt +\frac{b}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}y(t)e^{-j_{2}\pi kf_{0}t}\ dt = a X_{k}+ bY_{k}
\end{align}$$

> [!example]+ Esempio: Treno di impulsi rettangolari di durata $T$ e periodo $T_{0}$ (con $T<T_{0}$)
> Duty Cycle $\delta= \frac{t}{T_{0}}$. se si definiscono
> $$
> \text{rect}(t)=\begin{cases}
> 1 & |t|< \frac{1}{2} \\
> \frac{1}{2} & t=\pm \frac{1}{2} \\
> 0 & t> \frac{1}{2}
> \end{cases}
> $$
> Allora $x(t)=\sum_{n=-\infty}^\infty a\cdot \text{rect}\left( \frac{t-nT_{0}}{T} \right)$, i coefficienti dello sviluppo in serie del segnale è:
> $$
> \begin{align}
> X_{k}&= \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}\sum_{n=-\infty}^\infty a\cdot \text{rect}\left( \frac{t-nT_{0}}{T}e^{-j_{2}\pi kf_{0}t}\ dt \right)\rightarrow \begin{aligned}
> &\text{Ma nel periodo }\left[ -\frac{T}{2}, \frac{T}{2} \right]
> \\ &\text{c'è solo una replica di rect}\left( \frac{t}{T} \right)
> \end{aligned} \\
> &\rightarrow X_{k}= \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}a\cdot \text{rect}\left( \frac{t}{T} \right)e^{-j_{2}\pi kf_{0}t}\ dt= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}a\cdot e^{-j_{2}\pi kf_{0}t}\ dt  \\
> &= \frac{a}{T_{0}}\left[ \frac{e^{-j_{2}\pi kf_{0}t}}{(-j_{2}\pi kf_{0})} \right]^{\frac{T}{2}}_{-\frac{T}{2}}= \frac{e^{-j\pi kf_{0}t}-e^{-j\pi kf_{0}t}}{(-j_{2}\pi kf_{0})}=\frac{a}{T_{0}} \frac{\sin(\pi kf_{0}t)}{\frac{\pi k}{T_{0}}} \\
> &\rightarrow X_{k}= \frac{aT}{T_{0}}\text{sinc}\left( \frac{KT}{T_{0}} \right)=a\delta \text{sinc}(k\delta)
> \end{align}
> $$

### Funzione Sinc
![[Pasted image 20250325181108.png]]
$$\begin{align}
&\text{sinc}(\alpha)= \frac{\sin(\pi \alpha)}{\pi \alpha}\quad \text{sinc}(\alpha)=0 \ \forall \alpha\text{ intero} \\
&\lim_{ \alpha \to 0 } \frac{\sin(\pi \alpha)}{\pi \alpha}=1 \\
&a\left( \frac{T}{T_{0}} \right)\text{sinc}(kf_{0}t)=a \left( \frac{T}{T_{0}} \right)\text{sinc}\left( k \frac{T}{T_{0}} \right)=a\delta\text{sinc}(k\delta) 
\end{align}$$
La funzione $\text{sinc}$ è pari in quanto rapporto di due funzioni dispari. Nell'origine di ha una discontinuità che si può eliminare (dimostrato da limite). La funzione tende a $0$ per $\alpha$ che tende a $\infty$.

![[Pasted image 20250325181849.png]]

## Segnali Pari e Dispari
### Segnali Pari

>[!gray] Il segnale $x(t)$ è pari se
>1. $x(t)=x(-t)$. Il coefficiente della serie $X_{k}$ allora è una funzione pari di $k$ 
>2. $X_{k}=X_{-k}$ (essendo $x(t)$ reale, $X_{-k}=X^*_{k}$) si può scrivere $x(t)=X_{0}+2\sum_{k=1}^\infty \cos(2\pi kf_{0}t)$ 
>
>**Dimostrazione:** 
>1. 
>$$
\begin{align}
X_{-k}&= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi(-k)f_{0}t}\ dt\overset{\text{cambio di variabile}}{=} -\frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(-\alpha)e^{-j_{2}\pi kf_{0}\alpha}\ d\alpha=  \\
&\overset{\text{essendo }x(t)\text{ pari}}{=}
int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(-\alpha)e^{-j_{2}\pi kf_{0}\alpha}\ d\alpha = -\frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(\alpha)e^{-j_{2}\pi kf_{0}\alpha}\ d\alpha \\
&= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(\alpha)e^{-j_{2}\pi kf_{0}\alpha}\ d\alpha= X_{k}
\end{align}
>$$ 
>2. 
>$$
\begin{align}
x(t)&= X_{0}+\sum^\infty_{k=1} X_{k}e^{j_{2}\pi kf_{0}t}+\sum_{k=-\infty}^{-1}X_{k}e^{j_{2}\pi kf_{0}t}= \\
& \overset{\text{cambio di variabile }k\text{ in -k} }{=}X_{0}+\sum^\infty_{k=1}X_{k}e^{j_{2}\pi kf_{0}t}+\sum_{k=1}^\infty X_{-k}e^{-j_{2}\pi kf_{0}t}= \\
&=X_{0}+\sum^\infty_{k=1}X_{k}(e^{j_{2}\pi kf_{0}t}+e^{-j_{2}\pi kf_{0}t})=X_{0}+2\sum_{k=1}^\infty X_{k}\cos(2\pi f_{0}t)
\end{align}
>$$

Se $x(t)$ è reale e pari si può usare una formula semplificativa per il calcolo fi $X_{k}$:
$$\begin{align}
X_{k}&=\frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)e^{-j_{2}\pi kf_{0}t}\ dt=\frac{1}{T_{0}}\underset{\text{pari}\cdot \text{pari}=\text{pari}}{\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)\cos(2\pi kf_{0}t)\ dt} \\
&=-\frac{j}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t)\sin(2\pi kf_{0}t)\ dt
\end{align}$$
L'integrale di una funzione pari su un intervallo simmetrico rispetto a $0$ è pari al doppio dell'integrale su metà dell'intervallo
$$
X_{k}=\frac{2}{T_{0}}\int_{0}^{\frac{T_{0}}{2}}x(t)\cos(2\pi kf_{0}t)\ dt -0 = \frac{2}{T_{0}}\int_{0}^{\frac{T_{0}}{2}}x(t)\cos(2\pi kf_{0}t)\ dt \quad \in\mathcal{Re}
$$
L'integrale di una funzione dispari su un intervallo simmetrico rispetto a $0$ è nullo
### Segnali Dispari
>[!gray] Il segnale $x(t)$ è dispari se:
>1. $x(t)=-x(-t)$. Il coefficiente della serie di Fourier $X_{k}$ è una funzione dispari di $k$.
>2. $X_{k}=-X_{k}$. Inoltre, essendo $x(t)$ reale si ha $X_{-k}=X^*_{k}$, quindi il coefficiente $X_{k}$ è immaginario puro: $X_{-k}=X^*_{k}=-X_{k}$, ne consegue che $X_{0}=0$. SI può scrivere $$x(t)=2j\sum_{k=1}^\infty X_{k}\sin(2\pi kf_{0}t)$$
**Dimostrazione:**
>Se $x(t)$ è reale e dispari si può usare una formula semplificativa per il calcolo di $X_{k}$
>$$\begin{align}
X_{k}&= \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}} x(t)e^{-j_{2}\pi kf_{0}t}\ dt = \frac{1}{T_{0}}\underset{\text{dispari}\cdot \text{pari}=\text{dispari} }{\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}} x(t) \cos(2\pi kf_{0}t)\ dt} \\
&-\frac{j}{T_{0}}\underset{\text{dispari}\cdot \text{dispari}=\text{pari} }{\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}} x(t)\sin(2\pi kf_{0}t)\ dt}= \\
&= 0- \frac{2j}{T_{0}} \int_{0}^{\frac{T_{0}}{2}} x(t)\sin(2\pi kf_{0}t)\ dt
\end{align}
>$$

> [!example]+ Esempio: Segnale Onda Quadra
 ![[Pasted image 20250328131408.png]]

>[!example]+ Esempio: Segnale Onda Quadra Asimmetrica
![[Pasted image 20250328131548.png]]

> [!tip] Nota
> - Lo *Spettro di Ampiezza* esprime quindi quali sinusoidi (e con quali ampiezza) servono a sintetizzare il segnale di una certa forma
> - Lo *Spettro di Fase* indica la fase iniziale di ogni sinusoide che dipende dalla posizione del segnale da sintetizzare

## Sintesi del Segnale con un Numero Limitato di Armoniche
#### Onda Quadra Asimmetrica
Sviluppo in serie del segnale onda quadra $z(t)$ (onda quadra asimmetrica dell'esempio): essendo dispari è sviluppabile in soli seni
$$z(t)=2j\sum_{k=1}^\infty Z_{k}\sin(2\pi kf_{0}t)$$
con 
$$
Z_{k}=\begin{cases}
0 & k \text{ pari} \\
\frac{2A}{j\pi k} &k \text{ dispari}
\end{cases}
$$
Quindi:
$$
z(t)= \frac{4A}{\pi}\sum_{k=1,\text{dispari}}^\infty \frac{\sin(2\pi kf_{0}t)}{k}
$$
![[Pasted image 20250328132429.png]]

L'ampiezza tende a $0$ per $k\to \infty$ come $\frac{1}{k}$. Questa è la velocità minima con cui lo spettro di ampiezza può decrescere affinché la serie sia convergente. Quindi l'ampiezza delle componenti armoniche alle alte frequenze è ancora relativamente grande rispetto alla prime armoniche.
#### Onda Triangolare
Per osservare le peculiarità precedentemente menzionate, si considera lo sviluppo in serie del segnale onda triangolare $x(t)$

![[Pasted image 20250328132831.png|center|500]]

con 
$$
x(t)=\begin{cases}
A\left( 1+ \frac{4t}{T_{0}} \right) & -\frac{T_{0}}{2}\le 2 \le 0 \\
A\left( 1- \frac{4t}{T_{0}} \right) & 0\le t \le \frac{T_{0}}{2}
\end{cases}
$$
Essendo pari, si può usare la formula semplificata in cui si considera solo la parte destra del segnale:
$$
\begin{align}
X_{k}&= \frac{2}{T_{0}} \int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}x(t)\cos(2\pi kf_{0}t) \ dt = \frac{2}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}A\left( 1- \frac{4t}{T_{0}} \right)\cos_{2}(2\pi kf_{0}t)= \\
&= \frac{2A}{T_{0}}\int_{0}^{\frac{T_{0}}{2}}\cos(2\pi kf_{0}t)\ dt -\frac{8A}{T_{0}}\int_{0}^{\frac{T_{0}}{2}} \frac{t}{T_{0}}\cos(2\pi kf_{0}t)\ dt\overset{ \left( \int_{0}^{\frac{T_{0}}{2}} \cos(2\pi kf_{0}t) \ dt \right)}{=} \\
&= \int^{\frac{T_{0}}{2}}_{0} \frac{t}{T_{0}}\cos(2\pi kf_{0}t) \ dt = \frac{T_{0}}{(2\pi k)^2}[(-1)^k-1]
\end{align}
$$
quindi
$$
X_{k}= \frac{2A}{(\pi k)^2}[1-(-1)^k] = \begin{cases}
0 & k \text{ pari} \\
\frac{4A}{(\pi k)^2} & k \text{ disparo}
\end{cases}
$$
![[Pasted image 20250328134935.png]]

L'ampiezza tende a $0$ per $k\to \infty$ come $\frac{1}{k^2}$, quindi lo spettro di ampiezza decresce più velocemente rispetto al caso precente. Quindi le componenti armoniche alla alte frequenze hanno minore importanza nella sintesi dell'onda triangolare rispetto all'onda quadra.
### Osservazioni
L'onda quadra presenta discontinuità, cioè brusche variazioni temporali de valore del segnale. Queste variazioni comportano la presenza di armoniche di frquenza di ordine più elevato. Quindi un segnale che cambia molto velocemente richiede molte componenti di ordine più elevato.
Perciò:
- Un segnale avente velocità di cambiamento molto alta richiede molto componenti di armoniche a frequenza più basse. (l'andamento delle ampiezze delle armoniche tipo $\frac{1}{k^2}$ è tipico dei segnali conderivata prima discontinua)
- Un segnale con variazioni più lente ha un contenuto di armoniche a frequenze più basse. 
L'equazione di sintesi richiede un numero illimitato di armoniche per ricostruire il segnale periodico, mentre se ne viene usato un numero limitato si ottiene un'approssimazione.
