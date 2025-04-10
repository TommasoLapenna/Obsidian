---
order: "0"
sticker: emoji//0030-fe0f-20e3
---
# Derivata di un Versore
Siccome un versore è un vettore unitario, solo la direzione può cambiare in funzione di $t$, cioè può solo compiere una rotazione di $\Delta \theta$, quindi
$$
\Delta \hat{u} = \hat{u}(t+\Delta t)- \hat{u}(t)
$$
con $\Delta  \hat{u}$ arco di corda.
Al limite per $\Delta t\to 0$, $\Delta \hat{u}$ tende a $d \hat{u}$, perpendicolare ad $\hat{u}(t)$. Quindi gli angoli che $\Delta \hat{u}$ forma co $\hat{u}(t)$ e $\hat{u}(t+\Delta t)$ tendono a $90°$.

![[Pasted image 20250310174956.png]]

Quindi:
$$
du=|u(t)|d\theta = d\theta \Longrightarrow d \hat{u}= d\theta \hat{u}_{N}
$$
con $\hat{u}_{N}$ perpendicolare a $\hat{u}(t)$.
In conclusione, la formula di derivata di un versore è
$$
\frac{d \hat{u}}{dt}= \frac{d\theta}{dt} \hat{u}_{N}
$$
La derivata di un versore è un vettore perpendicolare rispetto al versore, di modulo $\frac{d\theta}{dt}$ (non necessariamente unitario, quindi il risultato non è un versore).
# Integrazione di un Vettore
Si divide una funzione vettoriale $\vec{a}(t)$ definita in un certo intervallo della variabile $t$ in sottointervalli $\Delta t_{i}$, dei quali si considera unvalore $\vec{a}(t_{i})$.
Si costruiscono i vettori $\vec{a(t_{i})}\Delta t_{i}$  e si sommano
$$
\vec{A}=\sum^N_{i=1} \vec{a}(t_{i})\Delta t_{i}
$$
Il risultato è il vettore $\vec{A}$ che unisce l'origine del primo vettore all'estremo dell'ultimo

![[Pasted image 20250310182457.png]]

Passando al limite $\Delta t \to 0$ si ottiene l'integrale
$$
\vec{A} = \lim_{ \Delta t \to 0 } \sum^n_{i=1} \vec{a}(t_{i})\Delta t_{i} = \int_{t_{1}}^{t_{N}} \vec{a}(t)dt 
$$
$\vec{A}(t)$ non dipende dal sistema di riferimento. Se si vuole usare il sistema cartesiano si ha che 
$$
\vec{a}(t) = a_{x(t)}\hat{u}_{x}+a_{y}(t)\hat{u}_{y}+a_{z}\hat{u}_{z}
$$
e l'integrale diventa
$$
\vec{A} = \hat{u}_{x}\int_{t_{1}}^{t_{N}}a_{x}(t)dt+ \hat{u}_{y}\int_{t_{1}}^{t_{N}}a_{y}(t)dt+\hat{u}_{z}\int_{t_{1}}^{t_{N}}a_{z}(t)dt
$$
Quindi l'integrale del vettore ha come componenti gli integrali delle componenti del vettore.
# TODO equazioni differenziali