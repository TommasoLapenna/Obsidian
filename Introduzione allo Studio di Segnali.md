Tags: [[Fondamenti di Segnali e Trasmissione]] [[University]] 

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
![[Pasted image 20250320122740.png]]
Si possono inoltre dividere i segnali nelle seguenti classi:
- *Deterministico:* Il segnale è noto per ogni valore del suo dominio (attraverso un espressione matematica)
- *Aleatorio:* Non è possibile conoscere con esattezza a priori il valore assunto da un segnale ad un certo istante
- *Periodico:* Se esiste un intervallo temporale $T_{0}(N_{0})$ tale che $x(t)=x(t+T_{0})\ \forall t$, $x[n]=x[n+N_{0}] \ \forall n$
- *Aperiodico:* Non esiste $T_{0}(N_{0})$ che soddisfa la relazione suddetta
### Proprietà Elementari dei Segnali Determinati a Tempo Continuo
Dalla legge di Ohm si sa che la potenza dissipata sul resistore $P=R\cdot i^2(t)\ [W]$, mentre l'energia dissipata sul resistore è $E=R\int_{-\infty}^{\infty}|i^2|(t)\ dt$. Si può quindi osservare il rapporto di proporzionalità tra potenza (e energia) ed il quadrato del segnale.
Nella teoria dei segnali, attraverso la normalizzazione, si ha un'astrazione delle grandezze delle dimensioni; si definiscono proprietà analoghe:
- *Potenza Istantanea Normalizzata di un Segnale $x(t)$:*
$$
P_{x}=|x(t)|^2
$$
- *Energia di un Segnale:*
$$
E_{x}=\int_{-\infty}^\infty |x(t)|^2\ dt
$$
Un segnale si dice a **Energia Finita** se $E<\infty$.
Per tutti i segnali fisici l'integrale dell'energia risulta convergente, conviene quindi utilizzare modelli ideali di segnali, utili per approssimare casi reali.

> **ESEMPIO:** Se si considera la tensione $v(t)$ di una batteria ideale, essa è costante per ogni valore di $t$, quindi $\int_{-\infty}^\infty|v(t)|^2\ dt=\infty$, allora la definizione di energia è mal posta. Nonostante ciò, se una batteria reale viene osservata in un periodo in cui è carica, $v(t)$ risulta essere un ottima approssimazione.

