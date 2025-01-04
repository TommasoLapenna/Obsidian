Tags: [[Analisi 2 e Probabilità]] [[University]]

Una variabile aleatoria è una funzione a valori reali definita nello spazio campionario
### Esempio
Lancio di 3 monete equilibrate
$Y=$ il numero di teste che si ottengono
$Y=0,1,2,3$ $$\begin{align}
&P\{Y=0\}=P(\{C,C,C\})=\frac{1}{8} \\
&P\{Y=1\}=P(\{C,C,T\},\{C,T,C\},\{T,C,C\})=\frac{3}{8} \\
&P\{Y=2\}=P(\{C,T,T\},\{T,T,C\},\{T,CT\})=\frac{3}{8} \\
&P\{Y=3\}=P(\{T,T,T\})=\frac{1}{8}
\end{align}$$Dato che $Y$ deve assumere almeno uno dei valori $0,1,2,3$ $$1=P(\cup_{i=0}^3\{Y=i\})=\sum_{i=0}^3P\{Y=i\}$$
### Definizione
Data una v.a., si definisce $$F(X)=P\{X\le x\}$$*Funzione di Ripartizione o Distribuzione*
Rappresenta la probabilità che, per ogni $x$, la v.a. sia minore o uguale a $x$
- $a\le b\Longrightarrow\{X\le a\}$ è contenuto in $\{X\le b\}$, $F(a)=P\{X\le a\}\le F(b)=P\{X\le b\}$, $F$ è non decrescente
### Definizione
Una v.a. si dice *Discreta* se può assumere un'infinità al più numerabile di valori
$X$ v.a. discreta, si definisce *Densità Discreta* $$P(a)=P\{X=a\}$$se $a$ assume i valori $x_1,x_2,\ldots,x_n$
- $P(\underset{X=X_i}{X_i})\ge0\quad i=1,\ldots,n$, $P(X)=0$ altrimenti
- $\sum_{i=1}^\infty P(X_i)=1$
### Esempio
![[Pasted image 20250104171951.png]]
### Esempio
La densità discreta di una v.a. $X$ $$p(i)=P\{X=i\}=c \frac{\lambda^i}{i!},\ c>0,\ i=0,1,2,\ \lambda>0 \ costante$$Calcolare:
1) $P\{x=0\}$
	Si determina $c>0$ $$\begin{align}
&\sum^\infty_{i=0}p(i)=1\iff\sum_{i=0}^\infty c \frac{\lambda^i}{i!}=1 \\
&\sum^\infty_{i=0} \frac{\lambda^i}{i!}=e^\lambda\qquad c\sum^\infty_{i=0} \frac{\lambda^i}{i!}=1 \\
&\qquad\qquad\qquad\quad \ ce^\lambda=1,\ c=e^{-\lambda} \\
&P\{X=0\}=e^{-\lambda} \frac{\lambda^0}{0!}=e^{-\lambda} \\
&P\{X>2\}=
\end{align}$$