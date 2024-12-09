Tags: [[Analisi 2 e Probabilità]] [[University]] 

1) Comporre le funzioni con
	$\left\{\begin{matrix} x=x_0+\rho\cos\theta \\ y=y_0+\rho\sin\theta \end{matrix}\right.$
2) Valutare il limite $f(\rho,\theta)$ per $\rho\to0$. tenendo fisso $\theta$ (ovvero si valuta il limite della funzione lungo una retta passante per il punto $(x_0,y_0)$)
	- Se il valore del limite dipende da $\theta$ si conclude che il limite non esiste
	- Se il limite è indipendente $\theta$
		$S(\rho)=\underset{\theta\in[0,2\pi]}{\sup}|f(x_0+\rho\cos\theta,y_0+\rho\sin\theta)-L|$
		$\lim_{\rho\to0}S(\rho)=0\Rightarrow\lim_{(x,y)\to(x_0,y_0)}f(x,y)=L$
		