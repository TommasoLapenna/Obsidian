Tags: [[Tags/Fondamenti di Segnali e Trasmissione|Fondamenti di Segnali e Trasmissione]] [[University]]

## Dalla Serie all'Integrale di Fourier
Si può rappresentare un segnale non periodico come un opportuna sovrapposizione di segnali elementari (in particolare sinusoidi).
### Trasformata Continua di Fourier
Rappresentazione di funzioni non periodiche, definite tra $-\infty$ e $\infty$, tramite somma di infinite armoniche semplici di ampiezza infinitesima e frequenza variabile tra $-\infty$  e $\infty$.

**Esempio: Impulso Rettangolare Aperiodico**

![[Pasted image 20250328223635.png]]

$x_{p}(t)$ è ottenuto periodicizzando $x(t)$ con periodo $T_{0}$. Il segnale originario $x(t)$ può essere considerato un caso limite di un segnale periodico: Partendo da $x_{p}(t)$, si ottiene un impulso base $x(t)$ centrato in $t=0$ se si pensa di fare una periodicizzazione di periodo $T_{0}\to \infty$ ($x(t)=\lim_{ T_{0} \to \infty }x_{p}(t)$), quindi

![[Pasted image 20250328224014.png]]
$x_{p}(t)$, essendo periodico, può essere rappresentato mediante la serie di Fourier
$$x_{p}(t)=\sum_{k=-\infty}^\infty X_{k}e^{j_{2}\pi kf_{0}t},\quad \text{con }f_{0}=\frac{1}{T_{0}},\quad X_{k}=\frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}X_{p(t)}e^{-j_{2}\pi kf_{0}t}\ dt$$

![[Pasted image 20250328224313.png | center | 550]]

Quando $T_{0}\to \infty$, si riduce la frequenza fondamentale $f_{0}$, quindi si riduce la distanza tra due generiche frequenze armoniche consecutive $kf_{0}-(k-1)f_{0}=f_{0}$. Ciò determina un infittimento dello spettro del segnale (la scala delle frequenze è stata normalizzata al valore della durata $T$ dell'impulso $x(t)$, attraverso la variabile data dal prodotto $fT$).
Si Può rimediare alla riduzione delle ampiezze delle armoniche $kf_{0}$ definendo un coefficiente di Fourier modificato:
$$
X(kf_{0})=T_{0}X_{k}=\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x_{p}(t)e^{-j_{2}\pi kf_{0}t}\ dt= T\text{sinc}(kf_{0}T)
$$
Così facendo l'ampiezza rimane la solita nonostante diventi più fitto il grafico, in quanto è evidente che non tende a $0$ per $T_{0}\to \infty$.

![[Pasted image 20250330120530.png]]



Si riscrive l'espansione in serie di Fourier di $x_{p}(t)$ usando il coeficiente modificato, ovvero al posto di $X_{k}$ si mette $\frac{X(kf_{0})}{T_{0}}$ ovvero $X(kf_{0})f_{0}$
$$
x_{p}(t)=\sum^\infty_{k=-\infty} X(kf_{0})e^{j_{2}\pi kf_{0}t}\cdot f_{0}
$$
in questo caso, quando $T_{0}\to \infty$:
- $x_{p}(t)\to x(t)$
- $f_{0}\to 0$, ovvero un valore infinitesimo indicato con $df$
- $kf_{0}\to$ ad un valore non discreto ma continuo, indicato con $f$
- dalla sommatoria si passa all'integrale
Il risultato è:
$$
x(t)=\int_{-\infty}^\infty X(f)e^{j_{2}\pi ft}\ df
$$
Viceversa, per il coefficiente modificato si ha
$$
X(kf_{0})= T_{0}X_{k}=\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}} x_{p}(t)e^{-j_{2}\pi kf_{0}t}\ dt
$$
in questo caso, quando  $T_{0}\to \infty$:
- $x_{p}(t)\to x(t)$
- $kf_{0}\to$ ad un valore non discreto ma continuo, indicato con $f$
- Gli estremi dell'integrale $\pm \frac{T_{0}}{2}\to \infty$
Il risultato è 
$$
X(f)=\lim_{\begin{align}
&T_{0}\to \infty \\
&f_{0}\to 0
\end{align} }\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x_{p}(t)e^{-j_{2}\pi kf_{0}}t\ dt = \int_{-\infty}^{\infty} x(t)e^{-j_{2}\pi f}\ dt 
$$
$X(f)$ è una funzione complessa della variabile continua $f$ (da $kf_{0}$ quando $f_{0}\to 0$), da cui lo spettro di ampiezza diventa non più a righe, ma continuo. 

![[Pasted image 20250330120436.png]]

Nella serie di Fourier per un segnale periodico, quest'ultimo viene raappresentato con componenti sinusoidali a frequenze in relazione armonica, cioè multiple di un'unica fondamentale, nonché di ampiezza finita. Nel caso del segnale aperiodico, con l'antitrasformata di Fourier si può ancora rappresentare il segnale aperiodico $x(t)$ come sovrapposizione di componenti sinusoidali, ma questa volta con ampiezza infinitesima $|X(f)|\ df$ e di frequenza $f$ variabile con continuità su tutto l'asse reale.
Più semplicemente:
- Il segnale aperiodico è visto come un segnale periodico di periodo illimitato e quindi con frequenza fondamentale infinitesamente piccola. Il numero discreto di armoniche della serie degenera  in un insieme continuo di componenti.

> [!gray] Un segnale aperiodico $x(t)$ è rappresentabile attraverso l'*Intergale di Foureir*
> *Antitrasformata di Fourier*:
> $$
> x(t)=\int_{-\infty}^\infty X(f)e^{j_{2}\pi ft}\ df
> $$
>Equazione di sintesi, rappresenta il segnale come sovrapposizione di segnali elementari.
> <br>
> *Trasformata Continua di Fourier:*
> $$
> X(f)=\int_{-\infty}^\infty x(t)e^{-j_{2}\pi ft}\ dt
> $$
> Equazione di analisi, permette di determinare il peso che le varie componenti frequenziali hanno nella composizione di $x(t)$.

Queste relazioni mettono in corrispondenza un segnale nel tempo con la propria trasformata di Fourier (funzione a valori complessi nella frequenza)
$$
\underset{\text{Dominio del Tempo}}{x(t)}\iff\underset{\text{Dominio della frequenza}}{X(f)}
$$
La conoscenza dell'andamento nel tempo di un segnale equivale a conoscerne l'andamento nella frequenza.
Altre rappresentazioni della trasformata ed antitrasformata:
$$
\begin{align}
&X(f)=\text{TCF}[x(t)]& &x(t)=\text{ICTF}[X(f)]& \\
&X(f)=\mathcal{F}[x(t)]& &x(t)=\mathcal F^{-1}[X(f)]&
\end{align}
$$
Si può estrarre dalla funzione complessa $X(f)$ le funzioni reali modulo $A(f)$ e fase $\theta(f)$ secondo la relazione
$$
X(f)=A(f)e^{j\theta(f)}
$$
con:
- $A(f)$ spettro di ampiezza del segnale
- $\theta(f)$ spettro di fae del segnale


> [!example]+ Esempio: Calcolo della trasformata di Fourier del segnale Impulso Rettangolare
> $x(t)=\text{rect}\left( \frac{t}{T} \right)$
> ![[Pasted image 20250330123419.png|center|550]]
> $$\begin{align} 
>  X(f)&= \int_{-\infty}^\infty x(t)e^{-j_{2}\pi f}\ dt =\int_{-\frac{T}{2}}^{\frac{T}{2}}e^{-j_{2}\pi ft}\ dt= \left[\frac{e^{-j2\pi f}}{-j_{2}\pi f}\right]^{\frac{T}{2}}_{-\frac{T}{2}}=\frac{\sin(\pi fT)}{\pi f} = \frac{T}{T}\cdot \frac{\sin(\pi fT)}{\pi f} \\
> &= T\text{sinc}(fT)
> \end{align}$$
> quindi
> $$
> \text{rect}\left( \frac{t}{T} \right)\iff T\cdot \text{sinc}(fT)
> $$
> **Spettro di Ampiezza:**
> $$
> |X(t)| = |T\cdot \text{sinc}(fT)|
> 
> $$
> ![[Pasted image 20250330152330.png| center | 500]]
> 
> Presenza di infiniti nulli per tutte le frequenze multiple intere dell'inversi della durata dell'impulso (escluso $f=0$)<br>
> **Spettro di Fase:**
> $$
> \angle X(f)=T\cdot \text{sinc}(fT)
> $$
> ![[Pasted image 20250330152525.png |center|500]] 
>$X(f)$ è reale, quindi la fase è data dal segno del $\text{sinc}$: $0$ oppure $\pm \pi$

>[!gray] Trasformata Impulso e Treno di Impulsi Rettangolare
>$$\begin{align}
&x(t)=\text{rect}\left( \frac{t}{T} \right)& &|X(f)|=|T\text{sinc}(fT)|& \\
&x(t)=\sum_{-\infty}^\infty \text{rect}\left( \frac{t-nT_{0}}{T} \right)& &X_{k}=\frac{T}{T_{0}}\text{sinc}\left( \frac{kT}{T_{0}} \right)&
\end{align}$$

> [!hint] Verifica Correttezza 
> Una verifica tra il segnale e la sua trasformata può essere effettuata osservando l'equazione di analisi quando si pone $f=0$, si ha:
> $$
> X(0)=\int_{-\infty}^{\infty}x(t)\ dt
> $$
> Cioè $X(0)$ è pari al valore medio del segnale

