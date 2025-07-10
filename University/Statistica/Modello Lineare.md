---
sticker: emoji//0039-fe0f-20e3
---
## Modelli Statistici
Si continua con l'inferenza sui parametri di una variabile aleatoria che regola l'incertezza circa una quantità $Y$ e sulla possibile predizione $Y_{n+1}$  ma in un contesto condizionato alla conoscenza del valore assunto da altre variabili che specificano l'ambiente dal quale originano le osservazioni.

> [!example]+ Esempio:
> Si vuole valutare l'incertezza circa il peso di un gruppo producendo stime condizionate al genere, sia per la media che predizione

L'obiettivo è ottenere valutazioni meno incerte sulle quantità di interesse, siano esse parametri o predizioni rispetto a quelle ottenibili per la popolazione generale.
## Modello Lineare Deterministico (Versione Base)
Sono necessarie:
- Una variabile $Y$ di risposta (quella che si vuole predire, v.a. dipendente)
- Alcune variabili $x_{1},\ldots,x_{r}$ di regressione (regressori, variabili di input osservabili, variabili indipendenti) osservate insieme a corrispondenti determinazioni della $Y,\ \{y_{1},\ldots,y_{n}\}$
- Sia la variabile risposta che i regressori si assumono continui
- Si assume una relazione lineare esatta come estrema semplificazione $$y=\alpha+\beta x_{1}+\ldots+\beta_{r}x_{r}$$
## Modello Lineare Stocastico Base
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

## Modello Lineare: Stima ai Minimi Quadrati
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
### Distribuzione dello Stimatore $B$
Considerando lo stimatore $B$ di $\hat{\beta}$
$$B= \frac{\sum_{i}(x_{i}-\overline x)(Y_{i}-\overline Y)}{\sum_{i}x_{i}^2-n\overline x^2}=\frac{\sum_{i}(x_{i}-\overline x)Y_{i}-\overline Y\sum_{i}(x_{i}-\overline x )}{\sum_{i}x_{i^2}-n\overline x^2}$$
$B$ è una combinazione di variabili normali $Y_{i}$, quindi normale
$$\begin{align} E[B]&= \frac{\sum_{i}(x_{i}-\overline x)E[Y_{i}]}{\sum_{i}x_{i}^2-n\overline x^2}= \frac{\sum_{i}(x_{i}-\overline x)(\alpha+\beta x_{i})}{\sum_{i}x_{i}^2-n\overline x^2}=\frac{\alpha \sum_{i}(x_{i}-\overline x)+\beta \sum_{i}x_{i}(x_{i}-\overline x)}{\sum_{i}x_{i} ^2}-n\overline x^2 \\
&=\frac{0+\beta \sum_{i}x_{i}^2-\beta \overline x\sum_{i}x_{i}}{\sum_{i}x_{i}^2-n\overline x^2} \end{align}$$
**Varianza:**
$$\begin{align}Var[B]&= Var\left( \frac{\sum_{i}(x_{i}-\overline x)Y_{i}}{\sum_{i}x_{i}^2-n\overline x^2} \right)= \frac{Var\left\{ \sum_{i}(x_{i}-\overline x)Y_{i} \right\}}{\left( \sum_{i}x_{i}^2-n\overline x^2 \right)^2}= \frac{\sum_{i}(x_{i}-\overline x)^2Var[Y_{i}]}{\left( \sum_{i}x_{i}^2-n\overline x^2 \right)^2} \\
&= \frac{\sigma^2\sum_{i}(x_{i}-\overline x)^2}{\left( \sum_{i}x_{i}^2-n\overline x ^2\right)^2}=\frac{\sigma^2}{\sum_{i}x_{i}^2-n\overline x^2}\end{align}$$
## Distribuzione dello Stimatore $A$
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
## Distribuzione dello Stimatore di $\sigma^2$
$$\begin{align}
\frac{\sum(Y_{i}-\mu)^2}{\sigma^2}&\sim \chi_{n}^2 \\
\frac{\sum(Y_{i}-\overline Y)^2}{\sigma^2}&\sim \chi^2_{{n-1}} \\
\frac{\sum(Y_{i}-A-Bx_{i})^2}{\sigma^2}&\sim \chi^2_{{n-2}}
\end{align}$$
$SS_R:=\sum^n_{i=1}(Y_{i}-A-Bx_{i})^2$ somma dei quadrati residui
$$\frac{SS_{R}}{\sigma^2}\sim \chi^2_{{n-2}}$$
$E\left[ \frac{SS_{R}}{\sigma^2} \right]=n-2$ e quindi che $E\left[ \frac{SS_{R}}{n-2} \right]=\sigma^2$
Si può cioè usare $\frac{SS_{R}}{n-2}$ come stimatore non distorto di $\sigma^2$
## Definizione di Statistiche *Sum of Squares*
$$\begin{align} 
S_{xy}&:=\sum_{i=1}^n(x_{i}-\overline x)(y_{i}-\overline y)=\sum^n_{i=1}x_{i}y_{i}-n\overline x\overline y \\
S_{xx}&:= \sum^n_{i=1}(x_{i}-\overline x)^2= \sum^n_{i=1}x_{i}^2-n\overline x^2 \\
S_{yy}&:= \sum^n_{i=1}(y_{i}-\overline y)^2=\sum^n_{i=1}y_{i}^2-n\overline y^2
\end{align}$$
Da queste espressioni si ricava
$$\hat{\beta} \frac{S_{xy}}{S_{xx}}\qquad \hat{\alpha}=\overline y-B\overline x\qquad ss_{R}= \frac{S_{xx}S_{yy}-S^2_{xy}}{S_{xx}}$$

