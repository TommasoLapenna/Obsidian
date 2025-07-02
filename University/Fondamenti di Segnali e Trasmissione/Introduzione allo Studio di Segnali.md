---
sticker: emoji//0031-fe0f-20e3
Order: "1"
---
Tags: [[Old Vault/Tags/Fondamenti di Segnali e Trasmissione]]  [[Old Vault/Indexes/University]] 

---

- [[#Definizione di Segnale|Definizione di Segnale]]
- [[#Tipi di Segnali|Tipi di Segnali]]
- [[#Tipi di Segnali#Proprietà Elementari dei Segnali Determinati a Tempo Continuo|Proprietà Elementari dei Segnali Determinati a Tempo Continuo]]
- [[#Tipi di Segnali#Segnale Periodico|Segnale Periodico]]
- [[#Segnali Notevoli|Segnali Notevoli]]
	- [[#Segnale Periodico#Gradino Unitario|Gradino Unitario]]
	- [[#Segnale Periodico#Esponenziale Monolatero|Esponenziale Monolatero]]
	- [[#Segnale Periodico#Seno|Seno]]
	- [[#Segnale Periodico#Coseno|Coseno]]
	- [[#Segnale Periodico#Esponenziale Complesso|Esponenziale Complesso]]
---

### Definizione di Segnale
Un segnale è una qualsiasi grandezza fisica alla quale è possibile associare un'informazione, la quale può essere di varia natura. In molti casi, l'andamento del segnale può essere perfettamente noto, pertanto il metodo più conveniente per studiare un segnale è attraverso il grafico di una funzione matematica (in una o più variabili).
## Tipi di Segnali
Si possono classificare i segnali per:
- **Dominio:**
	- *Segnali a Tempo Continuo:* Il dominio della funzione ha la cardinalità dei numeri reali (indicato con $x(t),\ y(t)$).
	- *Segnali a Tempo Discreto:* Il dominio ha la cardianlità dell'insieme dei numeri interi (indicato conm $x[n],\ y[n]$).
- **Codominio:**
	- *Segnali ad Ampiezza Continua:* Può assumere tutti i valori reali in un intervallo.
	- *Segnali ad Ampiezza Discreta:* Il codominio è un insieme numerabili, eventualmente illimitato.
	- 
![[Pasted image 20250320122740.png]]

Si possono inoltre dividere i segnali nelle seguenti classi:
- *Deterministico:* Il segnale è noto per ogni valore del suo dominio (attraverso un espressione matematica)
- *Aleatorio:* Non è possibile conoscere con esattezza a priori il valore assunto da un segnale ad un certo istante
- *Periodico:* Se esiste un intervallo temporale $T_{0}(N_{0})$ tale che $x(t)=x(t+T_{0})\ \forall t$, $x[n]=x[n+N_{0}] \ \forall n$
- *Aperiodico:* Non esiste $T_{0}(N_{0})$ che soddisfa la relazione suddetta
### Proprietà Elementari dei Segnali Determinati a Tempo Continuo
Dalla legge di Ohm si sa che la potenza dissipata sul resistore $P=R\cdot i^2(t)\ [W]$, mentre l'energia dissipata sul resistore è $E=R\int_{-\infty}^{\infty}|i^2|(t)\ dt$. Si può quindi osservare il rapporto di proporzionalità tra potenza istantanea ed il quadrato del segnale.
Nella teoria dei segnali, attraverso la normalizzazione, si ha un'astrazione delle grandezze delle dimensioni; si definiscono proprietà analoghe:

- *<span style="background:rgba(240, 200, 0, 0.2)">Potenza Istantanea Normalizzata di un Segnale $x(t)$:</span>*
$$
P_{x}=|x(t)|^2
$$
- <span style="background:rgba(240, 200, 0, 0.2)">*Energia di un Segnale:*</span>
$$
E_{x}=\int_{-\infty}^\infty |x(t)|^2\ dt
$$
Un segnale si dice a <span style="background:rgba(240, 200, 0, 0.2)">**Energia Finita** se $E\lt\infty$. </span>
Per tutti i segnali fisici l'integrale dell'energia risulta convergente, conviene quindi utilizzare modelli ideali di segnali, utili per approssimare casi reali. 

> [!example]+ Esempio
> Se si considera la tensione $v(t)$ di una batteria ideale, essa è costante per ogni valore di $t$, quindi $\int_{-\infty}^\infty|v(t)|^2\ dt=\infty$, allora la definizione di energia è mal posta. Nonostante ciò, se una batteria reale viene osservata in un periodo in cui è carica, $v(t)$ risulta essere un ottima approssimazione.


Si considera un segnale generico $x(t)$ a valori limitati ma energia infinita, attraverso un operazione di troncamento si costruisce il segnale 
$$
x_{T}(t)=\begin{cases}
x(t) & |t|\le \frac{T}{2} \\
0 & altrove
\end{cases}
$$
L'energia del segnale limitata dall'intervallo è limitata ($E_{x_{T}}\le\infty$). Se si espande l'intervallo ($T\to \infty$) si ottiene che $E_{x_{T}}\to \infty$, si introduce allora il concetto di potenza:

- <span style="background:rgba(240, 200, 0, 0.2)">*Potenza media su un Intervallo $T$ di un Segnale</span>*
$$
P_{T}= \frac{1}{T}\int_{-\frac{T}{2}}^ {\frac{T}{2}} |x(t)|^2\ dt
$$
- <span style="background:rgba(240, 200, 0, 0.2)">*Potenza Media*</span>
$$
\overline{P}=\lim_{ T \to \infty }P_{T} =\lim_{ T \to \infty }\frac{1}{T}\int_{-\frac{T}{2}}^ {\frac{T}{2}} |x(t)|^2\ dt
$$
Un segnale si dice a <span style="background:rgba(240, 200, 0, 0.2)">**Potenza Media Finita** se $\overline{P}\lt\infty$.</span>
Un segnale ha energia finita se ha potenza media nulla, un segnale con potenza media diversa da $0$ ha energia infinita

> [!example]+ Esempio: Potenza Media della Batteria Ideale
> $$ P_{v}=\lim_{ T \to \infty } \frac{1}{T}\int_{-\frac{T}{2}}^ {\frac{T}{2}} |v(t)|^2\ dt= \lim_{ T \to \infty } \frac{1}{T}\int_{-\frac{T}{2}}^ {\frac{T}{2}} v_{0}^2\ dt=v_{0}$$
### Segnale Periodico
Un segnale è periodico se esiste un intervallo temporale $T_{0}$ tale che
$$
x(t)= x(t+T_{0})\quad \forall t
$$
e si definisce la *Frequenza di Ripetizione*
$$
f_{0}=\frac{1}{T_{0}}
$$
Il segnale è completamente noto se si conosce il suo valore all'interno di un periodo.

![[Pasted image 20250322121215.png| center | 500]]

È dato un segnale $x(t)$ di durata finita in $\left( -\frac{T}{2}, \frac{T}{2} \right)$, quindi aperiodico, ovvero per cui $x(t)=0$ per $|t|> \frac{T}{2}$. A questo segnale si può associare un segnale periodico ripetendo $x(t)$ con periodo $T$ (o $T'>T$).

> [!gray] Dato un segnale periodico $x(t)$ di periodo $T_{0}$ e tale che $\int_{{\frac{T}{2}}}^ \frac{T}{2} |x(t)|^2\ dt <\infty$, si può dimostrare che ha energia infinita:
>**Dimostrazione**
$E=\int_{-\infty}^\infty|x(t)|^2\ dt=\infty$, essendo $x(t)$ periodico, $|x(t)|$ non va mai a $0$, quindi l'integrale non converge. Si tratta quindi di una somma di infinite aree di base $T_{0}$ che non valgono $0$

> [!gray] Dato un segnale periodico $x(t)$ di periodo $T_{0}$ e tale che $\int_{-\frac{T_{0}}{2}}^{ \frac{T_{0}}{2}}|x(t)|^2\ dt<\infty$, si può dimostrare che ha potenza media finita:
> **Dimostrazione**
> $$\overline{P}_{T}=\lim_{ T \to \infty }P_{T}=\lim_{ T \to \infty } \frac{1}{T}\int_{-\frac{T_{0}}{2}}^{ \frac{T_{0}}{2}}|x(t)|^2\ dt$$per un segnale periodico $x(t)$ di periodo $T_{0}$ la potenza media è pari alla potenza media calcolata in un intervallo di tempo pari al periodo $T_{0}$, cioè $$ \overline{P}=\frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{ \frac{T_{0}}{2}}|x(t)|^2\ dt $$ che per ipotesi ha valore finito
> 

![[Pasted image 20250324173316.png]]
Si sceglie come periodo $T=NT_{0}$ 
$$
\begin{align}
\overline{P}=&\lim_{ T \to \infty } \frac{1}{T}\int_{-\frac{T}{2}}^{ \frac{T_{}}{2}}|x(t)|^2\ dt   = \lim_{ N \to \infty }\frac{1}{NT_{0}}\int_{-\frac{NT_{0}}{2}}^{ \frac{NT_{0}}{2}}|x(t)|^2\ dt  \\
=&\lim_{ N \to \infty } \frac{1}{NT_{0}}\left\{\int_{-\frac{NT_{0}}{2}}^{ \frac{-NT_{0}}{2}+T_{0}}|x(t)|^2\ dt \int_{-\frac{NT_{0}}{2}+T_{0}}^{ \frac{-NT_{0}}{2}+2T_{0}}|x(t)|^2\ dt+\ldots+\int_{\frac{NT_{0}}{2}-T_{0}}^{ \frac{NT_{0}}{2}}|x(t)|^2\ dt \right\} \\
=&\lim_{ N \to \infty } \frac{1}{NT_{0}} N\left\{ \int_{-\frac{T_{0}}{2}}^{ \frac{T_{0}}{2}}|x(t)|^2\ dt\right\}= \frac{1}{T_{0}}\int_{-\frac{T_{0}}{2}}^{ \frac{T_{0}}{2}}|x(t)|^2\ dt
\end{align}
$$
Esistono segnali che non hanno né potenza finita, né energia finita. SI tratta di segnali non realizzabili fisicamente (ad esempio $x(t)=t$, $x(t)=e^{at}$ con reale positivo)
## Segnali Notevoli
#### Gradino Unitario
![[Pasted image 20250324174603.png]]
$$
\begin{align}
&u(t)=\begin{cases}
1 &t>0 \\
\frac{1}{2} & t=0 \\
0 & t<0
\end{cases} \\
& E_{u}=\int_{-\infty}^\infty|u(t)|^2\ dt =\int_{0}^\infty 1\ dt  \\

&P_{u}=\lim_{ T \to \infty } \frac{1}{T}\int_{-\frac{T}{2}}^{\frac{T}{2}}|u(t)|^2\ dt =\lim_{ T \to \infty } \frac{1}{T}\int_{0}^{\frac{T}{2}}1\ dt=\lim_{ T \to \infty } \frac{1}{T}\cdot \frac{T}{2}=\frac{1}{2}&
\end{align}
$$
Serve a modellare l'accensione all'istante $t=0$ di un generatore ideale di tensione, che eroga una tensione costante per $t\ge_{0}$.
#### Esponenziale Monolatero
![[Pasted image 20250324181055.png]]
$$
\begin{align}
&x(t)=e^{-\frac{t}{\tau}} u(t) \\
&E_{x}=\int_{\infty}^\infty |x(t)|^2\ dt = \int_{0}^{\infty} e^{-\frac{2t}{\tau}}\ dt=\left[ -\frac{\tau}{2}e^{-\frac{2t}{\tau}} \right]^{t=\infty}_{t=0}= \frac{\tau}{2}<\infty \\
&P_{x}= \lim_{ T \to \infty } \frac{1}{T}\int_{0}^{\frac{T}{2}}e^{-\frac{2t}{\tau}}\ dt= \lim_{ T \to \infty }\left[ -\frac{\tau}{2T}e^{-\frac{2t}{\tau}} \right]^{t=\frac{T}{2}}_{{t=0}}=\lim_{ T \to \infty }\left( -\frac{\tau}{2T}(e^{-\frac{2t}{\tau}}-1)=0 \right)  
\end{align}
$$
Descrive il fenomeno della scarica dei condensatori. La costante $\tau$ parametrizza la velocità di discesa.
#### Seno
![[Pasted image 20250324181035.png]]
$$
\begin{align}
x(t)=&A\cdot \sin\left( \frac{2\pi t}{T_{0}} \right) \\
P_{x}=& \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}A^2\sin^2\left( 2\pi\frac{ t}{T_{0}} \right)\ dt = \frac{A^2}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}\left[ \frac{1}{2}-\frac{1}{2} \cos\left(4\pi \frac{ t}{T_{0}} \right) \right]\ dt \\
=& \frac{A^2}{2}-\frac{A^2}{T_{0}}\int^{\frac{T_{0}}{2}}_{0} \cos\left( 4\pi  \frac{t}{T_{0}} \right)\ dt= \frac{A^2}{2}
\end{align}
$$
la sinusoide può essere utilizzata per rappresentare un generatore di corrente alternata ($f=\frac{1}{T_{0}}$)
#### Coseno
![[Pasted image 20250324183431.png]]
$$
\begin{align}
&y(t)=A\cdot \cos\left( \frac{2\pi t}{T_{0}} \right) \\
&P_{y}=\frac{1}{T_{0}} \int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}A^2\cos\left( \frac{2\pi t}{T_{0}} \right)\ dt=\frac{A^2}{T_{0}}\int_{-\frac{T_{0}}{2}}^{\frac{T_{0}}{2}}\left[ \frac{1}{2}+\frac{1}{2}\cos \left( \frac{4\pi t}{T_{0}} \right) \right]=\frac{A^2}{2} \\
&y(t)=x\left( t-T_{\frac{0}{4}} \right)
\end{align}
$$
Il segnale cosinusoidale di può ottenere ritardando quello sinusoidale di un quarto di periodo, pertanto, data la periodicità di $x(t)$, la potenza media $P_{y}$ è uguale a $P_{x}$.
I segnale sinusoidale e cosinusoidale, essendo entrambi periodici, posseggono entrambi energia illimitati. Sono quindi entrambi segnali ideali.
#### Esponenziale Complesso
![[Pasted image 20250324184039.png]]
Si tratta di un tipo di segnale che non è applicabile allo studio di problemi di realtà fisica (funzioni reali).
Essendo un segnale complesso, è composto da una parte reale e da una parte immaginaria 
$$
x(t)=e^{\frac{j_{2}\pi t}{T_{0}}}=x_{R}(t)+jx_{I}(t)
$$
La parte reale e quella immaginaria sono rispettivamente delle relazioni di Eulero
$$
\begin{align}
&x_{R}(t)=\mathcal R[x(t)]= \cos\left( \frac{2\pi t}{T_{0}} \right) \\
&x_{I}(t)=\mathcal I [x(t)]=\sin\left( \frac{2\pi t}{T_{0}} \right) \\
&|x(t)|^2= x_{R}^2(t)+x_{I}^2(t)=\cos^2\left( \frac{2\pi t}{T_{0}} \right)+\sin^2\left( \frac{2\pi t}{T_{0}} \right)=1
\end{align}
$$
L'esponenziale complesso $x(t)$ può essere interpretato come un vettore rotante che rutoa nel piano complesso con velocità $f_{0}=\frac{1}{T_{0}}$.
Infine si può dire che ha energia media illimitata (dato che è un segnale periodico), mentre la potenza media è
$$
P_{x}= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}|e^{j_{2}\pi  \frac{t}{T_{0}}}|^2\ dt= \frac{1}{T_{0}}\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}1\ dt = 1
$$