> [!example]+ Esempio: Funzione Gradino Unitario ed Esponenziale Unilatero
>*Gradino Unilatero* 
>$$
> u(t)=\begin{cases}
> 1 & t>0 \\
> \frac{1}{2} & t=0 \\
> 0 & t<0
> \end{cases}
> $$
>
>![[Pasted image 20250330155206.png | center | 550]]
Discontinua nell'origine, utile per rappresentare i segnali causali, cioè nulli per  $t<0$.
> Un esponente di questa classe è il segnale *Esponenziale Unilatero*:
> $$
> x(t)=e^{-\frac{t}{T}}\cdot u(t)= \begin{cases}
> e^{-\frac{t}{T}} & t\ge 0 \\
> 0 & t<0
> \end{cases}
> $$
> ![[Pasted image 20250330160720.png| center | 550]]
> TCF dell'esponenziale unilatero $x(t)$
> $$\begin{align}
> X(f)&=\int_{-\infty}^\infty x(t)e^{-j 2\pi f}\ dt=\int_{{-\infty}}^\infty e^{-\frac{t}{T}}u(t)e^{-j 2\pi}\ dt = \int_{0}^{\infty} e^{-t\left( \frac{1}{T}+j 2\pi f \right)}\ dt = \left[ - \frac{e^{-t \left( \frac{1}{T} +j 2\pi f \right)}}{\frac{1}{T}+(2\pi fT)^2} \right]^\infty_{0} \\
> &= - \frac{0-e^0}{\frac{1}{T}+j 2\pi f}= \frac{1}{\frac{1}{T}+j 2\pi f}= \frac{T}{1+j 2\pi f T}= \frac{T(1-j 2\pi fT)}{(1+j 2\pi ft)(1-j 2\pi fT)}= \frac{T(1-j 2 \pi fT)}{1+(2\pi fT)^2}
> \end{align}$$
> Quindi la trasformata è
> $$
> X(f)= \frac{T(1-j 2\pi fT)}{1+(2\pi fT)^2}\qquad \begin{aligned}
> &\mathcal{Re}\{(X(f)\}= \frac{T}{1+(2 \pi fT)^2}
> \\ &\mathcal{Im}\{X(f)\}= - \frac{T(2 \pi fT)}{1+(2\pi fT)^2}
> \end{aligned} 
> $$
> Allora gli spettri del segnale $x(t)$ sono:
> - Ampiezza
> $$
> A(f)= \frac{T}{\sqrt{ 1+(2\pi fT)^2 }}
> $$
> ![[Pasted image 20250331104700.png|center|400]]
> 
> - Fase
> $$
> \theta(f)=-\arctan(2\pi f T)
> $$
> ![[Pasted image 20250331105121.png|center|400]]
> 
## Proprietà della Trasformata di Fourier
### Crisi di Esistenza
Ci sono dei criteri sufficienti per la rappresentazione di un segnale $x(t)$ tramite la propria trasformata $X(f)$.

> [!gray] Condizioni Sufficienti
> Un *primo criterio sufficiente* è che segnale $x(t)$ ha energia finita, ovvero
> $$
> E_{x}=\int_{-\infty}^\infty |x(t)|^2\ dt<+\infty
> $$
> Allora la trasformata $X(f)$ esiste, nel senso che l'integrale di analisi è convergente, e la rappresentazione di $x(t)$ come antitrasformata ($x(t)=\int_{-\infty}^\infty X(f)e^{j 2\pi ft}\ df$) vale quasi ovunque (cioè eccetto al più un numero finito di punti). <br>
> Un *secondo criterio sufficiente* meno restrittivo (*Criterio di Dirichlet*) può essere enunciato come segue:
> 1. Se il segnale è assolutamente sommabile, ovvero 
> $$\int_{-\infty}^\infty|x(t)|\ dt<+\infty$$
> 2. Se in un qualunque intervallo finito $t_{1}\le t\le t_{2}$ il segnale $x(t)$ è continuo o ha un numero finito di discontinuità di prima specie
> 3. Se in un qualunque intervallo finito $t_{1}\le t\le t_{2}$ il segnale $x(t)$ ha un numero finito di massimi e minimi
> 
Allora $x(t)$ è rappresentabile come integrale di Fourier e nei punti di discontinuità l'integrale converge alla semisomma dei limiti destro e sinistro ($\frac{x(t_{0}^+)+x(t_{0}^-)}{2}$).

### Simmetrie degli Spettri
La funzione complessa $X(f)$ può essere rappresentata in forma polare o rettangolare
$$
X(f)=R(f)+jI(f)
$$
Si suppone che $X(f)$ sia reale, allora si ricava da $X(f)=\int_{-\infty}^\infty x(t)e^{-j 2 \pi ft}\ dt$
$$
R(f)=\int_{-\infty}^\infty x(t)\cos(2\pi ft)\ dt \qquad I(f)=-\int_{-\infty}^\infty x(t)\sin(2\pi ft)\ dt
$$
Si può osservare chiaramente che 
$$
\underset{\cos(a)=\cos(-a)}{R(f)=R(-f)}\qquad \underset{\sin(a)=-\sin(-a)}{I(f)=-I(-f)}
$$
- La parte reale è una funzione pari
- La parte immaginaria è una funzione dispari

>[!gray] Simmetire
> $$ X(f)=X^*(-f) $$
>La trasformata gode quindi di simmetria Hermitiana, cioè
>$$
>X(f)=R(f)+jI(f)=R(-f)-jI(f)=X^*(f)
>$$
Questa proprietà si riflette inoltre sulle funzioni $\theta(f)$ e $A(f)$
>$$
> \underset{\text{pari}}{A(f)=A(-f)}\qquad \underset{\text{dispari}}{\theta(f)=-\theta(-f)}
>$$

### Segnali Pari e Dispari
> [!gray] ->
> Se il segnale $x(t)$ è reale e pari
> $$
> R(f)=2\int_{0}^\infty x(t)\cos(2\pi ft)\ dt\qquad I(f)=0
> $$
> - $x(t)\cos(2\pi ft)$ è pari su un intervallo simmetrico
> - $x(t)\sin(2\pi ft)$ è dispari su un intervallo simmetrico
> Ciò dimostra che la trasformata di un segnale reale e pari è una funzione reale e pari della frequenza.
> $$\left.\begin{aligned}
> &X(f)=R(f)
> \\ &R(f)=R(-f)
> \end{aligned}\right\}\ X(f)=X(-f),\quad X(f)\text{ Reale}$$
> <br>Se il segnale $x(t)$ è reale e dispari
> $$
> R(f)=0\qquad I(f)=-2\int_{0}^\infty x(t)\sin(2\pi ft)\ dt
> $$
> - $x(t)\cos(2\pi ft)$ è dispari su un intervallo simmetrico
> - $x(t)\sin(2\pi ft)$ è pari su un intervallo simmetrico
> Ciò dimostra che la trasformata di un segnale reale e dispari è una funzione immaginaria pura e dispari.
> 

> [!example]+  Esempio: Calcolo della trasformata di Fourier del segnale Esponenziale Bilatero
> $y(t)=e^{-\frac{|t|}{T}}$
> ![[Pasted image 20250331122437.png|center|400]]
> $$
> \int_{-\infty}^\infty|y(t)|\ dt= \int_{-\infty}^\infty y(t)\ dt =2 \int_{0}^\infty e^{- \frac{t}{T}}\ dt = 2T<\infty
> $$
> Inoltre non presenta discontinuità di prima specie e in ogni intervallo finito ha un numero finito di massimi e minimi, per cui esiste la trasformata $X(f)$. Siccome $y(t)$ è reale e pari, $Y(f)$ sarà reale pari.
> $$\begin{align}
> Y(f)&=\int_{-\infty}^\infty y(t)e^{-j 2\pi ft}\ dt = \int_{-\infty}^0 e^{-t\left( - \frac{1}{T}+j 2\pi f \right)}\ dt+ \int_{0}^\infty e^{-t\left(  \frac{1}{T}+j 2\pi f \right)}\ dt \\
> &=  -\left[\frac{e^{-t\left( - \frac{1}{T}+j 2\pi ft \right)}}{- \frac{1}{T}+j2\pi ft}\right]_{t=-\infty}^{t=0}-\left[\frac{e^{-t\left(  \frac{1}{T}+j 2\pi ft \right)}}{ \frac{1}{T}+j2\pi ft}\right]_{t=0}^{t=\infty}= \frac{2T}{1+(2\pi fT)^2}
> \end{align}$$
> Come previsto, si ottiene
> $$
> R(f)= \frac{2T}{1+(2\pi fT)^2}\qquad I(f)=0
> $$
> Lo spettro normalizzato
> ![[Pasted image 20250331124654.png|center|400]]
> Lo spettro di fase $\angle X(f)$ è invece $0$

