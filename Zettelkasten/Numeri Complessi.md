---
sticker: emoji//0030-fe0f-20e3
---
Tags: [[Fondamenti di Segnali e Trasmissione]] [[University]]

- $j= \sqrt{ -1 }$ = Soluzione di $x^2+1=0$
- Coppia ordinata di numeri reali (con alcune proprietà particolari)
$$
\begin{matrix}
(x,y) &\longrightarrow&\text{Numero Complesso}&\Longrightarrow &z= x+jy \\ 
x=\text{Parte reale}& & & & x=\mathcal{Re}\{z\}\in \mathbb{R} \\
y=\text{Parte immaginaria}& & & & y=\mathcal{Im}\{z\}\in \mathbb{R}
\end{matrix}
$$
![[Pasted image 20250320112828.png]]
- **Coniugato:** Si definisce coniugato di $A=a_{R}+ja_{I}$ il numero $A^*=a_{R}-a_{I}$

$$\begin{align}
&|A|=\sqrt{ a_{R}^2+a_{I}^2 } & & |A^*|=\sqrt{ a_{R}^2+(-a_{I})^2 }=\sqrt{ a^2_{R}+a_{I}^2 } \\
&\angle A= \tan^{-1}\left( \frac{a_{I}}{a_{R}} \right)& &\angle A^*=\tan^{-1}\left( -\frac{a_{I}}{a_{R}} \right) = -\tan^{-1}\left( \frac{a_{I}}{a_{R}} \right)&
\end{align}\Longrightarrow \begin{matrix}
|A^*|=|A| \\
\angle A^*=-\angle A
\end{matrix}$$
![[Pasted image 20250320120026.png]]
### Rappresentazione Polare
Si rappresenta il vettore con modulo e fase: il numero complesso viene identificato da un angolo (*Fase*) e dalla distanza (*Modulo*) da un punto fisso detto polo (*Origine*)
![[Pasted image 20250320120321.png]]
Si ha che 
$$
x= r\cos \phi,\ y=r\sin \phi \Longrightarrow z=r(\cos \phi+j\sin \phi)
$$
### Formula di Eulero
$$
e^{j\theta}=\cos \theta+j\sin \theta \Longrightarrow \begin{cases}
\cos \theta= \frac{e^{j\theta}+e^{-j\theta}}{2} \\
\sin \theta= \frac{e^{j\theta-e^{-j\theta}}}{2j} 
\end{cases}
$$
![[Pasted image 20250320120932.png]]
Da Eulero quindi 
$$
z=r\cos \phi+jr\sin \phi=r(\cos \phi+j\sin \phi)=re^{j\phi}
$$
Se $r=1\Longrightarrow z=e^{j\phi}$, in questo caso $z$ è un punto nel piano complesso appartenente ad un cerchio di raggio unitario, individuato dal valore della fase