> [!example]
> Relazione fra $x$, la percentuale d'acqua durante la lavorazione di un certo materiale, con $Y$, la densità del prodotto finito.
>
> | $x_{i}$ | 5   | 6   | 7    | 10   | 12   | 15   | 18   | 20   |
> | ------- | --- | --- | ---- | ---- | ---- | ---- | ---- | ---- |
> | $y_{i}$ | 7.4 | 9.3 | 10.6 | 15.4 | 18.1 | 22.2 | 24.1 | 24.8 |
> 

## Modello Lineare vs Modello Quadratico
![[Pasted image 20250710034906.png|center|600]]

## Inferenza sui Parametri di Regressione
![[Pasted image 20250710035000.png|center|400]]

Note le distribuzioni degli stimatori dei parametri $\alpha,\beta,\sigma^2$ si può procedere alla verifica di ipotesi sul loro valore. Ci si concentra su $\beta$ che da conto dell'esistenza e del segno dell'associazione fra $X$ e $Y$
- Poiché $\frac{B-\beta}{\frac{\sigma}{\sqrt{ S_{XX} }}}\sim N(0,1)$
- Inoltre: $\frac{SS_{R}}{\sigma^2}\sim \chi^2_{n-2}$
- Quindi: $$\frac{\frac{B-\beta}{\frac{\sigma}{\sqrt{  S_{xx} }}}}{\sqrt{ \frac{SS_{R}}{\sigma^2}(n-2) }}=\frac{B-\beta}{\sqrt{ (n-2) }S_{xx}}\sim t_{n-2}$$
### Test d'ipotesi  
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
## Regressione della Media: Altezze padri vs Altezza figli
![[Pasted image 20250710154656.png|center|550]]