> [!example]+ Esempio: 
> $x(t)=\frac{t}{T}\text{rect}\left( \frac{t}{T} \right)$
> ![[Pasted image 20250331170758.png|center|400]]
> Le condizioni di Dirichlet sono verificate, infatti
> $$\int_{-\infty}^\infty|x(t)|\ dt= \int_{-\frac{T}{2}}^{\frac{T}{2}} \frac{|t|}{T}\ dt=2\int_{0}^{\frac{T}{2}} \frac{t}{T}\ dt= \frac{T}{4}<\infty$$
> Il segnale $x(t)$ presenta due discontinuità di prima specie, rispettivamente in $t=-\frac{T}{2}$ e $t=\frac{T}{2}$, Su qualsiasi intervallo finito $t_{1}\le t \le t_{2}$ ha un numero finito di massimi e minimi.
> La trasformata di Fourier è data da 
> $$
> X(f)=\int_{-\infty}^\infty x(t)e^{-j_{2}\pi ft}\ dt= \int_{-\frac{T}{2}}^{\frac{T}{2}} \frac{t}{T}e^{-j_{2}\pi ft}\ dt
> $$
> Attraverso l'integrazione per parti, può essere calcolata come
> $$\begin{align}
> X(f)&= \left[\frac{e^{-j 2\pi ft}}{(-j 2\pi ft)^2T}\right]^{\frac{T}{2}}_{-\frac{T}{2}}+ \left[ \frac{t\cdot e^{-j2ft}}{-j 2\pi ft } \right]^{\frac{T}{2}}_{-\frac{T}{2}} = \\
> &= - \frac{1}{(-j 2\pi f)^2T}\cdot [e^{-j\pi fT}-e^{j\pi fT}]+ \frac{1}{-j_{2}\pi f}\cdot \frac{1}{2} [e^{-j\pi fT}+e^{j\pi fT}]= \\
> &=\frac{1}{j_{2}\pi f}\cdot [\text{sinc}(fT)-\cos(\pi fT)]
> \end{align}$$
> 

## Teoremi sulla Trasformata di Fourier

> [!gray] ->
> Se $x(t)=a\cdot x_{1}(t)+b \cdot x_{2(t)}$, con $a$ e $b$ costanti, allora
> $$
> X(f)=aX_{1(f)}+b X_{2(f)}
> $$
> dove $X_{1}=TCF[x_{1}(t)]$ e $X_{2}=TCF[x_{2(t)}]$
> <br>**Dimostrazione:**
> Applicando la definizione di $TCF$:
> $$
> X(f)=\int_{-\infty}^\infty x(t)e^{-j_{2}\pi ft}\ dt = \int_{-\infty}^\infty [a\cdot x_{1}(t)+ b\cdot x_{2}(t)]e^{-j 2\pi ft}\ dt
> $$
> Sfruttando poi la linearità dell'integrale:
> $$
> X(f)=a\int_{-\infty}^\infty x_{1}(t)e^{-j 2\pi ft}\ dt+b\int_{-\infty}^\infty x_{2}(t)^{-j 2\pi ft} \ dt= a\cdot X_{1}(f)+b\cdot X_{2(f)}
> $$
> 

### Teorema di Dualità

> [!gray] ->
> Se $x(t)\iff X(f)$, allora
> $$
> X(t)\iff x(-f)
> $$
> ![[Pasted image 20250331173717.png|center|500]]
> <br>**Dimostrazione:**
> Il segnale $x(t)$ è legato alla sua trasformata dalla relazione 
> $$x(t)=\int_{-\infty}^\infty X(f)e^{j 2\pi ft}\ df$$
> Scambiando formalmente le variabili $t$ ed $f$ si ricava
> $$
> x(f)=\int_{-\infty}^{\infty}X(t)e^{j 2\pi ft} df
> $$
> Se poi si effettua un cambiamento di variabile sostituendo $f$ con $-f$ si ottiene
> $$
> x(-f)=\int_{-\infty}^\infty X(t)e^{-j 2\pi ft}\ dt
> $$
> 

> [!example]+ Esempio:
> Si è dimostrato che $\text{rect}\left( \frac{t}{T} \right)\iff T\text{sinc}(fT)$.
> Usando la dualità è possibile scrivere
> $$
> T\text{sinc}(Tt)\iff \text{rect}\left( -\frac{f}{T} \right)
> $$
> Poiché l'impulso rettangolare è una funzione pari, ponendo formalmente $B=T$ si ottiene
> $$
> \text{sinc}(Bt)\iff \frac{1}{B}\text{rect}\left( \frac{f}{B} \right)
> $$
> ![[Pasted image 20250331181859.png]]

### Teorema del ritardo

> [!gray] ->
> Se $X(f)=TCF[x(t)]$, la trasformata del segnale ritardato nel tempo di un valore $t_{0}$ è legata a $X(f)$
> $$x(t-t_{0})\iff X(f)e^{-j 2\pi ft_{0}}$$<br>**Dimostrazione:**
> Applicando la definizione di trasformata si ha
> $$
> x(t-t_{0})\iff \int_{-\infty}^\infty x(t-t_{0})e^{-j_{2}\pi ft}\ dt
> $$
> Se si effettua il cambiamento di variabile $\alpha=t-t_{0}$ si ricava
> $$
> x(t-t_{0})\iff \int_{-\infty}^\infty x(\alpha)e^{-j 2\pi f(\alpha+t_{0})}\ d \alpha=e^{-j_{2}\pi ft_{0}}\int_{-\infty}^\infty x(\alpha) e^{-j_{2}\pi f\alpha}= e^{-j_{2}\pi ft_{0}}X(f)
> $$
> Questa proprietà mostra che un ritardo temporale modifica lo spettro di fase della trasformata del segnale, ma non cambia il suo spettro di ampiezza. Infatti, indicando $y(t)=x(t-t_{0})$, $X(f)=TCF[x(t)]$ e $Y(f)=TCF[y(t)]$ si ottengono le seguenti relazioni
> $$
> Y(f)=X(f)e^{-j 2\pi ft_{0}} \qquad |Y(f)|=|X(f)|\qquad \angle Y(f)=\angle X(f)-2\pi ft_{0}
> $$

> [!example]+ Esempio: Impulso Rettangolare Ritardato
> Si considera un ritardo $t_{0}= \frac{T}{2}$, quindi $x(t)=A\cdot \text{rect}\left( \frac{t- \frac{T}{2}}T{} \right)$
> ![[Pasted image 20250331183851.png|center|400]]
> $$X(f)=AT\text{sinc}(fT)e^{-j_{2}\pi f \frac{T}{2}}=AT\text{sinc}(fT)e^{-j\pi fT}$$
> I rispettivi spettri sono
> $$\underset{\text{Non cambia}}{|X(f)|=|AT\cdot\text{sinc}(fT)|}\qquad \underset{\text{Ha un secondo termine}}{\angle X(F)=\angle AT\cdot\text{sinc}(fT)-\pi fT}$$
> Allo spettro di fase "originario" verrà quindi sommata una retta con pendenza $-\pi T$, in modulo $2\pi$ (ovvero la retta si ripete con periodo $2\pi$)
>
> ![[Pasted image 20250331184920.png|center|500]]
### Teorema del Cambiamento di Scala
Si considera una situazione generale in cui due segnali sono legati dalla relazione $y(t)=x(\alpha t)$, cioè si effettua un cambiamento della scala temporale. Moltiplicando la variabile indipendente $t$ del segnale $x(t)$ per il coefficiente $\alpha$ si producono i seguenti effetti:
- $|\alpha|>1\Longrightarrow$ Compressione della scala dei tempi
- $|\alpha|<1\Longrightarrow$ Dilatazione della scala dei tempi
- $|\alpha|>1\Longrightarrow$ Inversione della scala dei tempi
In altre parole, se $|\alpha|>1$ l'evoluzione del segnale viene accelerata, viceversa per $\alpha<1$.  Operazioni di questo tipo vengono effettuate correntemente nell'elaborazione dei segnali registrando il segnale ad una certa velocità e riproducendolo a velocità diversa.
![[Pasted image 20250331190237.png|center|500]]

> [!gray] ->
> Se $X(f)=TCF[x(t)]$ la trasformata del segnale accelerato/rallentato di un fattore $\alpha$ è legata a $X(f)$:
> $$
> x(\alpha t)\iff \frac{1}{|\alpha|}X\left( \frac{f}{\alpha} \right)
> $$
> <br>**Dimostrazione:**
> Si suppone per semplicità che $\alpha>0$, applicando la definizione di trasformata si ha
> $$
> x(\alpha t)\iff \int_{-\infty}^\infty x(\alpha t)e^{-j_{2}\pi ft}\ dt
> $$
> Si effettua la sostituzione $z=\alpha t$ al secondo membro
> - Se $\alpha>0$ 
>$$
> x(\alpha t)\iff \frac{1}{\alpha}\int_{-\infty}^\infty x(z)e^{ j_{2}\pi f \frac{z}{\alpha}}\ dz = \frac{1}{\alpha}\int_{-\infty}^\infty x(z)e^{-j_{2}\pi z \frac{f}{\alpha}}\ dz = \frac{1}{\alpha} X\left( \frac{f}{\alpha} \right)
> $$
> - Se $\alpha<0$ 
>$$
> x(\alpha t)\iff - \frac{1}{\alpha} \int_{-\infty}^\infty x(z)e^{-j_{2}\pi f \frac{z}{\alpha}}\ dz = - \frac{1}{\alpha}X\left( \frac{f}{\alpha} \right)
> $$
>
> Questi due risultati possono essere riassunti da
> $$
> x(\alpha t)\overset{TCF}{\iff} \frac{1}{|\alpha|} X\left( \frac{f}{\alpha} \right)
> $$
>
> Quindi una dilatazione dell'asse dei tempi comporta una compressione dell'asse delle frequenze e viceversa, se infatti il segnale viene rallentato, predominano le componenti frequenziali a bassa frequenza e lo spettro si addensa nell'intorno della frequenza nulla.

