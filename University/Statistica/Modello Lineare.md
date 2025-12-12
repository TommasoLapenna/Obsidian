---
sticker: emoji//1f51f
Order: "9"
---
- [[#Modelli Statistici|Modelli Statistici]]
- [[#Modello Lineare Deterministico (Versione Base)|Modello Lineare Deterministico (Versione Base)]]
- [[#Modello Lineare Stocastico Base|Modello Lineare Stocastico Base]]
- [[#Modello Lineare: Stima ai Minimi Quadrati|Modello Lineare: Stima ai Minimi Quadrati]]
- [[#Modello Lineare: Distribuzione degli Stimatori|Modello Lineare: Distribuzione degli Stimatori]]
	- [[#Modello Lineare: Distribuzione degli Stimatori#Distribuzione dello Stimatore $B$|Distribuzione dello Stimatore $B$]]
- [[#Distribuzione dello Stimatore $A$|Distribuzione dello Stimatore $A$]]
- [[#Distribuzione dello Stimatore di $\sigma^2$|Distribuzione dello Stimatore di $\sigma^2$]]
- [[#Definizione di Statistiche *Sum of Squares*|Definizione di Statistiche *Sum of Squares*]]
- [[#Modello Lineare vs Modello Quadratico|Modello Lineare vs Modello Quadratico]]
- [[#Inferenza sui Parametri di Regressione|Inferenza sui Parametri di Regressione]]
	- [[#Inferenza sui Parametri di Regressione#Test d'ipotesi|Test d'ipotesi]]
	- [[#Inferenza sui Parametri di Regressione#Intervalli di confidenza su $\beta$|Intervalli di confidenza su $\beta$]]
- [[#Regressione della Media: Altezze padri vs Altezza figli|Regressione della Media: Altezze padri vs Altezza figli]]
- [[#Inferenza su $\alpha$, $\sigma^2$ non noto|Inferenza su $\alpha$, $\sigma^2$ non noto]]
- [[#Inferenza sulla Risposta in Media|Inferenza sulla Risposta in Media]]
- [[#Varianza della Risposta in Media|Varianza della Risposta in Media]]
- [[#Inferenza sulla Risposta in Media,  $\sigma^2$ non noto|Inferenza sulla Risposta in Media,  $\sigma^2$ non noto]]
- [[#Inferenza sulla Predizione della Risposta|Inferenza sulla Predizione della Risposta]]
- [[#Coefficiente di Determinazione e di Correlazione|Coefficiente di Determinazione e di Correlazione]]
- [[#Analisi dei Residui|Analisi dei Residui]] (NON NELL'ESAME)


## Modelli Statistici
Si continua con l'inferenza sui parametri di una variabile aleatoria che regola l'incertezza circa una quantità $Y$ e sulla possibile predizione $Y_{n+1}$  ma in un contesto condizionato dalla conoscenza del valore assunto da altre variabili che specificano l'ambiente dal quale originano le osservazioni.

> [!example]+ Esempio:
> Si vuole valutare l'incertezza circa il peso di un gruppo producendo stime condizionate al genere, sia per la media che predizione

L'obiettivo è ottenere valutazioni meno incerte sulle quantità di interesse, siano esse parametri o predizioni rispetto a quelle ottenibili per la popolazione generale.
## Modelli Lineari

> [!info] Parametri Regressione
> $\alpha$ e $\beta$, insieme ad $\epsilon$ sono i *Parametri di Regressione*

### Modello Lineare Deterministico (Versione Base)
Sono necessarie:
- Una variabile $Y$ di risposta (quella che si vuole predire, v.a. dipendente)
- Alcune variabili $x_{1},\ldots,x_{r}$ di regressione (regressori, variabili di input osservabili, variabili indipendenti) osservate insieme a corrispondenti determinazioni della $Y,\ \{y_{1},\ldots,y_{n}\}$
- Sia la variabile risposta che i regressori si assumono continui
- Si assume una relazione lineare esatta come estrema semplificazione $$y=\alpha+\beta x_{1}+\ldots+\beta_{r}x_{r}$$
### Modello Lineare Stocastico Base
Si aggiunge, realisticamente, una componente aleatoria che consente una specifica approssimata della relazione, la presenza di errori di misurazione e qualunque  perturbazione la cui origine non sia specificata dal modello. $\epsilon$ è una variabile aleatoria.
$$Y=\alpha+\beta x_{1}+\ldots+\beta_{r}x_{r}+\epsilon$$
Si impone una condizione base per $\epsilon$ e cioè $E(\epsilon)=0$ che implica
$$E(Y-\alpha-\beta x_{1}-\ldots-\beta_{r}x_{r})=E(\epsilon)=0$$
Ovvero la retta di regressione stimata deve passare in mezzo ai dati sicché la media degli scostamenti si annulla.

> [!example]+ Esempio:
> | i       | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  |
> | ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | $x_{i}$ | 100 | 110 | 120 | 130 | 140 | 150 | 160 | 170 | 180 | 190 |
> | $y_{i}$ | 45  | 52  | 54  | 63  | 62  | 68  | 75  | 76  | 92  | 88  |
> ![[Pasted image 20250710030236.png|center|400]]
> - $y=\alpha+\beta x+\epsilon$
> - Naturalmente si deve stimare $a$ e $\beta$ in modo tale che la condizione $E(\epsilon)=0$ sia verificata

### Modello Lineare: Stima ai Minimi Quadrati
Da un metodo eucartistico si ottengono gli stimatori per $\alpha$ e $\beta$, questo metodo si chiama metodo dei minimi quadrati, che impone la minimizzazione del danno quadratico subito sostituendo alle osservazioni le stime fornite dal modello.
Si definisce il danno quadratico come
$$\sum^N_{i=1}(y_{i}-\alpha-\beta x_{i})^2$$
e si trovano $\hat{\alpha}$ e $\hat{\beta}$ che lo minimizzano.
$$\begin{align} SS&:= \sum^n_{i=1}(y_{i}-\alpha-\beta x_{i})^2 \\
\frac{\partial SS}{\partial\alpha}&= -2\sum^n_{i=1}(y_{i}-\alpha-\beta x_{i})=0 \\
&\to \sum^n_{i=1}(y_{i}-\alpha-\beta x_{i})=\sum^n_{i=1}\epsilon_{i}=0 \\
\frac{\partial SS}{\partial \beta}&= -2\sum^n_{i=1}x_{i}(y_{i}-\alpha-\beta x_{i})=0 \end{align}$$
Si risolve il sistema per $\alpha,\beta$
$$\begin{align} \sum^n_{i=1}&= n\alpha+\beta \sum^n_{i=1}x_{i} \\
\sum^n_{i=1}x_{i}y_{i}&=\alpha \sum^n_{i=1}x_{i}+\beta \sum^n_{i=1}x_{i}^2  \\
\hat{\alpha}&=\overline Y-\hat{\beta}\overline x \\
\hat{\beta}&= \frac{\sum_{i}x_{i}y_{i}-\overline x\sum_{i}y_{i}}{\sum_{i}x^2_{i}-n\overline x^2}\end{align}$$
$\hat{\alpha}$ e $\hat{\beta}$ sono stime da cui si possono derivare gli stimatori $A$ e $B$ che sostitusicono ai valori osservati le v.a. corrispondenti. La prima derivata parziale fa rispettare la condizione $E(\epsilon)=0$.
## Modello Lineare: Distribuzione degli Stimatori
Per determinare la distribuzione degli stimatori suggeriti dal metodo dei MQ è necessario fare delle assunzioni sulla componente aleatoria $\epsilon$
1. $\forall i\in\{1,n\}\quad \epsilon_{i}\sim N(0,\sigma^2)$
2. $\forall i\ne j\quad \epsilon_{i}\perp\!\!\!\perp \epsilon_{j}|\sigma^2,\alpha,\beta,\mathbf{ x}$
- La prima condizione fa riferimento alla distribuzione delle $Y_{i}$ attorno alla retta di regressione
- La seconda da conto dell'adeguatezza del modello lineare ad interpolare i dati
Dalle assunzioni ne consegue
$$
Y_{i}|\sigma^2,\alpha,\beta,\mathbf{x}\sim N(\alpha+\beta x_{i},\sigma^2)
$$
#### Distribuzione dello Stimatore $B$
Considerando lo stimatore $B$ di $\hat{\beta}$
$$B= \frac{\sum_{i}(x_{i}-\overline x)(Y_{i}-\overline Y)}{\sum_{i}x_{i}^2-n\overline x^2}=\frac{\sum_{i}(x_{i}-\overline x)Y_{i}-\overline Y\sum_{i}(x_{i}-\overline x )}{\sum_{i}x_{i^2}-n\overline x^2}$$
$B$ è una combinazione di variabili normali $Y_{i}$, quindi normale
$$\begin{align} E[B]&= \frac{\sum_{i}(x_{i}-\overline x)E[Y_{i}]}{\sum_{i}x_{i}^2-n\overline x^2}= \frac{\sum_{i}(x_{i}-\overline x)(\alpha+\beta x_{i})}{\sum_{i}x_{i}^2-n\overline x^2}=\frac{\alpha \sum_{i}(x_{i}-\overline x)+\beta \sum_{i}x_{i}(x_{i}-\overline x)}{\sum_{i}x_{i} ^2}-n\overline x^2 \\
&=\frac{0+\beta \sum_{i}x_{i}^2-\beta \overline x\sum_{i}x_{i}}{\sum_{i}x_{i}^2-n\overline x^2} \end{align}$$
**Varianza:**
$$\begin{align}Var[B]&= Var\left( \frac{\sum_{i}(x_{i}-\overline x)Y_{i}}{\sum_{i}x_{i}^2-n\overline x^2} \right)= \frac{Var\left\{ \sum_{i}(x_{i}-\overline x)Y_{i} \right\}}{\left( \sum_{i}x_{i}^2-n\overline x^2 \right)^2}= \frac{\sum_{i}(x_{i}-\overline x)^2Var[Y_{i}]}{\left( \sum_{i}x_{i}^2-n\overline x^2 \right)^2} \\
&= \frac{\sigma^2\sum_{i}(x_{i}-\overline x)^2}{\left( \sum_{i}x_{i}^2-n\overline x ^2\right)^2}=\frac{\sigma^2}{\sum_{i}x_{i}^2-n\overline x^2}\end{align}$$
#### Distribuzione dello Stimatore $A$
Si considera lo stimatore $A$ di $\hat{\alpha}$
$$A=\frac{1}{n}\sum_{i}Y_{i}-B\overline x\sim N(E(A), Var(A))$$
**Media:**
$$\begin{align}
E[A]&= \frac{1}{n}\sum_{i}E[Y_{i}]-\overline x E[B]= \frac{1}{n}\sum_{i}(\alpha+\beta x_{i})-\overline x\beta=\alpha+\beta \overline x- \overline x\beta=\alpha
\end{align}$$
**Varianza:**
Dato $A=\frac{1}{n}\sum_{i}Y_{i}-B\overline x$
$$\begin{align}Cov(\overline Y,B)&= Cov\left( \overline Y, \sum\delta_{i},Y_{i} \right),\quad \delta_{i}= \frac{x_{i}-\overline x}{\sum(x_{i}-\overline x)^2} \\
&=\sum\delta_{i}Cov(\overline Y,Y_{i})=\sum\delta_{i}Cov\left( \frac{1}{n}\sum Y_{i},Y_{i} \right)=\sum\delta_{i}Cov\left( \frac{1}{n}\sum Y_{i},Y_{i} \right) \\
&=\sigma^2\sum\delta_{i}=0 \\
 \\
Var[A]&= Var(\overline Y)+\overline x^2Var(B)-2\overline xCov(\overline Y,B)=\frac{\sigma^2}{n}+ \frac{\overline x^2\sigma^2}{\sum_{i}x_{i}^2-n\overline x^2} \\
&= \frac{\sigma^2\sum_{i}x_{i}^2}{n\left( \sum_{i}x_{i}^2-n\overline x^2 \right)}\end{align}$$
#### Distribuzione dello Stimatore di $\sigma^2$
$$\begin{align}
\frac{\sum(Y_{i}-\mu)^2}{\sigma^2}&\sim \chi_{n}^2 \\
\frac{\sum(Y_{i}-\overline Y)^2}{\sigma^2}&\sim \chi^2_{{n-1}} \\
\frac{\sum(Y_{i}-A-Bx_{i})^2}{\sigma^2}&\sim \chi^2_{{n-2}}
\end{align}$$
$SS_R:=\sum^n_{i=1}(Y_{i}-A-Bx_{i})^2$ somma dei quadrati residui
$$\frac{SS_{R}}{\sigma^2}\sim \chi^2_{{n-2}}$$
$E\left[ \frac{SS_{R}}{\sigma^2} \right]=n-2$ e quindi che $E\left[ \frac{SS_{R}}{n-2} \right]=\sigma^2$
Si può cioè usare $\frac{SS_{R}}{n-2}$ come stimatore non distorto di $\sigma^2$
#### Definizione di Statistiche *Sum of Squares*
$$\begin{align} 
S_{xy}&:=\sum_{i=1}^n(x_{i}-\overline x)(y_{i}-\overline y)=\sum^n_{i=1}x_{i}y_{i}-n\overline x\overline y \\
S_{xx}&:= \sum^n_{i=1}(x_{i}-\overline x)^2= \sum^n_{i=1}x_{i}^2-n\overline x^2 \\
S_{yy}&:= \sum^n_{i=1}(y_{i}-\overline y)^2=\sum^n_{i=1}y_{i}^2-n\overline y^2
\end{align}$$
Da queste espressioni si ricava
$$\hat{\beta} =\frac{S_{xy}}{S_{xx}}\qquad \hat{\alpha}=\overline y-\beta\overline x\qquad ss_{R}= \frac{S_{xx}S_{yy}-S^2_{xy}}{S_{xx}}$$

> [!example]
> Relazione fra $x$, la percentuale d'acqua durante la lavorazione di un certo materiale, con $Y$, la densità del prodotto finito.
>
> | $x_{i}$ | 5   | 6   | 7    | 10   | 12   | 15   | 18   | 20   |
> | ------- | --- | --- | ---- | ---- | ---- | ---- | ---- | ---- |
> | $y_{i}$ | 7.4 | 9.3 | 10.6 | 15.4 | 18.1 | 22.2 | 24.1 | 24.8 |
> 

## Modello Lineare vs Modello Quadratico
![[Pasted image 20250710034906.png|center|600]]

---

## Inferenza sui Parametri di Regressione

![[Pasted image 20250710035000.png|center|400]]

Note le distribuzioni degli stimatori dei parametri $\alpha,\beta,\sigma^2$ si può procedere alla verifica di ipotesi sul loro valore. Ci si concentra su $\beta$ che da conto dell'esistenza e del segno dell'associazione fra $X$ e $Y$
- Poiché $\frac{B-\beta}{\frac{\sigma}{\sqrt{ S_{XX} }}}\sim N(0,1)$
- Inoltre: $\frac{SS_{R}}{\sigma^2}\sim \chi^2_{n-2}$
- Quindi: $$\frac{\frac{B-\beta}{\frac{\sigma}{\sqrt{  S_{xx} }}}}{\sqrt{ \frac{SS_{R}}{\sigma^2}(n-2) }}=\frac{B-\beta}{\sqrt{ (n-2) }S_{xx}}\sim t_{n-2}$$
### Test d'ipotesi su $\beta$
Si confrontano le due ipotesi
$$H_{0}:\beta=0\quad vs\quad H_{1}:\beta\ne 0$$
Se $\beta=0$ la regione di rifiuto del test sarà individuata al livello di significatività $\gamma$ dai valori di $B$ tali che $$\sqrt{ \frac{(n-2)S_{xx}}{SS_{R}} }|B|> t_{\frac{\gamma}{2},n-2}$$
Il $p-$value può essere calcolato valutando $$2*P\left( t_{n-2}> \sqrt{ \frac{(n-2)S_{xx}}{SS_{R}} }|\hat{\beta}| \right)$$
### Intervalli di confidenza su $\beta$
Conoscendo la distribuzione dello stimatore si può affermare
$$P\left( -t_{\frac{\gamma}{2},n-2}< \sqrt{ \frac{(n-2)S_{xx}}{SS_{R}} }(B-\beta)< t_{\frac{\gamma}{2},n-2} \right)=1-\gamma$$
Quindi, a partire dai risultati campionari $\hat{\beta}$ si individua l'intervallo di confidenza
$$
\hat{\beta}\pm t_{\frac{\gamma}{2},n-2}\cdot \sqrt{ \frac{SS_{R}}{(n-2)S_{xx}} }
$$
### Regressione della Media: Altezze padri vs Altezza figli
![[Pasted image 20250710154656.png|center|550]]

Si ha evidenza che c'è una relazione lineare fra le altezze, ci si chiede quindi se si ha un effetto di regression, ovvero $H_{0}:\beta=1\ vs\ H_{1}:\beta<1$.
Si può calcolare l'intervallo di confidenza per $\beta$ al $95\%$
- $S_{xx}=171.6$, $S_{xy}=79.72$, $S_{yy}=38.529$ 
$$0.4646\pm 2.26 \sqrt{ \frac{1.4935}{8*1.71.6} }=\{0.3901,0.5390\}$$
Si verifica che $1$ non ricade nell'intervallo. Alternativamente si può valutare la statistica $$\frac{\hat{\beta}-\beta_{H_{0}}}{\sqrt{ \frac{SS_{R}}{(n-2)S_{xx}} }}= \frac{0.46-1}{0.3901}=-16.39$$
### Inferenza su $\alpha$, $\sigma^2$ non noto
Si sa che
$$\begin{gather}
A\sim N\left( \alpha, \frac{\sigma^2\sum_{i}x_{i^2}}{nS_{xx}} \right) \\
\frac{SS_{R}}{\sigma^2}\sim \chi^2_{n-2} \\
\frac{N(0,1)}{\sqrt{ \frac{\chi^2}{n} }}\sim t_{n-2}
\end{gather}$$
Si ottiene la statistica per la verifica delle ipotesi
$$\sqrt{ \frac{n(n-2)S_{xx}}{SS_{R}\cdot \sum_{i}x_{i}^2} }(A-\alpha)\sim t_{n-2}$$
di conseguenza, ad un livello di $1-\gamma$, l'intervallo di confiedenza bilaterale per un particolare campione è
$$\hat{\alpha}\pm t_{\frac{\gamma}{2},n-2}\cdot \sqrt{ \frac{SS_{R}\cdot \sum_{i}x_{i}^2}{(n-2)\cdot n S_{xx}} }$$
### Inferenza sulla Risposta in Media
Per ogni possibile per ogni valore del predittore $x_{0}$, cosa ci si può aspettare $E(Y|x_{0})?$
In termini di stima puntuale sarà
$$E[A+Bx_{0}]=E[A]+x_{0}E[B]=\alpha+\beta x_{0}$$
Se si vuole una stima intervallare si deve studiare la distribuzione di $A+Bx_{0}$, vedendo come si combinano fra loro gli stimatori $A$ e $B$.
Se si vuole la predizione in media per un certo valore di $x$, si dice $x_{0}$
$$E(Y_{x_{0}})=E(A+Bx_{0})=E(A)+E(B)x_{0}=\alpha+\beta x_{0}$$
Poiché $B=\sum^n_{i=1} \frac{(x_{i}-\overline x)Y_{i}}{S_{xx}}$ e $A=\overline Y-B\overline x$
$$A+Bx_{0}=\overline Y-B(\overline x-x_{0})=\sum^n_{i=1} \frac{1}{n}Y_{i}-\sum^n_{i=1} \frac{(x_{i}-\overline x)(\overline x-x_{0})}{S_{xx}}Y_{i}=\sum^n_{i=1}\left[ \frac{1}{n}- \frac{(x_{i}-\overline x)(\overline x-x_{0})}{S_{\times}} \right]Y_{i}$$
Ovvero una combinazione lineare di normali indipendenti di media $\alpha+\beta x_{0}$
### Varianza della Risposta in Media
$$\begin{align}
Var[A+Bx_{0}]&= \sum^n_{i=1}\left[ \frac{1}{n} - \frac{(x_{i}-\overline x)(\overline x-x_{0})}{S_{xx}} \right]^2 Var[Y_{i}] \\
&= \sigma^2 \sum^n_{i=1}\left[  \frac{1}{n^2}- \frac{2(x_{i}-\overline x)(\overline x-x_{0})}{nS_{xx}}+ \frac{(x_{i}-\overline x)^2(\overline x-x_{0})^2}{S^2_{xx}} \right] \\
&=\sigma^2 \left[ \frac{1}{n}- \frac{2(\overline x-x_{0})}{nS_{xx}} \sum^n_{i=1}(x_{i}-\overline x)+ \frac{(\overline x-x_{0})^2}{S^2_{xx}} \sum^n_{i=1}(x_{i}-\overline x)^2 \right] \\
&=\sigma^2\left[  \frac{1}{n}-0+ \frac{(\overline x-x_{0})^2}{S^2_{xx}}S_{\times} \right] \\
&=\sigma^2\left[ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{\times}} \right]
\end{align}$$
Ovvero tanto più ci si allontana dal centro delle osservazioni di $X$, tanto più cresce l'incertezza sulla risposta media.
### Inferenza sulla Risposta in Media,  $\sigma^2$ non noto
Pur disponendo di $$A+Bx_{0}\sim N\left( \alpha+\beta x_{0}\quad \sigma^2\left[ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} \right] \right)$$
Si deve come al solito eliminare $\sigma^2$ usando $$\frac{SS_{R}}{\sigma^2}\sim \chi^2_{n-2}$$
$$\frac{A+Bx_{0}-(\alpha+\beta x_{0})}{\sqrt{  \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} }\sqrt{  \frac{SS_{R}}{n-2} }}\sim t_{n-2}$$
Da qui si possono valutare gli intervalli di confidenza utilizzando i dati campionari
$$
\hat{\alpha}+\hat{\beta}_{x_{0}}\pm t_{\frac{\gamma}{2},n-2}\cdot \sqrt{ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} }
$$
![[Pasted image 20250710161930.png|center|400]]

### Inferenza sulla Predizione della Risposta
Per ogni possibile $x_{0}$ cosa è possibile dire su $Y|x_{0}$?
Il modello delle osservazioni era $$Y\sim N(\alpha+\beta x_{0},\sigma^2)$$
Mentre l'incertezza sul valore degli stimatori produceba
$$
A+Bx_{0}\sim N\left( \alpha+\beta x_{0},\ \sigma^2\left[ \frac{1}{n} + \frac{(\overline x-x_{0})^2}{S_{xx}}\right] \right)
$$
Studiano $Y-A+Bx_{0}$
$$
Y-A-Bx_{0}\sim N\left( 0,\sigma^2\left[ 1+ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} \right] \right)
$$
Sostituendo infine $\sigma^2$ con il suo stimatore si ottiene
$$\frac{Y-A-Bx_{0}}{\sqrt{  \frac{n+1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}}\sqrt{ \frac{SS_{R}}{n-2} } }}\sim t_{n-2}$$
Infine, l'intervallo di predizione cercato risulta
$$
\hat{\alpha}+\hat{\beta}x_{0}\pm t_{\frac{\gamma}{2},n-2}\cdot \sqrt{ \left[ 1+ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} \right] \frac{SS_{R}}{n-2} }
$$

> [!example]+ Esempio: Altezze:
> ![[Pasted image 20250710162602.png|center|400]]

### Coefficiente di Determinazione e di Correlazione
Si parte dalla variabilità delle $y$ attorno alla loro media
$$
S_{yy}:= \sum^n_{i=1}(Y_{i}-\overline Y)^2
$$
Si considera anche la variabilità delle $y$ rispetto alla retta di regressione (media di $Y$ in funzione delle $x$ e della relazione lineare)
$$
SS_{R}:=\sum_{i=1}^n(y_{i}-\hat{\alpha}-\hat{\beta}x_{i})^2 = \frac{S_{xx}S_{yy}-S^2_{xy}}{S_{xx}}
$$
Una misura relativa del decremento di variabilità sarà quindi il cd coefficiente di determinazione $R^2$
$$
R^2:= \frac{S_{yy}-ss_{R}}{S_{yy}}=1- \frac{ss_{R}}{S_{yy}}
$$
Si ricorda la definizione del coefficiente di correlazione $r:= \frac{\sum_{i}(x_{i}-\overline x)(y_{i}-\overline y)}{\sqrt{ \sum_{i}(x_{i}-\overline x)^2 \sum_{i}(y_{i}-\overline y)^2 }}= \frac{S_{xy}}{\sqrt{ S_{xx}S_{yy} }}$
$$\begin{align}
r^2&= S^2_{xy}\quad \text{ma dalla formulazione di }SS_{r} \\
&= \frac{S_{xx}S_{yy}-SS_{R}S_{xx}}{S_{xx}S_{yy}}= 1- \frac{SS_{R}}{S_{yy}}=R^2
 \end{align}$$
 Quindi la misura di associazione fra variabili coincide con la riduzione di variabilità della $Y$ dovuta all'introduzione della stima e all'impiego del modello lineare.

## Analisi dei Residui

## Estensione 1: Linearizzazione
La risposta media potrebbe non essere una funzione lineare dei parametri. Se la forma di questa relazione può essere determinata si possono allora trasformare le variabili e usare il modello lineare.

> [!example]+ Esempio:
> L'intensità $W(t)$ di un segnale dopo un tempo $t$ potrebbe seguire un decadimento esponenziale
> $$
> W(t)\approx c \exp[-dt]
> $$
> Se si prendono i logaritmi naturali, ciò può essere espresso come
> $$
> \log W(t)\approx \log c-dt
> $$
> Se si pone 
> $$Y=\log W(t)\qquad \alpha=\log c \qquad \beta=-d$$
> la relazione iniziale può essere modellizzata da 
> $$
> Y=\alpha+\beta t+\epsilon
> $$
> permettendo quindi di stimare $\alpha$ e $\beta$ con l'usuale metodo dei minimi quadrati, e fare previsioni tramite
> $$
> W(t)\approx \exp[A+Bt]
> $$
> 

## Estensione 2: Regression Polinomiale
## Estensione 3: Regressione Lineare Multipla
La risposta di un esperimento può essere predetta da più di una variabile indipendente. In questo caso si usa quindi la regressione lineare multipla, che è un modello di regressione in cui ci sono $k$ variabili indipendenti, la risposta è legata tramite una relazione lineare:
$$
Y=\beta_{0}+\beta_{1}x_{1}+\ldots+\beta_{k}x_{k}+\epsilon
$$
dove per $j\in\{1,\ldots,k\}$ $x_{j}$ è la $j-$esima variabile di ingresso e $\epsilon\sim N(0,\sigma^2)$ (con $\sigma^2$ costante).

I parametri $\beta_{0},\ldots,\beta_{k}$, così come $\sigma^2$ si suppongono incogniti e devono essere stimati dai dati. Le singole variabili $Y_{i}$ sono legate alle covariate tramite
$$
E[Y_{i}]=\beta_{0}+\beta_{1}x_{i1}+\ldots+\beta_{k}x_{ik}
$$
La somma dei residui al quadrato è
$$
S= \sum^n_{i=1}(y_{i}-\beta_{0}-\beta_{1} x_{i 1}-\beta_{2} x_{i 2}-\ldots-\beta_{k}x_{ik})^2
$$
che deve essere minimizzata tramite le stime dei parametri di regressione ai minimi quadrati.
Per determinare le stime ai quadrati minimi si calcolano le derivate parziali rispetto a $\beta_{0},\ldots,\beta_{k}$ della somma di quadrati precedente, e la si pone uguale a 0.

Le $k+1$ equazioni che si ottengono sono piuttosto tediose da scrivere, conviene portare il problema in forma matriciale:
$$
\mathbf{Y}=\mathbf{x}\beta+\epsilon
$$
Definito: $p=k+1$
$$
\mathbf{y}:=\begin{bmatrix}
Y_{1} \\
Y_{2} \\
\vdots \\
Y_{n}
\end{bmatrix}
\qquad
\mathbf{X}:= \begin{bmatrix}
1 & x_{11} & x_{12} & \cdots & x_{1k} \\
1 & x_{21} & x_{22} & \cdots & x_{2k} \\
\vdots &  & & & \vdots \\
1 & x_{n1} & x_{n 2} & \cdots & x_{nk}
\end{bmatrix}
\qquad
\beta:= \begin{bmatrix}
\beta_{0} \\
\beta_{1} \\
\vdots \\
\beta_{k}
\end{bmatrix}
\qquad 
\epsilon:= \begin{bmatrix}
\epsilon_{1} \\
\epsilon_{2} \\
\vdots \\
\epsilon_{n}
\end{bmatrix}
$$
- $\mathbf{y}$ è una $n\times 1$
- $\mathbf{ X}$ è una $n\times p$
- $\beta$ è una $p\times 1$
- $\epsilon$ è una $n\times 1$
Allora la quantità da minimizzare sarà:
$$\begin{gather}
S= \underset{1\times n}{(\mathbf{y}-\mathbf{X}\beta)^T}\underset{n\times 1}{(\mathbf{y}-\mathbf{X}\beta)}=\mathbf{y}^T\mathbf{y}-\beta^T\mathbf{X}^T\mathbf{y}-\mathbf{y}^T-\mathbf{X}\beta+\beta^T\mathbf{X}^T\mathbf{X}\beta \\
\frac{\delta S}{\delta \beta}=-\mathbf{X}^T\mathbf{y}-\mathbf{y}^T\mathbf{X}+2\mathbf{X}^T\mathbf{X\beta}=0 \\
\mathbf{X}^T\mathbf{X}\beta=\mathbf{X^T\mathbf{y}}
\end{gather}$$
Se $\mathbf{X}^T\mathbf{X}$ è invertibile:
$$
\hat{\beta}=(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X^T}\mathbf{y}
$$

> [!example] Example:
> ![[Pasted image 20251212111224.png|center|600]]

**Proprietà degli Stimatori:**
- Gli stimatori $B_{0},\ldots,B_{k}$, ricavabili dalle stime ai minimi quadrati, sono combinazioni lineari delle $\mathbf{Y}$, che si stanno supponendo essere variabili aleatori normali e indipendenti. Tali stimatori hanno distribuzione normala multivariata.
- Gli stimatori dei minimi quadrati sono corretti: $$
\begin{align}
E[\mathbf{B}]&=E[(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{Y}] \\
&= E[(\mathbf{X^T}\mathbf{X})^{-1}\mathbf{X}^T(\mathbf{X}\beta+\epsilon) ] \\
&=E[(\mathbf{ X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{X}\beta+(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\epsilon] \\
&= E[\beta+(\mathbf{X^T\mathbf{X}})^{-1}\mathbf{X^T}\epsilon] \\
&=\beta+(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^{T}\mathbf{E}[\epsilon]=\beta
\end{align}
$$
- *Varianza e Covarianza dei* $B_{j}$: Si denota con $Cov(\mathbf{B})$ la matrice delle covarianze, vale dire 
$$Cov(\mathbf{B}):=\begin{bmatrix}
Cov(B_{0},B_{0}) & \cdots & Cov(B_{0},Bk) \\
\vdots & \ddots & \vdots \\
Cov(B_{k},B_{0}) & \cdots & Cov(B_{k},B_{k})
\end{bmatrix}$$
Si pone $\mathbf{C}:= (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T$, con dimensione $p\times n$. Si può riscrivere allora $\mathbf{B}$ nella forma
$$\begin{bmatrix}
B_{0} \\ \vdots  \\ B_{i-1} \\ \vdots \\ B_{k}
\end{bmatrix}=\mathbf{B}=\mathbf{CY}=\begin{bmatrix}
C_{11} & \cdots & C_{1n} \\
\vdots & & \vdots \\
C_{i_{1}} & \cdots & C_{in} \\
\vdots & & \vdots \\
C_{p1} & \cdots & C_{pn}
\end{bmatrix}$$
Si ha quindi che 
$$B_{i-1}= \sum^n_{l=1}C_{il}Y_{l}\qquad B_{j-1}=\sum^n_{r=1}C_{jr}Y_{r}$$
La covarianza di una coppia di stimatori $B$ risulta 
$$Cov(B_{i-1},B_{j-1})=Cov\left( \sum^n_{l=1}C_{il}Y_{l},\sum^n_{r=1}C_{jr}Y_{r} \right)= \sum^n_{l=1}\sum^n_{r=1}C_{il}C_{jr}Cov(Y_{l},Y_{r})$$
siccome quando $l\ne r$ si ha che $Y_{l}$ e $Y_{r}$ sono indipendenti:
$$Cov(Y_{l},Y_{r})=\begin{cases}
0 & \text{se }l\ne r \\
Var[Y_{r}] & \text{se }l=r
\end{cases}$$
e siccome $Var[Y_{r}]=\sigma^2$ si ottiene che 
$$Cov(B_{i-1},B_{j-1})=\sigma^2\sum^n_{r=1}C_{ir}C_{jr}=\sigma^2\cdot\underset{\text{elemento }j-\text{esimo della matrice}}{(\mathbf{C}\mathbf{C}^T)_{ij}}$$
Quindi
$$
Cov(\mathbf{ B})=\sigma^2\mathbf{C}\mathbf{ C}^T
$$
Inoltre, siccome 
$$
\mathbf{C}^T:= ((\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T)^T=\mathbf{X}((\mathbf{X}^T\mathbf{X})^{-1})^T=\mathbf{X}(\mathbf{X}^T\mathbf{X})^{-1}
$$
Allora:
$$
\mathbf{CC}^{T}= (\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{X}(\mathbf{X}^T\mathbf{X})^{-1}=(\mathbf{X}^T\mathbf{X})^{-1}
$$
La matrice di varianza e covarianza diventa
$$Cov(\mathbf{B})=\sigma^2(\mathbf{X}^T\mathbf{X})^{-1}$$
-  *Stimatore di* $\sigma^2$: se si pone
$$
SS_{R}:= \sum^n_{i=1}(Y_{i}-B_{0}-B_{1}{x_{i 1}}-B_{2}{ x_{i 2}}-\ldots-B_{k}x_{ik})^2
$$
è possibile dimostrare che
$$
\frac{SS_{R}}{\sigma^2}\sim \chi^2_{{n-(k+1)}}
$$
da cui deriva che
$$
E\left[ \frac{SS_{R}}{\sigma^2} \right]=n-k-1\qquad E\left[ \frac{SS_{R}}{n-k-1} \right]=\sigma^2
$$
Per cui $\frac{SS_{R}}{n-k-1}$ è uno stimatore corretto di $\sigma^2$

**Bontà dell'adattamento del modello ai dati**:
- Il *Coefficiente di Determinazione Multipla* 
$$R^2:= 1- \frac{SS_{R}}{\sum^n_{i=1}(Y_{i}-\overline Y)}^2$$
misura la diminuzione di variabilità nelle risposte quando si usa il criterio dei minimi quadrati
---
## Risposta Media
Si suppone di essere prossimi a realizzare una serie di esperimenti, ripetuti più volte e on livelli delle covariate uguali a quelli che hanno condotto la stima. Basandosi sui dati precedenti, si vuole stimare la risposta media di questi nuovi esperimenti.

Il parametro incognito è dato da
$$
E[Y|x]=\beta_{0}+\beta_{1}x_{1}+\ldots+\beta_{k}x_{k}
$$
il naturale stimatore puntuale è $\sum^k_{i=0}B_{i}x_{i}$ ($x_{0}\equiv 1$.
Per determinare la distribuzione di questo stimatore si usa una variabile aleatoria normale, in quanto esprimibile come combinazione lineare delle variabili aleatorie normali e indipendeti $Y_{1},\ldots,Y_{n}$.

- **Media:** $$\begin{align}
E\left[ \sum^k_{i=0} x_{i}B_{i}\right]&=\sum^k_{i=0}x_{i}E[B_{i}]=\underset{\text{in quanto }E[B_{i}]=\beta_{i}}{\sum^k_{i=0}x_{i}\beta_{i}} =E[Y|x]
\end{align}$$
- **Varianza:** $$Var\left( \sum^k_{i=0}x_{i}B_{i} \right)=Cov\left( \sum^k_{i=0}x_{i}B_{i},\ \sum^k_{j=0}x_{j}B_{j} \right)=\sum^k_{i=0}\sum^k_{j=0}x_{i}x_{j}Cov(B_{i},B_{j})=\sigma^2\mathbf{x}^T(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{x}$$
Quindi
$$
\frac{\sum_{i}x_{i}B_{i}-\sum_{i}x_{i}\beta_{i}}{\sigma \sqrt{ \mathbf{ x}^T(\mathbf{X}^T\mathbf{X})^{-1} }\mathbf{x}}\sim N(0,1)
$$
- In caso che $\sigma^2$ non sia noto lo sostituisce con il suo stimatore $\frac{SS_{R}}{n-k-1}$
$$
\frac{\sum_{i}x_{i}\beta_{i}-\sum_{i}x_{i}\beta_{i}}{\sqrt{ \frac{SS_{R}}{n-k-1} }\sqrt{ \mathbf{x}^T(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{x} }}\sim t_{n-k-1}
$$
- Intervalli di confidenza al livello $\gamma$ di significatività per la risposta media:
$$
\sum^k_{i=0}x_{i}B_{i}\pm t_{\frac{\gamma}{2},n-k-1}\cdot \sqrt{ \frac{SS_{R}}{n-k-1} }\sqrt{ \mathbf{X}^T(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{x} }
$$
### Predizione di Risposte Future
Piuttosto che usare uno stimatore della risposta media, si potrebbe ottenere un predittore della risposta, si utilizza quindi il campione di dati per predire nel modo migliore il valore che verrà assunto dalla variabile aleatoria
$$
Y(\mathbf{x})=\sum^k_{i=0}\beta_{i}x_{i}+\epsilon
$$
Un predittore puntuale è dato da $\sum^k_{i=0}B_{i}x_{i}$, dove $B_{i}$ è lo stimatore dei minimi quadrati di $\beta_{i}$.
Si nota che la risposta futura è indipendente dai $B_{i}$, quindi $Y(\mathbf{x})-\sum^k_{i=0}B_{i}x_{i}$ è normale ocn media nulla e varianza
$$
Var\left[ Y(\mathbf{x})-\sum^k_{i=0}B_{i}x_{i} \right]=Var\left( \sum^k_{i=0}B_{i}x_{i} \right)=\sigma^2+\sigma^2\mathbf{x}^T(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{x}
$$
Quindi
$$
\frac{Y(\mathbf{x})-\sum_{i}B_{i}x_{i}}{\sigma \sqrt{ 1+\mathbf{x}^T(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{x} }}\sim N(0,1)
$$
ovvero, tramite la sola sostituzione di $\sigma$ con il relativo stimatore,
$$
\frac{Y(\mathbf{x})-\sum_{i}B_{i}x_{i}}{\sqrt{ \frac{SS_{R}}{n-k-1} }\sqrt{ 1+\mathbf{ x}^T(\mathbf{ X}^T\mathbf{X})^{-1}\mathbf{x} }}\sim t_{n-k-1}
$$
Con livello di confidenza $1-\gamma$, la risposta $Y(\mathbf{x})$ cadrà entro 
$$
\sum^k_{i=0}\beta_{i}x_{i}\pm t_{\frac{\gamma}{2},n-k-1}\cdot \sqrt{ \frac{SS_{R}}{n-k-1} }\sqrt{ 1+\mathbf{x}^T(\mathbf{X^T\mathbf{X}})^{-1}\mathbf{x} }
$$