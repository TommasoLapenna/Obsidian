Tags: [[Tags/Fondamenti di Segnali e Trasmissione|Fondamenti di Segnali e Trasmissione]] [[University]]

\int^{\frac{T_{0}}{2}}_{-\frac{T_{0}}{2}}
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
è rappresentato come la somma di una costante $A_{0}$ e di una serie il cui il $k-$esm termine (detto $k-$esima oscillazione armonica, o armonica) ha:
- Ampiezza $2A_{k}$
- Frequenza $kf_{0}$ (frequenza armonica) 
- Fase iniziale $\theta_{k}$
I termini coseno costituiscono la base dello spazio vettoriale dei segnali periodici di periodo $T_{0}$
![[Pasted image 20250324192654.png]]