Si ha evidenza che c'è una relazione lineare fra le altezze, ci si chiede quindi se si ha un effetto di regression, ovvero $H_{0}:\beta=1\ vs\ H_{1}:\beta<1$.
Si può calcolare l'intervallo di confidenza per $\beta$ al $95\%$
- $S_{xx}=171.6$, $S_{xy}=79.72$, $S_{yy}=38.529$ 
$$0.4646\pm 2.26 \sqrt{ \frac{1.4935}{8*1.71.6} }=\{0.3901,0.5390\}$$
Si verifica che $1$ non ricade nell'intervallo. Alternativamente si può valutare la statistica $$\frac{\hat{\beta}-\beta_{H_{0}}}{\sqrt{ \frac{SS_{R}}{(n-2)S_{xx}} }}= \frac{0.46-1}{0.3901}=-16.39$$
## Inferenza su $\alpha$, $\sigma^2$ non noto
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
## Inferenza sulla Risposta in Media
Per ogni possibile per ogni valore del predittore $x_{0}$, cosa ci si può aspettare $E(Y|x_{0})?$
In termini di stima puntuale sarà
$$E[A+Bx_{0}]=E[A]+x_{0}E[B]=\alpha+\beta x_{0}$$
Se si vuole una stima intervallare si deve studiare la distribuzione di $A+Bx_{0}$, vedendo come si combinano fra loro gli stimatori $A$ e $B$.
Se si vuole la predizione in media per un certo valore di $x$, si dice $x_{0}$
$$E(Y_{x_{0}})=E(A+Bx_{0})=E(A)+E(B)x_{0}=\alpha+\beta x_{0}$$
Poiché $B=\sum^n_{i=1} \frac{(x_{i}-\overline x)Y_{i}}{S_{xx}}$ e $A=\overline Y-B\overline x$
$$A+Bx_{0}=\overline Y-B(\overline x-x_{0})=\sum^n_{i=1} \frac{1}{n}Y_{i}-\sum^n_{i=1} \frac{(x_{i}-\overline x)(\overline x-x_{0})}{S_{xx}}Y_{i}=\sum^n_{i=1}\left[ \frac{1}{n}- \frac{(x_{i}-\overline x)(\overline x-x_{0})}{S_{\times}} \right]Y_{i}$$
Ovvero una combinazione lineare di normali indipendenti di media $\alpha+\beta x_{0}$
## Varianza della Risposta in Media
$$\begin{align}
Var[A+Bx_{0}]&= \sum^n_{i=1}\left[ \frac{1}{n} - \frac{(x_{i}-\overline x)(\overline x-x_{0})}{S_{xx}} \right]^2 Var[Y_{i}] \\
&= \sigma^2 \sum^n_{i=1}\left[  \frac{1}{n^2}- \frac{2(x_{i}-\overline x)(\overline x-x_{0})}{nS_{xx}}+ \frac{(x_{i}-\overline x)^2(\overline x-x_{0})^2}{S^2_{xx}} \right] \\
&=\sigma^2 \left[ \frac{1}{n}- \frac{2(\overline x-x_{0})}{nS_{xx}} \sum^n_{i=1}(x_{i}-\overline x)+ \frac{(\overline x-x_{0})^2}{S^2_{xx}} \sum^n_{i=1}(x_{i}-\overline x)^2 \right] \\
&=\sigma^2\left[  \frac{1}{n}-0+ \frac{(\overline x-x_{0})^2}{S^2_{xx}}S_{\times} \right] \\
&=\sigma^2\left[ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{\times}} \right]
\end{align}$$
Ovvero tanto più ci si allontana dal centro delle osservazioni di $X$, tanto più cresce l'incertezza sulla risposta media.
## Inferenza sulla Risposta in Media,  $\sigma^2$ non noto
Pur disponendo di $$A+Bx_{0}\sim N\left( \alpha+\beta x_{0}\quad \sigma^2\left[ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} \right] \right)$$
Si deve come al solito eliminare $\sigma^2$ usando $$\frac{SS_{R}}{\sigma^2}\sim \chi^2_{n-2}$$
$$\frac{A+Bx_{0}-(\alpha+\beta x_{0})}{\sqrt{  \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} }\sqrt{  \frac{SS_{R}}{n-2} }}\sim t_{n-2}$$
Da qui si possono valutare gli intervalli di confidenza utilizzando i dati campionari
$$
\hat{\alpha}+\hat{\beta}_{x_{0}}\pm t_{\frac{\gamma}{2},n-2}\cdot \sqrt{ \frac{1}{n}+ \frac{(\overline x-x_{0})^2}{S_{xx}} }
$$
![[Pasted image 20250710161930.png|center|400]]

## Inferenza sulla Predizione della Risposta
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

## Coefficiente di Determinazione e di Correlazione
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