> [!example]+ Esempio: Segnale $\text{sinc}$
> Si considera il segnale $x(t)=\text{sinc}\left( \frac{t}{T} \right)$ e il segnale $y(t)=x\left( \frac{t}{2} \right)\text{sinc}\left( \frac{t}{2T} \right)$. Poiché $|\alpha|<1$, l'evoluzione del segnale viene rallentata.
> ![[Pasted image 20250401142248.png|center|450]]
> Si ha che
> $$
> X(f)=T\text{rect}(fT)\qquad Y(f)=2X(2f)=2T\text{rect}(2fT)
> $$
> ![[Pasted image 20250401142433.png|center|450]]
> Si può osservare che al segnale più lento corrisponde una trasformata contenente componenti a frequenze più basse
> $$
> \text{Dilatazione nel tempo}\iff \text{Compressione in frequenza}
> $$
> In modo analogo, se $\alpha=2>1$, il segnale viene accelerato
> $$\begin{align}
> x(t)=\text{rect}\left( \frac{t}{T} \right)&\iff X(f)=T\text{sinc}(fT) \\
> y(t)=x(2t)= \text{rect}\left( \frac{2t}{T} \right)&\iff Y(f)=\frac{1}{2}X\left( \frac{f}{2} \right)= \frac{T}{2}\text{sinc}\left( \frac{fT}{2} \right)
> \end{align}$$
> Al segnale più veloce corrisponde una trasformata contenete componenti a frequenze più alte
> $$
> \text{Compressione nel tempo}\iff \text{Dilatazione in frequenza}
> $$

### Teorema della Modulazione

> [!gray] ->
> Se $x(t)\iff X(f)$, allora
> $$
> x(t)=\cos(2\pi f_{0}t)\iff \frac{X(f-f_{0})+X(f+f_{0})}{2}
> $$
> <br>**Dimostrazione:**
> Si trova la trasformata del primo membro
> $$
> TCF[x(t)\cos(2\pi f_{0}t)]=\int_{-\infty}^\infty x(t)\cos(2\pi f_{0}t)e^{-j_{2}\pi ft}\ dt=
> $$
> applicando $\cos(2\pi f_{0}t)= \frac{e^{j_{2}\pi f_{0}t}+e^{-j_{2}\pi f_{0}t}}{2}$ si ricava
> $$\begin{align}
> =&\frac{1}{2}\int_{-\infty}^\infty x(t)e^{j_{2}\pi f_{0}t}e^{e^{-j_{2}\pi ft}}\ dt+\frac{1}{2}\int_{-\infty}^\infty x(t)e^{-j_{2}\pi f_{0}t}e^{-j_{2}\pi ft}\ dt =  \\
> =&\frac{1}{2}\int_{-\infty}^\infty x(t)e^{-j_{2}\pi(f-f_{0})t}+\frac{1}{2}\int_{-\infty}^\infty x(t)e^{-j_{2}\pi(f+f_{0})t}\ dt
> \end{align}$$
> ma per la *Traslazione in Frequenza* si ottiene
> $$
> \int_{-\infty}^\infty x(t)e^{j_{2}\pi(f-f_{0})t} \ dt = X(f-f_{0})\qquad \int_{-\infty}^\infty x(t)e^{j_{2}\pi(f+f_{0})t} \ dt= X(f+f_{0})
> $$
> Da cui il risultato (segnale modulato $x(t)\cos(2\pi f_{0}t)$)

> [!hint] Proprietà di Traslazione in Frequenza
> Se un segnale viene moltiplicato per un fattore esponenziale complesso $\exp(j2\pi f_{0}t)$, la sua trasformata viene traslata attorno alla frequenza $f_{0}$. Questo risultato rappresenta la *Traslazione in Frequenza* delle trasformata
> $$
> x(t)e^{j_{2}\pi f_{0}t}\iff X(f-f_{0})
> $$

> [!example]+ Esempio: Radar
> È noto che gli oggetti metallici riflettono le onde elettromagnetiche, e che questa proprietà dei corpi conduttori si accentua al crescere della frequenza della radiazione incidente. Su questo fenomeno sono basati i sistemi radar di rivelazione e misura della distanza di oggetti metallici. L'eventuale ricezione di un'eco permette di rivelare la presenza del bersaglio radar, cioè un oggetto metallico di grosse dimensioni.
> Attraverso la misura del ritardo $\tau$ dell'eco è possibile calcolare la distanza $d$ dell'oggetto riflettente il trasmettitore
> $$
> d=\frac{c\tau}{2}
> $$
> con $c$ velocità di propagazione dell'onda elettromagnetica ($c=3\cdot 10^8 \frac{m}{s}$), $\frac{1}{2}$ per il fatto che l'impulso percorre due volte la distanza $d$.
> Il valore tipico della durata dell'impulso è circa $1\mu$, per evitare (come succede per impulsi di durata maggiore) che l'eco si sovrapponga all'impulso trasmesso.
> ![[Pasted image 20250401145717.png|center|500]]
> Lo spettro di ampiezza del segnale trasmesso è allora 
> $$
> |X(f)|= T\text{sinc}(fT)|
> $$
> che si estende dalla frequenza $0$ fino a $f_{1}=\frac{1}{T}= 1 MHz$ (avendo $T=1\mu s$) che rappresenta il primo nullo della funzione $\text{sinc}$.
> Questi valori di frequenza però sono troppo bassi per provocare una riflessione adeguata e non garantiscono l'efficacia del radar.
> Diventa quindi necessario trasmetter un segnale che presenti contemporaneamente durata limitata, ma la cui parte significativa dello spettro si trovi a frequenze molto più elevate, nell'ordine di $1 GHz$ (per dar luogo ad una buona riflessione).
> Ciò che viene trasmesso dal radar è allora un impulso a radiofrequenza
> $$
> x(t)=\text{rect}\left( \frac{t}{T} \right)\cos(2\pi f_{0}t)
> $$
> ![[Pasted image 20250401150800.png|center|500]]
> Quindi lo spettro dell'impulso è della forma 
> $$
> \text{rect}\left( \frac{t}{T} \right)\cos(2\pi f_{0}t)\iff \frac{T\text{sinc}[(f-f_{0})T]+T\text{sinc}[(f+f_{0})T]}{2}
> $$
> ![[Pasted image 20250401151010.png|center|500]]
### Teoremi di Derivazione e Integrazione
#### Teorema di Derivazione

> [!gray] ->
> Se $x(t)\iff X(f)$, allora
> $$
> \frac{dx(t)}{dt}\iff j 2\pi ft\cdot X(f)
> $$
> <br>**Dimostrazione:**
> Si considera $x(t)$ con trasformata $X(f)$, espresso come integrale di Fourier $x(t)\int_{-\infty}^\infty X(f)e^{j 2\pi ft}\ df$. Se inoltre il segnale è derivabile
> $$\begin{align}
> \frac{dx(t)}{dt}&= \frac{d}{dt}\int_{-\infty}^\infty X(f)e^{j 2\pi ft}\ df = \int_{-\infty}^\infty \frac{d}{dt}[X(f)e^{j 2\pi ft}]\ df = \int_{-\infty}^\infty X(f) \frac{d}{dt} e^{j2\pi ft}\ df \\&=\int_{-\infty}^\infty X(f)(j 2\pi f)e^{j 2 \pi ft}\ df
> \end{align}$$
> Si può affermare $j 2\pi f X(f)$ è la trasformata $\frac{dx(t)}{dt}$. Ponendo  $Y(f)=(j2 \pi f)X(f)$ si ha infine
> $$
> \frac{dx(t)}{dt}=\int_{-\infty}^\infty Y(f)e^{j 2\pi ft}\ df 
> $$
> Quindi 
>$$
> \frac{dx(t)}{dt}\iff j2\pi f\cdot X(f) = Y(f)
> $$
> <br>L'operazione di derivata temporale di un segnale si traduce, nel dominio della frequenza, in una semplice operazione algebrica.
> $$\begin{align}
> |Y(f)|= |j 2\pi f\cdot X(f)|= 2 \pi f\cdot |X(f)|\qquad \angle Y(f)=\angle X(f)+\angle X(f)+\text{sgn}(f)\cdot \frac{\pi}{2}
> \end{align}$$
> L'effetto è un'alterazione di tutte le componenti frequenziali secondo un fattore $j 2\pi ft$ proporzionale al valore della frequenza stessa. Oltre ad uno sfasamento di $\pm \frac{\pi}{2}$, la derivata comporta una esaltazione delle componenti ad alta frequenza.
> 

> [!example]+ Esempio: 
> $x(t)=\exp\left( - \frac{|t|}{T} \right)$ e la sua derivata $y(t)$
> ![[Pasted image 20250401154504.png|center|550]]
#### Teoremi di Integrazione

