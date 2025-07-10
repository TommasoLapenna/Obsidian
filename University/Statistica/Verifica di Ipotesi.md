---
sticker: emoji//0038-fe0f-20e3
---
- [[#Verifica di Ipotesi: Approccio Frequentista|Verifica di Ipotesi: Approccio Frequentista]]
	- [[#Verifica di Ipotesi: Approccio Frequentista#Ipotesi e Livelli di Significatività|Ipotesi e Livelli di Significatività]]
- [[#Verifica di Ipotesi su $\mu$, $X\sim N(\mu,\sigma^2)$, $\sigma^2$ nota|Verifica di Ipotesi su $\mu$, $X\sim N(\mu,\sigma^2)$, $\sigma^2$ nota]]
- [[#Errori di Seconda Specie $\beta$|Errori di Seconda Specie $\beta$]]
	- [[#Errori di Seconda Specie $\beta$#Calcolo e Determinazione di $n$|Calcolo e Determinazione di $n$]]
- [[#$p-$Value|$p-$Value]]
- [[#Test Unilaterali|Test Unilaterali]]
	- [[#Test Unilaterali#Rifiuto di $H_{0}$ e Curva OC|Rifiuto di $H_{0}$ e Curva OC]]
- [[#Scelta delle Ipotesi Unilaterali|Scelta delle Ipotesi Unilaterali]]
- [[#Verifica delle Ipotesi e Intervalli di Confidenza|Verifica delle Ipotesi e Intervalli di Confidenza]]
- [[#$\sigma^2$ Non Noto, $t-$Test|$\sigma^2$ Non Noto, $t-$Test]]
- [[#Confronto fra due Popolazioni Normali|Confronto fra due Popolazioni Normali]]
- [[#Test $t$ su Dati Appaiati|Test $t$ su Dati Appaiati]]
- [[#Test sulla Varianza di una $X\sim N(\mu,\sigma^2)$|Test sulla Varianza di una $X\sim N(\mu,\sigma^2)$]]
- [[#Test sulla Uguaglianza della Varianza di Due Popolazioni Normali|Test sulla Uguaglianza della Varianza di Due Popolazioni Normali]]
- [[#Test sul $\pi$ di una Popolazione Bernoulliana|Test sul $\pi$ di una Popolazione Bernoulliana]]
- [[#Test sul $\pi$ di due Popolazioni Bernoulliane|Test sul $\pi$ di due Popolazioni Bernoulliane]]
- [[#Test di Fisher-Irwin sul $\pi$ di due Popolazioni Bernoulliane|Test di Fisher-Irwin sul $\pi$ di due Popolazioni Bernoulliane]]
- [[#Test sul Parametro $\lambda$ di una Poisson|Test sul Parametro $\lambda$ di una Poisson]]

## Verifica di Ipotesi: Approccio Frequentista
Si restringe l'attenzione alla formulazione e verifica di ipotesi circa il valore assunto dai parametri $\theta$ di una legge che regola l'incertezza du una v.a. osservabile $X$.
L'obiettivo è decidere se l'ipotesi fatta è accettabile alla luce dei risultati di un campione di $n$ osservazioni da $X$.
Accettare o rifiutare un'ipotesi non implica che esse siano necessariamente vere o false ma solo che il campione supporta o meno l'ipotesi fatta, considerando la possibilità con cui essi potrebbero avvenire utilizzando un gran numero di campioni.
### Ipotesi e Livelli di Significatività
Si suppone di volere verificare una qualunque ipotesi su $\theta$, che si chiamerà ipotesi *nulla*, denotata con $H_{0}$.
Sia, ad esempio, $X$ una caratteristica con distribuzione normale con media $\theta$ e varianza $1$, due possibili ipotesi nulle su $\theta$ sono:
1. $H_{0}:\theta=1$
2. $H_{0}:\theta\le 1$
Si considera un campione aleatorio $X_{1},X_{2},\ldots,X_{n}$ proveniente da questa popolazione, e si utilizza per eseguire una verifica o test della ipotesi nulla $H_{0}$.
Il test sarà definito da una regione $C$ nello spazio campionario a $n$ dimensioni: se il vettore $(x_{1},x_{2},\ldots,x_{n})$ appartiene a $C$ l'ipotesi viene rifiutata, mentre viene accettata in caso contrario.
Una regione $C$ con queste caratteristiche viene detta **Regione Critica** del test.

Schematizzando, il test statistico determinato dalla regione critica $C$ è quello che:
$$\text{accetta }H_{0}\ \text{se }(x_{1},x_{2},\ldots,x_{n})\notin C$$

> [!example]+ Esempio:
> Si considera una popolazione bernulloniana $X=\{0,1\}$, $p(X=1)=\pi$, si osserva un campione $n=3$.
> Sia $$H_{0}:\pi=\frac{2}{5}\qquad H_{1}:\pi> \frac{2}{5}$$
> $H_{1}$ è l'ipotesi alternativa, incompatibile con $H_{0}$.
> Un esempio di regione critica potrebbe essere
> $$C=\left\{ x_{1},x_{2},x_{3}:\sum^3_{i=1}x_{i}\ge  2 \right\}$$
> Se $H_{0}$ fosse vera, la probabilità di non accettare $H_{0}$ è
> $$\sum^3_{i=2}\begin{pmatrix} 3 \\ i \end{pmatrix}\left( \frac{2}{5} \right)^i \left( \frac{3}{5} \right)^{3-1}=\left( \frac{2}{5} \right)^3+3 \left( \frac{2}{5} \right)^2 \frac{3}{5}=0.352$$
> Si chiama questa circostanza sfavorevole un error di $I$ specie. Tradizionalmente se ne indica l'ammontare con $\alpha$

**Riassunto:**
- Si considera uno stimatore puntuale del parametro da testare, $T(\mathbf{X})$
- Si valuta la sua distribuzione di probabilità nello spazio dei campioni, valendo l'ipotesi $H_{0}$
- Si osserva la determinazione campionaria e si calcola la stima del parametro utilizzando quello stimatore
- SI valuta se la stima appartiene alla regione critica del test: in quel caso si rifiuta $H_{0}$
- Sfortunatamente questo evento si verifica con probabilità $\alpha$ quando $H_{0}$ è vero

> [!example]+ Esempio:
> Si considera di avere $X=\{0,1\}$, $p(X=1)=\pi$ e $n=6$ osservazioni.
> $$H_{0}:\theta=\frac{3}{5}\qquad H_{1}:\theta=\frac{3}{5}$$
> Valendo $H_{0}$, osservare $X=1$ sei volte ha probabilità $\frac{3}{5}^6=0.046$. Al livello di significatività $\alpha\approx 0,05$ la regione critica del test è  6 successi su 6 prove, quindi un unico campione.
> Se si fa così, ripetendo il test molte molte volte, pur essendo vero $H_{0}$, si sbaglierebbe in un $5\%$ dei casi.

## Verifica di Ipotesi su $\mu$, $X\sim N(\mu,\sigma^2)$, $\sigma^2$ nota
Si dispone di un campione aleatorio $X_{1},\ldots,X_{n}$, $X\sim N(\mu,\sigma^2\ \small{\text{(nota)}})$. Si vuole verificare l'ipotesi nulla contro l'ipotesi alternativa
$$
H_{0}:\mu=\mu_{0}\quad vs\quad H_{1}:\mu\ne\mu_{0}
$$
Siccome $\overline X:= \frac{1}{n} \sum^n_{i=1}X_{i}$ è lo stimatore puntuale per $\mu$, sembra ragionevole accettare $H_{0}$ quando $\overline x$ nonè troppo lontana da $\mu_{0}$
$$C=(X_{1},X_{2},\ldots,X_{n}:|\overline X-\mu_{0}|>c)$$
per una scelta opportuna della costate $c$ dipendente da $\alpha$

Scelta la taglia dell'errore di prima specie
$$\alpha=P[\text{errore di }I\text{ specie}]=P_{\mu_{0}}(|\overline X-\mu_{0}|>c)$$
Si sa che assunto $\mu=\mu_{0}$ $$\frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\sim Z$$
$$\begin{align}
\alpha&= P_{\mu_{0}}\left( \left| \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}} \right|> \frac{c\sqrt{ n }}{\sigma} \right)=P\left( |Z|> \frac{c\sqrt{ n }}{\sigma} \right)=2P\left( Z> \frac{c\sqrt{ n }}{\sigma}=z_{\frac{\alpha}{2}} \right) \\
&\to c=z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }}
\end{align}$$

Riassumendo:
- Si rifiuta $H_{0}$ quando $$|\overline x-\mu_{0}|> z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }}$$ o equivalentemente quando $$\left| \frac{\overline x-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}} \right|>z_{\frac{\alpha}{2}}$$

> [!hint] Osservazioni
> - Più piccolo il livello di $\alpha$
> 	- Meno si è disposti a rischiare di rifiutare $H_{0}$, più è necessaria evidenza molto difforme da $H_{0}$ per rifiutare l'ipotesi
> - $H_{1}$ indirizza per la individuazione della regione di rifiuto $C$ ed è quindi essenziale
> - Le ipotesi alternative possono essere bilaterali $\ne$, unilaterali $>$ o $<$, puntuali, $=$
> - La verifica delle ipotesi è definita inferenza decisionale e soffre di *cut off* precisi che fanno decidere per una delle due ipotesi a fronte di differenze minime nella evidenza campionaria.

## Errori di Seconda Specie $\beta$
Dato $$H_{0}:\mu=\mu_{0}\quad vs \quad H_{1}:\mu\ne \mu_{0}$$
È possibile scegliere $H_{0}$ pur essendo vero $H_{1}$, ovvero che sia $\mu\ne\mu_{0}$. La probabilità di questo evento è chiamata *probabilità dell'errore di seconda specie* ed è indicata con $\beta$.
Cioè, pur essendo il valore del parametro $\mu\ne\mu_{0}$, con che probabilità si avrebbe osservato un campione nella regione di accettazione del test definita secondo $H_{0}$?
Per determinare la risposta si deve valutare
$$\beta(\mu):=(\text{accettare } H_{0})=P_{\mu}\left( \left| \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\le z_{\frac{\alpha}{2}} \right| \right)=P_{\mu}\left( -z_{\frac{\alpha}{2}}\le \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\le z_{\frac{\alpha}{2}} \right)$$
Operativamente si considera che, valendo $H_{1}$
$$\overline X\sim N\left( \mu,   \frac{\sigma^2}{n}  \right)$$
allora
$$\begin{align} 
\beta(\mu)&= P_{\mu}\left( -z_{\frac{\alpha}{2}}\le \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\le z_{\frac{\alpha}{2}} \right)= \\
&=P_{\mu}\left( \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}-z_{\frac{\alpha}{2}}\le \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+ \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\le \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+z_{\frac{\alpha}{2}} \right) \\
&=P_{\mu}\left( \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}-z_{\frac{\alpha}{2}}\le \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}=Z\le \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+z_{\frac{\alpha}{2}} \right)= \\
&=\Phi \left( \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+z_{\frac{\alpha}{2}} \right)-\Phi\left( \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}} -z_{\frac{\alpha}{2}}\right)
\end{align}$$

> [!hint] Osservazioni
> - Più due medie ipotizzate sono vicine, più è grande l'errore di II specie fino ad arrivare a $1-\alpha$, cosa che avviene quando $\mu=\mu_{0}$
> - La procedura basta sulla determinazione del livello di significatività assicura che l'errore di II specie che si compie sia minimo rispetto ad ogni altra procedura.
> - $1-\beta(\mu)$ è detta *funzione potenza del test* e assume valori crescenti all'aumentare di $|\mu_{0}-\mu|$

> [!example]+ Esempio:
> - $X\sim N(\mu,\sigma^2=4)$
> - Si estrae da un campione aleatorio $X_{1},\ldots,X_{n}$, $n=9$
> - Si hanno delle $x_{1},\ldots,x_{n}$ che producono $\overline x=10$. Si considerano $$H_{0}:\mu=9\qquad H_{1}:\mu\ne 9$$
> - Si assume di voler decidere ad un livello di significatività $\alpha=0.05$
> - La zona di accettazione del test (standardizzato) è $[-1.96\le z\le 1.96]$
> - Poiché $z= \frac{12-9}{\frac{2}{3}}=\frac{3}{2}=1.5$, si accetta $H_{0}$
> Con quale probabilità si è commesso un errore di II specie?
> 
> ![[Pasted image 20250709234158.png|center|400]]

### Calcolo e Determinazione di $n$
Dato un valore di $\mu$ ben preciso, $\mu_{1}$, come visto prima sarà
$$
\beta=\Phi\left( \frac{\mu_{0}-\mu_{1}}{\frac{\sigma}{\sqrt{ n }}} +z_{\frac{\alpha}{2}}\right)-\Phi\left( \frac{\mu_{0}-\mu_{1}}{\frac{\sigma}{\sqrt{ n }}}-z_{\frac{\alpha}{2}} \right)
$$
Si assume che $\mu_{1}>\mu_{0}$. Se si fissa $\beta$ e si vuole determinare $n$ che assicura una certa potenza del test, allora poiché $\frac{\mu_{0}-\mu_{1}}{\frac{\sigma}{s\sqrt{ n }}}-z_{\frac{\alpha}{2}}<z_{\frac{\alpha}{2}}$
$$\Phi\left( \frac{\mu_{0}-\mu_{1}}{\frac{\sigma}{\sqrt{ n }}}-z_{\frac{\alpha}{2}} \right)\approx 0$$
Quindi
$$\beta \approx \Phi\left( \frac{\mu_{0}-\mu_{1}}{\frac{\sigma}{\sqrt{ n }}} +z_{\frac{\alpha}{2}}\right)$$
Ma poiché in ottica di testi di ipotesi
$$\beta=P[Z<-z_{\beta}]=\Phi(-z_{\beta})$$
dove $z_{\beta}$ è il quantile della normale standardizzata valendo $\mu_{1}$ quindi $-z_{\beta}=\frac{\mu_{0}-\mu_{1}}{\frac{\sigma}{\sqrt{ n }}}+z_{\frac{\alpha}{2}}$, quindi
$$n\approx\left[ \frac{\left( z_{\frac{\alpha}{2}}+z_{\beta} \right)\sigma}{\mu_{1}-\mu_{0}} \right]^2$$

Nell'esempio precedente dove $\sigma^2=4$, se si voleva un $\beta=0.05$ (con $\mu_{1}=10\ vs \ \mu_{0}=9$) allora per $z_{\frac{\alpha}{2}=0.05}=1.96$ si rifiuta $H_{0}$ se è falsa con una probabilità del $95\%$ se
$$n\approx \left[ \frac{(1.96+1.64)\cdot2}{10-9} \right]^2\approx 52$$
## $p-$Value
Un approccio alternativo alla verifica delle ipotesi è quello del $p-$value. Si usa solo nelle ipotesi nulla che stabilisce la distribuzione dello stimatore.
Si valuta la probabilità di osservare stime del parametro uguali o più estreme di quelle osservate sul campione disponibile.
- **Vantaggio:** Si ha uno *score* della distanza fra l'ipotesi e l'osservazione di una stima del parametro che supera la logica dell'*on-off*
- **Difetto:** È uno *score* attribuito all'ipotesi nulla, valutato tramite una misura di probabilità su eventi che non si sono osservati

> [!example] Esempio:
> - $X\sim N(\mu,\sigma^2=4)$, si osservano $x_{1},\ldots,x_{n}$, $N=9$
> - Dai dati si calcola la media $\overline x=10$
> Si calcola il $p-$value relativo all'ipotesi $H_{0}:\mu\ge 12$:
> - I valori più estremi rispetto all'ipotesi, in questo caso, riguardano la coda sinistra della distribuzione, quindi $$p-value=\Phi\left( z=\frac{10-12}{\frac{2}{3}}=-3 \right)=0.00134$$
> - $C 1$: Si sarebbe in una zona di rifiuto di una procedura di test dell'ipotesi con $\alpha=0.05$
> - $C2$: La logica del $p-$value suggerisce (in questo caso) la direzione della ipotesi alternativa e dato un livello di significatività si confronta con il cut-off di rifiuto, ma si da anche la forza del rifiuto

## Test Unilaterali
Si considera il test per il quale sappia la direzione dell'ipotesi alternativa che non sarà generica $\ne$
$$H_{0}:\mu=\mu_{0}\quad vs\quad H_{1}:\mu>\mu_{0}$$
Si rifiuterà l'ipotesi nulla considerando una regione critica
$$
P_{\mu_{0}}(\overline X-\mu_{0}>c)=\alpha
$$
Però valendo $H_{0}$
$$\begin{gather} Z= \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\sim N(0,1)  \\
P\left( \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}} >c \frac{\sqrt{ n }}{\sigma}=z_{\alpha}\right)=\alpha\end{gather}$$
Quindi
$$c=z_{\alpha} \frac{\sigma}{\sqrt{ n }}$$
### Rifiuto di $H_{0}$ e Curva OC
Si rifiuta $H_{0}$ se
1. $\overline X-\mu_{0}>z_{\alpha} \frac{\sigma}{\sqrt{ n }}$ oppure se
2. $\frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}>z_{\alpha}$ oppure se
3. $p-value=1-\Phi\left( \frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}} \right)<\alpha$
Curva OC
$$\begin{align}
\beta(\mu)&:=P_{\mu}(\text{accettare }H_{0}|\mu)= P_{\mu}\left( \overline X\le\mu_{0}+z_{\alpha} \frac{\sigma}{\sqrt{ n }} \right)=P_{\mu}\left( \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}\le \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+z_{\alpha} \right) \\
&=P_{\mu}\left( Z\le \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+z_\alpha \right)=\Phi\left( \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}+z_{\alpha} \right)
\end{align}$$
## Scelta delle Ipotesi Unilaterali
Si considera questo set di ipotesi
$$
H_{0}:\mu\le\mu_{0}\quad vs \quad H_{1}:\mu>\mu_{0}
$$
L'ipotesi $H_{0}$
- Controlla la probabilità di non essere accettata erroneamente ($\alpha$)
- Non controlla quella di essere accettata erroneamente che dipende dal $H_{1}$ e può arrivare a $1-\alpha$

> [!example]+ Esempio:
> - $H_{0}:$ La media mg di nicotina nelle sigarette è $\mu\ge 1.6mg$
> - $H_{1}$: Un produttore dice di produrle con media$<1.6mg$
> - Si dispone di un campione proveniente dal produttore di $n=20$, $\overline x=1.54$, nota $\sigma=0.8mg$
> Il test adatto sembra essere:
> $$H_{0}:\mu\ge 1.6\quad vs \quad H_{1}:\mu <1.6$$
> Si vuole garantire di accettare $H_{0}$ con bassa probabilità di sbagliare, ovvero si vorrebbe un $\beta$ modesto, ma questo dipende da $\mu\in[0,1.6)$.
> Scelto $\alpha=0-05$, $-z_{0.05}=-1.64$, poiché il valore della statistica test è
> $$\frac{\overline H-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}= \frac{1.54-1.6}{\frac{0.8}{\sqrt{ 20 }}}\approx -0.335$$
> Si accetta $H_{0}$
> 
> **Errore di II Specie:**
> Con quale probabilità si da torto al produttore se lui ha ragione? Curva OC
> $$\begin{align}
> \beta(\mu)&:=P_{\mu}(\text{accettare }H_{0})\quad \mu\in[0,1.6) \\
> &=P_{\mu}\left( \overline X\ge\mu_{0}-z_{\alpha} \frac{\sigma}{\sqrt{ n }} \right)=P_{\mu}\left( \frac{\overline X-\mu}{\frac{\sigma}{\sqrt{ n }}}\ge \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}-z_{\alpha} \right)=P_{\mu}\left( Z\ge \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}}-z_{\alpha} \right) \\
> &= 1-\Phi\left( \frac{\mu_{0}-\mu}{\frac{\sigma}{\sqrt{ n }}} -z_{\alpha}\right)
> \end{align}$$
> Si guarda la curva  OC: se la riduzione di nicotina ha portato il contenuto medio ad esempio a $1.4mg$, allora $\beta=0.69$
> 
> ![[Pasted image 20250710002238.png|center|300]]
> 

## Verifica delle Ipotesi e Intervalli di Confidenza
L'intervallo di confidenza al livello $1-\alpha$ per la media $\mu$ ($\sigma$ noto) era calcolato
$$
\overline x-z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }}\qquad \overline x+z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }}
$$
Considerando le v.a. $\overline X$, si ha che gli intervalli aleatori comprendono $\mu$ con probabilità $1-\alpha$
$$
P\left\{ \mu\in \overline X-z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }},\overline X+z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }} \right\}=1-\alpha
$$
Nella regione critica del test si assume $E(\overline X)=\mu_{0}$ e si prende correttamente la decisione di accettare $H_{0}$ $(1-\alpha)\%$ di volte qualora
$$
|\overline x-\mu_{0}|<z_{\frac{\alpha}{2}} \frac{\sigma}{\sqrt{ n }}
$$
Si può effettuare il test costruendo un intervallo di confidenza verificando se $\mu_{0}$ è compreso nell'intervallo.
## $\sigma^2$ Non Noto, $t-$Test
L'obiettivo è verificare se la media $\mu=\mu_{0}$ non conoscendo $\sigma^2$
$$H_{0}:\mu=\mu_{0}\qquad H_{1}:\mu\ne\mu_{0}$$
Rammentando che:
$$
\left| \frac{\frac{\overline X-\mu_{0}}{\frac{\sigma}{\sqrt{ n }}}\sim N(0,1)}{\sqrt{ \frac{(n-1)S^2}{(n-1)\sigma^2} \sim \chi^2_{{n-1}}}} \right|\sim t_{{n-1}}
$$
Se si introduce $s$ come stima di $\sigma$ si rifiuterà l'ipotesi nulla se 
$$
\left| \frac{\overline x-\mu_{0}}{\frac{s}{\sqrt{ (n-1) }}} \right|> t_{\frac{\alpha}{2},n-1}
$$

Se l'ipotesi è unilaterale allora
$$H_{0}:\mu=\mu_{0}\qquad H_{1}:\mu\ge \mu_{0}$$
Quindi si rifiuterà $H_{0}$ qualora
$$
\frac{\overline H-\mu_{0}}{\frac{S}{\sqrt{ n }}}>t_{\alpha,n-1}
$$
## Confronto fra due Popolazioni Normali
È la massima semplificazione del confronto fra due popolazioni che vengono considerate rispetto alla sola media
- **Varianze note:** Si dispone di due campioni dalle v.a. $X_{1},\ldots,X_{n}$, $Y_{1},\ldots,Y_{m}$ indipendenti di varianze note $\sigma_{x}^2$, $\sigma_{y}^2$. Si vogliono testare le ipotesi $$H_{0}:\mu_{x}=\mu_{y}\qquad H_{1}:\mu_{x}\ne \mu_{y}$$Siano $\overline X$ e $\overline Y$ gli stimatori delle medie, allora $$\overline X-\overline Y\sim N\left( \mu_{x}-\mu_{y},\ \frac{\sigma^2_{x}}{n}+\frac{\sigma^2_{y}}{m} \right)\qquad \frac{\overline X-\overline Y-(\mu_{x}-\mu_{y})}{\sqrt{ \frac{\sigma^2_{x}}{n}+\frac{\sigma^2_{y}}{m} }}\sim N(0,1)$$Allora, valendo $H_{0}$ $$\frac{\overline X-\overline Y}{\sqrt{ \frac{\sigma^2_{x}}{n}+\frac{\sigma^2_{y}}{m} }}\sim N(0,1)$$per cui la ragione di accettazione del test al livello di significatività $1-\alpha$ sarà $$
P_{H_{0}}\left( -z_{\frac{\alpha}{2}}\le \frac{\overline X-\overline Y}{\sqrt{ \frac{\sigma^2_{x}}{2}+\frac{\sigma^2_{y}}{m} }}\le z_{\frac{\alpha}{2}} \right)=1-\alpha
$$Rifiutando $H_{0}$ qualora $$\frac{|\overline x-\overline y|}{\sqrt{ \frac{\sigma^2_{x}}{n} +\frac{\sigma^2_{y}}{m}}}> z_{\frac{\alpha}{2}}$$
Testando l'eguaglianza fra le medie di $X$ e $Y$ assumendo,
- **Varianze non note, ma uguali:** Varianze $\sigma^2_{x}$, $\sigma_{y}^2$. In questo caso lo stimatore della somma delle varianze è $$S_{p}^2:= \frac{(n-1)S^2_{x}+(m-1)S_{y}^2}{n+m-2}$$ e risulta $$\frac{\overline X-\overline Y-(\mu_{x}-\mu_{y})}{S_{p}\sqrt{ \frac{1}{n}+\frac{1}{m} }}\sim t_{n+m-2}$$Quindi se si assume vera $H_{0}$ $$\frac{\overline X-\overline Y}{S_{p}\sqrt{  \frac{1}{n}+\frac{1}{m} }\sim t_{n+m-2}}$$e si rifiuterà $H_{0}$ se $$\left| \frac{\overline x-\overline y}{S_{p}\sqrt{ \frac{1}{n}+ \frac{1}{m} }} \right|> t_{\frac{\alpha}{2},n+m-2}$$
Si deve sempre testare l'eguaglianza fra le medie di $X$ e $Y$ assumendo
- **Varianze non note, diverse, ma $n$ e $m$ molto grandi:** Varianze $\sigma^2_{x},\sigma^2_{y}$, in questa situazione, apporssimaticamente $$ \frac{\overline X-\overline Y}{\sqrt{ \frac{S^2_{x}}{n}+ \frac{S^2_{y}}{m} }}\sim N(0,1) $$per cui si accetta $H_{0}$ qualora $$z_{\frac{\alpha}{2}}\le \frac{\overline x-\overline y}{\sqrt{ \frac{s^2_{x}}{n}+\frac{s^2_{y}}{m} }}\le z_{\frac{\alpha}{2}}$$
## Test $t$ su Dati Appaiati
Se le $W_{i}$ scontano le principali differenze dei vari soggetti per la variabile riproposta si potrebbe assumere
$$
W\sim N(\mu_{W},\sigma^2_{W})
$$
e testare le ipotesi 
$$H_{0}:\mu_{W}=0\quad vs \quad H_{1}:\mu_{W}\ne 0$$
L'ipotesi $\mu_{W}=0$ assume l'assenza di differenza nella risposta al seguito del trattamento e si procede come nel caso della verifica di ipotesi di una sola variabile $X$ distribuita come una normale con varianza incognita, ovvero si accetta $H_{0}$ se
$$
-t_{\frac{\alpha}{2},n-1}\le \sqrt{ n } \frac{\overline W}{s_{W}}\le t_{\frac{\alpha}{2},n-1}
$$
L'ipotesi $\mu_{W}=0$ assume l'assenza di differenza nella risposta al seguito del trattamento e si procede come nel caso della verifica di ipotesi di una sola variabile $\overline X$ distribuita come una normale con varianza incognita, ovvero si accetta $H_{0}$ se
$$-t_{\frac{\alpha}{2},n-1}\le \sqrt{ n } \frac{\overline W}{s_{W}}\le t_{\frac{\alpha}{2},n-1} $$
## Test sulla Varianza di una $X\sim N(\mu,\sigma^2)$
Disponendo di un campione aleatorio $X_{1},\ldots,X_{n}$, $X\sim N(\mu,\sigma^2)$ si vuole testare il sistema di ipotesi:
$$
H_{0}:\sigma^2=\sigma^2_{0}\quad vs\quad H_{1}:\sigma^2\ne\sigma^2_{0}
$$
Se vale $H_{0}$ $$\frac{S^2}{\sigma_{0}^2}(n-1)\sim \chi^2_{{n-1}}$$
e quindi essendo
$$P_{H_{0}}\left( \chi^2_{1-\frac{\alpha}{2},n-1}\le \frac{S^2}{\sigma_{0}^2}(n-1)\le \chi^2_{\frac{\alpha}{2},n-1} \right)=1-\alpha$$
Si accetterà $H_{0}$ se $$\chi_{1-\frac{\alpha}{2}}^2\le \frac{s^2}{\sigma_{0}^2}(n-1)\le \chi^2_{\frac{\alpha}{2},n-1}$$
## Test sulla Uguaglianza della Varianza di Due Popolazioni Normali
Siano $X_{1},\ldots,X_{n}$ e $Y_{1},\ldots,Y_{m}$ le v.a.sottostanti due campioni indipendenti $X\sim N(\mu_{x},\sigma^2_{x})$, $Y\sim N(\mu_{y},\sigma^2_{y})$. Si ha un sistema di ipotesi
$$
H_{0}:\sigma^2_{x}=\sigma^2_{y}\quad vs\quad H_{1}:\sigma^2_{x}\ne \sigma^2_{y}
$$
Poiché $(n-1) \frac{S^2_{x}}{\sigma^2_{x}}\sim \chi^2_{n-1}$, $(m-1) \frac{S^2_{y}}{\sigma^2_{y}}\sim \chi^2_{m-1}$ e $\frac{\frac{\chi^2_{n}}{n}}{\frac{\chi^2_{m}}{m}}\sim F_{n,m}$ allora, se vale $H_{0}$
$$\frac{\frac{(n-1)S^2_{x}}{(n-1)\sigma^2_{x}}}{\frac{(m-1)S^2_{x}}{(m-1)\sigma^2_{y}}}=H_{0}\ \frac{S^2_{x}}{S^2_{y}}\sim F_{n-1,m-1}$$
Ovvero si accetta $H_{0}$ qualora
$$
F_{1-\frac{\alpha}{2},n-1,m-1}\le \frac{s^2_{x}}{s^2_{y}}\le F_{\frac{\alpha}{2},n-1,m-1}
$$
## Test sul $\pi$ di una Popolazione Bernoulliana
Sia $X=\{0,1\}$ si dispone di un campione aleatorio $X_{1},\ldots,X_{n}$, si considera la v.a. 
$$Y=\sum^n_{i=1}X_{i}\sim Bin(\pi,n)$$
Con le ipotesi 
$$H_{0}:\pi\le \pi_{0}\quad vs \quad H_{1}:\pi>\pi_{0}$$
Il test risulterà respinto qualora la $Y$ osservata sul campione supererà un valore $k^*$ che soddisfa il livello di significatività $\alpha$, ovvero si respinge $H_{0}$ se 
$$Y\ge k^*,\quad k^*=\min\left\{ \sum^n_{i=k}\begin{pmatrix}
n \\ i
\end{pmatrix}\pi_{0}^i(1-\pi_{0})^{n-i}\le\alpha \right\}$$
**Alternativa:**
Test basato sulla distribuzione approssimata tramite TLC, si sfrutta l'approssimazione della binomiale alla normale, sicché se si conosce $\pi$
$$
\frac{Y-n\pi}{\sqrt{ n\pi(1-\pi) }}\sim N(0,1)
$$
Per un test 
$$H_{0}:\pi\le\pi_{0}\quad vs \quad H_{1}:\pi>\pi_{0}$$
Si rifiuta l'ipotesi nulla quando
$$
\frac{y-n\pi_{0}}{\sqrt{ n\pi_{0}(1-\pi_{0}) }}\ge z_{\alpha}
$$
## Test sul $\pi$ di due Popolazioni Bernoulliane
- Sia $X^A=\{0,1\}$, si dispone di v.a. $X_{1}^A,\ldots,X_{n}^A$ e si considera $$Y^A=\sum^{n_{A}}_{i=1}X_{i}^A\sim Bin(\pi^A,n_{A})$$
- Sia $X^B=\{0,1\}$, si dispone di v.a. $X_{1}^B,\ldots,X_{n}^A$ e si considera $$Y^B=\sum^{n_{B}}_{i=1}X_{i}^B\sim Bin(\pi^B,n_{B})$$
- Si vuole sottoporre a verifica il sistema di ipotesi $$H_{0}:\pi^A=\pi^B\quad vs \quad H_{1}:\pi^A\ne \pi^B$$
Dai risultati campionari si avrà $Y^A$, $Y^B$, cioè la somma dei pezzi di tipo "1" sarà $k=y^A+y^B$. 
Si deve calcolare la regione di rifiuto del test valendo l'ipotesi che le unità statistiche siano governate dalla medesima legge, ovvero $A$ e $B$ siano la stessa popolazione.
## Test di Fisher-Irwin sul $\pi$ di due Popolazioni Bernoulliane
La popolazione complessiva ha dimensione $n_{A}+n_{B}$ di cui si è estratto $k=y^A+y^B$ osservazioni di tipo "1".
Valendo $H_{0}$ la probabilità di estrazione di $y^A$ dipende solo da $n_{A}$, $n_{B}$
$$P_{H_{0}}(y^A=i|y^A+y^B=k)=\frac{\begin{pmatrix} n_{A} \\ i \end{pmatrix}\begin{pmatrix} n_{B} \\ k-i \end{pmatrix}}{\begin{pmatrix} n_{A}+n_{B} \\ k\end{pmatrix}}$$
$H_{0}$ risulterà respinta qualora $y^A$ apparterrà alla regione critica al livello di significatività $\alpha$, ovvero se
$$y^A\ge k^*:=\min\left\{ k: \sum^{n_{A}}_{i=k}\frac{\begin{pmatrix} n_{A} \\ i \end{pmatrix}\begin{pmatrix} n_{B} \\ k-i \end{pmatrix}}{\begin{pmatrix} n_{A}+n_{B} \\ k\end{pmatrix}}\le \frac{\alpha}{2}  \right\}$$
oppure
$$y^A\le k^*:=\max\left\{ k: \sum^{n_{A}}_{i=1}\frac{\begin{pmatrix} n_{A} \\ i \end{pmatrix}\begin{pmatrix} n_{B} \\ k-i \end{pmatrix}}{\begin{pmatrix} n_{A}+n_{B} \\ k\end{pmatrix}}\le \frac{\alpha}{2}  \right\}$$
## Test sul Parametro $\lambda$ di una Poisson
Si vuole testare un set di ipotesi sul parametro di una Poisson, ad esempio:
$$H_{0}:\lambda=\lambda_{0}\quad vs \quad H_{1}:\lambda\ne\lambda_{0}$$
Sia quindi $X_{1},X_{2},\ldots,X_{n}$ un campione aleatorio proveniente da una Poisson di parametro $\lambda$, allora $Y=\sum X_{i}\sim Po(n\lambda)$ e si testerà l'ipotesi su $\lambda$ nella distribuzione di $Y$, che è (a meno di $n$) la distribuzione dello stimatore di $\lambda$.

Con riferimento a $Y$, la zona di rifiuto del test nel caso bilaterale sarà $$y\in\{y^+,y^*\}$$
dove
$$y^*>k^*:=\min\left\{ \sum^n_{i=k} \frac{(n\lambda_{0})^i\exp(-n\lambda_{0})}{i!}< \frac{\alpha}{2} \right)\qquad y^*<k^*:=\max\left\{ \sum^n_{i=0} \frac{(n\lambda_{0})^i\exp(-n\lambda_{0})}{i!}< \frac{\alpha}{2} \right)$$

> [!example]+ Esempio:
> - Il numero di clienti settimanali $X$ nel negozio d'antiquariato è stato nelle ultime 6 settimane $\{3,2,4,6,5\}$. Totale clienti $\sum_{i=1}^6 x_{i}=y=25$. 
> - Si assume che $X\sim Po(\lambda)\to Y\sim Po(6*\lambda)$
> - Si valuta l'ipotesi $$H_{0}:\lambda=3.5\quad vs\quad H_{1}:\lambda\ne 3.5$$
> - Si pone ad esempio $\alpha=0.05$
> - Se ne ricava che approssimativamente la regione di accettazione è $y\in{12,29}$, quindi si accetta $H_{0}$