> [!gray] ->
> Se $x(t)\iff X(f)$ e $\int_{-\infty}^t x(\alpha)\ d\alpha$, allora
> $$
> \int_{-\infty}^t x(\alpha)\ d\alpha \iff \frac{X(f)}{j 2\pi f}
> $$
> <br>**Dimostrazione:**
> Questo risultato segue immediatamente dal teorema di derivazione, e richiede che $X(0)=0$ per evitare che per $f\to_{0}$ il rapporto $\to \infty$ (ipotesa necessaria.
> Se $y(t)=\int_{-\infty}^t x(\alpha)\ d\alpha$ allora
> $$x(t)=\frac{dy(t)}{dt}$$
> Per il teorema della derivazione
> $$
> Y(f)=\frac{X(f)}{2\pi f}
> $$
> L'operazione, come per la derivata, nel dominio della frequenza si traduce in una semplice operazione algebrica. In questo caso vengono esaltate le componenti a bassa frequenza nello spettro del segnale e attenuate quelle alle alte frequenze, sempre con una fase variata di $\pm \frac{\pi}{2}$.

> [!example]+  Esempio:
> ![[Pasted image 20250401160434.png|center|550]]



> [!example]+ Esempio: Calcolo TCF dell'Impulso Triangolare
> $x(t)=A\cdot A\text{tr}\left( \frac{t}{T} \right)$
> ![[Pasted image 20250401161021.png|center|400]]
> Si trova la derivata prima $s(t)$ di $x(t)$
>  ![[Pasted image 20250401161815.png|center|400]]
>  $s(t)$ può essere espressa come segue:
>  $$s(t)= \frac{A}{T}\text{rect}\left( \frac{t+ \frac{T}{2}}{T} \right)- \frac{A}{T}\text{rect}\left( \frac{t- \frac{T}{2}}{T} \right)
> $$
> Utilizzando il teorema del ritardo e la trasformata dell'impulso rettangolare si calcola la trasformata di $s(t)$
> $$\begin{align}
> &S(f)= \frac{A}{T}T \text{sinc}(fT)e^{j 2\pi f \frac{T}{2}}- \frac{A}{2}\text{sinc}(fT)e^{-j 2\pi f \frac{T}{2}} \\
> &S(f)= A\text{sinc}(fT) (e^{j \pi fT}- e^{-j \pi fT})= 2jA\text{sinc}(fT)\sin(\pi fT)
> \end{align}$$
> Si osserva che $x(t)$ è evidentemente il segnale integrale di $s(t)$ e che $x(\infty)=0$, ovvero $s(t)$ sottende area nulla, è possibile utilizzare il teorema di integrazione e ricavare
> $$
> X(f)= \frac{S(f)}{j 2\pi f}= \frac{j 2A\text{sinc}(fT)\sin (\pi f T)}{j 2\pi f}= A T \text{sinc}^2(fT)
> $$
> Quindi:
> $$
> x(t)= A\cdot \text{tr}\left( \frac{t}{T} \right)\iff X(f)=AT\text{sinc}^2(fT)
>$$

### Teorema del Prodotto
> [!gray] ->
> Si considerano due segnali $x(t)$ e $y(t)$ con le rispettive trasformate di Fourier $X(f)$ e $Y(f)$. Si vuole calcolare la trasformata prodotto $z(t)= x(t)y(t)$, allora
> $$Z(t)= X(f)\otimes Y(f)$$
> <br>**Dimostrazione:**
> Si ha che la trasformata di $z(t)$ è espressa da
> $$
> Z(f)=\int_{{t=-\infty}}^\infty z(t)e^{-j 2\pi ft}\ dt= \int_{t=-\infty}^\infty x(t)y(t)e^{-j 2\pi ft}\ dt 
> $$
> Sostituendo a $x(t)$ la sua espressione come integrale di Fourier si ricava
> $$
> Z(f)=\int_{t=-\infty}^\infty \left[ \int_{v=-\infty}^\infty X(v)e^{j 2\pi vt}\ dv \right]y(t)e^{-j 2\pi ft}\ dt
> $$
> Se si inverte l'ordine di integrazione (ammettendo che sia lecita), si ricava
> $$
> Z(f)=\int_{v=-\infty}^\infty X(v)\left[\int_{t=-\infty}^\infty y(t)e^{-j 2\pi(f-v)t \ ft}\ dt\right]\ dv 
> $$
> Da cui segue
> $$
> Z(f)=\int_{v=-\infty}^\infty X(v)Y(f-v)\ dv = X(f)\otimes Y(f)
> $$
> dove l'operazione indicata con il simbolo $\otimes$ prende il nome di *Integrale (o Prodotto) di Convoluzione*.
> <br> In breve
> $$
> x(t)y(t)\iff X(f)\otimes Y(f)
> $$
> Scambiando formalmente il ruolo di $x(t)$ e $y(t)$, per la proprietà commutativa del prodotto, anche $Z(f)$ non deve cambiare. Ne segue che l'integrale di convoluzione gode anch'esso di proprietà commutativa nel senso che
> $$
> X(f)\otimes Y(f)=\int_{-\infty}^\infty X(v)Y(f-v)\ dv= \int_{-\infty}^\infty Y(v)X(f-v)\ dv = Y(f)\otimes X(f)
>$$
### Teorema della Convoluzione
> [!gray] ->
> Si considerano due segnali $x(t)$ e $y(t)$ con le rispettive trasformate di Fourier $X(f)$ e $Y(f)$. allora
> $$
> x(t)\otimes y(t)\iff X(f)Y(f)
> $$
> <br>**Dimostrazione:**
> Si considera il segnale $z(t)$ come
> $$
> z(t)=x(t)\otimes y(t) = \int_{\alpha=-\infty}^\infty x(\alpha)y(t-\alpha)\ d\alpha
> $$
> Allora la sua trasformata è
> $$
> Z(f)=\int_{t=-\infty}^\infty z(t)e^{-j 2\pi ft}\ dt= \int_{t=-\infty}^\infty \left[\int_{\alpha=-\infty}^\infty x(\alpha)y(t-\alpha)\ d\alpha\right]e^{-j 2\pi ft}\ dt
> $$
> Invertendo i due integrali
> $$\begin{align}
> &= \int_{\alpha=-\infty}^\infty x(\alpha)\left[ \int_{t=-\infty}^\infty y(t-\alpha)e^{-j 2\pi ft(t-\alpha+\alpha)}\ dt \right]\ d\alpha  \\
> &= \int_{\alpha=-\infty}^\infty x(\alpha)\left[ \int_{t=-\infty}^\infty y(t-\alpha)e^{-j 2\pi f (t-\alpha)}\ dt \right] e^{-j 2\pi f\alpha}\ d\alpha
> \end{align}$$
> Con la sostituzione $\beta=t-\alpha$ si ottiene
> $$\begin{align}
> &= \int_{\alpha=-\infty}^\infty x(\alpha)\left[ \int_{\beta=-\infty}^\infty y(\beta)e^{-j2\pi f\beta}\ d\beta\right]e^{-j 2\pi f\alpha}\ d\alpha= \int_{\alpha=-\infty}^\infty x(\alpha)Y(f)e^{-j 2\pi f\alpha}\ d\alpha= X(f)Y(f)
> \end{align}$$


> [!hint] Significato della Convoluzione
> Si suppone di avere due segnali $x(t)$ e $y(t)$ in figura. Si cerca di trovare il valore di $z(t)$ per un particolare valore del tempo, sia $t_{0}$:
> $$
> z(t_{0})=\int_{-\infty}^\infty x(\alpha)\cdot y(t-\alpha)\ d\alpha
> $$
> ![[Pasted image 20250401181203.png]]
> Per calcolare $z(t_{0})$, i passi sono:
> 1. Ribaltamento attorno all'asse delle ordinate del segnale $y(\alpha)$ per avere $y(t-\alpha)$ 
> ![[Pasted image 20250401181311.png|center|300]]
> 2. Traslazione di $y(-\alpha)$ all'istante $t_{0}$ per avere $y(t_{0}-\alpha)$ 
> ![[Pasted image 20250401181657.png|center|300]]
> 3. Calcolo del segnale prodotto $x(\alpha)y(t_{0}-\alpha)$ 
> ![[Pasted image 20250401184050.png|center|410]]
> 4. Calcolo dell'integrale del segnale prodotto calcolato al passo precedente 
> ![[Pasted image 20250401184357.png|center|410]]
> Attraverso questi passi ripetuti (teoricamente) infinite volte, ovvero per ogni valore di $t_{0}$, si arriva a determinare l'andamento di $z(t)$, solitamente si arriva alla soluzione per via grafica

> [!example]+ Esempio: Applicazione del Teorema del Prodotto
> Si considera il caso particolare in cui
> $$
> x(t)=y(t)=\text{sinc}(2Bt)\qquad z(t)=x(t)y(t)\text{sinc}^2(2Bt)
> $$
> Si ha che 
> $$
> X(f)=Y(f)= \frac{1}{2B}\text{rect}\left( \frac{f}{2B} \right)
> $$
> È possibile calcolare $Z(f)$ svolgendo l'integrale di convoluzione di due segnali rettangolari nel dominio della frequenza:
> $$
> Z(f)=\int_{y=-\infty}^\infty X(v)Y(f-v)\ dv= X(f)\otimes Y(f)
> $$
> Il calcolo della convoluzione può essere svolto esaminando i quattro casi seguenti, a seconda della traslazione $f$ applicata a $Y(-v)$
> ![[Pasted image 20250401185424.png]]
> ![[Pasted image 20250401185702.png]]
> ![[Pasted image 20250401185742.png]]
> ![[Pasted image 20250401185820.png]]
> ![[Pasted image 20250401185916.png]]
> ![[Pasted image 20250401185944.png]]
> ![[Pasted image 20250401190034.png]]
> ![[Pasted image 20250401190056.png]]
> ![[Pasted image 20250401190118.png]]
> ![[Pasted image 20250401190145.png]]
> ![[Pasted image 20250401190205.png]]
> ![[Pasted image 20250401190226.png]]
> ![[Pasted image 20250401190312.png]]
> 
<br>**Qual'è la traformata della funzione trapezio?**
Si applica il teorema della convoluzione
>$$\begin{align}
>&z(t)= x(t)\otimes y(t)= \text{rect}\left( \frac{t}{A} \right)\otimes  \text{rect}\left( \frac{t}{B} \right) \\
>&Z(f)= X(f)Y(f)=AB\text{sinc(Af)}\text{sinc}(Bf)
>\end{align}$$
### Trasformate di Fourier Generalizzate
Si considera la funzione gradino:
$$
u(t)=\begin{cases}
1 & t>0 \\
\frac{1}{2} & t=0 \\
0 & t<0
\end{cases}
$$
![[Pasted image 20250402173245.png|center|450]]
Questa funzione è un'astrazione matematica, in quanto un segnale fisico non può presentare una discontinuità di prima specie come $u(t)$ (il valore $\frac{1}{2}$ in $0$ è scelto per consistenza con il criterio di Dirichlet). 
Nell'origine però questo segnale non è derivabile (sarebbe nulla sempre tranne in $t=0$ dove non è definita). 
Si può però pero realizzare una funzione gradino reale, che passa dallo stato $0$ allo stato $1$ in un tempo non infinitesimo, ma comunque piccolo, detto *Tempo di Salita*
$$
u_{\epsilon}(t)=\begin{cases}
0 & t<-\epsilon \\
\frac{1}{2}+\frac{t}{2\epsilon}& -\epsilon <tz\epsilon \\
1 & t>\epsilon
\end{cases}
$$
![[Pasted image 20250402174401.png|center|450]]
La derivata del gradino reale è
$$
\delta\epsilon= \frac{du_{\epsilon}(t)}{dt}= \frac{1}{2\epsilon}\text{rect}\left( \frac{t}{2\epsilon} \right)
$$
![[Pasted image 20250402175856.png|center|450]]
Inversamente
$$
u_{\epsilon}(t)=\int_{-\infty}^t \delta_{\epsilon}\ d\alpha
$$
Il gradino reale approssima sempre meglio il gradino ideale riducendo il tempo di salita (ovvero riducendo il parametro $\epsilon$) (base tendete a $0$ e altezza tendente a $\infty$)
$$
u(t)=\lim_{ \epsilon \to 0 } u_{\epsilon}(t)
$$
![[Pasted image 20250402180351.png|center|450]]
Per quanto riguarda la derivata invece, per $\epsilon\to 0$, $\delta_{\epsilon}(t)$  ha durata sempre più piccola e un'ampiezza sempre più grande. Alla fine il valore che assume la derivata si trova nel seguente modo:
$$
u_{\epsilon}(t)=\int_{-\infty}^t \delta_\epsilon(\alpha)1 d\alpha
$$
Siccome $u(t)=\lim_{ \epsilon \to 0 }u_{\epsilon}(t)$, risulta
$$
u(t)=\lim_{ \epsilon \to 0 } \int_{-\infty}^t
 \delta_{\epsilon}(\alpha)\ d\alpha$$
Se si invertono il limite e l'integrale si può riscrivere nella forma sintetica
$$
u(t)=\int_{-\infty}^t \delta(\alpha)\ d\alpha
$$
dove $\delta(t)=\lim_{ \epsilon \to 0 }\delta_{\epsilon}(t)$
### Funzione Generalizzata Impulsiva o $\delta$ di Dirac
L'impulso unitario è un entità matematica che non può esistere in senso fisico, ma assume significato solo quando si considera la sua proprietà di carattere integrale, cioè come derivate della funzione gradino $u(t)=\int_{\infty}^t\delta(\alpha)\ d\alpha$. Quindi ogni volta che si incontra una funzione impulsiva $\delta(t)$ di Dirac
**Proprietà:**
Si calcola 
$$
I=\int_{-\infty}^\infty \delta (t)\ dt
$$
con $x(t)$ segnale continuo in $t=0$
$$
I=\int_{-\infty}^\infty x(t)\lim_{ \epsilon \to 0 } \delta_\epsilon(t)\ dt = \lim_{ \epsilon \to 0 } \int_{-\infty}^\infty x(t)\delta_{\epsilon}(t)\ dt
$$
Si valuta adesso l'integrale tralasciando il limite $\epsilon\to 0$
$$
\int_{-\infty}^\infty x(t)\delta_{\epsilon}(t)\ dt =\int_{-\infty}^\infty x(t) \frac{1}{2\epsilon}\text{rect}\left( \frac{t}{2\epsilon} \right)= \frac{1}{2\epsilon}\int_{-\epsilon}^\epsilon x(t)\ dt= \frac{1}{2\epsilon}2\epsilon \ x(\tilde{t})= x(\tilde{t})
$$
![[Pasted image 20250402183527.png|center|400]]
$x(\tilde{t})$ per il teorema della media, dove $\tilde{t}\in(-\epsilon,\epsilon)$
Se si considera poi il limite 
$$
\lim_{ \epsilon \to 0 }\int_{-\infty}^\infty x(t)\delta_{\epsilon}(t)\ dt = \lim_{ \epsilon \to 0 }x(\tilde{t})
$$
Quando $\epsilon\to_{0}$, naturalmente $\tilde{t}\to_{0}$, quindi essendo $x(t)$ continua in $t=0$, si ricava in conclusione
$$
\int_{-\infty}^\infty x(t)\delta(t)\ dt = x(0)
$$
Questa proprietà prende il nome di *Proprietà campionatrice* dell'impulso unitario $\delta(t)$ e può essere considerata una maniera alternativa di definire la funzione $\delta(t)$ attraverso una sua proprietà integrale

> [!hint] Rappresentazione Simbolica della funzione $\delta$
> ![[Pasted image 20250402184330.png|center|500]]
> Il simbolo accanto alla freccia indica l'area sottesa da funzione questa funzione è unitaria e non rappresenta un valore riportato sull'asse delle ordinate. 

![[Pasted image 20250402185157.png]]
### Proprietà della Funzione Generalizzata $\delta(t)$

> [!gray] Proprietà Campionatrice
> $$
> \int_{\infty}^\infty x(t)\delta(t)\ dt = x(0)
> $$

Da questa proprietà si deduce immediata mente che la funzione $\delta(t)$ è pari, cioè $\delta(t)=\delta(-t)$. Quest'ultima proprietà deve essere intesa in senso integrale relativamente alla proprietà campionatrice, si può scrivere infatti
$$
\int_{-\infty}^\infty \delta(-t)x(t)\ dt \overset{\alpha=-t}{=}\int_{\infty}^{-\infty} \delta(\alpha)x(-\alpha)\ d\alpha = \int_{-\infty}^\infty \delta(\alpha)x(-\alpha)= x(0)
$$
La proprietà campionatrice può essere estesa considerando la funzione impulsiva traslata $\delta(t-t_{0})$. Infatti
$$\int_{-\infty}^\infty x(t)\delta(t-t_{0})\ dt \overset{\alpha=t-t_{0}}{=} \int_{-\infty}^\infty x(t_{0}+\alpha)\delta(\alpha)\ d\alpha = [x(t_{0}+\alpha)]_{\alpha=0}= x(t_{0})$$
 ^143178

 Da cui consegue che
$$
x(t)=\delta(t-t_{0})=x(t_{0})\delta(t-t_{0})
$$
Questa uguaglianza vale sempre in senso integrale, infatti
$$
\int_{-\infty}^\infty x(t_{0})\delta(t-t_{0})\ dt= x(t_{0})\int_{-\infty}^\infty \delta(t-t_{0})\ dt= x(t_{0})=\int_{-\infty}^\infty x(t)\delta(t-t_{0})\ dt
$$
Se si riprende [[#^143178|$\int_{-\infty}^\infty x(t)\delta(t-t_{0})\ dt \overset{\alpha=t-t_{0}}{=} \int_{-\infty}^\infty x(t_{0}+\alpha)\delta(\alpha)\ d\alpha = [x(t_{0}+\alpha)]_{\alpha=0}= x(t_{0})$]] e si cambia $t$ con $\alpha$
$$
\int_{-\infty}^\infty x(\alpha)\delta(\alpha-t_{0})\ d\alpha = \int_{-\infty}^\infty x(\alpha)\delta(t_{0}-\alpha)\ d\alpha= x(t_{0})
$$
Da cui segue che, chiamando $t$ il generico valore $t_{0}$, si ha che
$$
x(t)=\int_{-\infty}^\infty x(\alpha)\delta(t-\alpha)\ d\alpha = x(t)\otimes \delta(t)
$$
- Questa relazione indica che la funzione generalizzata $\delta(t)$ può intendersi come *Elemento Neutro* rispetto all'operazione di integrale di convoluzione

TODO Esempio ----->
### Trasformata Generalizzata di Fourier della $\delta$ di Dirac
Si  calcola la trasformata della funzione generalizzata $\delta(t)$. Applicando direttamente la definizione di trasformata e ricordando la proprietà campionatrice si ha
$$
\Delta (f)= \int_{-\infty}^\infty \delta(t) e^{-j 2\pi ft}\ dt= [e^{-j 2\pi ft}]_{t=0}=1
$$
![[Pasted image 20250403010846.png|center|500]]
Lo spettro della funzione di $\delta$ di Dirac ha ampiezza costante pari a 1 per ogni valore della frequenza. La peculiarità della funzione $\delta$ è riflessa anche nella sua trasformata: lo spettro di $\delta$ contiene componenti a qualunque frequenza arbitrariamente grande e tutte con la medesima ampiezza.
Dal teorema della dualità si ricava poi
$$
x(t)= 1\iff \delta(-f)=\delta(f)
$$
![[Pasted image 20250403011127.png|center|500]]
Questo mostra che l'introduzione delle funzioni generalizzate permette di calcolare la trasformata di un segnale ad energia infinta come un segnale costante (questa trasformata deve intendersi in senso generalizzato)
### Trasformata Notevole: Funzione $\frac{1}{t}$
$x(t)=\frac{1}{t}$
![[Pasted image 20250403011943.png|center|450]]
Saltando i conti, si ha che la trasformata
$$
-j \pi\ \text{sgn}(t)\iff - \frac{1}{f}
$$
Da cui per la dualità si ricava che 
$$
\text{sgn}(t)\iff \text{SGN(f)}= \frac{1}{j \pi f}
$$
![[Pasted image 20250403111149.png|center|500]]
La trasformata di $u(t)$ in senso ordinario non esiste, facendo uso della funzione $\text{sgn}(t)$ si può esprimete $u(t)$ come 
$$
u(t)= \frac{1}{2}= \text{sgn}(t) + \frac{1}{2}
$$
da cui
$$
U(f)= \frac{1}{2}\text{SGN}(f)+ \frac{1}{2}\delta(f)= \frac{1}{j 2\pi f}+ \frac{1}{2}\delta(f)
$$
### Teorema d'Integrazione Completo
Come già spiegato, la trasformata del gradino unitario ideale $u(t)$ non esiste in senso ordinario.
Con i risultati però ottenuti precedentemente, si può rimuovere l'ipotesi $X(0)=0$ che è alla base dell'applicabilità del teorema di integrazione nella sua forma incompleta ricavata precedentemente
$$
\int_{-\infty}^t x(\alpha)\ d\alpha \iff \frac{X(f)}{j 2\pi f}
$$
Per definizione di integrale di conviluzione si può scrivere che
$$
x(t)\otimes u(t)=\int_{-\infty}^\infty x(\alpha)u(t-\alpha)\ d\alpha= \int_{-\infty}^t x(\alpha)\ d\alpha
$$
![[Pasted image 20250403112519.png]]
Risulta, visto che la trasformata di un integrale di convoluzione è uguale al prodotto delle trasformate dei fattori
$$
\int^t_{-\infty}x(\alpha)\ d\alpha = x(t)\otimes u(t)\iff X(f)U(f)= X(f)\left[ \frac{1}{j 2\pi f}+ \frac{1}{2} \delta(f) \right]
$$

> [!gray] Il teorema di integrazione afferma quindi che
> $$
> y(t)= \int_{-\infty}^t x(\alpha)\ d\alpha \iff \frac{X(f)}{j 2\pi f}+ \frac{1}{2}\delta(f)X(0)
> $$

Il termine aggiuntivo tiene conto dell'eventuale valore medio diverso da zero del segnale.
### Trasformata Generalizzata delle Funzioni Seno, Coseno e dei Segnali Periodici
La funzione generalizzata $\delta(t)$ permette di calcolare trasformate di Fourier non esistenti in senso ordinario. Altri esempi di questo tipo di segnali si possono ottenere applicando i teoremi del ritardo e della traslazione in frequenza alle trasformate generalizzate già ottenute
$$\begin{align}
\delta(t)&\iff_{1}& &\Longrightarrow& &\delta(t-t_{0})\iff e^{-j 2\pi ft_{0}}& \\
1&\iff\delta(f)& &\Longrightarrow& &e^{j 2\pi f_{0}t}=1\cdot e^{j 2\pi f_{0}t}\iff \delta(f-f_{0})&
\end{align}$$
Quest'ultima relazione permette di calcolare la trasformata continua di Fourier di un'oscillazione cosinusoidale, infatti si ha
$$
x_{c}(t)=\cos(2 \pi f_{0} t)= \frac{e^{j 2\pi f_{0}t}+e^{-j 2\pi f_{0}t}}{2}\iff X_{c}(f)= \frac{\delta(f-f_{0})+\delta(f+f_{0})}{2}
$$
![[Pasted image 20250403123233.png|center|450]]
Invece per una oscillazione sinusoidale
$$
x_{s}=\sin(2 \pi f_{0}t)= \frac{e^{j 2\pi f_{0}t}-e^{-j 2\pi f_{0}t}}{2j}\iff X_{s}(f)= \frac{\delta(f-f_{0})-\delta(f+f_{0})}{2j}
$$
![[Pasted image 20250403123257.png|center|450]]
Con questi risultati si può dare una nuova interpretazione al teorema della modulazione, tenendo presente il teorema del prodotto (trasformata del prodotto di due segnali è la convoluzione delle trasformate) si scrive
$$
x(t)=\cos(2\pi f_{0}t)\iff X(f)\otimes\left[ \frac{\delta(f-f_{0})+\delta(f+f_{0})}{2} \right]
$$
ma 
$$
X(f)\otimes\delta(f-f_{0})=\int_{-\infty}^\infty X(\alpha)\delta(f-f_{0}-\alpha)\ d\alpha = \underset{\text{Proprietà campionatrice}}{X(f-f_{0})=X(f+f_{0})}
$$
quindi:
$$
x(t)\cos(2\pi f_{0}t)\iff \frac{X(f-f_{0})+X(f+f_{0})}{2}
$$
Avendo determinato la trasformata continua di Fourier di una oscillazione sinusoidale in forma reale o complessa, si riesce ad esprimere anche a esprimere la trasformata continua di un segnale periodico qualunque.
Se $x(t)$ è periodico (periodo $T_{0}$ e $f_{0}=\frac{1}{T_{0}}$), si può scrivere come la serie di Fourier
$$
x(t)= \sum_{k=-\infty}^\infty X_{k}e^{j \frac{2\pi kt}{T_{0}}}\quad\underset{\text{Teorema di linearità }X(f)=\sum_{k=-\infty}^\infty X_{k} \mathcal F\{e^{j 2\pi f_{0}t}\} }{\overset{e^{j 2\pi f_{0}t}\iff\delta(f-f_{0})}{\iff}}\quad X(f)=\sum_{k=-\infty}^\infty X_{k}\delta\left( f- \frac{k}{T_{0}} \right)
$$
Questa relazione mostra che il contenuto spettrale di un segnale periodico è concentrato nelle frequenza armoniche, piuttosto che con continuità su tutte le frequenza come per un segnale aperiodico.
Il contributo del segnale della $k-$esima armonica è rappresentato da una $\delta$ posizionata alla frequenza $\frac{k}{T_{0}}$ e di integrale pari a $X_{k}$.
Lo spettro è ancora a riche come nella serie, ma le frecce sono rappresentazioni simboliche della presenza di una $\delta$ a quella frequenza.
![[Pasted image 20250403125657.png]]

> [!example]+ Esempio:
> Calcolo della trasformata di $x(t)= \cos^2\left( \frac{2\pi t}{T_{0}} \right)$, può essere riscritto nella forma ($\cos^2\alpha=\frac{1}{2}+\frac{1}{2}\cos(2\alpha)$) $$x(t)=\frac{1}{2}+\frac{1}{2}\cos\left( \frac{4\pi t}{T_{0}} \right)$$
> da cui si ricava l'espressione
> $$
> X(f)= \frac{1}{2}\delta (f)+ \frac{1}{2} \frac{\delta\left( f- \frac{2}{T_{0}} \right)+\delta\left( f+ \frac{2}{T_{0}} \right)}{2}= \frac{1}{2}\delta(f)+\frac{1}{4}\delta\left( f- \frac{2}{T_{0}} \right)+ \frac{1}{4}\delta\left( f+ \frac{2}{T_{0}} \right)
> $$
> ![[Pasted image 20250403162152.png|center|400]]
> 

Se calcolare $X(f)$ è difficile, può essere conveniente la seguente strada. Dato $x(t)$:
1. Si calcola $s(t)$, derivata del segnale $x(t)$
2. Si calcola $S(f)$, trasformata di Fourier di $s(t)$
3. Utilizzando il teorema dell'integrale per il calcolo di $X(f)$ a partire da $S(f)$, dato che $s(t)$ è la derivata di $x(t)$, a sua volta $x(t)$ è l'integrale di $s(t)$
$$  
x(t)=\int_{-\infty}^t s(\alpha)\ d\alpha
$$

> [!example]+ Esempio
> Calcolo della trasformata del segnale $x(t)=\text{rect}\left( \frac{t}{T} \right)$.
> Si può utilizzare il teorema del calcolo integrale per il calcolo di $X(f)$, si ricava dunque la derivata prima $s(t)$ del segnale $x(t)$, in modo che risulti $x(t)=\int_{-\infty}^t s(\alpha)\ d\alpha$.
> Quindi
> $$
> x(t)=\text{rect}\left( \frac{t}{T} \right)= u\left( t + \frac{T}{2} \right)-u\left( t- \frac{T}{2} \right)
> $$
> Si calcola poi la derivata, che sarà sempre nulla tranne in corrispondenza dei due gradini
> $$
> \frac{d}{dt}x(t)= \frac{d}{dt}\left\{ u\left( t+\frac{T}{2} \right)+u\left( t- \frac{T}{2} \right) \right\} = \delta\left( t+\frac{T}{2} \right)- \delta\left( t-\frac{T}{2} \right)
> $$
> Si è completato quindi il primo passo (calcolo di $s(t)$), può procedere adesso con il calcolo della trasformata di quest'ultimo
> $$
> S(f)= 1\cdot e^{j 2\pi f \frac{T}{2}}- 1\cdot e^{-j 2\pi f \frac{T}{2}}= e^{j \pi fT}-e^{-j\pi fT}
> $$
> Infine si completa l'ultimo passo (applicazione del teorema di integrazione), di cui la condizione $S(0)=0$ è verificata
> $$
> X(f)= \frac{S(f)}{j 2\pi f}= \frac{e^{j \pi fT- e^{j \pi fT}}}{j 2\pi f}= \frac{\sin(\pi fT)}{\pi f}= T \frac{\sin(\pi fT)}{\pi fT}= T\text{sinc}(fT)
> $$
> ![[Pasted image 20250403163408.png|center|400]]

> [!example]+ Esempio:
> Calcolo della trasformata di $x(t)= \frac{|t|}{T}\text{rect}\left( \frac{t}{2T} \right)$.
> Poiché $x(t)$ è lineare a tratti, si può applicare il teorema dell'integrale. Si ricava innanzitutto la derivata prima $s(t)$ in modo che $x(t)=\int_{-\infty}^ts(\alpha)\ d\alpha$ 
> $$
> s(t)=\underset{1}{\delta (t+T)}-\underset{2}{\delta(t-T)}\underset{3}{-\frac{1}{T}\text{rect}\left( \frac{t+ \frac{T}{2}}{T} \right)}\underset{4}{+ \frac{1}{T}\text{rect}\left(  \frac{t- \frac{T}{2}}{T} \right)}
> $$
> Si calcola la trasformata
> $$\begin{align}
> S(f)&= 1\cdot e^{j 2\pi fT}-1\cdot e^{-j 2\pi fT}- \frac{1}{T}\text{sinc}(fT)e^{j \pi fT}+\frac{1}{T}\text{sinc}(fT)e^{j\pi fT}= \\
> &=2j \frac{e^{j 2\pi fT} e^{-j 2\pi fT}}{2j}- \text{sin}(fT) 2j \frac{e^{j\pi fT}-e^{-j \pi fT}}{2j}= 2j\sin(2\pi fT)-2j \text{sinc}(fT)\sin(\pi fT)
> \end{align}$$
> Siccome $x(+\infty)$ o $S(0)=0$, si può applicare il teorema di integrazione incompleto:
> $$\begin{align}
> X(f)&= \frac{S(f)}{j 2\pi ft}= \frac{2j\sin(2\pi fT)-2j\text{sinc(fT)sin(pifT)}}{j 2\pi fT}= \\
> &= \frac{2j-T\sin(2\pi fT)}{j 2\pi fT}- \frac{2j\text{sinc}(fT)T\sin(\pi fT)}{j 2\pi fT}= 2T\text{sinc}(2fT)-T\text{sinc}^2(fT)
> \end{align}$$
> ![[Pasted image 20250403164828.png|center|400]]
> Si può ricavare lo stesso risultato osservando xche $x(t)$ può essere espresso come la differenza fra un impulso rettangolare e uno triangolare, aventi la stessa durata $2T$
> $$\begin{align}
> x(t)&=\text{rect}\left( \frac{t}{2T} \right)- \left( 1- \frac{|t|}{T} \right)\text{rect}\left( \frac{t}{2T} \right) \\
> X(f)&=2T\text{sinc}(2fT)-T\text{sinc}^2(fT)
> \end{align}$$

Es3.21 da fare
### Periodicizzazione e Formule di Somma di Poisson
Si considera un segnale aperiodico $x(t)$ e si costruisce il segnale $y(t)$ periodico di periodo $T_{0}$ secondo la relazione di periodicizzazione
$$
y(t)=\sum_{n=-\infty}^\infty x(t-nT_{0})
$$
![[Pasted image 20250406181347.png]]
Il segnale $y(t)$ può essere sviluppato in serie di Foruier:
$$ y(t)=\sum_{k=-\infty}^\infty Y_{k}e^{j 2\pi k f_{0}t} $$
Si espande sulla relazione tra la trasformata $X(f)$ e il coefficiente $Y_{k}$
$$\begin{align}
Y_{k}&= \frac{1}{T_{0}}\int_{- \frac{T_{0}}{2}}^{\frac{T_{0}}{2}y(t)}e^{j 2\pi}\ dt= \frac{1}{T_{0}}\int_{- \frac{T_{0}}{2}}^{\frac{T_{0}}{2}} \sum_{n=-\infty}^\infty x(t-n T_{0})e^{-j 2\pi kf_{0}t}\ dt= \\
&= \frac{1}{T_{0}} \sum_{n=-\infty}^\infty \int_{- \frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(t-nT_{0})e^{-j 2\pi kf_{0}}t\ dt = \frac{1}{T_{0}}\sum_{n=-\infty}^\infty \int_{-\frac{T_{0}}{2}-nT_{0}}^{\frac{T_{0}}{2}- nT_{0}}x(\alpha) e^{-j 2\pi k_{0}}(\alpha)+n T_{0}\ d\alpha = \\
&= \frac{1}{T_{0}}\sum_{n=-\infty}^\infty \int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}x(\alpha)e^{-j 2\pi k_{0}\alpha}e^{-j 2\pi k_{0} nT_{0}}\ d\alpha 
\end{align}$$
Si ha che $e^{j 2\pi k_{0}nT_{0}}=r^{-j 2\pi kn}=(\cos( 2\pi kn)-j (\sin(2 \pi kn)))=1$, essendo $k$ e $n$ interi, si ha
$$
Y_{k}= \frac{1}{T_{0}} \sum_{n=-\infty}^\infty \int_{-\frac{T_{0}}{2}-nT_{0}}^{\frac{T_{0}}{2}-nT_{0}} x(\alpha)e^{-j 2\pi_{0}\alpha_{0}\alpha}= \frac{1}{T_{0}}\int_{-\infty}^\infty x(\alpha)e^{-j 2\pi(kf_{0})\alpha}\ d \alpha= \frac{1}{T_{0}}X(kf_{0})= \frac{1}{T_{0}}X\left( \frac{k}{T_{0}} \right)
$$
![[Pasted image 20250406183008.png]]

Si ottiene una relazione detta di *Campionamento di Frequenza*.
I coefficienti della serie del segnale periodico $y(t)$ sono, a meno del fattore $\frac{1}{T_{0}}$, i valori campioni della trasformata del segnale base $x(t)$ presi in corrispondenza delle frequenze armoniche $kf_{0}$:
$$
Y_{k}= \frac{1}{T_{0}} X\left( \frac{k}{T_{0}} \right)
$$
e quindi si ottiene la *Prima Formula di Poisson*
$$
\sum_{n=-\infty}^\infty x(t-nT_{0})=\sum_{k=-\infty}^\infty \frac{1}{T_{0}}X\left( \frac{k}{T_{0}} \right)e^{j \frac{2\pi kt}{T_{0}}}
$$

> [!example]+ Esempio
> $y(t)=|\cos(2\pi_{1}t)|$
> ![[Pasted image 20250406183827.png|center|500]]
> con periodo $T_{1}= \frac{1}{f_{1}}$. La trasformata si calcola con
> $$
> y(t)=\sum_{k=-\infty}^\infty x\left( t-k \frac{T_{1}}{2} \right)
> $$
> Si può considerare $y(t)$ come la periodicizzazione del segnale aperiodico $x(t)$, dove
> $$
> x(t)=\cos(2\pi f_{1}t)\text{rect}\left( \frac{t}{\frac{T_{1}}{2}} \right)
> $$
> Quindi
> $$
> \begin{align}
> &TCF\left( \text{rect}\left( \frac{t}{\frac{T_{1}}{2}} \right) \right)= \frac{T_{1}}{2}\text{sinc}\left( \frac{fT_{1}}{2} \right) \\
>  \\
> & X(f)= \frac{T_{1}}{2} \frac{1}{2}\left[ \text{sinc}\left( \frac{(f+f_{1})T_{1}}{2} \right) +\text{sinc}\left( \frac{(f-f_{1})T_{1}}{2} \right) \right] \\
> &X(f)= \frac{T_{1}}{2} \frac{\text{sinc}\left(\frac{fT_{1}+1}{2}  \right)+\text{sinc}\left(  \frac{fT_{1}-1}{2} \right)}{4} 
> \end{align}
> $$
> E per la somma di Poisson (essendo $T_{0}= \frac{T_{1}}{2}$) si ha
> $$
> Y_{k}= \frac{1}{T_{0}}X\left( \frac{k}{T_{0}}\right)\qquad Y_{k}=\frac{2}{T_{1}}X\left( \frac{2k}{T_{1}} \right)=\frac{ \text{sinc}\left( \frac{2k+1}{2}\right)+\text{sinc}\left( \frac{2k-1}{2} \right)}{2}
> $$
> ![[Pasted image 20250406185333.png|center|500]]

> [!example]+ Esempio:
> La trasformata di un segnale $x(t)$ di un segnale $s(t)$ ha spettro di ampiezza $|S(f)|$ e ha spettro di fase nullo. Calcolare $s(t)$
> ![[Pasted image 20250406185929.png|center|450]]
> Lo spettro può essere scomposto in due segnale come $S(f)=S_{1}(f)+S_{2}(f)$
> ![[Pasted image 20250406190357.png]]
> Ricordando che
> $$\begin{align}
> &\text{rect}\left( \frac{t}{T} \right)& &\iff& &T\text{sinc}(fT)& \\
> &T\text{sinc}(tT)& &\iff& &\text{rect}\left( -\frac{f}{T} \right)=\text{rect}\left( \frac{f}{T} \right)& \\
> & B\text{sinc}(Bt)& &\iff& &\text{rect}\left( \frac{f}{B} \right)&
> \end{align}$$
> In questo caso si ha
> $$
> s_{1}(t)=A 2B \text{sinc}(2Bt)\iff S_{1}(f)=A\text{rect}\left( \frac{f}{2B} \right) 
> $$
> Ricordando che
> $$
> S_{2}(f)= A\left( 1- \frac{|f|}{B} \right)\text{rect}\left( \frac{f}{2B} \right)= A\text{tri}\left( \frac{f}{B} \right)=A \frac{1}{B}\text{rect}\left( \frac{f}{B} \right)\otimes\text{rect}\left( \frac{f}{B} \right)
> $$
> Si ottiene
> $$
> s_{2}(t)= A \frac{1}{B}\text{sinc}(Bt)\text{sinc}(Bt)= AB \text{sinc}^2(Bt)
> $$